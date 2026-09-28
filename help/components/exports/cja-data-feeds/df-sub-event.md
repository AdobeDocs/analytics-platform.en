---
title: Understand Sub-Events and Object Arrays in Data Feeds
description: Learn how Customer Journey Analytics data feeds export sub-events from schema arrays, preserving hierarchy instead of flattening them as Workspace does.
hide: true
feature: Components
---
# Sub-events in data feeds

{{release-limited-testing}}

In the XDM schema, anything that is an array (string or object) is a sub-event. Sub-events in Customer Journey Analytics are represented in data feed exports with their hierarchy. 

In Adobe Analytics, sub-events are represented as a single column.

Use the following information to understand how to work with sub-events in your Customer Journey Analytics data feeds.

## Sub-events in the XDM schema, Workspace, and data feeds

You define sub-events in the XDM schema, either as string arrays or object arrays.

These sub-events are represented differently, depending on whether you view them in Analysis Workspace or data feeds.

| Location | How sub-events are represented |
| --- | --- |
| **Analysis Workspace** | Individual objects in an array of objects are selectable as individual components, separate from any visible hierarchy. |
| **Data feeds** | Objects in an array of objects are represented as a group, with their hierarchy intact. |

## Add sub-event data to a data feed

When you attempt to add a column that is a sub-event while building a data feed, a dialog displays that allows you to add all of the peer sub-events. All of these events will appear in a single column of the data feed output. 

## View sub-event data in data feed output

Sub-event data (such as multiple products in a single event) appears differently in Customer Journey Analytics data feeds than in Adobe Analytics data feeds. The following table compares how each product represents sub-event data.

| Product | How sub-event data appears in data feeds | Example: Product list |
| --- | --- | --- |
| **Adobe Analytics** | Flattened into a delimited string in a single column. | A product list contains multiple products grouped in a single string:<p>`;LG Washing Machine 2000;1;1600,;LG Dryer 2000;1;500` <!--screenshot of what this looks like: product lists, list vars. --></p> |
| **Customer Journey Analytics** | Sub-events keep the hierarchy defined in your XDM schema. They stay grouped in the same column, together with their parent event and sibling sub-events. | A product list maintains its hierarchy that is defined in the XDM schema as an array:<p>`[{"name":"LG Washing Machine 2000","units":1,"revenue":1600},{"name":"LG Dryer 2000","units":1,"revenue":500}]` <!--screenshot of what this looks like: product lists, list vars. --></p> |

{style="table-layout:auto"}

## Query sub-event data in data feed output

Because sub-event data [appears differently in Customer Journey Analytics data feeds](#customer-journey-analytics-vs-adobe-analytics), the queries you use for it differ from those you use for Adobe Analytics data feeds.

The following examples show how to find events that include a specific product. The examples use Google BigQuery syntax. Other data warehouses, such as Snowflake and Databricks, support the same approach with minor syntax differences.

+++ Query product data in Adobe Analytics data feeds

In Adobe Analytics data feeds, an event with two products purchased together appears as a single delimited string in the `product_list` column:

```text
Power Tools;Cordless Drill;1;129.99;event1=1;eVar10=DrillBundle,Power Tools;Drill Battery Pack;2;39.98;event1=1;eVar10=DrillBundle
```

To find events that include a Cordless Drill, you parse this string with a regular expression:

```sql
SELECT hitid_high, hitid_low, post_evar10
FROM aa_hit_data
WHERE REGEXP_CONTAINS(product_list, r'(^|,)[^;]*;Cordless Drill;')
```

+++

+++ Query product data in Customer Journey Analytics data feeds

In Customer Journey Analytics data feeds, the same two products appear as an array of objects in the `product_list_items` column. No delimiter parsing is required:

```json
{
  "row_id": "01K3F2M9-...-4821",
  "timestamp_utc": "2026-09-16T14:32:07.512000Z",
  "product_list_items": [
    { "category": "Power Tools", "product": "Cordless Drill", "quantity": 1, "revenue": 129.99,
      "events": {"event1": 1}, "merchandising": {"eVar10": "DrillBundle"} },
    { "category": "Power Tools", "product": "Drill Battery Pack", "quantity": 2, "revenue": 39.98,
      "events": {"event1": 1}, "merchandising": {"eVar10": "DrillBundle"} }
  ]
}
```

How you write the query depends on whether you want one row per event or one row per matching product.

**Return one row per event**

To filter events without changing the number of rows, use `UNNEST` inside an `EXISTS` subquery:

```sql
SELECT row_id, timestamp_utc, product_list_items
FROM `project.dataset.cja_data_feed` AS f
WHERE EXISTS (
  SELECT 1
  FROM UNNEST(f.product_list_items) AS item
  WHERE item.product = 'Cordless Drill'
);
```

This query returns one row for each matching event, with the complete `product_list_items` array intact, regardless of how many products in the array match.

**Return one row per matching product**

To return one row for each matching product, move `UNNEST` into the outer `FROM` clause:

```sql
SELECT f.row_id, f.timestamp_utc, item.product, item.quantity, item.revenue
FROM `project.dataset.cja_data_feed` AS f,
     UNNEST(f.product_list_items) AS item
WHERE item.product = 'Cordless Drill';
```

An event with more than one matching product appears as multiple rows, and the event's columns, such as `row_id`, repeat on each row. Use this approach only when you need product-level detail. To count events in the results, use `COUNT(DISTINCT row_id)` instead of counting rows.

This approach applies to any array field in your XDM schema, not only products.

+++






