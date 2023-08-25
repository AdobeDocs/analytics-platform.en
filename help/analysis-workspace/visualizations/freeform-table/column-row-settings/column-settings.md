---
description: Column settings let you configure column formatting, some of which can be conditional.
title: Column settings
feature: Visualizations
exl-id: b41d8a12-e8d9-405c-ac71-6567397aec6b
---
# [!UICONTROL Column Settings]

[!UICONTROL Column Settings] let you configure column formatting, some of which can be conditional.

View a video on row and column settings here:

>[!VIDEO](https://video.tv.adobe.com/v/40382/?quality=12)

## Edit [!UICONTROL Column Settings] {#edit-column-settings}

To access [!UICONTROL Column Settings], drag a Freeform Table to the project, then click the gear icon in the column heading.

![](assets/column_settings.png)

You can edit settings **for multiple columns at once**. Just select multiple columns and click the settings icon of any one of those columns. Any changes that you make apply to all columns with cells selected in them.

| Element | Description |
| --- | --- |
| Number | Determines if a cell shows/hides the numeric value for the metric. For example, if the metric is Page Views, the numeric value is the number of page views for the row item. |
| Percent | Determines if a cell shows/hides the percent value for the metric. For example, if the metric is Page Views, the percent value is the number of page views for the row item divided by the total page views for the column.  Note:  We can show percentages greater than 100%, to be more accurate. We are also moving the upper bound cap to 1,000% to ensure columns can grow in widths too large. |
| Anomalies | Determines if anomaly detection is run on the values in this column. |
| Wrap Header Text | Lets you wrap the header text in Freeform tables to make headers more readable and tables more shareable. This is useful for .pdf rendering and for metrics with long names. Enabled by default. |
| Interpret zero as no value | For cells with a 0 value, determines whether to show a 0 or a blank cell. This is useful when you look at data for each day of a month, and some days haven't happened yet.  Instead of showing 0's for future dates, blank cells can be shown instead. Charts respect this setting as well (i.e., they do not showing a line or bar with 0 values when this setting is checked). |
| Background | Determines if a cell shows/hides all cell formatting, including the bar graph and conditional formatting. |
| Bar Graph | Shows a horizontal bar graph representing the cell's value relative to the total for the column. |
| Conditional Formatting | See the section below. |
| Table Cell Preview | Shows a preview of how each cell appears with the currently selected formatting options applied. |

## Conditional formatting {#conditional-formatting}

Conditional formatting applies formatting to upper, midpoint, and lower limits that you can define. Applying conditional formatting (colors, etc) within Freeform tables is also automatically enabled on breakdowns, unless "Custom" limits are selected.

![](assets/conditional-formatting.png)

| Element | Description |
| --- | --- |
| Conditional Formatting | Applies a preconfigured color set of your choosing to cells. Depending on which of the 4 available color schemes you select, different colors are assigned to high values, midpoint values, and low values. <br> Replacing a dimension in the table resets the conditional formatting limits. Replacing a metric recalculates the limits for that column (where a metric is on the X axis and a dimension is on the Y axis). |
| Use Percent Limits | Change the limit range to be based on percentages rather than absolute values. This works for metrics that are solely percentage based (like Bounce Rate) as well as for metrics that have a count and a percentage (like Page Views.) |
| Auto-generated | Automatically calculate upper/mid/lower limits based on the data. The upper limit is the largest value in this column. The lower limit is the lowest, and the midpoint is the average of the upper and lower limits. |
| Custom | Manually assign upper/mid/lower limits. This gives you the flexibility to determine when a column value becomes good, average, or poor. |
| Conditional formatting palette | Choose which of the 4 available color schemes to use for your conditional formatting. |

## Use non-default attribution model {#attribution}

Allows you to override the default attribution model set in [Data views](/help/data-views/component-settings/attribution.md).

>[!NOTE]
>
>Consider the following when updating a component's attribution to a non-default attribution model:
>
>* **When using the component in a report with *a single dimension*:** The component's attribution overrides the allocation model applied to the dimension in the report.
>
>* **When using the component in a report with *multiple dimensions*:** The component's attribution does not override the allocation models applied to each of the dimensions in the report.
>
>   Multiple dimensions are available only when [exporting data to the cloud](/help/analysis-workspace/export/export-cloud.md).
>
> For more information about allocation, see [Persistence component settings](/help/data-views/component-settings/persistence.md).

To use a non-default attribution model for a metric in an Analysis Workspace:

1. Click the Settings (gear) icon on a metric in a Freeform Table column.

   ![Attribution checkbox](assets/attribution-checkbox.png)

2. Under **[!UICONTROL Data Settings]**, check **[!UICONTROL Use non-default attribution model]**. For more information on different attribution models, see [Attribution models](/help/data-views/component-settings/attribution.md).

   ![Select attribution model](assets/attribution-select.png)

>[!MORELIKETHIS]
>
>* [Manage data sources](/help/analysis-workspace/visualizations/t-sync-visualization.md)
