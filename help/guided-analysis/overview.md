---
title: Guided analysis overview
description: A method of analyzing data in Customer Journey Analytics that lets product teams easily generate reports and insights.
---
# Guided analysis overview

{{release-limited-testing}}

Guided analysis is a reporting format that allows product teams to quickly self-serve their data needs so that they can make more data-driven product decisions. Cross-functional teams can connect in real time to use and understand these reports.

Similar to Analysis Workspace and Mobile scorecards, a Guided analysis report uses data from a [Data view](../data-views/data-views.md), which references data in Adobe Experience Platform through a [Connection](../connections/overview.md). All reports created in Guided analysis can seamlessly transfer to Analysis Workspace for additional research.

Guided analysis reports currently feature three analysis types: [Funnel](analysis-types/funnel.md), [Trends](analysis-types/trends.md), and [User growth](analysis-types/user-growth.md). Each of these analysis types has multiple view types, which provide additional insights to each of these reports.

## Provisioning

Guided analysis is a paid add-on to Customer Journey Analytics. If your organization would like to start using this feature, contact your Adobe Account Team.

## Interface

The interface for Guided analysis, regardless of analysis type, comprises the following main UI elements:

1. **Query rail**: Use this rail on the left to build out your analysis.
1. **Chart**: Once you select the desired events, people, or steps, a chart is shown on the right that visualizes the data.
1. **Table**: A table below the chart that shows the numbers used in the visualization.
1. **Settings and insights**: Several UI elements above the chart that allow you to customize the data returned.

[Screenshot of UI]

Guided analysis contains the following interface parts:

| Interface preview | UI Element | Description |
| --- | --- | --- |
| [Screenshot of query rail] | Query rail | Configure the desired components that make up a report. Different analysis types share several query options; if two analysis types share query options, they carry over when switching analysis types. See [Analysis types](analysis-types/overview.md) for more information around query options for each respective analysis type. |
| [Screenshot of chart] | Chart | A visualization of the data returned based on your input from the query rail and settings. Which visualization you see depends on the view type above the chart. Available view types depend on the [Analysis type](analysis-types/overview.md) above the query rail. |
| [Screenshot of table] | Table | A table representation of the data returned based on your input from the query rail and settings. Columns in the table depend on the view type above the chart. Available view types depend on the [Analysis type](analysis-types/overview.md) above the query rail. |
| [Screenshot of settings] | Settings | Several options above the chart that allow you to customize how the chart and table return data.<ul><li>**View type**: A drop-down selector that lets you present data for a given [Analysis type](analysis-types/overview.md) in a different way. Each analysis type has at least two view types.</li><li>**Chart settings**: Fine-tune what your chart looks like and which events you want it to use. Available options depend on the view type selected.</li><li>**Date range**: A calendar picker that allows you to determine the date range of the report. Some analysis types also allow intervals, such as daily, weekly, or monthly.</li><li>**Insights**: Provides contextual insights depending on the report that you view. You can show or hide these insights using the light bulb icon in the top right.</li></ul> |
| [Screenshot of analysis menu] | Analysis menu | Commands in the top-right of Guided analysis that provide overarching actions.<ul><li>**Data view selector**: Change the data view that this analysis uses. When you change the data view, available components in the query rail also change.</li><li>**Save**: Saves the analysis. If you're saving a new analysis, a modal window appears that requests a name and description.</li><li>**Save as**: Saves the analysis separately from the current analysis, creating a copy. A modal window appears that requests a new name and description.</li><li>**Open in Workspace**: Recreates the current Guided analysis in Analysis Workspace. The Workspace project is created in a new tab, preventing interruption while working within Guided analysis. Use this command when Guided analysis doesn't quite give you the flexibility or specific insight that you're looking for. For example, you want a [Trends](analysis-types/trends.md) report that uses Sessions for one segment, and People for another segment.</li><li>**Download PNG**: Downloads the chart graphic as a `.png`. The query rail and table are not included in the graphic.</li><li>**Download SVG**: Downloads the chart graphic as a `.svg`. The query rail and table are not included in the graphic.</li></ul> |

{style="table-layout:auto"}

## Permissions

Adobe plans to provide permissions specific to Guided analysis in the future.

<!-- Once your organization is provisioned to use Guided analysis, product profile administrators can grant access to it in the Adobe Admin Console.

1. Log in to the [Adobe admin console](https://adminconsole.adobe.com).
1. Select **[!UICONTROL Customer Journey Analytics]** in the list of products.
1. Select the desired product profile to edit permissions.
1. Click the **[!UICONTROL Permissions]** tab, then click **[!UICONTROL Edit]** under [!UICONTROL Reporting Tools].
1. Drag **[!UICONTROL Guided analysis]** from the list of [!UICONTROL Available Permission Items] to the list of [!UICONTROL Included Permission Items].
1. Click **[!UICONTROL Save]**. -->
