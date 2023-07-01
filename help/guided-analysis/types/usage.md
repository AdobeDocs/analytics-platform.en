---
title: Usage (Trends)
description: Measure user engagement over time.
exl-id: 1d103bd3-3e72-4c82-a534-c896f8433029
---
# Usage (Trends)

{{release-limited-testing}}

The **Usage** [View type](overview.md) provides valuable insight around the performance of your product or behavior of your users over time. The horizontal axis of this report is always a time granularity, while the vertical axis measures your desired events. Use cases for this view type include:

* **Evaluate product performance**: Trends allow you to assess the overall performance of your product over a given period. By analyzing metrics such as user engagement, conversion rates, or revenue, you can identify if the performance of your product is improving, stagnating, or declining.
* **Feature adoption**: Trends allow you to understand how users adopt new features or updates that you release. You can determine which features are popular and which features require improvement. This information allows you to make data-driven decisions around what features to prioritize your development efforts around.
* **User behavior**: Trends can provide insight into user behavior over time. By examining specific actions that users take, you can identify patterns where users might drop off. You can combine insights from this view type with [Friction](friction.md) for even more insight around behavior.
* **A/B testing and experimentation**: If you run A/B tests within your product, you can use Trends to gauge which tests are the most successful over time.

[Screenshot of trends]

## Query rail

The query rail allows you to configure the following components:

* **Events**: The events that you want to measure in your report. Each event selected here is represented as a colored line or set of bars, depending on chart type. A row representing the trended event is added to the table. You can incldue up to five events.
* **People**: The segments that you want to measure in your report. Each segment selected here doubles the number of lines in the chart and rows in the table. Each set of events is represented for each segment. You can include up to five segments.

## Chart settings

Trends offer the following chart settings. You can adjust the chart settings using the menu between the view type and calendar selector.

* **Metric**: The metric that you want to measure. Options include Events, Sessions, Users, Events per session, and Events per user.
* **Chart type**: The type of visualization that you want to use. Options include Line, Bar, Stacked bar, and Stacked area.

## Apply time comparison

{{apply-time-comparison}}

## Date range

Sets the desired date range. There are two important components to this setting:

* **Interval**: The date granularity that you want to view data in. Valid options include Hourly, Daily, Weekly, Monthly, and Quarterly. The same date range can have different intervals which affect the number of data points in the chart and the number of columns in the table. For example, viewing an analysis spanning three days with daily granularity would show only three data points, while an analysis spanning three days with hourly granularity would show 72 data points.
* **Date**: The starting and ending date. Date range presets are available for your convenience, or you can use the calendar selector to set the exact desired date.
