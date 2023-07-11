---
title: Conversion trends
description: Track changes in conversion rate over time.
feature: Guided Analysis
---
# Conversion trends

{{release-limited-testing}}

The **Conversion trends** view type provides a trended visualization around conversion rates over time. The horizontal axis is always a date granularity, while the vertical axis represents conversion rate. Using this view type in conjunction with [Friction](friction.md) allows you to establish and refine the desired funnel. You can then use this view type to view conversion rates for that funnel over time. Use cases for this view type include:

* **Track optimization efforts**: After identifying key bottlenecks that you want to improve using [Friction](friction.md), you can use this view type to track how those optimizations impact conversion rate over time.
* **A/B testing evaluation**: Evaluate the effectiveness of A/B tests or experiments conducted within the context of a funnel. By comparing conversion rates between different variations, you can easily determine which tests provide higher conversion rates, leading to data-driven decisions around which variations to implement permanently.
* **Campaign evaluation over time**: Measure the effectiveness of marketing campaigns over time. You can create a segment that focuses on users that touched a given campaign, and compare their conversion rates with other campaigns. You can also compare current conversion rates with similar campaigns that were run in the past.

[Screenshot of funnel]

## Query rail

The query rail allows you to configure the following components:

* **Steps**: The event touch points that you want to track. Each bar in the chart represents a step. You can include up to ten steps.
* **People**: The segments that you want compare the funnel across. Each segment selected splits each step into multiple bars. Each color represents a different segment. You can include up to three segments.

## Chart settings

Funnel offers the following chart settings. You can adjust the chart settings using the menu between the view type and calendar selector.

* **Metric**: The metric that you want to measure. Options include Sessions and Users.
* **Chart type**: The type of visualization that you want to use. The only option is Line.
* **Conversion from**: Determines the percentage calculation from step to step. Options include calculating conversion from First step or Previous step.

## Apply time comparison

{{apply-time-comparison}}

## Date range

The desired date range. There are two important components to this setting:

* **Interval**: The date granularity that you want to view data in. Valid options include Hourly, Daily, Weekly, Monthly, and Quarterly. The same date range can have different intervals which affect the number of data points in the chart and the number of columns in the table. For example, viewing an analysis spanning three days with daily granularity would show only three data points, while an analysis spanning three days with hourly granularity would show 72 data points.
* **Date**: The starting and ending date. Date range presets are available for your convenience, or you can use the calendar selector to set the exact desired date.
