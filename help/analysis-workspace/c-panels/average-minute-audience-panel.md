---
title: Media Average Minute Audience Panel
description: Learn how to use and interpret the Media Average Minute Audience panel in Analysis Workspace.
feature: Panels
role: User, Admin
exl-id: c55b5534-a9a6-47f1-8b43-c8c0b8686c53
---
# Media average minute audience panel {#media-average-minute-audience-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_mediaminuteaverageaudience_button"
>title="Media average minute audience"
>abstract="Create a panel to analyze average minute audience for specific content, or over a specific time period."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_mediaaverageminuteaudience_panel"
>title="Media average minute audience"
>abstract="Shows the performance of specific media content or the performance over a custom time period. Specify the reporting dimension and optionally segment content."

<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

_This article documents the Media average minute audience panel in_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**_.<br/>_See [Media average minute audience panel](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/panels/average-minute-audience-panel) for the_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics** version of this article._

>[!ENDSHADEBOX]

>[!NOTE]
>
>The **[!UICONTROL Media average minute audience]** panel is available only to customers who have purchased the Streaming Media Collection for Customer Journey Analytics. 
>
>Contact your Adobe Sales representative or Adobe account team for more information. 
>

In Analysis Workspace, the average minute audience can provide information on 

* the time spent viewing a specific media stream divided by the duration of the content, or 
* the time spent viewing during a custom time period with selected granularity.

The Media average minute audience panel enables you to understand average consumption of your content by comparing programs of any length or genre. For example, you can understand average consumption when comparing a 30-minute sitcom with a 3-hour sporting event.

In addition, you can use the Media average minute audience panel to compare or append this digital average minute audience to linear TV average minute metrics. 

The Media average minute audience panel provides the following benefits over the Average Minute Audience metric:

* Supports custom time periods

