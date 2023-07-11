---
title: Net growth
description: Balance user gains and losses.
feature: Guided Analysis
---
# Net growth

{{release-limited-testing}}

The **Net growth** view type provides insights around the rate at which you acquire or lose users over a specific period. The horizontal axis is always a time granularity, while the vertical axis is always the measurement of growth.

Each data point represent's that data point's net growth, which is calculated using the following formula:

`([New users] + [Return users]) / [Dormant users]`

Similar to the [Active](active.md) view type, users are defined as the following:

* **New**: The user was active during the current data point, and has not appeared in any previous data points.
* **Return**: The user did not appear in the immediately previous data point, but is not a new user.
* **Dormant**: The user did not appear in the current data point, but appeared in the immediately previous data point. Dormant users do not count toward the total number of active users.

**Repeat** users are not factored in to this calculation, as they do not represent any growth or loss.

The result of this formula is a ratio at which your user base grew or shrunk during that data point. A net growth of `1` represents an equalibrium; the product gained the same number of users it lost. A net growth greater than `1` represents positive growth; there were more new/return users than dormant users. Likewise, a net growth less than `1` represents a loss of active users; there were more dormant users than new/return users.

Use cases for this view type include:

* **User acquisition analysis**: Allows you to assess the effectiveness of your user acquisition strategies. Analyzing the sources of user growth, such as search engines, campaigns, or other marketing channels, allows you to identify the most significant sources of growth so you can allocate resources accordingly.
* **Performance evaluation**: Allows you to assess the overall performance of your product in terms of acquiring new users. By tracking growth trends, you can better understand if your product is attracting and retaining users at a desired pace.
* **Churn analysis**: Net growth takes includes attrition in its formula (dormant users). You can assess the overall health of your user base over time. If net growth is consistently below `1`, it indications a high amount of attrition, prompting you to investigate reasons behind it and implement retention strategies.

[Screenshot of user growth]

## Query rail

The query rail allows you to configure the following components:

* **Events**: The event that you want to measure. Since this view type is user-based, a user can touch the event once within the set date granularity to be in the net growth. You can include only one event in a query.
* **People**: The segment that you want to measure. You can include only one segment in a query.

## Date range

The desired date range. There are two important components to this setting:

* **Interval**: The date granularity that you want to view data in. Valid options include Daily, Weekly, Monthly, and Quarterly. The same date range can have different intervals which affect the number of data points in the chart and the number of columns in the table. For example, viewing an analysis spanning three days with daily granularity would show only three data points, while an analysis spanning three days with hourly granularity would show 72 data points.
* **Date**: The starting and ending date. Date range presets are available for your convenience, or you can use the calendar selector to set the exact desired date.
