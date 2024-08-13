---
description: There are two ways to use metrics in Analysis Workspace.
title: Metrics
feature: Metrics
exl-id: 4edfb5d7-da20-4bd8-8041-387b291daf96
role: User
---
# Metrics

Metrics allow you to quantify data points in Analysis Workspace. They are most commonly used as columns in a visualization and tied to dimensions.

## Types of metrics

Adobe offers several types of metrics for use in Analysis Workspace:

* **Standard metrics**: Example of standard metrics are People, Sessions, Events.

* **Calculated metrics** ![Calculated metric icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg): User-defined metrics that are based on standard metrics, static numbers, or algorithmic functions.

* **Calculated metric templates**  <img src="./assets/adobe-logo.svg" width="18"> : Adobe-defined metrics that behave similarly to calculated metrics. You can use them as-is in Workspace projects, or save a copy to customize its logic.


![Workspace panel highlighting Metrics in the left-pane.](assets/cja-metrics.png)

You can see whether a metric is approved ![Approved icon](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  or not. If you want more details on a metric, hover over the metric, and select ![Info icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg).


Metrics are flexible in their use within Analysis Workspace. Drag a metric to an empty Freeform table to see that metric trended over the project's date period. You can also drag a metric when a dimension is present to see that metric compared to each dimension item. Dragging a metric on top of an existing metric header replaces it, and dragging a metric next to a header lets you see both metrics side-by-side.

## Use metrics in Analysis Workspace

Metrics can be used in various ways within Analysis Workspace. For information about how to add metrics and other types of components to Analysis Workspace, see [Use components in Analysis Workspace](/help/components/use-components-in-workspace.md).

## Create calculated metrics

Calculated metrics allow you to easily see how metrics relate to each other using simple operators or statistical functions. 

There are several ways to create calculated metrics. The method you choose determines whether the calculated metric is available from the component list across all projects, or only in the project where it was created.

### Create calculated metrics for all projects

You can use the calculated metric builder to create calculated metrics. When created in this way, calculated metrics are available in the component list and can then be used in projects throughout your organization. 

For information about how to access the calculated metrics builder, see [Build metrics](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).

### Create calculated metrics for a single project

You can create quick calculated metrics that are available only for the project where they were created.

To create a calculated metric for a single project:

1. In Analysis Workspace, open the project where you want to create the calculated metric.

1. In a freeform table, right-click one or more header column cells, then select **[!UICONTROL Create metric from selection]**

   ![Workspace panel highlighting Create from selection](assets/create-metric-from-selection.png)

1. To create a calculated metric for this project only, choose from the following options:

   * [!UICONTROL **Divide**]
   
   * [!UICONTROL **Subtract**]

   * [!UICONTROL **Add**]

   * [!UICONTROL **Multiply**]

   Or, to open the calculated metric builder and create the calculated metric for all projects, select [!UICONTROL **Open in Calculated Metric Builder**], then continue with [Build metrics](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).

[Calculated Metrics: Implementation-less metrics](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/calculated-metrics/calculated-metrics-implementationless-metrics.html) (3:42)

## Compare metrics with different attribution models

If you'd like to quickly and easily compare one attribution model to another, right-click a metric and select **[!UICONTROL Compare Attribution Models]**:

![Workspace panel highlighting Compare attribution models](assets/compare-attribution.png)

This shortcut lets you quickly and easily compare one attribution model to another without dragging in a metric and configuring it twice.
