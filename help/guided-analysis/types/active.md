---
title: Active
description: Measure the growth of your user base.
exl-id: 0a300bb2-7620-4e29-a6b5-542476893009
feature: Guided Analysis
---
# Active

{{release-limited-testing}}

The **Active** view type provides insights around the growth and acquisition of users over a specific period. The horizontal axis is always a time granularity, while the vertical axis is always a measurement of users. Users are analyzed from the start of the date range, split into four categories:

* **New**: The user was active during the current data point, and has not appeared in any previous data points. Hover over '[!UICONTROL New users]' in the chart's legend to see how far the report looks back to determine a new user. This date is dynamically selected based on the date range's length and granularity.
* **Repeat**: The user appeared in the immediately previous data point and the current data point.
* **Return**: The user did not appear in the immediately previous data point, but is not a new user.
* **Dormant**: The user did not appear in the current data point, but appeared in the immediately previous data point. Dormant users do not count toward the total number of active users.

All active users (new + repeat + return) appear as a shade of teal above the horizontal axis, while all dormant users appear in orange below the horizontal axis.

Use cases for this view type include:

* **User retention and churn:** Provides a clear visualization around periods of high or low user retention. Recognizing these periods of high or low retention can help you make product decisions to encourage high retention or help minimize churn.
* **Campaign assessment**: Viewing a specific campaign can help you understand not only how much traffic it generated, but also how well the campaign helped users remain engaged.
* **User lifecycle analysis**: Analyzing active user growth throughout the user lifecycle can help identify specific stages where user engagement dips. For example, if there there is a high ratio of dormant users for those who are in an onboarding stage, it can indicate usability issues or a need for better in-product guidance.

[Screenshot of user growth]

## Query rail

The query rail allows you to configure the following components:

* **Events**: The event that you want to measure. Since this view type is user-based, a user can touch the event once within the set date granularity to be counted as an active user. You can include only one event in a query.
* **People**: The segment that you want to measure. You can include only one segment in a query.

## Chart settings

This view type offers the following chart settings. You can adjust the chart settings using the menu between the view type and calendar selector.

* **Metric**: The metric that you want to measure. Options include Number of users and Percentage of users.
* **Chart type**: The type of visualization that you want to use. Options include Stacked bar and Stacked area.

## Apply time comparison

{{apply-time-comparison}}

## Date range

The desired date range. There are two important components to this setting:

* **Interval**: The date granularity that you want to view data in. Valid options include Hourly, Daily, Weekly, Monthly, and Quarterly. The same date range can have different intervals which affect the number of data points in the chart and the number of columns in the table. For example, viewing an analysis spanning three days with daily granularity would show only three data points, while an analysis spanning three days with hourly granularity would show 72 data points.
* **Date**: The starting and ending date. Date range presets are available for your convenience, or you can use the calendar selector to set the exact desired date.
