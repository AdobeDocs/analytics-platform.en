---
title: Guided analysis overview
description: A method of analyzing data in Customer Journey Analytics that lets product teams get high-quality insights quickly. Also referred to as Product Analytics.
keywords: product analytics
exl-id: 1ac8157f-87e8-4d98-a2ca-f6beb68d9d6b
feature: Guided Analysis
---
# Guided analysis overview

Adobe Product Analytics enables product teams to self-serve data and insights about their product experience through guided analysis workflows, built on the cross-channel data of Customer Journey Analytics. Guided analysis is a reporting format that allows product teams to quickly self-serve their data needs so that they can get high-quality insights quickly and make more data-driven product decisions. Cross-functional teams can connect in real time to use and understand these reports.

Similar to Analysis Workspace and Mobile scorecards, a Guided analysis report uses data from a [Data view](../data-views/data-views.md), which references data in Adobe Experience Platform through a [Connection](../connections/overview.md). All reports created in Guided analysis can seamlessly transfer to Analysis Workspace for additional research.

Guided analysis provides multiple ways to analyze and view data. View types can show the same data in different ways, leading to different insights using the same events and segments. You get different query rails and visualization settings depending on the view that you choose. You can freely switch between views, and any applicable query rail components carry over if the view supports them.

Guided analysis categorizes view types into **Analysis types**. The following analysis and view types are available:

| Analysis type | View type | Description |
| --- | --- | --- |
| [!UICONTROL Impact] | [Release](types/release.md) | Compare performance across equal periods pre- and post-release. |
| [!UICONTROL Impact] | [First use](types/first-use.md) | Measure the impact of first-time feature use on key indicators. |
| [!UICONTROL Funnel] | [Friction](types/friction.md) | Compare conversion rates between steps. |
| [!UICONTROL Funnel] | [Conversion trends](types/conversion-trends.md) | Track changes in conversion rates over time. |
| [!UICONTROL User growth] | [Active](types/active.md) | Identify who is new, retained, returning, or dormant. |
| [!UICONTROL User growth] | [Net growth](types/net-growth.md) | Are you gaining or losing users? |
| [!UICONTROL Trends] | [Usage](types/usage.md) | Measure user engagement over time. |
| [!UICONTROL Trends] | [Frequency](types/frequency.md) | Measure engagement by frequency of use. |

{style="table-layout:auto"}

## Access

If your organization is provisioned for guided analysis, you can access it from the Customer Journey Analytics homepage. 

1. Click **[!UICONTROL Guided analysis]** from the homepage, which takes you directly to the [Usage trends view](types/usage.md). 

   ![Landing page tile](assets/landing-page-tile.png)

1. Click **[!UICONTROL Create new]** to see the different view options and choose a different starting point for your analysis. 

   ![Create a new modal](assets/create-new-modal.png)

## Interface

The interface for guided analysis follows a question and answer format. Form your question in the query rail, then get an answer with a written insight, chart, and table. You can then ask the next question with the visualization settings and view types.

Regardless of analysis type, guided analysis uses the following UI elements:

