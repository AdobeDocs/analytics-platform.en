---
title: Funnel
description: Identify areas of friction across a sequence of steps.
---
# Funnel

{{release-limited-testing}}

The **Funnel** [Analysis type](overview.md) provides a visual representation of a user journey or conversion process in your product. The horizontal axis represents each event that a user must touch in order. The vertical axis represents the percentage of users that touched each event. All touchpoints must be done in order, but can happen at any time within the reporting window. Use cases for this analysis type include:

* **Conversion analysis**: Funnel allows you to analyze conversions at each stage of the funnel. By tracking the number of users who progress from one step to the next, you can identify bottlenecks that have unusual or undesired conversion rates. This information is valuable to understand where you can improve your product for immediate results.
* **Onboarding optimization**: Funnel is helpful to help optimize your product's onboarding process. By examining user behavior around key events, you can identify which steps that users struggle with or fail to complete.
* **Feature adoption and engagement**: Funnel helps you understand how users interact with specific features in your product. By analyzing the progression of users through feature-related steps, you can assess feature adoption rates and identify areas where users might abandon or underuse certain features. You can then use this information to focus on feature or UI improvements to increase adoption rates.
* **Campaign evaluation**: Funnel can help measure the effectiveness of marketing campaigns. You can create a segment that focuses on users that touched a given campaign, and compare their conversion process with other campaigns or within your product overall.

[Screenshot of funnel]

## Query rail

The query rail allows you to configure the following components:

* **Steps**: The event touch points that you want to track. Each bar in the chart represents a step. You can include up to 10 steps in a report.
* **People**: Sets the segments that you want to measure in your report. Each segment selected here splits each step into multiple bars. Each color represents a different segment. Up to 3 segments are supported.

## View types

Funnel offers the following view types. You can change the view type using the drop-down menu in the top-left of the chart.

* **Friction**: Compare conversion rates between steps.

## Chart settings

Funnel offers the following chart settings. You can make adjustments to the chart settings using the menu between the view type and calendar selector.

* **Metric**: Sets the metric that you want to measure. Options include Sessions and Users.
* **Chart type**: Sets the type of visualization that you want to use. The only option is currently Steps.
* **Conversion from**: Determines the percentage calculation from step to step. Options include First step and Previous step.

## Date range

The starting and ending date of the project. Date range presets are available for your convenience, or you can use the calendar selector to set the exact desired date. Date intervals are not available for this analysis type.
