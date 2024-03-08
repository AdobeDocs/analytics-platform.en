---
title: Guided analysis overview
description: A method of analyzing data in Customer Journey Analytics that lets product teams get high-quality insights quickly. Also referred to as Product Analytics.
keywords: product analytics
exl-id: 1ac8157f-87e8-4d98-a2ca-f6beb68d9d6b
feature: Guided Analysis
role: User
---
# Guided analysis overview

Guided analysis enables users to self-serve high quality data and insights about the customer journey through guided workflows, built on the cross-channel data of Customer Journey Analytics. Cross-functional teams, from marketing to product, can connect in real time to use and understand these reports.

>[!NOTE]
>
> Guided analysis is currently only available as part of Adobe Product Analytics, which is a paid add-on to Customer Journey Analytics. If your organization would like to start using this set of capabilities, contact your Adobe Account Team.

Similar to Analysis Workspace and Mobile scorecards, guided analysis uses data from a [Data view](../data-views/data-views.md), which references data in Adobe Experience Platform through a [Connection](../connections/overview.md). Many reports created in guided analysis can seamlessly transfer to Analysis Workspace for additional research.

The following guided analysis views are available:

| Analysis type | View type | Description |
| --- | --- | --- |
| [!UICONTROL Funnel] | [Friction](types/friction.md) | Compare conversion rates between steps. |
| [!UICONTROL Funnel] | [Conversion trends](types/conversion-trends.md) | Track changes in conversion rates over time. |
| [!UICONTROL Impact] | [Release](types/release.md) | Compare performance across equal periods pre- and post-release. |
| [!UICONTROL Impact] | [First use](types/first-use.md) | Measure the impact of first-time feature use on key indicators. |
| [!UICONTROL Retention] | [Retention rates](types/retention-rates.md) | Measure your users' ongoing return habits. |
| [!UICONTROL Trends] | [Usage](types/usage.md) | Measure user engagement over time. |
| [!UICONTROL Trends] | [Frequency](types/frequency.md) | Measure engagement by frequency of use. |
| [!UICONTROL User growth] | [Active](types/active.md) | Identify who is new, retained, returning, or dormant. |
| [!UICONTROL User growth] | [Net growth](types/net-growth.md) | Are you gaining or losing users? |
| [!UICONTROL User stream] | [Timeline](types/timeline.md) | Explore patterns in session activity. |

{style="table-layout:auto"}

## Access

If your organization is provisioned for guided analysis, you can access it from the Customer Journey Analytics homepage. 

1. Click **[!UICONTROL Guided analysis]** from the homepage, which takes you directly to the [Usage trends view](types/usage.md). 

   ![Landing page tile](assets/landing-page-tile.png){style="border:1px solid gray"}

1. Click **[!UICONTROL Create new]** to see the different view options and choose a different starting point for your analysis. 

   ![Create a new modal](assets/create-new-modal.png){style="border:1px solid gray"}

If your organization is not yet provisioned for guided analysis, contact your Adobe Account Team.

## Interface

The interface for guided analysis follows a question and answer format. Form your question in the query rail, then get an answer with a written insight, chart, and table. You can then ask the next question with view types and visualization settings.

Guided analysis uses the following UI elements:

