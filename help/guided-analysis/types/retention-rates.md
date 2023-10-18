---
title: Retention rates
description: Measure how many users continue to use your product.
feature: Guided Analysis
keywords: product analytics
---
# Retention rates

The **[!UICONTROL Retention rates]** view shows the percentage of users that return after their initial engagement within the desired date range. The horizontal axis represents the number of days since a user's first engagement. The vertical axis represents the percentage of users who engage again.

This analysis counts users based on two important events:

* The first time a user engaged with the event within the date range
* The most recent time a user engaged with the event within the analyzed date range

The "day 0" duration bucket represents the first time that a user engages with the event, and always equals exactly 100%. The amount of time that passes between the initial engagement and the return engagement determines where that the user appears under.

* If a user engages with the event only once during the desired date range (the initial engagement), they only appear in the "day 0" duration bucket.
* If a user engages with the event multiple days after initially qualifying for inclusion in the analysis, they appear in the latest qualifying duration bucket and all duration buckets leading up to it.
* If a user engages with the event many times during the configured date range, only the first and last events are included in the analysis.

## Use cases

Use cases for this view type include:

* **Cohort analysis**: Group users into cohorts based on any event, such as sign-ups or purchases. You can compare the stickiness of these groups and determine how to approach improving that group's user experience.
* **Subscription service analysis**: If your product employs a subscription or another type of recurring revenue model, you can see the percentage of users that are making the most of your product. Those who do not use your product or service are more likely to churn, allowing you a way to identify and focus on those users.
* **User engagement**: Evaluate how certain types of users engage with your product, and compare side by side how often they return. A given segment with a steeper retention curve than others can provide you with insight around improving potential subpar experiences that they might have.

## Query rail

The query rail allows you to configure the following components:

* **[!UICONTROL Start & return event]**: The event criteria that a user must engage with to qualify for inclusion in your analysis. One event is supported, but you can include property filters.
* **[!UICONTROL People]**: The segments that you want to measure. Each selected segment adds a row to the cohort table. You can include up to three segments.

## Chart settings

The [!UICONTROL Retention rates] view offers the following chart settings, which can be adjusted in the menu above the chart:

* **[!UICONTROL Metric]**: How you want to measure users retained. Options include [!UICONTROL Users retained] and [!UICONTROL Percentage of users retained].
* **[!UICONTROL Chart type]**: The type of visualization that you want to use. Options include [!UICONTROL Bar] and [!UICONTROL Line].

## Duration settings

Allows you to control how the analysis displays users by the number of days elapsed.

* **[!UICONTROL Auto durations]**: Automatically set durations based on the date range length and how close to the current day that the date range is.
* **[!UICONTROL Custom durations]**: Manually set the desired elapsed days. You can set four durations.

You cannot set a duration for longer than the time it takes for a user to engage with an event and qualify for the last duration bucket before reaching the present day. For example, if the current date is September 30 and your configured date range is September 1 - September 30, the maximum duration for this date range is 14 days. 

## Date range

The desired date range for your analysis. There are two components to this setting:

* **[!UICONTROL Interval]**: The date granularity that you want to view retention data. Valid options include Daily, Weekly, Monthly, and Quarterly. The same date range can have different intervals, which affect automatically set duration days.
* **[!UICONTROL Date]**: The starting and ending date. Rolling date range presets and previously saved custom ranges are available for your convenience, or you can use the calendar selector to choose a fixed date range.

If you select a date range close to the present day, users that initially engage too close to the current day are not included. This analysis always gives all users the chance to be included in all duration buckets. A message below the calendar picker provides information around the date range where users engage, and the interval that is reserved only for returning users:

* **Analyzing the first [Date interval] of the cohort from [Date range]**: If a user engages with the event within this date range, they are included in the analysis. This date range guarantees all users enough time to qualify for all duration buckets. This date range can be different than your selection if it is close to the present day.
* **The final [Date interval] is reserved to complete the analysis**: If a user engages with the event for the first time within this interval, they are **not** included in the analysis. Users that initially engage with the event within this interval would not have an opportunity to qualify for all duration buckets, or are outside of the desired date range.

## Cohort table

The table below the chart provides an aggregate view (similar to chart data), and a full cohort table. The full cohort table provides details around each individual date interval and when users engaged.
