---
title: Trends
description: Find patterns and changes in user engagement over time.
---
# Trends

{{release-limited-testing}}

The **Trends** [Analysis type](overview.md) provides valuable insight around the performance of your product or behavior of your users over time. The horizontal axis of this report is always a time granularity, while the vertical axis measures your desired events. Use cases for this analysis type include:

* **Evaluate product performance**: Trends allow you to assess the overall performance of your product over a given period. By analyzing metrics such as user engagement, conversion rates, or revenue, you can identify if the performance of your product is improving, stagnating, or declining.
* **Feature adoption**: Trends allow you to understand how users adopt new features or updates that you release. You can determine which features are popular and which features require improvement. This information allows you to make data-driven decisions around what features to prioritize your development efforts around.
* **User behavior**: Trends can provide insight into user behavior over time. By examining specific actions that users take, you can identify patterns where users might drop off. You can combine insights from this analysis type with a [Funnel](funnel.md) for even more insight around behavior.
* **A/B testing and experimentation**: If you run A/B tests within your product, you can use Trends to gauge which tests are the most successful over time.

[Screenshot of trends]

## Query rail

The query rail allows you to configure the following components:

* **Events**: Sets the events that you want to measure in your report. Each event selected here is represented as a colored line or set of bars, depending on chart type. A row representing the trended event is added to the table. Up to five events are supported.
* **People**: Sets the segments that you want to measure in your report. Each segment selected here doubles the number of lines in the chart and rows in the table. Each set of events is represented for each segment. Up to five segments are supported.

## View types

Trends offer the following view types. You can change the view type using the drop-down menu in the top-left of the chart.

* **Usage:** Measure user engagement over time.

## Chart settings

Trends offer the following chart settings. You can adjust the chart settings using the menu between the view type and calendar selector.

* **Metric**: Sets the metric that you want to measure. Options include Events, Sessions, Users, Events per session, and Events per user.
* **Chart type**: Sets the type of visualization that you want to use. Options include Line, Bar, Stacked bar, and Stacked area.

## Apply time comparison

Trends offer the ability to compare the current time period to a previous time period. If you select an option in this menu, every line receives a similarly colored dotted line. This dotted line represents that same metric in the selected previous date range. Setting this option doubles the number of lines in the chart and rows in the table.

Available time comparison options include the previous period, 13 weeks prior, 52 weeks prior, and a Customized date range. If you select Customized date range, additional options appear to let you select the number and granularity. If you select None, the date comparison is removed.

## Date range

Sets the desired date range. There are two important components to this setting:

* **Interval**: The date granularity that you want to view data in. Valid options include Hourly, Daily, Weekly, Monthly, and Quarterly. The same date range can have different intervals which affect the number of data points in the chart and the number of columns in the table. For example, viewing a report spanning three days with daily granularity would show only three data points, while a report spanning three days with hourly granularity would show 72 data points.
* **Date**: The starting and ending date of the project. Date range presets are available for your convenience, or you can use the calendar selector to set the exact desired date.
