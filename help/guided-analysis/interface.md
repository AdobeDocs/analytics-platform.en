---
title:
description:
---
# Guide Analysis interface

The interface for a Guided Analysis project, regardless of analysis type, comprises of the following main UI elements:

* **Query rail**: Use this rail on the left of your project to build out your analysis.
* **Chart**: Once you select the desired events, people, or steps, a chart is shown on the right that visualizes the data.
* **Table**: A table below the chart that shows the numbers used in the visualization.
* **Settings and insights**: Several UI elements above the chart that allow you to customize the data returned.

[Screenshot of UI]

## Query rail

[Screenshot of query rail]

The query rail is where you configure the desired components that make up a report. Different analysis types share several query options; if two analysis types share the same query options, they carry over when switching analysis types. See [Analysis types](analysis-types/overview.md) for more information around query options for each respective analysis type.

## Chart

[Screenshot of chart]

A visualization of the data returned based on your input from the query rail and settings. Which visualization you see is dependent on the view type above the chart. Available view types depend on the [Analysis type](analysis-types/overview.md) above the query rail.

## Table

[Screenshot of table]

A table representation of the data returned based on your input from the query rail and settings. Columns in the table depend on the view type above the chart. Available view types depend on the [Analysis type](analysis-types/overview.md) above the query rail.

## Settings

[Screenshot of settings]

Several options above the chart that allow you to customize how the chart and table return data.

* **View type**: A drop-down selector that lets you present data for a given [Analysis type](analysis-types/overview.md) in a different way. Each analysis type has at least two view types.
* **Chart settings**: Fine-tune what your chart looks like and which events you want it to use. Available options depend on the view type selected.
* **Date range**: A calendar picker that allows you to determine the date range of the report. Some analysis types also allow interval
