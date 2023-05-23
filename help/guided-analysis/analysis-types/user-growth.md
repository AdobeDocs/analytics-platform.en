---
title: User growth
description: Track the growth of your product's user base.
---
# User growth

{{release-limited-testing}}

The **User growth** [Analysis type](overview.md) provides insights around the growth and acquisition of users over a specific period. The horizontal axis is always a time granularity, while the vertical axis is always a measurement of users. Users are analyzed from the start of the date range, split into four categories:

* **New**: It is the user's first time appearing in the specified date range. The first data point in a report is always 100% new users, since the report does not look at dates outside of the reporting range.
* **Repeat**: The user appeared in the immediately previous data point and the current data point.
* **Return**: The user did not appear in the immediately previous data point, but is not a new user. Return users cannot appear in the first or second data points, as they must first appear as a new user then a dormant user.
* **Dormant**: The user did not appear in the current data point, but appeared in the immediately previous data point. Dormant users do not count toward the total number of active users.

All active users (new + repeat + return) appear as a shade of teal above the horizontal axis, while all dormant users appear in orange below the horizontal axis.

Use cases for this analysis type include:

* **Performance evaluation**: User growth allows you to assess the overall performance of your product in terms of acquiring new users. By tracking growth trends, you can better understand if your product is attracting and retaining users at a desired pace.
* **User retention and churn:** This report provides a clear visualization around periods of high or low user retention. Recognizing these periods of high or low retention can help you make product decisions to encourage high retention or help minimize churn.
* **Campaign assessment**: Viewing a user growth report specific to a specific campaign can help you understand not only how much traffic it generated, but also how well the campaign helped users remain engaged.

[Screenshot of user growth]

## Query rail

The query rail allows you to configure the following components:

* **Events**: Sets the event that you want to measure in your report. Since this report is user-based, a user can touch the event once within the set date granularity to be counted as an active user. Only one event is supported.
* **People**: Sets the segment that you want to measure in your report. Only one segment is supported.

## View types

User growth offers the following view types. You can change the view type using the drop-down menu in the top-left of the chart.

* **Active:** Measure the growth of your user base.

## Chart settings

User growth offers the following chart settings. You can adjust the chart settings using the menu between the view type and calendar selector.

* **Metric**: Sets the metric that you want to measure. Options include Number of users and Percentage of users.
* **Chart type**: Sets the type of visualization that you want to use. Options include Stacked bar and Stacked area.

## Date range

Sets the desired date range. There are two important components to this setting:

* **Interval**: The date granularity that you want to view data in. Valid options include Hourly, Daily, Weekly, Monthly, and Quarterly. The same date range can have different intervals which affect the number of data points in the chart and the number of columns in the table. For example, viewing a report spanning three days with daily granularity would show only three data points, while a report spanning three days with hourly granularity would show 72 data points.
* **Date**: The starting and ending date of the project. Date range presets are available for your convenience, or you can use the calendar selector to set the exact desired date.
