---
title: Retention rates
description: Measure how many users continue to use your product.
feature: Adobe Product Analytics, Guided Analysis
keywords: product analytics
exl-id: c35a0ee0-e6b7-47b5-a5bc-308cde1585de
role: User
---
# Retention rates

The **[!UICONTROL Retention rates]** view shows users repeat usage behavior in your product over time, which can help you understand your product market fit. In this view, the horizontal axis represents the number of days since a user's initial engagement and the vertical axis represents the percentage of users who engage again.

This analysis counts users based on two important events:

* Start event: The first time a user engaged with the event within the date range
* Return event: The most recent time a user engaged with the event within the analyzed date range

The "Day 0" duration bucket represents the initial time that a user engaged with the event, and always equals exactly 100%. This bucket is the denominator used to calculate the percentage of users retained.

Subsequent duration buckets count the number of users who returned on or after that duration. This count is the numerator used to calculate the percentage of users retained.

* If a user engages with the event only once during the desired date range (the initial engagement), they only appear in the "Day 0" duration bucket.
* If a user engages with the event multiple days after initially qualifying for inclusion in the analysis, they appear in the latest qualifying duration bucket and all duration buckets leading up to it. This type of calculation is sometimes referred to as "unbounded retention." You can change this calculation setting in the query rail.

Users that qualify for duration buckets are based on time elapsed, not calendar day. For example, if a user qualifies for an event at 11:55 PM on September 6, then qualifies for a return event at 12:05 AM on September 7, they would not appear in the 1-day duration bucket. A full 24 hours must elapse before the user qualifies for the 1-day duration bucket.

![Retention rates screenshot](../assets/retention-rates.png){style="border:1px solid gray"}

## Use cases

Use cases for this view type include:

* **Cohort analysis**: Group users into cohorts based on actions that they take, such as sign-ups or purchases. You can compare how well these groups retain and determine how to approach improving each group's user experience.
* **Product market fit**: Measure regular usage of your product and visualize as retention curves. Greater retention signifies greater product market fit, and where your curve flattens out indicates how long it takes to reach your fit. View this analysis at an overall level or breakdown by individual product features to get deeper insights.
* **Subscription service analysis**: If your product employs a subscription or another type of recurring revenue model, you can see the percentage of users that are making the most of your product. You can identify certain qualities and behaviors that these users exhibit.
* **User engagement**: Evaluate how certain types of users engage with your product, and compare side by side how often they return. A given segment with lower retention than others can provide you with insight into improving potential subpar experiences that they might have.

## Query rail

The query rail allows you to configure the following components:

* **[!UICONTROL Start event]**: The event criteria that a user must engage with to qualify for inclusion in your analysis. Users who engage with the start event are included in the initial bucket of users that totals to 100%. One event is supported, but you can include property filters. You can link the start and return events together using the three-dot menu. Linking the start and return events mean that the criteria to appear in the initial duration bucket and subsequent duration buckets are the same.
* **[!UICONTROL Return events]**: The event criteria that a user must engage with to qualify for inclusion in subsequent duration buckets. You can select up to three return events. Each return event generates a side-by-side analysis with the other included return events.
* **[!UICONTROL Counted as]**: The counting method that you want to apply to retained users. Options include:
  * **[!UICONTROL Metric]**: Count the number of [!UICONTROL Users retained] or the [!UICONTROL Percentage of users retained].
  * **[!UICONTROL Returning]**: By default, this analysis includes users in the bucket that they returned and all preceding buckets. Change this setting to **[!UICONTROL On exactly]** to include users in only the exact bucket that they qualify for.
  * **[!UICONTROL Each]**: The time period that you want each duration bucket to be. This setting is identical to the **[!UICONTROL Interval]** setting when selecting the date range.
  * **[!UICONTROL Duration settings]**: Allows you to control how the analysis displays users by the number of days elapsed. Available duration buckets depend on the date range that you set. **[!UICONTROL Auto durations]** automatically set duration buckets based on the date range length and how close to the current day that the date range is. **[!UICONTROL Custom durations]** allow you to set four duration buckets at desired intervals manually.
* **[!UICONTROL Segments]**: The segments that you want to measure. Each selected segment adds a row to the cohort table. You can include up to three segments.

## Chart settings

The [!UICONTROL Retention rates] view offers the following chart settings, which can be adjusted in the menu above the chart:

* **[!UICONTROL Chart type]**: The type of visualization that you want to use. Options include [!UICONTROL Bar] and [!UICONTROL Line]. The line visualization shows Day 0 visually in the chart.

## Date range

The desired date range for your analysis. There are two components to this setting:

* **[!UICONTROL Interval]**: The date granularity by which you want to view retention data. Valid options include Daily, Weekly, and Monthly. The same date range can have different intervals, which impact duration bucket options.
* **[!UICONTROL Date]**: The starting and ending date. Rolling date range presets and previously saved custom ranges are available for your convenience, or you can use the calendar selector to choose a fixed date range.

If you select a date range close to the present day, users that initially engage too close to the current day are not included. This analysis always gives all users the chance to be included in all duration buckets. A message below the calendar picker provides information about the date range where users engage, and the interval that is reserved only for returning users:

* **[!UICONTROL Analyzing users who did the start event in [Date interval]]**: If a user engages with the event within this date range, they are included in the analysis. This date range guarantees all users enough time to qualify for all duration buckets. This date range can be different than your selection if it is close to the present day.
* **[!UICONTROL Data from [Date interval] is reserved to complete the analysis]**: If a user engages for the first time within this period, they are **not** included in the analysis. For recent date ranges, these users would not have an opportunity to qualify for all duration buckets. For past date ranges, these users were active outside of the selected date range.

## Cohort table

The table below the chart provides an aggregate view (similar to chart data), and a full cohort table. The full cohort table provides details of each individual date interval and when users engaged.
