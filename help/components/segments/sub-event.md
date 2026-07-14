---
title: Sub-Event Analysis
description: Learn how sub-event analysis lets you filter individual products or other containers within an event in Csutomer Journey Analytics, eliminating attribution bleed in product reports.
feature: Segmentation
hold: true
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
subfeature_v2:
  - id: a544b409-2610-410d-a842-474ac1d0d54e
    internal-label: Segment Builder
---
# Sub-event analysis

{{release-limited-testing}}

Sub-event analysis lets you analyze event data at a level more granular than the event level. Instead of filtering on entire event, you can segment on individual containers within events. For example:

- Segmenting on a specific product category without including all other products purchased in the same order
- Segmenting on a specific assets category within content analytics data?
- Segmenting on a spefific media channel within media analytics data.


In Customer Journey Analytics, you define containers within a data view for which you want to use sub-event analysis. Without sub-event analysis, segmenting on a container item attribute returns all events where any item within an event matches the container item attribute. The result is incorrect attribution and inflated revenue metrics. Sub-event analysis scopes the filter to individual item rows within a event and solves these issues.

In sub-event analysis exclude logic behaves differently from standard event-level exclusion against the container. When you exclude item attributes within the container, the segment returns events that **have items** within the container but don't match your exclusion criteria. The segment does not return event with no items at all. 


## Example

You want to measure revenue from the professional suites category only. Without sub-event analysis, applying a segment for professional suits includes revenue from every product on any order (event) that contains at least one product with the professional suits category. With sub-event analysis, you scope the filter to the product level and return only revenue for products of the professional suits category.

You also want to measure online revenue from all other categories except the Men category.

>[!BEGINTABS]

>[!TAB Event analysis]

In the segmentation builder or as part of a **[!UICONTROL Quick segment]**, you specify to **[!UICONTROL Include]** the **[!UICONTROL Dimension]** **[!UICONTROL product_category]** **[!UICONTROL equals]** **[!UICONTROL Professional Suits]** on the **[!UICONTROL Events]** container. 

![Panel showing segementation on event level for product category professional suits](./assets/product-category-segmentation-events.png)

As a result, all orders containing at least one **[!UICONTROL Professional Suits]** **[!UICONTROL product_category]** are considered, and revenue from other products in those orders is included in the **[!UICONTROL Revenue]** metric.
When you report on categories, all other values for **[!UICONTROL product_category]** are reported that were part of an order that included a product with the **[!UICONTROL Professional Suits]** **[!UICONTROL product_category]**.

>[!TAB Sub-event analysis]

In the segmentation builder or as part of a **[!UICONTROL Quick segment]**, you specify to **[!UICONTROL Include]** the **[!UICONTROL Dimension]** **[!UICONTROL product_category]** **[!UICONTROL equals]** **[!UICONTROL Professional Suites]** on the **[!UICONTROL Products]** container. 

![Panel showing segementation on sub-event level for product category professional suits](./assets/product-category-segmentation-subevents.png)

As a result, all orders containing at least a **[!UICONTROL Professional Suits]** **[!UICONTROL product_category]** are considered, and only the revenue of products belonging to the **[!UICONTROL Professional Suits]** **[!UICONTROL product_categorey]** are included for the **[!UICONTROL Revenue]** metric.
When you report on categories, only the **[!UICONTROL Professional Suits]** **[!UICONTROL Rproduct_category]** is reported.

>[!TAB Sub-event analysis (exclude)]

In the segmentation builder or as part of a **[!UICONTROL Quick segment]**, you specify to **[!UICONTROL Exclude]** the **[!UICONTROL Dimension]** **[!UICONTROL product_category]** **[!UICONTROL equals]** **[!UICONTROL Professional Suits]** on the **[!UICONTROL Products]** container. 

![Panel showing segementation on sub-hit level to exclude product category Men](./assets/product-category-segmentation-subevents-exclude.png)

To exclude at the product level, events that contain at least one product are included, then the exclusion on sub-event level is applied within that scope. This exclusion differs from event-level exclusion, which excludes the entire event.

>[!ENDTABS]


<!-- AI generated content

title: Sub-Event Analysis in Customer Journey Analytics
description: Learn how to analyze data below the event level in Customer Journey Analytics using sub-event containers to segment individual items within event arrays.
feature: Filters, Segments
role: User, Admin
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
    internal-label: Segments, Segments (CJA)
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: e5aeaef3-57b4-4cce-b025-6dea43f9e14b
    internal-label: Admin
