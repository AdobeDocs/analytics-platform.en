---
title: Understand Sub-Events and Object Arrays in Data Feeds
description: Learn how Customer Journey Analytics data feeds export sub-events from schema arrays, preserving hierarchy instead of flattening them as Workspace does.
hide: true
feature: Components
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
---
# Sub-events in data feeds

{{release-limited-testing}}

[Sub-events](/help/components/segments/sub-event.md) in Customer Journey Analytics allow you to analyze event data at a level more granular than the event level.

Use the following information to understand how to work with sub-events in your Customer Journey Analytics data feeds.

## Understand sub-events

### Sub-events in the XDM schema

In the XDM schema, each element of an array (a string array or an object array) is a sub-event.

To view an event with sub-events within the XDM schema in Adobe Exprience Platform, select [!UICONTROL **Schemas**], then expand an event that contains sub-events.

In the following example, `Product list items` is an object array containing various sub-events.

![XDM schema containing an object array and sub-events](assets/df-sub-event-schema.png)

### Sub-event example: Products in a purchase event

A customer purchases two products in a single order: one cordless drill and two drill battery packs. Your implementation sends a single purchase event that includes both products in the `productListItems` object array:

```json
{
  "eventType": "commerce.purchases",
  "timestamp": "2026-09-16T14:32:07.512Z",
  "commerce": {
    "purchases": { "value": 1 }
  },
  "productListItems": [
    { "SKU": "CD-2000", "name": "Cordless Drill", "quantity": 1, "priceTotal": 129.99 },
    { "SKU": "BP-2000", "name": "Drill Battery Pack", "quantity": 2, "priceTotal": 39.98 }
  ]
}
```

This event contains two sub-events, one for each object in the `productListItems` array. The following table shows which fields belong to the event and which belong to its sub-events.

| Level | Fields | What the fields describe |
| --- | --- | --- |
| **Event** | `eventType`, `timestamp`, `commerce.purchases.value` | The purchase as a whole. Each field has one value for the event. The **Orders** metric counts `1` for this event, regardless of how many products it contains. |
| **Sub-event** | `SKU`, `name`, `quantity`, `priceTotal` in each `productListItems` object | An individual product in the purchase. Each field has one value per product. For example, `quantity` is `1` for the cordless drill and `2` for the drill battery pack. |

{style="table-layout:auto"}

>[!NOTE]
>
>Sub-events include only the data that is sent with the event. Customer Journey Analytics does not reconstruct cart contents from earlier events, such as cart adds or checkouts. For products to appear as sub-events of a purchase event, your implementation must include them in `productListItems` on that purchase event.

## Add sub-event data to a data feed

When you attempt to add a column that is a sub-event while building a data feed, a dialog displays, prompting you to add any of the peer sub-events. In the data feed output, all of these events appear in a single column. 

## View sub-event data in data feed output

### Sub-event differences between Analysis Workspace and data feeds

Sub-events are represented differently between Analysis Workspace and data feeds in Customer Journey Analytics.

| Location | How sub-events are represented |
| --- | --- |
| **Analysis Workspace (in Customer Journey Analytics)** | Selectable as individual components, separate from any visible hierarchy. |
| **Data feeds (in Customer Journey Analytics)** | Represented as a group, with their hierarchy intact. |

### Sub-event differences between Adobe Analytics and Customer Journey Analytics

Sub-event data (such as multiple product details in a single purchase event) appears differently in Customer Journey Analytics data feeds than in Adobe Analytics data feeds. The following table compares how each product represents sub-event data.

| Product | How sub-event data appears in data feeds | Example: Product list |
| --- | --- | --- |
| **Adobe Analytics** | Flattened into a delimited string in a single column. | A product list contains multiple products grouped in a single string:<p>`Power Tools;Cordless Drill;1;129.99,Power Tools;Drill Battery Pack;2;39.98` <!--screenshot of what this looks like: product lists, list vars. --></p> |
| **Customer Journey Analytics** | Sub-events retain the hierarchy defined in your XDM schema. While grouped in the same column, they show their relational hierarchy to their parent event and sibling sub-events. | A product list maintains its hierarchy that is defined in the XDM schema as an array:<p>`[{"category":"Power Tools","product":"Cordless Drill","quantity":1,"revenue":129.99},{"category":"Power Tools","product":"Drill Battery Pack","quantity":2,"revenue":39.98}]` <!--screenshot of what this looks like: product lists, list vars. --></p> |

{style="table-layout:auto"}

### Differences from Adobe Analytics

### How output differs between Adobe Analytics and Customer Journey Analytics data feeds

Sub-event data (such as multiple product details in a single purchase event) appears differently in Customer Journey Analytics data feeds than in Adobe Analytics data feeds. The following table compares how each product represents sub-event data.

| Product | How sub-event data appears in data feeds | Example: Product list |
| --- | --- | --- |
| **Adobe Analytics** | Flattened into a delimited string in a single column. | A product list contains multiple products grouped in a single string:<p>`Power Tools;Cordless Drill;1;129.99,Power Tools;Drill Battery Pack;2;39.98` <!--screenshot of what this looks like: product lists, list vars. --></p> |
| **Customer Journey Analytics** | Sub-events retain the hierarchy defined in your XDM schema. While grouped in the same column, they show their relational hierarchy to their parent event and sibling sub-events. | A product list maintains its hierarchy that is defined in the XDM schema as an array:<p>`[{"category":"Power Tools","product":"Cordless Drill","quantity":1,"revenue":129.99},{"category":"Power Tools","product":"Drill Battery Pack","quantity":2,"revenue":39.98}]` <!--screenshot of what this looks like: product lists, list vars. --></p> |

{style="table-layout:auto"}

## How sub-events differ between Analysis Workspace and data feeds output

Sub-events are represented differently between Analysis Workspace and data feeds in Customer Journey Analytics.

| Location | How sub-events are represented |
| --- | --- |
| **Analysis Workspace** | Selectable as individual components, separate from any visible hierarchy. |
| **Data feeds** | Represented as a group, with their hierarchy intact. |


## View sub-event data in data feed output

Sub-event data (such as multiple product details in a single purchase event) appears differently in Customer Journey Analytics data feeds than in Adobe Analytics data feeds. The following table compares how each product represents sub-event data.

| Product | How sub-event data appears in data feeds | Example: Product list |
| --- | --- | --- |
| **Adobe Analytics** | Flattened into a delimited string in a single column. | A product list contains multiple products grouped in a single string:<p>`Power Tools;Cordless Drill;1;129.99,Power Tools;Drill Battery Pack;2;39.98` <!--screenshot of what this looks like: product lists, list vars. --></p> |
| **Customer Journey Analytics** | Sub-events retain the hierarchy defined in your XDM schema. While grouped in the same column, they show their relational hierarchy to their parent event and sibling sub-events. | A product list maintains its hierarchy that is defined in the XDM schema as an array:<p>`[{"category":"Power Tools","product":"Cordless Drill","quantity":1,"revenue":129.99},{"category":"Power Tools","product":"Drill Battery Pack","quantity":2,"revenue":39.98}]` <!--screenshot of what this looks like: product lists, list vars. --></p> |

{style="table-layout:auto"}

## Query sub-event data in data feed output

Because sub-event data [appears differently in Customer Journey Analytics data feeds](#view-sub-event-data-in-data-feed-output), the queries you use for it differ from those you use for Adobe Analytics data feeds.

The following examples show how to find events that include a specific product. The examples use Google BigQuery syntax. Other data warehouses, such as Snowflake and Databricks, support the same approach with minor syntax differences.

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






