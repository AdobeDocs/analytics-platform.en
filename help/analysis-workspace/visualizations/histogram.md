---
description: A histogram is similar to a bar chart, but it groups numbers into ranges (buckets).
title: Histogram
feature: Visualizations
exl-id: 5901eb15-51cf-45a0-a80b-5824adf33bdd
role: User
---
# Histogram

The ![Histogram](/help/assets/icons/Histogram.svg) [!UICONTROL Histogram] visualization is similar to a [!UICONTROL Bar] visualization, but it groups numbers into ranges (buckets). Analytics automates the "bucketing" of numbers into ranges, but you can change the settings in [Advanced Settings](#advanced-settings).

## Use

To create a histogram:

1. Add a histogram. See [Add a visualization to a panel](freeform-analysis-visualizations.md#add-visualizations-to-a-panel).
1. Drag a metric from the **[!UICONTROL Metrics]** component list, or select a metric from the [!UICONTROL *Add a metric*] dropdown menu.
1. (optional) Select **[!UICONTROL Show advanced settings]**. See [Advanced settings](#advanced-settings).
1. Select **[!UICONTROL Build]**.

>[!NOTE]
>
>Histograms support only standard metrics, not calculated metrics.

In the example below, a histogram is used to bucket sessions for the number of persons. The histogram shows that most persons do have between 16-21 sessions for the selected data range.

![](assets/histogram.png)

## Advanced settings {#section_09D774C584864D4CA6B5672DC2927477}

As part of the visualization, specific histogram settings are available.

|  Histogram settings  | Description  |
|---|---|
|  **[!UICONTROL Starting bucket]**  | Determines which bucket the histogram starts with. "1" is the default. You can set starting numbers from 0 to infinity (no negative numbers).  |
|  **[!UICONTROL Metric buckets]**  | Lets you increase/decrease the number of data ranges (buckets.) The maximum number of buckets is 50.  |
|  **[!UICONTROL Metric bucket size]** | Lets you set the size of each bucket. For example, you can change the bucket size from 1 page view to 2 page views.  |
|  **[!UICONTROL Counting method]**  | Select from **[!UICONTROL Person]**, **[!UICONTROL Session]**, or **[!UICONTROL Event]**. For example, page views per session, or page views per person, or page views per event.  |

<!--Russ or Meike - Check Hit Type link above. -->

**Examples**:

| Starting bucket | Metric buckets | Metric bucket size | Result |
|:----:|:--:|:--:|:--|
| 1 | 5 | 2 | ![Histogram, starting bucket 1, metric buckets 5, metric bucket size 2](assets/histogram-1-5-2.png) |
| 0 | 3 | 5 | ![Histogram, starting bucket 0, metric buckets 3, metric bucket size 5](assets/histogram-0-3-5.png) |

>[!MORELIKETHIS]
>
>[Add a visualization to a panel](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Visualization settings](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Visualization context menu](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>


## Blog post

Refer to this blog post about information on [using histograms to identify unexpected data values](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/using-histograms-to-identify-unexpected-data-values/ba-p/596168).
