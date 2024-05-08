---
title: Engagement view
description: Understand the breadth and width of feature engagement.
feature: Adobe Product Analytics, Guided Analysis
keywords: product analytics
role: User
---
# [!UICONTROL Engagement] view

The **[!UICONTROL Engagement]** view provides insight around how often a feature is used versus how many people use it. This analysis works best when comparing several features to each other.

Features that plot toward the top of this visualization indicate that it is visited frequently among those who use it. Features that plot toward the right of this visualization indicate that the greatest proportion of users visit that feature. The median number of times a feature is used divides the graph horizontally. The median percentage of daily active users divides the graph vertically.

* Features in the top-left of the graph mean that a feature is not widely adopted. However, among those who use it, use it frequently.
* Features in the top-right of the graph mean that a feature is both widely adopted and frequently used.
* Features in the bottom-right of the graph mean that a feature is widely adopted, but not frequently used.
* Features in the bottom-left of the graph mean that a feature is not widely adopted, nor is it frequently used.

## Use cases

Use cases for this view type include:

* **Feature adoption**: You can establish a direct correlation between engagement and adoption of a specific feature. Understanding which features are used the most can help determine which features to prioritize enhancing.
* **Discover underutilized features**: Features with low daily active users but high usage can indicate a hidden but valuable feature. Consider exposing these types of features to more users.
* **Improve popular features**: Features with high daily active users but low usage can indicate that a feature is highly requested but underused. Consider investing in improving these features so that they are used more often.
* **Create feature-based segments**: Analyzing how often a feature is used against how many users adopt it can help determine the types of users adopting a given feature. You can create segments based on users that use a feature casually, or based on users that frequently use that feature.
* **Feature adoption A/B testing**: Compare the usage of multiple features using segments. Add the segments of each cohort in the query rail to easily determine the difference in feature usage.

## Query rail

The query rail allows you to configure the following components:

* **[!UICONTROL Events]**: The events that you want to measure. These events typically represent usage of a given feature. Each selection is represented as point within the matrix. You can include up to ten events.
* **[!UICONTROL Counted as]**: Determine the details around how the x-axis counts users. You can measure the average percent of daily, weekly, monthly, or quarterly active users. The y-axis automatically adjusts the average times per user based on the x-axis selection.
* **[!UICONTROL Segments]**: The segments that you want to measure. Each selected segment doubles the number of plotted points in the chart and rows in the table. You can include up to three segments.

## Chart settings

The [!UICONTROL Engagement] view offers the following chart settings, which can be adjusted in the menu above the chart:

* **[!UICONTROL Medians]**: Determine where the median lines are shown and how plotted points relate to these medians.
  * **[!UICONTROL Standard]**: Show the absolute value of usage and engagement.
  * **[!UICONTROL Normalized]**: Show relevant changes from the medians.
* **[!UICONTROL Top events overlay]**: See how your events are doing compared to the most common events.

## Time comparison

{{apply-time-comparison}}

## Date range

The desired date range for your analysis. There are two components to this setting:

* **[!UICONTROL Interval]**: The date granularity that you want to view trend data by. This view type treats [!UICONTROL Interval] similarly to [!UICONTROL Counted as] in the query rail. Hourly active users is not supported.
* **[!UICONTROL Date]**: The starting and ending date. Rolling date range presets and previously saved custom ranges are available for your convenience, or you can use the calendar selector to choose a fixed date range.
