---
title: Friction
description: Compare conversion rates between steps.
exl-id: f0ba3f00-bf1f-48db-8b6e-137460abf4f8
feature: Guided Analysis
---
# Friction

{{release-limited-testing}}

The **Friction** view type provides a visual representation of a critical user journey in your product. The horizontal axis represents each event that a user must touch in order. The vertical axis represents the percentage of users or sessions that touched each event. All touchpoints must be done in eventual order, but can happen at any time within the reporting window. Use cases for this view type include:

* **Conversion analysis**: You can analyze conversions at each stage of the funnel. By tracking the number of users who progress from one step to the next, you can identify bottlenecks that have unusual or undesired conversion rates. This information is valuable to understand where you can improve your product for immediate results.
* **Onboarding optimization**: Optimize your product's onboarding process by examining user behavior around key events. You can identify which steps that users struggle with or fail to complete.
* **Feature adoption and engagement**: Understand how users interact with specific features in your product. By analyzing the progression of users through feature-related steps, you can assess feature adoption rates and identify areas where users might abandon or underuse certain features. You can then use this information to focus on feature or UI improvements to increase adoption rates.
* **Campaign evaluation**: Measure the effectiveness of marketing campaigns. You can create a segment that focuses on users that touched a given campaign, and compare their conversion process with other campaigns or within your product overall.

[Screenshot of funnel]

## Query rail

The query rail allows you to configure the following components:

* **Steps**: The event touch points that you want to track. Each bar in the chart represents a step. You can include up to ten steps.
* **People**: The segments that you want compare the funnel across. Each segment selected splits each step into multiple bars. Each color represents a different segment. You can include up to three segments.

## Chart settings

Funnel offers the following chart settings. You can adjust the chart settings using the menu between the view type and calendar selector.

* **Metric**: The metric that you want to measure. Options include Sessions and Users.
* **Chart type**: The type of visualization that you want to use. The only option is Steps.
* **Conversion from**: Determines the percentage calculation from step to step. Options include calculating conversion from First step or Previous step.

## Apply time comparison

{{apply-time-comparison}}

## Date range

The starting and ending date. Date range presets are available for your convenience, or you can use the calendar selector to set the exact desired date.