---

# Sub-event analysis

Sub-event analysis lets you segment and analyze data at a level below the individual event — for example, a specific product within a product list, or a single item within an array field. Without this capability, all data in arrays is automatically lifted to the event level, which causes attribution bleed, inflated counts, and inaccurate metrics.

**Example:** A customer purchases three items in a single order. Without sub-event analysis, a segment for *red shoes* would match the entire event, pulling in all three products. With sub-event analysis, the segment evaluates each item in the product list individually, returning only the red shoes row.

Sub-event analysis is built on *sub-event containers* — containers that an administrator configures in the data view. Once configured, these containers are available for use in the Segment builder and in certain visualizations.

## Configure sub-event containers (administrators)

Administrators configure sub-event containers from the **[!UICONTROL Containers]** tab in the data view builder. This tab appears before the **[!UICONTROL Components]** tab.

### System containers and custom containers

The **[!UICONTROL Containers]** tab has two sections:

| Section | Description |
|---|---|
| **[!UICONTROL System]** | The standard Person, Session, and Event containers. Administrators can rename a system container's display name but cannot otherwise modify it. |
| **[!UICONTROL Custom]** | Schema-based or component-based containers that you create from your data view's schema fields. These represent the sub-event level of your data — for example, `productListItems` in an e-commerce schema. |

The **[!UICONTROL Container type]** column shows whether each custom container is **[!UICONTROL Schema-based]** or **[!UICONTROL Component-based]**. Component-based containers only appear after you add the corresponding dimension or metric to the data view.

### Curate a container

Custom containers must be curated before they are available in the Segment builder. Curating a container is an explicit opt-in: only curated containers are valid for use in segments.

To curate a custom container, select the container in the **[!UICONTROL Custom]** table and enable it for segmentation.

>[!NOTE]
>
>A maximum of 100 custom containers can be curated per data view, across all Customer Journey Analytics SKUs. This limit may change in the future. Any auto-generated occurrence metrics from curated containers count toward the 5,000 component limit per data view.

### Container display names

The container's internal name is immutable after creation. Only the display name is editable. You can also add context labels and hide a container from reporting without removing it.

## Use sub-event containers in segments

Once an administrator has curated at least one sub-event container, it is available in the Segment builder as a new container option alongside Person, Session, and Event.

### Container auto-inference

When you drag a dimension that belongs to a sub-event container (for example, `productID`) into the Segment builder canvas, the builder automatically selects the most granular applicable sub-event container rather than defaulting to the Event container. This means the segment evaluates at the sub-event level without any additional configuration.

>[!NOTE]
>
>Container auto-inference applies when the dimension is exclusively part of one sub-event container. If a dimension appears in multiple containers, you must select the container manually.

### Mixed containers

When you add dimensions or metrics from different sub-event containers in a single segment rule, the builder uses the highest (least granular) container that covers all components. If all components share the same sub-event container, that shared container is used.

### Exclude logic

Exclusion at the sub-event level works differently from event-level exclusion. To exclude a specific sub-event condition, the system first includes events that contain a matching sub-event, then applies the exclusion within those events. This means the segment identifies *events that have the sub-event* and then removes the matching sub-event rows — rather than excluding all events where the sub-event does not exist.

This behavior is intentional but counterintuitive. Use explicit **[!UICONTROL Include]** and **[!UICONTROL Exclude]** containers when building sub-event exclusion logic to make the intent clear.

### Filter by container in the left rail

The Segment builder left rail includes a new option to filter the component list by container. Selecting a container shows only the dimensions and metrics that belong to that container, making it easier to build focused sub-event segment conditions.

This container filter is available in the Segment builder only. It is not currently available in other left rail panels.

## Auto-generated occurrence metrics

When an administrator curates a sub-event container, an **Occurrences** metric is automatically generated for that container. This metric counts the number of sub-event rows that match the container and appears in the left rail as a selectable metric when building segments.

These auto-generated metrics behave like the standard Person, Session, and Event count metrics:

- They cannot be duplicated or structurally modified.
- You can rename them, add context labels, and hide them from reporting.
- If you rename the curated container, the auto-generated metric name updates automatically — unless you have already manually renamed the metric.

## Histogram visualization

The Histogram is the only visualization that requires you to select a sub-event container explicitly. A container drop-down menu appears in the Histogram panel when sub-event containers are available in the data view, allowing you to scope the distribution to a specific container level.

No other panels or visualizations require changes to support sub-event containers.

-->
