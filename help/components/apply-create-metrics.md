---
description: There are two ways to use metrics in Analysis Workspace.
title: Metrics
feature: Metrics
exl-id: 4edfb5d7-da20-4bd8-8041-387b291daf96
---
# Metrics

Metrics allow you to quantify data points in Analysis Workspace. They are most commonly used as columns in a visualization and tied to dimensions.


## Types of metrics

Adobe offers several types of metrics for use in Analysis Workspace:

* **Standard metrics**: Example of standard metrics are People, Sessions, Events.

* **Calculated metrics** ![Calculated metric icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg): User-defined metrics that are based on standard metrics, static numbers, or algorithmic functions.

* **Calculated metric templates**  <img src="./assets/adobe-logo.svg" width="18"> : Adobe-defined metrics that behave similarly to calculated metrics. You can use them as-is in Workspace projects, or save a copy to customize its logic.


![Metrics in the UI](assets/cja-metrics.png)

You can see whether a metric is approved ![Approved icon](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  or not. If you want more details on a metric, hover over the metric, and select ![Info icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg).


Metrics are flexible in their use within Analysis Workspace. Drag a metric to an empty Freeform table to see that metric trended over the project's date period. You can also drag a metric when a dimension is present to see that metric compared to each dimension item. Dragging a metric on top of an existing metric header replaces it, and dragging a metric next to a header lets you see both metrics side-by-side.

## Calculated metrics

Calculated metrics allow you to easily see how metrics relate to each other using simple operators or statistical functions. There are several ways to create calculated metrics:

You can select **[!UICONTROL Components]** > **[!UICONTROL Calculated metrics]**. This takes you to the [Calculated metric builder](/help/components/calc-metrics/calc-metr-overview.md), where you can build custom metrics from existing metrics.

To make it easier to quickly create calculated metrics, **[!UICONTROL Create metric from selection]** has been added to the column right-click menu in Freeform Tables. This option displays when one or more header column cells are selected.

![Create from selection](assets/create-metric-from-selection.png)

[Calculated Metrics: Implementation-less metrics](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/calculated-metrics/calculated-metrics-implementationless-metrics.html) (3:42)

## Compare metrics with different attribution models

If you'd like to quickly and easily compare one attribution model to another, right-click a metric and select **[!UICONTROL Compare Attribution Models]**:

![Compare attribution](assets/compare-attribution.png)

This shortcut lets you quickly and easily compare one attribution model to another without dragging in a metric and configuring it twice.