| Interface preview | UI Element | Description |
| --- | --- | --- |
| ![Query rail](assets/query-rail.png){style="border:1px solid gray"} | Query rail | Configure your "question" be selecting the desired components (events, properties, and segments) that make up an analysis. The following options are available across all view types, with additional settings available on a per view basis. <ul><li>**Analysis selector**: A drop-down that lets you switch to a new analysis type. Your query selections are maintained within the allowed limits for the new analysis type.</li><li>**View selector**: A drop-down that lets you switch to a new view ("answer") for the query you formed. Your query selections are maintained within the allowed limits for the new view type.</li><li>**Events**: The events that you want to measure. Each view type enforces different limits to the number of events that you can configure.</li><li>**Filters**: Use the ![Filter](assets/filter.png) icon in the Events or Segments section to narrow down by specific properties. When a property is selected, both standard filter criteria (such as [!UICONTROL Equals], [!UICONTROL Contains], or [!UICONTROL Ends with]) and the top 1000 property values are available.</li><li>**Counted as**: The counting method that you want to apply to the selected events.</li><li>**Segments**: The segments that you want to measure. Each view type enforces different limits to the number of segments that you can configure.</li></ul> |
| ![Chart](assets/chart.png){style="border:1px solid gray"} | Chart | A visualization of the data returned based on your input from the query rail and settings. Which visualization you see depends on the view and settings above the chart. The chart also includes: <ul><li>**Tooltips**: Hover over any chart data point to expose a tooltip with more information.</li><li>**Legend**: Hover over the chart legend series to view definitions where available, focus on that series, and temporarily hide other series. Hide a series in the legend by clicking it.</li><li>**Annotations**: Applicable [annotations](../components/annotations/overview.md) are visible between the visualization and the legend. It is shown as a ![Annotation icon](assets/annotation.png) icon in the annotation's configured color. View types that show data over time place the ![Annotation icon](assets/annotation.png) icon under the configured date or date range. View types that do not show data over time show the ![Annotation icon](assets/annotation.png) icon in the lower right corner of the chart.</li><li>**Click actions**: Expose available next actions by left-clicking any data point. Options include **Save segment**.</li></ul> |
| ![Table](assets/table.png){style="border:1px solid gray"} | Table | A table representation of the data returned based on your input from the query rail and settings. Columns in the table depend on the view type above the chart. The table also includes: <ul><li>**Click actions**: Hide or expose a chart series by toggling the ![Show hide icon](assets/hide-in-chart.png) icon in each row. Additional actions are available by clicking the **[!UICONTROL More]** menu. Options include **Save segment**.</li></ul> |
| ![Visualization settings](assets/visualization-settings.png){style="border:1px solid gray"} | Visualization settings | Options above the chart that allow you to ask the next question and customize how the chart and table return data. The following options are available across all view types, with additional settings available on a per view basis. <ul><li>**Chart settings**: Fine-tune what your chart and table display. Available options depend on the view selected.</li><li>**Date range**: A calendar picker that allows you to determine the date range of the analysis. You can also select an interval for trended views, such as daily, weekly, or monthly.</li><li>**Insights**: Contextual insights depending on the analysis you view. You can tab to additional insights using the arrows or show or hide these insights using the light bulb icon in the top right.</li></ul> |
| ![Menu](assets/menu.png){style="border:1px solid gray"} | Menu | Commands in the top-right of guided analysis that provide overarching actions for your analysis.<ul><li>**Data view selector**: Change the data view that the analysis uses. When you change the data view, available components in the query rail also change.</li><li>**Copy link**: Copies a link to the analysis to your clipboard. You will be prompted to save before sharing.</li><li>**Share**: Opens the sharing modal, with further options for sharing to individual users or groups. You will be prompted to save before sharing.</li><li>**Save**: Saves the analysis. If you're saving a new analysis, a modal window appears that requests a name and description.</li><li>**Save as**: Saves the analysis separately from the current analysis, creating a copy. A modal window appears that requests a new name and description.</li><li>**Open in Workspace**: Recreates the current guided analysis in Analysis Workspace. The Workspace project is created in a new tab, preventing interruption while working within guided analysis. It is a copy of the analysis, and does not remain in sync with the original guided analysis once opened. Use this command when you want to handoff to your analyst team, or dive deeper into the data than what guided analysis allows for.</li><li>**Copy to clipboard**: Copies the chart graphic to your clipboard, to be pasted in other applications. The query rail and table are not included in the graphic.</li><li>**Download PNG**: Downloads the chart graphic as a `.png`. The query rail and table are not included in the graphic.</li><li>**Download CSV**: Downloads the table data as a `.csv`. The query rail and chart are not included in the file.</li></ul> |

{style="table-layout:auto"}

## Provisioning

Guided analysis is part of Adobe Product Analytics, which is a paid add-on to Customer Journey Analytics. If your organization would like to start using this set of capabilities, contact your Adobe Account Team.

Once your organization is provisioned to use guided analysis, product profile administrators can add or remove access to it in the Adobe Admin Console.

1. Log in to the [Adobe Admin Console](https://adminconsole.adobe.com).
1. Select **[!UICONTROL Customer Journey Analytics]** in the list of products.
1. Select the desired product profile for the permissions that you want to edit.
1. Click the **[!UICONTROL Permissions]** tab, then click **[!UICONTROL Edit]** under [!UICONTROL Reporting Tools].
1. Click the plus icon next to **[!UICONTROL Guided Analysis Access]** in list of [!UICONTROL Available Permission Items], which adds it to the list of [!UICONTROL Included Permission Items].
1. Click **[!UICONTROL Save]**.

>[!TIP]
>
>Some admins prefer to enable guided analysis and disable Analysis Workspace for new users to Customer Journey Analytics. Once those users mature with the product and your organizational data, you can then enable access to Analysis Workspace.
