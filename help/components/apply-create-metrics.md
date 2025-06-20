---
description: There are two ways to use metrics in Analysis Workspace.
title: Metrics
feature: Metrics
exl-id: 4edfb5d7-da20-4bd8-8041-387b291daf96
role: User
---
# Metrics

Metrics allow you to quantify data points in Analysis Workspace. They are most commonly used as columns in a visualization and tied to dimensions.

## Use metrics in Analysis Workspace

Metrics are flexible in their use within Analysis Workspace. Drag a metric to an empty Freeform table to see that metric trended over the project's date period. You can also drag a metric when a dimension is present to see that metric compared to each dimension item. Dragging a metric on top of an existing metric header replaces it, and dragging a metric next to a header lets you see both metrics side-by-side.

For information about how to add metrics and other types of components to Analysis Workspace, see [Use components in Analysis Workspace](/help/components/use-components-in-workspace.md).


## Types of metrics

Adobe offers several types of metrics for use in Analysis Workspace:


* **Standard metrics**: Example of standard metrics are People, Sessions, Events.

  Contrary to Adobe Analytics, Customer Journey Analytics allows you to define standard metrics in a flexible way within the scope of a connection and a data view. 

  * **People**: The People metric in Customer Journey Analytics is the count distinct of Person IDs. Depending on what you choose as the Person ID when you configure datasets in your connection, the People metric can mean different things.
  * **Sessions**: The Sessions metric in Customer Journey Analytics is what you define as part of the configuration of the Sessions settings in your data view. See [Session settings](/help/data-views/session-settings.md).
  * **Events**: The Events metric in Customer Journey Analytics are comprised of the events that are part of any event dataset you have configured as part of your connection.

  See [Standard metrics](#standard-metrics) for the full list of standard metrics.

* **Calculated metrics** ![Calculator](/help/assets/icons/Calculator.svg): User-defined metrics that are based on standard metrics, static numbers, or algorithmic functions.

* **Calculated metric templates**  ![AdobeLogoSmall](/help/assets/icons/AdobeLogoSmall.svg) : Adobe-defined metrics that behave similarly to calculated metrics. You can use them as-is in Workspace projects, or save a copy to customize the logic. See [Default calculated metrics](calc-metrics/cm-workflow/../default-calcmetrics.md).

You can see whether a metric is approved ![Approved icon](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  or not. If you want more details on a metric, hover over the metric, and select ![Info icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg). See [Component info](use-components-in-workspace.md#component-info) for more information.


## Standard metrics

The full list of standard metrics in Customer Journey Analytics:
{{standard-metrics}}


## Create calculated metrics

Calculated metrics allow you to easily configure how metrics relate to each other, using simple operators or statistical functions. See [Calculated metrics overview](/help/components/calc-metrics/calc-metr-overview.md) for more information.

There are several ways to create calculated metrics. The method you choose determines whether the calculated metric is available from the component list across all projects, or only in the project where it was created.

### Create calculated metrics for all projects

You can use the [calculated metric builder](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md) to [create calculated metrics](/help/components/calc-metrics/cm-workflow/cm-workflow.md). When created in this way, calculated metrics are available in the component list and can then be used in projects throughout your organization. 

### Create calculated metrics for a single project

You can quickly create a calculate metric that is available only for the project where it was created.

To create a calculated metric for a single project:

1. In Analysis Workspace, open the project where you want to create the calculated metric.

1. In a freeform table, right-click the column header of a single column.

   Or

   Select two columns while holding the Shift key, then right-click one of the selected columns.
   
1. Select **[!UICONTROL Create metric from selection]**

   ![Workspace panel highlighting Create from selection](assets/create-metric-from-selection.png)

1. To create a calculated metric for this project only, choose from the available options.

   When a single column is selected, the following options are available:

   * [!UICONTROL **Mean**]: Creates a new column that shows the mean value in the set of dimension elements for the column. This uses the [Mean](/help/components/calc-metrics/cm-functions.md#mean) function.
   
   * [!UICONTROL **Median**]: Creates a new column that shows the median value in the set of dimension elements for the column. This uses the [Median](/help/components/calc-metrics/cm-functions.md#median) function.

   * [!UICONTROL **Column max**]: Creates a new column that shows the largest value in the set of dimension elements for the column. This uses the [Column Maximum](/help/components/calc-metrics/cm-functions.md#column-maximum) function.

   * [!UICONTROL **Column min**]: Creates a new column that shows the smallest value in the set of dimension elements for the column. This uses the [Column Minimum](/help/components/calc-metrics/cm-functions.md#column-minimum) function.

   * [!UICONTROL **Column sum**]:Creates a new column that adds all numeric values for a metric within a column (across the elements of a dimension). This uses the [Column Sum](/help/components/calc-metrics/cm-functions.md#column-sum) function.

   When two columns are selected, the following options are available:

   * [!UICONTROL **Divide**]: Creates a new column that divides the values of the two selected columns.
   
   * [!UICONTROL **Subtract**]: Creates a new column that subtracts the values of the two selected columns.

   * [!UICONTROL **Add**]: Creates a new column that adds the values of the two selected columns.

   * [!UICONTROL **Multiply**]: Creates a new column that multiplies the values of the two selected columns.

   * [!UICONTROL **Percent change**]: Creates a new column that shows the percent change between the two selected columns.


## Compare metrics with different attribution models

To quickly compare one attribution model to another for a metric, select **[!UICONTROL Compare attribution models]** from the context menu for a metric.

![Workspace panel highlighting Compare attribution models](assets/compare-attribution.png)

This shortcut lets you compare one attribution model to another without dragging in a metric and configuring it twice.


