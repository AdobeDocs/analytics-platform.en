---
title: Sub-Container Components from Arrays and Maps in Data Feeds
description: Learn how Customer Journey Analytics data feeds export sub-container components from array and map fields, and how to query them in your data warehouse.
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
# Sub-container components in data feeds

{{release-limited-testing}}

Sub-container components are dimensions and metrics based on fields inside an array or map in your XDM schema. They allow you to analyze data at a level more granular than the event level, such as the individual products in a purchase. For information about using this data in segments, see [Sub-events](/help/components/segments/sub-event.md).

Use the following information to understand how sub-container components from array and map fields appear in your Customer Journey Analytics data feeds.

## Understand sub-container components

### Sub-container components in the XDM schema

In the XDM schema, each element of an array (a string array or an object array) is a sub-container. Each entry in a map field is also a sub-container, as described in [Map fields in data feeds](#map-fields-in-data-feeds). Dimensions and metrics based on the fields within a sub-container are sub-container components.

To view sub-containers within the XDM schema in Adobe Experience Platform, select [!UICONTROL **Schemas**], then expand an event that contains sub-containers.

In the following example, `Product list items` is an object array containing various sub-container components.

![XDM schema containing an object array and sub-container components](assets/df-sub-event-schema.png)

### Sub-container differences between Analysis Workspace and data feeds

Sub-container components are represented differently between Analysis Workspace and data feeds in Customer Journey Analytics.

| Location | How sub-container components are represented |
| --- | --- |
| **Analysis Workspace (in Customer Journey Analytics)** | Selectable as individual components, separate from any visible hierarchy. |
| **Data feeds (in Customer Journey Analytics)** | Represented as a group, with their hierarchy intact. |

### Sub-container differences between Adobe Analytics and Customer Journey Analytics

Sub-container data (such as multiple product details in a single purchase event) appears differently in Customer Journey Analytics data feeds than in Adobe Analytics data feeds. The following table compares how each product represents sub-container data.

| Product | How sub-container data appears in data feeds | Example: Product list |
| --- | --- | --- |
| **Adobe Analytics** | Flattened into a delimited string in a single column. | A product list contains multiple products grouped in a single string:<p>`Power Tools;Cordless Drill;1;129.99,Power Tools;Drill Battery Pack;2;39.98` <!--screenshot of what this looks like: product lists, list vars. --></p> |
| **Customer Journey Analytics** | Sub-container components retain the hierarchy defined in your XDM schema. While grouped in the same column, they show their relational hierarchy to their parent event and sibling sub-containers. | A product list maintains its hierarchy that is defined in the XDM schema as an array:<p>`[{"category":"Power Tools","product":"Cordless Drill","quantity":1,"revenue":129.99},{"category":"Power Tools","product":"Drill Battery Pack","quantity":2,"revenue":39.98}]` <!--screenshot of what this looks like: product lists, list vars. --></p> |

{style="table-layout:auto"}

### Sub-container example: Products in a purchase event

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

This event contains two sub-containers, one for each object in the `productListItems` array. The following table shows which fields belong to the event and which belong to its sub-containers.

| Level | Fields | What the fields describe |
| --- | --- | --- |
| **Event** | `eventType`, `timestamp`, `commerce.purchases.value` | The purchase as a whole. Each field has one value for the event. The **Orders** metric counts `1` for this event, regardless of how many products it contains. |
| **Sub-container** | `SKU`, `name`, `quantity`, `priceTotal` in each `productListItems` object | An individual product in the purchase. Each field has one value per product. For example, `quantity` is `1` for the cordless drill and `2` for the drill battery pack. |

{style="table-layout:auto"}

>[!NOTE]
>
>Sub-containers include only the data that is sent with the event. Customer Journey Analytics does not reconstruct cart contents from earlier events, such as cart adds or checkouts. For products to appear as sub-containers of a purchase event, your implementation must include them in `productListItems` on that purchase event.

## Add sub-container components to a data feed

When you add a sub-container component to a data feed, a dialog prompts you to add the other components from the same sub-container. 

![Dialog prompting you to add related sub-container components](assets/data-feeds-add-subevent.png)

Fields from the same sub-container appear on the canvas as a collapsible nested group rather than a flat item. 

![Sub-container group](assets/data-feeds-subevent-added.png)

This group reflects the underlying data structure.

In the data feed output, all of these components appear as a nested array in a single column.

For information about how to add components, including sub-container components, to a data feed, see [Create a data feed](/help/components/exports/cja-data-feeds/create-feed.md).

## Query sub-container data in data feed output

Because sub-container data [appears differently in Customer Journey Analytics data feeds](#sub-container-differences-between-adobe-analytics-and-customer-journey-analytics), the queries you use for it differ from those you use for Adobe Analytics data feeds.

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

## Use map fields in data feeds

Map fields in your XDM schema store key-value pairs. Data feeds export each map as an array of objects, the same way as other [sub-container data](#query-sub-container-data-in-data-feed-output). Each object contains the map key and its value as separate fields.

Field names in the output come from the component IDs that you configure for the data feed, not fixed names such as `key` or `value`. The examples in this section use sample component IDs.

<!-- Confirm with Nate before publishing: how the outer array column is named in the output (for example, `survey_responses`). -->

### Simple maps

Simple maps are the map type that you can create in your own schema. Each key is a string, and each value is a string or an integer.

For example, a survey map stores each question as a key and the response as a value:

```json
{
  "_yourtenant": {
    "surveyResponses": {
      "How did you hear about us?": "Search engine",
      "How likely are you to recommend us?": 9
    }
  }
}
```

In the data feed output, `survey_question` and `survey_answer` are the component IDs for the key and the value:

```json
{
  "survey_responses": [
    { "survey_question": "How did you hear about us?", "survey_answer": "Search engine" },
    { "survey_question": "How likely are you to recommend us?", "survey_answer": 9 }
  ]
}
```

### Identity map

Each identity in the [`identityMap`](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/field-groups/profile/identitymap) field is exported as one object. The object contains the identity namespace (the key), along with the identifier, authenticated state, and primary flag. The namespace repeats for each identity in that namespace.

Only the identity map attributes that exist as dimensions in your data view and that you add to the data feed are exported.

```json
{
  "identity_map": [
    { "identity_namespace": "ECID", "identity_id": "83290187457380573620940587193016478103", "authenticated_state": "ambiguous", "is_primary": true },
    { "identity_namespace": "CRMID", "identity_id": "C-1048576", "authenticated_state": "authenticated", "is_primary": false }
  ]
}
```

### Nested maps

Some Adobe-defined fields, such as `segmentMembership`, are maps of maps. Data feeds flatten these into a single array, with the first-level key and second-level key as separate fields in each object. The first-level key repeats in each object it applies to, so no data or relationships are lost.

For example, `segment_namespace` and `segment_id` are the component IDs for the first-level key and the second-level key:

```json
{
  "segment_membership": [
    { "segment_namespace": "ups", "segment_id": "04a81716-43d6-4e7a-a49c-f1d8b3129ba9", "status": "realized" },
    { "segment_namespace": "ups", "segment_id": "53cba6b2-a23b-454a-8069-fc41308f1c0f", "status": "exited" }
  ]
}
```








