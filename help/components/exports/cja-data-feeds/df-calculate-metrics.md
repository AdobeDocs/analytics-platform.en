---
description: Learn how to compare data feeds functionality in Customer Journey Analytics and Adobe Analytics
keywords: clickstream;data feed;datafeed;Data Feed
title: Compare Data Feeds Functionality in Customer Journey Analytics and Adobe Analytics
feature: Components
hide: true
---

# Query Nested Sub-Event Structures: UNNEST + EXISTS Pattern

For Ron — pulled directly from the PRD ([Feature: CJA Data Feeds Core](../prd/features/data-feeds-core.md#querying-nested-sub-event-structures-sql-guidance)). Same technique you demoed live on the THD and NRG alpha calls on Sept 16; this write-up generalizes it and adds a worked example against a realistic AA product string, as a starting point for a customer-facing doc with Luke.

---

## The core technique: `UNNEST` + `EXISTS` to filter without exploding

Use `UNNEST` inside an `EXISTS` subquery to filter parent rows on a condition buried in a nested/repeated field, without changing the row count or shape of the outer query:

```sql
SELECT
  order_id,
  order_date,
  shipments
FROM
  `project.dataset.orders` AS o
WHERE EXISTS (
  SELECT 1
  FROM UNNEST(o.shipments) AS s,
       UNNEST(s.line_items) AS item
  WHERE item.sku IN ('SKU-1001', 'SKU-1002', 'SKU-1003')
);
```

This returns exactly **one row per matching order**, with the full, unflattened `shipments` array intact in the output — regardless of how many individual line items inside the array actually match. `EXISTS` performs a semi-join: it only asks "does at least one match exist inside this row's nested data?" and stops there. The pattern is portable across major warehouses (BigQuery, Snowflake, Databricks) with only minor syntax variations.

## Contrast: when you actually want one row per matching item

If the goal is different — enumerating every matching line item rather than just filtering orders — moving the `UNNEST`s into the outer `FROM` clause instead produces row multiplication:

```sql
SELECT
  o.order_id,
  o.order_date,
  item.sku
FROM
  `project.dataset.orders` AS o,
  UNNEST(o.shipments) AS s,
  UNNEST(s.line_items) AS item
WHERE item.sku IN ('SKU-1001', 'SKU-1002', 'SKU-1003');
```

An order with 2 matching line items across its shipments will appear as 2 output rows here — one per match — because each `UNNEST` on a repeated field turns 1 row into N rows, and scalar parent columns (`order_id`, `order_date`) get carried along and duplicated onto each of those N rows. This is expected SQL behavior for querying repeated fields, not a bug — but customers should reach for it deliberately, only when they actually need item-level granularity, since **row counts can no longer be used to count events/orders once exploded** — use `COUNT(DISTINCT row_id)` instead (Row ID stays unique and stable per source row regardless of how the query explodes it).

## Concrete example: AA product string → CJA `product_list_items`

To ground the pattern in what THD/NRG are actually migrating from, here's the same idea applied to a real Adobe Analytics `products` string. Per Adobe's own `s.products` syntax (fields delimited by `;`, multiple products delimited by `,`, multi-value fields like events/eVars delimited by `|`) — see [Adobe Analytics: products variable](https://experienceleague.adobe.com/en/docs/analytics/implementation/vars/page-vars/products) — a hit with two products purchased together might look like this in the old flat AA `product_list` column:

```
"Power Tools;Cordless Drill;1;129.99;event1=1;eVar10=DrillBundle,Power Tools;Drill Battery Pack;2;39.98;event1=1;eVar10=DrillBundle"
```

To find hits that included a "Cordless Drill," an AA-era customer would regex-parse this string, e.g.:

```sql
-- Old AA-style approach: regex over the flat product_list string
SELECT hit_id, post_evar10
FROM aa_hit_data
WHERE REGEXP_CONTAINS(product_list, r'(^|,)[^;]*;Cordless Drill;')
```

In CJA Data Feeds, the same two products arrive as a `product_list_items` array of structs on the event row — no delimiter parsing required:

```json
{
  "row_id": "01K3F2M9-...-4821",
  "timestamp_utc": "2026-09-16T14:32:07.512000Z",
  "product_list_items": [
    { "category": "Power Tools", "product": "Cordless Drill",       "quantity": 1, "revenue": 129.99,
      "events": {"event1": 1}, "merchandising": {"eVar10": "DrillBundle"} },
    { "category": "Power Tools", "product": "Drill Battery Pack",   "quantity": 2, "revenue": 39.98,
      "events": {"event1": 1}, "merchandising": {"eVar10": "DrillBundle"} }
  ]
}
```

Finding the same "hits that included a Cordless Drill" using the `EXISTS` + `UNNEST` pattern — no regex, no exploding:

```sql
SELECT row_id, timestamp_utc, product_list_items
FROM `project.dataset.cja_data_feed` AS f
WHERE EXISTS (
  SELECT 1
  FROM UNNEST(f.product_list_items) AS item
  WHERE item.product = 'Cordless Drill'
);
```

And the item-level equivalent of the old regex-and-parse workflow — one output row per matching product, if that granularity is actually needed:

```sql
SELECT f.row_id, f.timestamp_utc, item.product, item.quantity, item.revenue
FROM `project.dataset.cja_data_feed` AS f,
     UNNEST(f.product_list_items) AS item
WHERE item.product = 'Cordless Drill';
```

Same tradeoff as the generic orders/shipments example above: the first form filters hits/events (one row each); the second enumerates matching products (one row per match, `row_id` duplicated across matches for that event).

## Why this matters for Data Feeds specifically

- This isn't limited to commerce/product use cases — any XDM array field produces the same nested structure and the same choice.
- Fully exploding is sometimes still the right call (e.g., building a downstream table that mirrors an existing flat convention), but customers should make that tradeoff deliberately, understanding the row-count/cost implications — not by default, because they didn't know the `EXISTS` alternative exists.
- Reinforces the existing AA-differences guidance: "customers must UNNEST/EXPLODE the list column to work with sub-events one-row-per-item" is true only when item-level output is actually the goal — filtering-only use cases don't require exploding at all.

---

*Sources: [THD alpha feedback call, Sept 16](../Teams/2026-09-16%20THD%20-%20Adobe%20CJA%20Data%20Feeds%20Alpha%20Feedback%20Call%20-%20Teams%20CoPilot.md); [NRG alpha feedback call, Sept 16](../Teams/2026-09-16%20NRG%20-%20Adobe%20CJA%20Data%20Feeds%20Alpha%20Feedback%20Call%20-%20Teams%20CoPilot.md); [Adobe Analytics: products variable syntax](https://experienceleague.adobe.com/en/docs/analytics/implementation/vars/page-vars/products)*