| Interface preview | UI Element | Description |
| --- | --- | --- |
| ![Query rail](assets/query-rail.png) | Query rail | Configure the desired components (events, properties, and segments) that make up an analysis. Each analysis type enforces different limits to the number of events and segments that you can configure.<p>Use the filter icon to narrow down by specific event properties or create segments on the fly. Once a property is selected, in addition to standard filter criteria such as equals, contains, and ends with, a list of the top 1000 property values are available for filtering quickly.<p>If you switch to a new analysis type, your query selections are maintained within the allowed limits for that analysis type. |
| ![Chart](assets/chart.png) | Chart | A visualization of the data returned based on your input from the query rail and settings. Which visualization you see depends on the view and settings above the chart. Available views depend on the analysis type above the query rail. The chart also includes: <ul><li>**Tooltips**: Hover over any chart data point to expose a tooltip with more information.</li><li>**Legend**: Hover over the chart legend to expose series definitions, when available.</li><li>**Annotations**: Matching [Annotations](../components/annotations/overview.md) are visible between the visualization and the legend. It is shown as a ![Annotation icon](assets/annotation.png) icon in the annotation's configured color. View types that show data over time place the ![Annotation icon](assets/annotation.png) icon under the configured date or date range. View types that do not show data over time show the ![Annotation icon](assets/annotation.png) icon in the lower right corner of the chart.</li><li>**Click actions**: Expose available next actions by left-clicking any data point. Options include **Save segment**.</li></ul> |
| ![Table](assets/table.png) | Table | A table representation of the data returned based on your input from the query rail and settings. Columns in the table depend on the view type above the chart. Available views depend on the analysis type above the query rail. The table also includes: <ul><li>**Click actions**: Expose available next actions by clicking the **[!UICONTROL More]** menu. Options include **Save segment**.</li></ul> |
| ![Visualization settings](assets/visualization-settings.png) | Visualization settings | Several options above the chart that allow you to customize how the chart and table return data.<ul><li>**View type**: A drop-down selector that lets you present data for a given analysis type in a different way.</li><li>**Chart settings**: Fine-tune what your chart and table display. Available options depend on the view selected.</li><li>**Date range**: A calendar picker that allows you to determine the date range of the analysis. You can also select an interval for trended views, such as daily, weekly, or monthly.</li><li>**Insights**: Contextual insights depending on the analysis you view. You can tab to additional insights using the arrows or show or hide these insights using the light bulb icon in the top right.</li></ul> |
| ![Menu](assets/menu.png) | Menu | Commands in the top-right of Guided analysis that provide overarching actions for your analysis.<ul><li>**Data view selector**: Change the data view that the analysis uses. When you change the data view, available components in the query rail also change.</li><li>**Save**: Saves the analysis. If you're saving a new analysis, a modal window appears that requests a name and description.</li><li>**Save as**: Saves the analysis separately from the current analysis, creating a copy. A modal window appears that requests a new name and description.</li><li>**Open in Workspace**: Recreates the current Guided analysis in Analysis Workspace. The Workspace project is created in a new tab, preventing interruption while working within Guided analysis. It is a copy of the analysis, and does not remain in sync with the original guided analysis once opened. Use this command when you want to handoff to your analyst team, or dive deeper into the data than what Guided analysis allows for.</li><li>**Copy to clipboard**: Copies the chart graphic to your clipboard, to be pasted in other applications. The query rail and table are not included in the graphic.</li><li>**Download PNG**: Downloads the chart graphic as a `.png`. The query rail and table are not included in the graphic.</li><li>**Download CSV**: Downloads the table data as a `.csv`. The query rail and chart are not included in the file.</li></ul> |

{style="table-layout:auto"}

## Provisioning

Guided analysis is part of Adobe Product Analytics, which is a paid add-on to Customer Journey Analytics. If your organization would like to start using this set of capabilities, contact your Adobe Account Team.

Once your organization is provisioned to use Guided analysis, product profile administrators can add or remove access to it in the Adobe Admin Console.

1. Log in to the [Adobe Admin Console](https://adminconsole.adobe.com).
1. Select **[!UICONTROL Customer Journey Analytics]** in the list of products.
1. Select the desired product profile for the permissions that you want to edit.
1. Click the **[!UICONTROL Permissions]** tab, then click **[!UICONTROL Edit]** under [!UICONTROL Reporting Tools].
1. Click the plus icon next to **[!UICONTROL Guided Analysis Access]** in list of [!UICONTROL Available Permission Items], which adds it to the list of [!UICONTROL Included Permission Items].
1. Click **[!UICONTROL Save]**.

>[!TIP]
>
>Some admins prefer to enable Guided analysis and disable Analysis Workspace for new users to Customer Journey Analytics. Once those users mature with the product and your organizational data, you can then enable access to Analysis Workspace.
