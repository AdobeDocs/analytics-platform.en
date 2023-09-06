---
title: First use view
description: Measure the impact of first-time feature use on key indicators.
feature: Guided Analysis
keywords: product analytics
---
# [!UICONTROL First use] view

The **[!UICONTROL First use]** view shows a comparison of how key indicators performed before and after a user uses a product feature for the first time. The horizontal axis of this report is a relative time interval before and after the event, while the vertical axis measures the desired key indicators. A vertical bar in the middle of the chart represents day 0 for when a feature is first used by a given user. Because users do not always adopt features on the same day and your rollouts may happen over several days, day 0 will mean something different for each individual user.

>[!VIDEO](https://video.tv.adobe.com/v/3421661/?learn=on)

## Use cases

Use cases for this view type include:

* **New feature analysis**: If you're launching a new feature within your product, you can compare how key indicators performed before and after users were exposed to that new feature for the first time. 
* **Phased rollouts**: Because the analysis looks for first use of the feature rather than a fixed date, this view is particularly helpful if you phase rollout your features over a period of time.
* **New product version analysis**: If you're launching a new version of your product, you can compare how key indicators performed before and after users were exposed to that new version for the first time. Select "any event" as your first-use event and filter it to your Version number property.
* **Existing feature improvements**: If you're making improvements to an existing feature within your product, you can compare how key indicators performed before and after users were exposed to those new improvements for the first time. You can accomplish this analysis in a few ways depending on your feature instrumentation. 1) Select an event that represents the improvement as your first-use event, and/or 2) Select the date when the changes started to rollout, and/or 3) Segment the analysis to the group of people exposed to the improvements. 
* **Campaign effectiveness**: When a user clicksthrough from a given campaign, you can compare how key indicators performed before and after the user interacted with that campaign.

## Query rail

The query rail allows you to configure the following components:

* **[!UICONTROL Key indicators]**: The events that you want to measure per user. Each selected key indicator is represented as a colored line. A row representing the event is added to the table. You can include up to three events.
* **[!UICONTROL Factors]**: There are two factors for this view:
  * **[!UICONTROL Date]**: How far back you want to start looking for the first time use event to have occurred.
  * **[!UICONTROL Event]**: The event that you want to look for first use of, to center the analysis on. 
* **[!UICONTROL People]**: The segment that you want to measure. The selected segment filters your data to focus only on the individuals who match your segment criteria.

## Chart settings

The First use view offers the following chart settings, which can be adjusted in the menu above the chart:

* **[!UICONTROL Metric]**: The metric that you want to measure. Options include [!UICONTROL Events per user], [!UICONTROL Events], [!UICONTROL Sessions], and [!UICONTROL Users].
* **[!UICONTROL Chart type]**: The type of visualization that you want to use. Options include Line.

## Date range

Date selections in Impact analysis operates differently than other analysis types, since the analysis revolves around the date specified in the query rail. The following options are available:

* **[!UICONTROL Interval]**: The date granularity that you want to view trended data by. Valid options include [!UICONTROL Daily], [!UICONTROL Weekly], [!UICONTROL Monthly], and [!UICONTROL Quarterly]. Changing the interval affects the options available for the Before and after period.
* **[!UICONTROL Before and after period]**: The amount of time to analyze before and after the first use event specified in the query rail. Available options depend on the [!UICONTROL Interval] selection.
