---
title: Retention analysis
description: Measure how many users continue to use your product.
feature: Adobe Product Analytics, Guided Analysis
keywords: product analytics
exl-id: c35a0ee0-e6b7-47b5-a5bc-308cde1585de
role: User
---
# Retention analysis {#retention}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_retention_button"
>title="Retention"
>abstract="Measure how many users continue to use your product."

<!-- markdownlint-enable MD034 -->

The ![Retention](/help/assets/icons/Retention.svg) **[!UICONTROL Retention]** analysis measures how users continue to use your product over time, which can help you understand your product market fit. The analysis counts users based on two important events:

* Start event: The event used to qualify users for inclusion in your analysis. 
* Return event: One or more events that a user must engage with to count as a returning user in your analysis.

In this analysis, the chart's x-axis represents the time since a user's initial start event and the y-axis represents the percentage of users who engage with one or more return events. You can view both retention and churn across durations, and the durations shown can be customized through the query settings. Below the chart, a table provides aggregated data with the option to show individual cohorts, which are a group of people who did the starting event on the same date. 

>[!VIDEO](https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/guided-analysis/retention)


## Use cases

Use cases for this analysis include:

* **Cohort analysis**: Group users into cohorts based on actions that they take, such as sign-ups or purchases. You can compare how well these groups retain and determine how to approach improving each group's user experience.
* **Product market fit**: Measure regular usage of your product and visualize as retention curves. Greater retention signifies greater product market fit, and where your curve flattens out indicates how long it takes to reach your fit. View this analysis at an overall level or breakdown by individual product features to get deeper insights.
* **Subscription service analysis**: If your product employs a subscription or another type of recurring revenue model, you can see the percentage of users that are making the most of your product. You can identify certain qualities and behaviors that these users exhibit.
* **User engagement**: Evaluate how certain types of users engage with your product, and compare side by side how often they return. A given segment with lower retention than others can provide you with insight into improving potential subpar experiences that they might have.

## Interface

See [Interface](../overview.md#interface) for an overview of the Guided analysis interface. The following settings are specific to this analysis:

### Query rail

The query rail allows you to configure the following components:

* **[!UICONTROL Start event]**: The event criteria that a user must engage with to qualify for inclusion in your analysis. Users who engage with the start event are counted in the "Users" column of the table. This event serves as the denominator for retention rates shown. One event is supported, and property filters can be applied as needed. By default, the start and return event are linked, meaning a user must do the selected event once to be included in the cohort, and then again to be counted as a returning user. Under the More menu, you can unlink the start and return events if you want the returning action to be different from the inclusion action. 
* **[!UICONTROL Return events]**: The event criteria that a user must engage with to count as a returning users in the duration buckets. You can select up to three return events to compare retention across.
* **[!UICONTROL Counted as]**: The counting method that you want to apply to retained users. Options include:
  * **[!UICONTROL Metric]**: Show the number of [!UICONTROL Users] or the [!UICONTROL Percentage of users] retained. The denominator for percentage users retained is the included users for the cohort and is the same across all duration buckets.
  * **[!UICONTROL Returning]**: Allows you to control how returning users are counted. Options include:
    * **[!UICONTROL On or after]**: Often referred to as "unbounded" retention, this option counts a user if they return on or after the specified duration. For example, on day 7 or anytime after day 7. This option is helpful for showing how users continue to engage and generates a smoother retention curve as a result. 
    * **[!UICONTROL On exactly]**: Often referred to as "bounded" retention, this option counts a user if they return on the specified duration exactly. For example, on day 7 exactly. This option is helpful for showing how users return within specific timeframes and generates a retention curve with more undulation as a result. Note: The cohort analysis in Analysis Workspace uses "on exactly" counting as the basis for its analysis.
  * **[!UICONTROL Each]**: The time period that you want each duration bucket to be. Options include:
    * **[!UICONTROL Day/Week/Month]**: Options available are dependent on the date range selected. These options are identical to the **[!UICONTROL Interval]** setting when selecting the date range and updates that setting automatically.
    * **[!UICONTROL Custom brackets]**: This option is available for the "On each" setting only. It allows you to count users across a larger timeframe; for example, Day 7-10, instead of only Day 7.
  * **[!UICONTROL Duration settings]**: Allows you to control the duration buckets displayed on the chart and table. A duration is the period of time after the start event that the return event has occurred. Note: Users that qualify for duration buckets are based on time elapsed, not calendar days. For example, if a user qualifies for an event at 11:55 PM on September 6, then qualifies for a return event at 12:05 AM on September 7, they would not appear in the 1-day duration bucket. A full 24 hours must elapse before the user qualifies for the 1-day duration bucket. Available duration buckets depend on the date range that you set. 
    * **[!UICONTROL Auto durations]** automatically defines the duration buckets based on the date range length and how close to the current day that the date range is. 
    * **[!UICONTROL Custom durations]** allow you to customize the four duration buckets displayed on the chart and table.
* **[!UICONTROL Segments]**: The segments that you want to measure. Each selected segment adds a row to the cohort table. You can include up to three segments.

### Chart settings

The [!UICONTROL Retention] analysis offers the following chart settings, which can be adjusted in the menu above the chart:

* **[!UICONTROL Chart type]**: The type of visualization that you want to use. Options include [!UICONTROL Bar] and [!UICONTROL Line].

### Date range

The desired date range for your analysis. There are two components to this setting:

* **[!UICONTROL Interval]**: The date granularity by which you want to view retention data. Valid options include Daily, Weekly, and Monthly. The same date range can have different intervals, which impact duration bucket options.
* **[!UICONTROL Date]**: The starting and ending date. Rolling date range presets and previously saved custom ranges are available for your convenience, or you can use the calendar selector to choose a fixed date range.

If you select a date range close to the present day, users that initially engage too close to the current day are not included. This analysis always gives all users the chance to be included in all duration buckets. A message below the calendar picker provides information about the date range where users engage, and the interval that is reserved only for returning users:

* **[!UICONTROL Analyzing users who did the start event in [Date interval]]**: If a user engages with the event within this date range, they are included in the analysis. This date range guarantees all users enough time to qualify for all duration buckets. This date range can be different than your selection if it is close to the present day.
* **[!UICONTROL Data from [Date interval] is reserved to complete the analysis]**: If a user engages for the first time within this period, they are **not** included in the analysis. For recent date ranges, these users would not have an opportunity to qualify for all duration buckets. For past date ranges, these users were active outside of the selected date range.

<!--
## Example

See below for an example of the analysis.

![Retention](../assets/retention.png)

-->