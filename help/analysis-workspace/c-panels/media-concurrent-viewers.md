---
title: Media Concurrent Viewers panel
description: How to use and interpret the Media concurrent viewers panel in Analysis Workspace.
feature: Panels
exl-id: a442fb9c-165f-4136-95e2-ce92b9280c25
role: User
---
# Media concurrent viewers panel {#media-concurrent-viewers-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_mediaconcurrentviewers_button"
>title="Media concurrent viewers"
>abstract="Create a panel to analyse average minute audience for specific content, or over a specific time period."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_mediaconcurrentviewers_panel"
>title="Media concurrent viewers"
>abstract="Analyze concurrent viewers over time, view peak concurrency, or break down and compare.<br/><br>**Granularity**: Select time period to view concurrent viewers by.<br/>**Panel summary numbers**:<br/>Option to show summary numbers with date or time details for each line. Maximum will show details for peak concurrency. Minimum will show details for the trough.<br/>**Series breakdown (optional)**: Break down visualization by segments, dimensions, dimension items or date ranges. View up to 10 lines at a time. Breakdowns are limited to a single level."

<!-- markdownlint-enable MD034 -->



>[!NOTE]
>
>The Media average minute audience panel is available only to customers who have purchased the Streaming Media Collection Add-on for Customer Journey Analytics. 
>
>Contact your Adobe Sales representative or Adobe account team for more information. 
>

You can analyze concurrent viewers to understand where peak concurrency occurred or where drop-offs happened to provide valuable insight into the quality of content and viewer engagement. And to help with troubleshooting or planning for volume or scale.

In Analysis Workspace, the Concurrent viewers metric is the number of unique persons viewing your media streams at a specific point in time, regardless of the number of sessions.

The Media Concurrent Viewers panel enables analysis of concurrent viewers over time, with details on peak concurrency and the ability to break down and compare.  To access the Media Concurrent Viewers panel, navigate to a data view with components enabled from the Streaming Media Collection Add-on. Then, click the panel icon on the far-left and drag the panel into your Analysis Workspace project.

+++ View a video demonstration of this functionality.

