---
title: Guided analysis overview
description: A method of analyzing data in Customer Journey Analytics that lets product teams get high-quality insights quickly. 
keywords: product analytics
exl-id: 1ac8157f-87e8-4d98-a2ca-f6beb68d9d6b
feature: Guided Analysis
role: User
---
# Guided analysis overview

Guided analysis enables users, from marketing to product to analysts, to self-serve high quality data and insights about the customer journey through guided workflows, built on the cross-channel data of Customer Journey Analytics. Similar to Analysis Workspace and Mobile scorecards, Guided analysis uses data from a [Data view](/help/data-views/data-views.md), which references data in Adobe Experience Platform through a [Connection](../connections/overview.md). Many reports created in Guided analysis can seamlessly transfer to Analysis Workspace for additional research.

The following guided analyses are available:

| Icon |Analysis | Description |
| :----:|--- | --- |
| ![PeopleGroup](/help/assets/icons/PeopleGroup.svg) |[Active growth](types/active-growth.md) | Identify who is new, retained, returning, or dormant. |
| ![ConversionTrens](/help/assets/icons/ConversionTrends.svg) |[Conversion trends](types/conversion-trends.md) | Track changes in conversion rates over time. |
| ![EngagementGraph](/help/assets/icons/EngagementGraph.svg) |[Engagement](types/engagement.md) | Understand the breadth and depth of feature engagement. |
| ![FirstUse](/help/assets/icons/FirstUse.svg) |[First use impact](types/first-use-impact.md) | Measure the impact of first-time feature use on key indicators. |
| ![Histogram](/help/assets/icons/Histogram.svg)| [Frequency](types/frequency.md) | Measure engagement by frequency of use. |
| ![ConversionFunnel](/help/assets/icons/ConversionFunnel.svg) |[Funnel](types/funnel.md) | Compare conversion rates between steps. |
| ![NetGrowth](/help/assets/icons/NetGrowth.svg) | [Net growth](types/net-growth.md) | Are you gaining or losing users? |
| ![Release](/help/assets/icons/Release.svg) | [Release impact](types/release-impact.md) | Compare performance across equal periods pre- and post-release. |
| ![Retention](/help/assets/icons/Retention.svg) |[Retention](types/retention.md) | Measure your users' ongoing return habits. |
| ![Timeline](/help/assets/icons/Timeline.svg) | [Timeline](types/timeline.md) | Explore patterns in session activity. |
| ![GraphTrend](/help/assets/icons/GraphTrend.svg) |[Trends](types/trends.md) | Measure user engagement over time. |



## Access

You can access Guided analysis from the Customer Journey Analytics homepage. 

1. Select **[!UICONTROL Guided analysis]** from the homepage, which takes you directly to the [Trends analysis](types/trends.md). 

   ![Landing page tile](assets/landing-page-tile.png){style="border:1px solid gray"}

1. Select **[!UICONTROL Create new]** to see the different view options and choose a different starting point for your analysis. 

   ![Create a new modal](assets/create-new-modal.png){style="border:1px solid gray"}

You can also access Guided analysis from within an Analysis Workspace project.

1. Select **[!UICONTROL Blank project]** from the homepage to create an empty Workspace project.
   
   ![Create blank project](assets/blank-project.png){style="border:1px solid gray"}

1. Select ![Guided analysis](/help/assets/icons/GuidedAnalysis.svg) **[!UICONTROL Guided Analysis]** in the left rail.
   
   ![Workspace left rail](assets/workspace-left-rail.png){style="border:1px solid gray"}

1. Drag any new analysis onto the Workspace canvas, then select **[!UICONTROL Create]** to generate the desired analysis (for example: **[!UICONTROL Create Trends]**). You can also drag an existing analysis onto the Workspace canvas from under the **[!UICONTROL Saved]** section.

   ![Create panel](assets/create-guided-analysis-panel.gif)

## Interface

The interface for Guided analysis follows a question and answer format. Form your question in the query rail, then get an answer with a written insight, chart, and table. You can then ask the next question with analyses and visualization settings.

