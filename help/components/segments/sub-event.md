---
title: Sub-Event Analysis
description: Learn how sub-event analysis lets you filter individual products or other containers within an event in Csutomer Journey Analytics, eliminating attribution bleed in product reports.
feature: Segmentation
hide: true
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
subfeature_v2:
  - id: a544b409-2610-410d-a842-474ac1d0d54e
    internal-label: Segment Builder
---
# Sub-event analysis

{{release-limited-testing}}

Sub-event analysis lets you analyze event data at a level more granular than the event level. Instead of filtering on entire events, you can segment on individual containers within events. For example:

* Segmenting on a specific product category without including all other products purchased in the same order.
* Segmenting on a specific assets category within content analytics data.
* Segmenting on a specific media channel within media analytics data.

In Customer Journey Analytics, you define containers within a data view for which you want to use sub-event analysis. Without sub-event analysis, segmenting on a container item attribute returns all events, sessions, people, (global) accounts [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, buying groups [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, opportunities [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, or other [containers](/help/data-views/create-dataview.md#containers-1) you have defined. The result is incorrect attribution and inflated revenue metrics. Sub-event analysis scopes the filter to individual container rows within an event and solves these issues.

In sub-event analysis, exclude logic behaves differently from standard event-level exclusion against the container. When you exclude item attributes within the container, the segment returns events that **have items** within the container but don't match your exclusion criteria. The segment does not return events with no items at all. 


## Example

You want to measure revenue from the professional suits category only. Without sub-event analysis, applying a segment for professional suits includes revenue from every product on any order (event) that contains at least one product with the professional suits category. With sub-event analysis, you scope the filter to the product level and return only revenue for products of the professional suits category.

You also want to measure online revenue from all other categories except the professional suits category.

>[!BEGINTABS]

>[!TAB Event analysis]

In the segmentation builder or as part of a **[!UICONTROL Quick segment]**, you specify to **[!UICONTROL Include]** the **[!UICONTROL Dimension]** **[!UICONTROL product_category]** **[!UICONTROL equals]** **[!UICONTROL Professional Suits]** on the **[!UICONTROL Events]** container. 

![Panel showing segementation on event level for product category professional suits](./assets/product-category-segmentation-events.png)

As a result, all orders containing at least one **[!UICONTROL Professional Suits]** **[!UICONTROL product_category]** are considered, and revenue from other products in those orders is included in the **[!UICONTROL Revenue]** metric.
When you report on categories, all other values for **[!UICONTROL product_category]** are reported that were part of an order that included a product with the **[!UICONTROL Professional Suits]** **[!UICONTROL product_category]**.

>[!TAB Sub-event analysis]

You have defined a **[!UICONTROL Product Details]** [custom container](/help/data-views/create-dataview.md#containers) in your data view for the purpose of sub-event analysis on products.

![Product Details container](assets/product-details-container.png)

In the segmentation builder or as part of a **[!UICONTROL Quick segment]**, you specify to **[!UICONTROL Include]** the **[!UICONTROL Dimension]** **[!UICONTROL product_category]** **[!UICONTROL equals]** **[!UICONTROL Professional Suits]** on the **[!UICONTROL Product Details]** container. 

![Panel showing segementation on sub-event level for product category professional suits](./assets/product-category-segmentation-subevents.png)

As a result, all orders containing at least a **[!UICONTROL Professional Suits]** **[!UICONTROL product_category]** are considered, and only the revenue of products belonging to the **[!UICONTROL Professional Suits]** **[!UICONTROL product_categorey]** are included for the **[!UICONTROL Revenue]** metric.
When you report on categories, only the **[!UICONTROL Professional Suits]** **[!UICONTROL product_category]** is reported.

>[!TAB Sub-event analysis (exclude)]

You have defined a **[!UICONTROL Product Details]** [custom container](/help/data-views/create-dataview.md#containers) in your data view for the purpose of sub-event analysis on products.

![Product Details container](assets/product-details-container.png)

In the segmentation builder or as part of a **[!UICONTROL Quick segment]**, you specify to **[!UICONTROL Exclude]** the **[!UICONTROL Dimension]** **[!UICONTROL product_category]** **[!UICONTROL equals]** **[!UICONTROL Professional Suits]** on the **[!UICONTROL Product Details]** container. 

![Panel showing segementation on sub-hit level to exclude product category Men](./assets/product-category-segmentation-subevents-exclude.png)

To exclude at the product level, events that contain at least one product are included, then the exclusion on sub-event level is applied within that scope. This exclusion differs from event-level exclusion, which excludes the entire event.

>[!ENDTABS]