>[!VIDEO](https://video.tv.adobe.com/v/330177/?quality=12)

{{videoaa}}

+++

## Use

To use an [!UICONTROL Media concurrent viewers] panel:

1. Create a [!UICONTROL Media concurrent viewers] panel. For information about how to create a panel, see [Create a panel](panels.md#create-a-panel).  

1. Ensure you select a data view for the panel that has components configured from the Streaming Media Collection Add-on.

1. Specify the [input](#panel-input) for the panel.

1. Observe the [output](#panel-output) for the panel.

### Panel input

You can configure the Media concurrent viewers panel using these input settings:

|Setting|Description|
|---|---|
|**[!UICONTROL Panel date range]**|The panel date range default is Today.  You may edit it to view a single day or many months at a time. <br> <br>This visualization is limited to 1440 rows of data (for example, 24-hours at minute-level granularity).  If a date range and granularity combination results in more than 1440 rows, the granularity is automatically updated to accommodate the full date range.|
|**[!UICONTROL Granularity]**|The granularity default is Minute.<br>This visualization is limited to 1440 rows of data (for example, 24-hours at minute-level granularity).  If a date range and granularity combination results in more than 1440 rows, the granularity is automatically updated to accommodate the full date range.|
|**[!UICONTROL Panel summary numbers]**| To see date or time details for concurrent viewers, a summary number is available. The Maximum shows details for peak concurrency. **[!UICONTROL Minimum]** shows details for the trough.  The panel default shows Maximum only, but you can change it to show Minimum or both Maximum and Minimum.<br><br>If you are using breakdowns, a summary number is displayed for each.|
|**[!UICONTROL Series breakdown]**| Optionally, you can break down your visualization by filters, dimensions, dimension items, or date ranges.<br>You may view up to 10 lines at a time. Breakdowns are limited to a single level.<br>When dragging a dimension, the top dimension items are selected automatically based on the selected panel date range.<br>To compare date ranges, drag 2 or more date ranges into the series breakdown filter.|

Here is an example of the panel configured for **[!UICONTROL Minute]** granularity, with **[!UICONTROL Maximum only]** summary numbers. And broken down by **[!UICONTROL Other]**, **[!UICONTROL Table]**, **[!UICONTROL Mobile Phone]**, **[!UICONTROL Gaming Console]**, **[!UICONTROL Media Player]**, **[!UICONTROL Set-top Box]**, **[!UICONTROL Television]**.

![The Media Concurrent Viewers Series breakdown view showing 7 of 10 dimensions, segments or date ranges.](assets/concurrent-viewers-series-breakdown.png)

### Panel output

The Media Concurrent Viewers panel returns a line chart and summary numbers to include details for the maximum and/or minimum concurrent viewers.  At the top of the panel, a summary line is provided to remind you of the panel settings you selected.

At any time, you can edit and rebuild the panel by clicking the edit pencil on the top right.

If you select a series breakdown, a line on the line chart and a summary number is displayed for each:

![The Media Concurrent Viewers output.](assets/concurrent-viewers-output.png)

### Data source

The only metric that can be used in this panel is **[!UICONTROL Concurrent viewers]**:

|Metric|Description|
|---|---|
|**[!UICONTROL Concurrent viewers]**| The number of unique persons viewing your media streams at a specific point in time, regardless of the number of sessions. |

A Freeform table is not available in this view.  To view the data source, you can download the data source from the line chart visualization context menu and select **[!UICONTROL Download data as CSV]**.  Series breakdowns are included.

![The Concurrent viewers output options with "Download data as CSV" highlighted.](assets/concurrent-viewers-download-csv.png)

## FAQs

|Question|Answer|
|---|---|
|Where is the Freeform table? How can I see the data source?| The Freeform table is not available in this view.  You can download the data source from the line chart context menu and select **[!UICONTROL Download data as CSV]**.|
|Why did my granularity change?|This visualization is limited to 1440 rows of data (for example, 24-hours at minute-level granularity).  If a date range and granularity combination results in more than 1440 rows, the granularity is automatically updated to accommodate the full date range.<br><br>When changing from a larger date range to a smaller one, the granularity is updated to the lowest detail allowable once the date range is changed. To view a higher granularity, edit the panel and rebuild.|
|How do I compare video names, filters, content types, and others?|To compare these items in a single visualization, drag filters, dimensions, or specific dimension items in the series breakdown filter.<br><br>The view is limited to 10 breakdowns.  To view more than 10, you must use multiple panels.|
|How do I compare date ranges?|To compare date ranges in a single visualization, use the series breakdowns by dragging 2 or more date ranges.  The date ranges override the panel date range.|
|How do I change the visualization type?|This panel only allows for the line visualization for the time series.|
|Can I run anomaly detection?|No.  Anomaly detection is not available for this panel.|
|Why use unique persons instead of active sessions?|Using unique persons enables removal of unwanted spikes at show boundaries (where sessions are ending and starting at the same time).|
|What does it mean to have concurrent viewers at higher granularity than minute?|With a granularity larger than a minute, concurrent viewers is the sum of unique concurrent viewers for all minutes within that time range.  For example, at hour-level granularity concurrent viewers are the sum of unique concurrent viewers for all minutes within the hour.|
|Does the workspace panel show the same information as the Concurrent Viewers Report?|No.  In Analysis Workspace, the Concurrent viewers metric is defined as the number of unique persons viewing your media stream at a specific point in time. Regardless of the number of sessions.<br><br>This metric is different than Concurrent viewer reporting in the Reports section, which uses Concurrent Active Sessions. Using unique persons accounts for the removal of unwanted peaks at show boundaries (where sessions are ending and starting at the same time).|

<!-- For more information about Media Concurrent Viewers, visit [MA doc page]( https://url). -->


>[!MORELIKETHIS]
>
>[Create a panel](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>