Guided analysis uses the following UI elements:

| Interface preview | UI Element | Description |
| --- | --- | --- |
| ![Query rail](assets/query-rail.png){style="border:1px solid gray"} | **[!UICONTROL Query rail]** | Configure your *question* by selecting the desired components (events, properties, and segments) that make up an analysis. The following options are available across all analysis, with additional settings available on a per view basis. <ul><li>**View**: Select from the options to switch to a new analysis. Your query selections are maintained within the allowed limits for the new analysis.</li><li>**Events**: The events that you want to measure. Each analysis enforces different limits to the number of events that you can configure.  Events are sometimes labeled as **[!UICONTROL Start and return events]**, **[!UICONTROL Steps]**, or **[!UICONTROL Key indicators]**. Events are identified in the analysis using 1, 2, ...<br/>Select ![Add](/help/assets/icons/Add.svg) **[!UICONTROL Add an event]** to add new events.</li><li>**[!UICONTROL Factors]**: If available, allows you to specify factors such as date since and first time event.</li><li>**Counted as**: The counting method that you want to apply to the selected events. Select from the drop-down menu.</li><li>**Segments**: The segments that you want to measure. Each analysis enforces different limits to the number of segments that you can configure. Segments are identified in the analysis using A, B, ...<br/>Select ![Add](/help/assets/icons/Add.svg) **[!UICONTROL Add a segment]** to add new segments.</li><li>**[!UICONTROL Breakdown]**: If available, the breakdown you want to apply to the analysis.</li></ul>On some of the settings, additional configuration is available.<ul><li>**Filters**: Use ![Filter](assets/filter.png) to narrow down events or segments by specific dimensions. When a dimension is selected, both standard filter criteria (such as **[!UICONTROL Equals]**, **[!UICONTROL Contains]**, or **[!UICONTROL Ends with]**) and the top 1000 dimension values are available.<br/>Select ![Filter](/help/assets/icons/Filter.svg) to add additional filters.<br/>Select ![Remove](/help/assets/icons/Remove.svg) to remove a filter.</li><li>**More actions**: Use ![More](/help/assets/icons/More.svg) to select actions, like<ul><li>![Rename](/help/assets/icons/Rename.svg) **[!UICONTROL Rename]**: to rename an event or segment.</li><li>![Duplicate](/help/assets/icons/Duplicate.svg) **[!UICONTROL Duplicate]**: to duplicate an event or segment.</li><li>![Delete](/help/assets/icons/Delete.svg) **[!UICONTROL Remove]**: to remove an event, segment or breakdown.</li><li>![Edit segment](/help/assets/icons/Edit.svg) **[!UICONTROL Edit segment]**: to edit a segment in the [Segment builder](/help/components/filters/filter-builder.md).</li><li>![Star](/help/assets/icons/Star.svg) **[!UICONTROL Add to favorites]**: to add the segment to the list of favorite segments in the [Segment manager](/help/components/filters/manage-filters.md).</li><li>![SaveAsFloppy](/help/assets/icons/SaveAsFloppy.svg) **[!UICONTROL Save as]**: to save the segment as a new component. In the **[!UICONTROL Save segments to components]** dialog, you can specify a segment name and a description. You can select ![StarOutline](/help/assets/icons/StarOutline.svg) to mark the new segment as a favorite. Select **[!UICONTROL Save]** to save the segment as a new segment.</li><li>![Link](/help/assets/icons/Link.svg) **[!UICONTROL Link start and return events]**.: to link start and return events in a [Retention](types/retention.md) analysis.</li><li>![Unlink](/help/assets/icons/Unlink.svg) **[!UICONTROL Unlink start and return events]**: to unlink start and return events in a [Retention](types/retention.md) analysis.</li></ul></li></ul> |
| ![Chart](assets/chart.png){style="border:1px solid gray"} | **[!UICONTROL Chart]** | A visualization of the data returned based on your input from the query rail and settings. Which visualization you see depends on the view and settings above the chart. The chart also includes: <ul><li>**Tooltips**: Hover over any chart data point to expose a tooltip with more information.</li><li>**Legend**: Hover over the chart legend series to view definitions where available, focus on that series, and temporarily hide other series. Select a series in the legend to hide the series.</li><li>**Annotations**: Applicable [annotations](../components/annotations/overview.md) are visible between the visualization and the legend. It is shown as a ![Annotation icon](assets/annotation.png) icon in the annotation's configured color. Analyses that show data over time place the ![Annotation icon](assets/annotation.png) icon under the configured date or date range. Analyses that do not show data over time show the ![Annotation icon](assets/annotation.png) icon in the lower right corner of the chart.</li><li>**Select actions**: Expose the next available actions by selecting any data point. Options include **Save segment**.</li></ul> |
| ![Table](assets/table.png){style="border:1px solid gray"} | **[!UICONTROL Table]** | A table representation of the data returned based on your input from the query rail and settings. Rows in the table using event (1, 2, ...) and segment identifiers (A, B, ...) for reference. Columns in the table depend on the analysis above the chart. The table also includes for each row: <ul><li>**Select actions**: Toggle ![Show hide icon](assets/hide-in-chart.png) to hide or expose a chart series for a row. Select ![More](/help/assets/icons/More.svg) for additional actions. Options include **Save segment**.</li></ul> |
| ![Visualization settings](assets/visualization-settings.png){style="border:1px solid gray"} | **[!UICONTROL Visualization settings]** | Options above the chart that allow you to ask the next question and customize how the chart and table return data. The following options are available across all analysis, with additional settings available on a per analysis basis. <ul><li>![GraphTrend](/help/assets/icons/GraphTrend.svg) **Chart settings**: Fine-tune what your chart and table display. Available options depend on the analysis selected.</li><li>![Layer](/help/assets/icons/Layer.svg) **Overlay settings**: Add an overlay. Available options depend on the analysis selected.</li><li>![Bucket](/help/assets/icons/Bucket.svg) **[!UICONTROL Bucket settings]**: Auto bucket or apply custom bucket settings to the data. Available options depend on the analysis selected.<li>![DataCorrelated](/help/assets/icons/DataCorrelated.svg) **[!UICONTROL Compare settings]**: Compare data to a specific date range. Available options depend on the analysis selected.</li><li>![Footsteps](/help/assets/icons/Footsteps.svg) **[!UICONTROL Display settings]**: Select how to show the data. Available options depend on the analysis selected.<li>![Calendar](/help/assets/icons/Calendar.svg) **Date range**: A calendar picker that allows you to determine the date range of the analysis. You can also select an interval for trended analyses, such as daily, weekly, or monthly.</li><li>![LightBulb](/help/assets/icons/LightBulb.svg) **Insights**: Contextual insights depending on the analysis that you view. These insights provide observations for the current analysis. If multiple insights are available, you can view them using the arrows on the right. You can toggle the visibility of this box by using the light bulb icon in the top right.</li></ul> |
| ![Menu icon](assets/menu.png){style="border:1px solid gray"} | **[!UICONTROL Menu]**<br/>Available in a Guided analysis project | Commands in the top-right of a Guided analysis project that provide overarching actions for your analysis.<ul><li>![Data icon](/help/assets/icons/Data.svg) ***Name of data view***: Change the data view that the analysis uses. When you change the data view, available components in the query rail also change.</li><li>![Link icon](/help/assets/icons/Link.svg) **Copy link**: Copies a link to the analysis to your clipboard. You are prompted to save before sharing.</li><li>**Share**: Opens the sharing modal, with further options for sharing to individual users or groups. You can share an analysis with other users, or generate a link to share with anyone.</li><li>**Save**: Saves the analysis. If you're saving a new analysis, the **[!UICONTROL Save analysis]** dialog appears that requests a name and description. Once saved, an **[!UICONTROL Analysis saved]** dialog allows you to share your analysis.</li><li>![Add to Workspace icon](/help/assets/icons/MultipleAdd.svg) **[!UICONTROL Add to Workspace]**: Shows available Workspace projects that you can add this analysis to. Selecting a Workspace project opens that Workspace project in a new tab, adding the analysis at the bottom of the project.</li></ul>Select ![More icon](/help/assets/icons/More.svg) for more actions, like:<ul><li>**[!UICONTROL Save as]**: Saves the analysis separately from the current analysis, creating a copy. A dialog appears that requests a new name and description.</li><li>**[!UICONTROL Export to Workspace]**: Recreates the current Guided analysis query in Analysis Workspace. The Workspace project is created in a new tab, preventing interruption while working within Guided analysis. It is a copy of the analysis, and does not remain in sync with the original analysis once opened. Use this command when you want to handoff to your analyst team, or dive deeper into the data than what the analysis allows for.</li><li>**[!UICONTROL Copy chart to clipboard]**: Copies the chart graphic to your clipboard, to be pasted in other applications. The query rail and table are not included in the graphic.</li><li>**[!UICONTROL Download PNG]**: Downloads the chart graphic as a `.png`. The query rail and table are not included in the graphic.</li><li>**[!UICONTROL Download CSV]**: Downloads the table data as a `.csv`. The query rail and chart are not included in the file.</li></ul> |
| ![Menu visualization](assets/menu-visualization.png){style="border:1px solid gray"} | **Menu**<br/>Available in a Guided analysis visualization in Analysis workspace. | Commands in a Guided analysis visualization in Analysis workspace.<ul><li>![GraphScatter](/help/assets/icons/GraphScatter.svg) **[!UICONTROL Chart]**: to show only the chart of the analysis.</li><li>![Table](/help/assets/icons/Table.svg) **[!UICONTROL Table]**: to show only the table of the analysis.</li><li>![TableAndChart](/help/assets/icons/TableAndChart.svg) **[!UICONTROL All]**: to show chart and table of the analysis.</li><li>![Edit](/help/assets/icons/Edit.svg) **[!UICONTROL Edit]**: to edit the configuration of the analysis</li><li>![Calendar](/help/assets/icons/Calendar.svg) **[!UICONTROL *Date range*]**: to configure the date range for the analysis.</li></ul> |