* Allows for updating the duration classification after views are processed (if the duration classification was not present or needs to be corrected)

  If you do this update when using the metric, the duration classification does not exist (if the classification wasn't present). Or the duration classification is out of date (if the classification was present but incorrect).

## Use

To use a **[!UICONTROL Media average minute audience]** panel:

1. Create a **[!UICONTROL Media average minute audience]** panel. For information about how to create a panel, see [Create a panel](panels.md#create-a-panel).  

1. Ensure you select a data view for the panel that has components configured from the Streaming Media Collection.

1. Specify the [input](#panel-input) for the panel.

1. Observe the [output](#panel-output) for the panel.

### Panel input

Use the input settings described in this section to configure the Media average minute audience panel.

1. Configure the following input settings:

   | Setting | Description |
   |---------|------------|
   | **Panel date range** | The panel date range default is [!UICONTROL **This month**]. You can edit it to view a single day or many months at a time. <br></br> This visualization is limited to 1440 rows of data (for example, 24-hours at minute-level granularity). If a date range and granularity combination results in more than 1440 rows, the granularity is automatically updated to accommodate the full date range. |
   | [!UICONTROL **Drop a segment here (or any other component)**] | Like other panels, this setting segments your selections based on segments you've created. This setting is a great way to look at specific platforms, live streams, or other common media segments. |
   | [!UICONTROL **Calculate metric for**] | Choose whether you want to see the average minute audience for [**[!UICONTROL Specific content]**](#specific-content). Or if you want to see the average minute audience for a [**[!UICONTROL Custom time period]**](#custom-time-period).<br/><br/>Select [!UICONTROL **Custom time period**]: <ul><li>If the duration is unavailable, or </li><li>if you want to view the average minute audience for a time series with multiple pieces of content, or</li><li>for content without a specific assigned duration (like during a live stream or event)</li></ul></li></li></ul> <p>This setting changes the workflow and report output.</p>  |

1. Continue with [Specific content](#specific-content) or [Custom time period](#custom-time-period), depending on the option you chose in the [!UICONTROL **Calculate metric for**] drop-down menu.

#### Specific content

1. If you selected [!UICONTROL **Specific content**] in the [!UICONTROL **Calculate metric for**] drop-down menu when [configuring panel inputs](#panel-inputs), specify the following configuration options:

   | Setting | Description |
   |---------|------------|
   | [!UICONTROL **Reporting dimension**] | When you select specific content, you can select the report output to use either the video name or content ID fields to show the content and its associated average minute audience. |
   | [!UICONTROL **Filter content by (optional)**] | Choose how to filter the specific content, depending on the view you want or the way your data is structured. <ul>[!UICONTROL **Show, season, episode**]: Displays your available shows in the drop-down, which you can filter using a search (or by dragging and dropping the show name from the left column). You can end your selection there to see all the seasons of your show, or you can filter by individual seasons and then by individual episodes. This setting shows the data for those shows, seasons, or episodes for the selected time period.</li><li>[!UICONTROL **Custom dimension**]: If your show name is under a custom dimension, you can find it either by searching in the dimension (optional) drop-down menu or by using the left column search. The dimension item automatically populates based on that selection and is treated as an episode.</li><li>[!UICONTROL **None**]: Shows all the video names that have average minute audience data for the selection you've chosen. (This option is selected by default.)</li></ul>  |

1. Continue with [Specific content advanced settings](#specific-content-advanced-settings) to configure advanced settings. 

#### Specific content advanced settings

1. With [!UICONTROL **Specific content**] selected in the [!UICONTROL **Calculate metric for**] drop-down menu, select [!UICONTROL **Show advanced settings**], then specify the following configuration options:

   | Options | Description |
   |---------|------------|
   | **[!UICONTROL Table settings]** | The default option **[!UICONTROL Show calculation values in table]** shows the numerator and denominator of the average minute audience as the preceding columns in the table. Deselecting this option removes those two columns. The average minute audience column remains in the table next to the video name or content ID. |
   | **[!UICONTROL Time spent metric]** | You can choose the default **[!UICONTROL Content Time Spent]** option, which includes only content time. Or you can choose to use **[!UICONTROL Media Time Spent]**, which includes content and ad time together as the numerator calculation for the average minute audience. |

1. Select [!UICONTROL **Build**] to finish creating the Media average minute audience panel.

1. Continue with [Panel output](#panel-output) for information about how to use the Media average minute audience panel.

#### Custom time period

1. If you selected [!UICONTROL **Custom time period**] in the [!UICONTROL **Calculate metric for**] drop-down menu when [configuring panel inputs](#panel-inputs), specify the following configuration options:

   | Options | Description |
   |---------|------------|
   | **[!UICONTROL Granularity]** | The default granularity is [!UICONTROL **5-Minute**], but you can choose any of the granularities that are used as the denominator for the time series within your selected time period. For example, selecting 12:00 pm to 12:30 pm with a 5-minute granularity returns the average minute audience over the full half hour as well as six rows with the average minute audience for each 5-minute period. These rows are used as the datapoints for the time series chart. |
   | [!UICONTROL **Filter content by (optional)**] | Choose how to filter the specific content, depending on the view you want or the way your data is structured. <ul>[!UICONTROL **Show, season, episode**]: Displays your available shows in the drop-down, which you can filter using a search (or by dragging and dropping the show name from the left column). You can end your selection there to see all the seasons of your show, or you can filter by individual seasons and then by individual episodes. This setting shows the data for those shows, seasons, or episodes for the selected time period.</li><li>[!UICONTROL **Custom dimension**]: If your show name is under a custom dimension, you can find it either by searching in the dimension (optional) menu or by using the left column search. The dimension item automatically populates based on that selection and is treated as an episode.</li><li>[!UICONTROL **None**]: Shows all the video names that have average minute audience data for the selection you've chosen. (This option is selected by default.)</li></ul>  |

1. Continue with [Custom time period advanced settings](#custom-time-period-advanced-settings) to configure advanced settings. 

#### Custom time period advanced settings

1. With [!UICONTROL **Custom time period**] selected in the [!UICONTROL **Calculate metric for**] drop-down menu, select [!UICONTROL **Show advanced settings**], then specify the following configuration option:

   | Option | Description |
   |---------|------------|
   | **[!UICONTROL Table settings]** | The default setting displays the calculation values in the table, which displays the numerator and denominator of the average minute audience as the preceding columns in the table. Deselecting this option removes those two columns leaving only the average minute audience next to the time period. |

1. Select [!UICONTROL **Build**] to finish creating the Media average minute audience panel.

1. Continue with [Panel output](#panel-output) for information about how to use the Media average minute audience panel.

### Panel output

The panel output differs depending on whether you chose [!UICONTROL **Specific content**] or [!UICONTROL **Custom time period**] in the [!UICONTROL **Calculate metric for**] drop-down menu when [configuring panel inputs](#panel-inputs).

#### Specific content

The Media average minute audience panel returns the following:

* Total average minute audience for your entire selection
* Filters and average minute audience for the individual videos, displayed in a table 
* Content time spent and video length (duration) if that advanced setting was selected

To edit and rebuild the panel at any time, select ![Edit](/help/assets/icons/Edit.svg) in the top right.

![Default view](assets/specific-content-panel-output.png)

#### Specific content data source

The Media average minute audience panel uses only the average minute audience metric to gather data. Breakdowns or other metrics cannot be used in the panel.

| Metric | Description |
|--------|-------------|
| **[!UICONTROL Average minute audience]** | The time spent viewing your media stream divided by the video length (duration) supplied via Classifications. |

#### Custom time period {#custom-time-period-output}

The Media average minute audience panel returns the following:

* The total average minute audience for your entire selection

* The maximum and minimum average minute audience

* The line series graph showing the average minute audience over the entire selection.

* A table that shows the filters and average minute audience for the granularities, as well as the content time spent and granularity for each time period 

  This table displays only if the option under advanced settings called [!UICONTROL **Show calculation values in table**] is selected.

To edit and rebuild the panel at any time, select ![Edit Media average minute audience panel](/help/assets/icons/Edit.svg) in the top right.


#### Custom time period data source

The Media average minute audience panel uses only the average minute audience metric to gather data. Breakdowns or other metrics cannot be used in the panel.

|Metric|Description|
|---|---|
|**[!UICONTROL Average Minute Audience]**| The time spent viewing your media stream divided by the total selection or selected granularity in minutes.|


>[!MORELIKETHIS]
>
> [Create a panel](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
> [Media concurrent viewers panel](media-concurrent-viewers.md)
> [Media playback time spent panel](media-playback-time-spent.md)
>