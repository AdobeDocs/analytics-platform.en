---
title: Guided analysis interface
description: Learn about the overall structure of the Guided analysis project UI.
---
# Guide Analysis interface

{{release-limited-testing}}

The interface for a Guided Analysis project, regardless of analysis type, comprises the following main UI elements:

* **Query rail**: Use this rail on the left of your project to build out your analysis.
* **Chart**: Once you select the desired events, people, or steps, a chart is shown on the right that visualizes the data.
* **Table**: A table below the chart that shows the numbers used in the visualization.
* **Settings and insights**: Several UI elements above the chart that allow you to customize the data returned.

[Screenshot of UI]

## Query rail

[Screenshot of query rail]

The query rail is where you configure the desired components that make up a report. Different analysis types share several query options; if two analysis types share query options, they carry over when switching analysis types. See [Analysis types](analysis-types/overview.md) for more information around query options for each respective analysis type.

## Chart

[Screenshot of chart]

A visualization of the data returned based on your input from the query rail and settings. Which visualization you see depends on the view type above the chart. Available view types depend on the [Analysis type](analysis-types/overview.md) above the query rail.

## Table

[Screenshot of table]

A table representation of the data returned based on your input from the query rail and settings. Columns in the table depend on the view type above the chart. Available view types depend on the [Analysis type](analysis-types/overview.md) above the query rail.

## Settings

[Screenshot of settings]

Several options above the chart that allow you to customize how the chart and table return data.

* **View type**: A drop-down selector that lets you present data for a given [Analysis type](analysis-types/overview.md) in a different way. Each analysis type has at least two view types.
* **Chart settings**: Fine-tune what your chart looks like and which events you want it to use. Available options depend on the view type selected.
* **Date range**: A calendar picker that allows you to determine the date range of the report. Some analysis types also allow intervals, such as daily, weekly, or monthly.
* **Insights**: Provides contextual insights depending on the report that you view. You can show or hide these insights using the light bulb icon in the top right.

## Project menu

[Screenshot of project menu]

Commands in the top-right of the project that provide overarching actions.

* **Data view selector**: Change the data view that this project uses. When you change the data view, available components in the query rail also change.
* **Save**: Saves the project. If you're saving a new project, a modal window appears that requests a name and description.
* **Save as**: Saves the project separately from the current project, creating a copy. A modal window appears that requests a new name and description.
* **Open in Workspace**: Recreates the current Guided analysis project in Analysis Workspace. The workspace project is created in a new tab, preventing interruption while working on your Guided analysis project. Use this command when Guided Analysis doesn't quite give you the flexibility or specific insight that you're looking for. For example, you want a [Trends](analysis-types/trends.md) report that uses Sessions for one segment, and People for another segment.
* **Download PNG**: Downloads the chart graphic as a `.png`. The query rail and table are not included in the graphic.
* **Download SVG**: Downloads the chart graphic as a `.svg`. The query rail and table are not included in the graphic.