## Provisioning

Guided analyses are included in Customer Journey Analytics packages in the following way:

| Package | Available analyses |
| --- | --- |
| [!UICONTROL Customer Journey Analytics add-ons] | Active growth, Conversion trends, Frequency, Funnel, Net growth, Retention, Trends |
| [!UICONTROL Customer Journey Analytics Foundation] | Trends |
| [!UICONTROL Customer Journey Analytics Select] | Foundation views + Active growth, Conversion trends, Frequency, Funnel, Net growth, Retention |
| [!UICONTROL Customer Journey Analytics Prime] | Select views + Engagement, First use impact, Release impact, Timeline |
| [!UICONTROL Customer Journey Analytics Ultimate] | Prime views |

{style="table-layout:auto"}

Product profile administrators can add or remove access to Guided analysis in the Adobe Admin Console.

1. Log in to the [Adobe Admin Console](https://adminconsole.adobe.com).
1. Select **[!UICONTROL Customer Journey Analytics]** in the list of products.
1. Select the desired product profile for the permissions that you want to edit.
1. Select the **[!UICONTROL Permissions]** tab, then click **[!UICONTROL Edit]** under [!UICONTROL Reporting Tools].
1. Select ![AddCircle](/help/assets/icons/AddCircle.svg)  next to **[!UICONTROL Guided Analysis Access]** in the list of [!UICONTROL Available Permission Items], which adds it to the list of [!UICONTROL Included Permission Items].
1. Select **[!UICONTROL Save]**.

See [User level access](/help/technotes/access-control.md#user-level-access) for more information.

>[!TIP]
>
>Some admins prefer to enable Guided analysis and disable Analysis Workspace for new users to Customer Journey Analytics. Once those users mature with the product and your organizational data, you can then enable access to Analysis Workspace.
