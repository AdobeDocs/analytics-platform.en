---
title: Engagement analysis
description: Understand the breadth and depth of feature engagement.
feature: Adobe Product Analytics, Guided Analysis
keywords: product analytics
role: User
exl-id: 8a48ad3b-fa30-497e-8306-f8d881b1a335
---
# [!UICONTROL Engagement] analysis {#engagement}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_engagement_button"
>title="Enagement"
>abstract="Understand the breadth and depth of feature engagement."

<!-- markdownlint-enable MD034 -->


The ![EngagementGraph](/help/assets/icons/EngagementGraph.svg) **[!UICONTROL Engagement]** analysis provides insight into how often a feature is used versus how many people use it. This analysis works best when comparing several features to each other. It helps fuel investment decisions by understanding what your core, power, one-time, and questionable features are.

Features that plot toward the top of this visualization indicate that they are frequently used among engaged users. Features that plot toward the right of this visualization indicate that they are widely adopted among your active users. The median number of times a feature is used divides the graph horizontally. The median percentage of active users divides the graph vertically. Medians are calculated based on the events selected in the query, not all data.

* Features in the top-left of the matrix are your **power** features; they are not widely adopted, but are frequently used by engaged users. 
* Features in the top-right of the matrix are your **high impact** features; they are both widely adopted and frequently used.
* Features in the bottom-left of the matrix are your **low impact** features; they are not widely adopted or frequently used.
* Features in the bottom-right of the matrix are your **one-time** features; they are widely adopted, but not frequently used.

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Engagement analysis](https://video.tv.adobe.com/v/3429489/&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

## Use cases

Use cases for this analysis include:

* **Engagement by feature**: You can establish a direct correlation between engagement and adoption of a specific feature. Understanding which features are used the most can help determine which features to invest in further.
* **Discover underused features**: Features with low active users but high usage can indicate a power feature, one that is valuable but not discovered or used by the wider population. Consider enhancing the discoverability of these features so that more users leverage them. 
* **Improve popular features**: Features with high active users but low usage can indicate that a feature is highly requested but underused. These situations present opportunities to learn more from your users about what improvements would make the feature more valuable for them. 
* **Create feature-based segments**: Viewing feature usage in this way to prompt additional analysis opportunities. Create a segment for any point on the chart to dive into that user group further and apply those learnings to your user engagement strategy.
* **Feature adoption A/B testing**: Compare the usage of multiple features across different groups of users. Add segments in the query rail to determine the difference in feature usage across key user groups.

## Interface

See [Interface](../overview.md#interface) for an overview of the Guided analysis interface. The following settings are specific to this analysis:

### Query rail

The query rail allows you to configure the following components:

* **[!UICONTROL Events]**: The events that you want to measure. Each event represents usage of a given feature and displays as a point within the matrix. You can include up to ten events. The median is calculated based on the events selected.
* **[!UICONTROL Counted as]**: Along the x-axis, you can measure the average percent of daily, weekly, monthly, or quarterly active users. The y-axis automatically adjusts the average times per user based on the x-axis selection.
* **[!UICONTROL Segments]**: The segments that you want to measure. Each selected segment doubles the number of plotted points in the chart and rows in the table. You can include up to three segments.

>[!TIP]
>
>If multiple events represent usage of a single feature, you can derive a new event that represents the feature in Data Views.

### Chart settings

The [!UICONTROL Engagement] analysis offers the following chart settings, which can be adjusted in the menu above the chart:

* **[!UICONTROL Medians]**: Determine where the median lines are shown and how the plotted points relate to those medians.
  * **[!UICONTROL Standard]**: Show the absolute value of usage and engagement.
  * **[!UICONTROL Normalized]**: Show relative changes from each median.
* **[!UICONTROL Top events overlay]**: See how your events are doing compared to the top 20 events, based on company and user recency & relevancy (the same algorithm applied to the event selector in the query rail).

### Time comparison

{{apply-time-comparison}}

### Date range

The desired date range for your analysis. There are two components to this setting:

* **[!UICONTROL Interval]**: The date granularity that you want to view trend data by. This analysis treats [!UICONTROL Interval] similarly to [!UICONTROL Counted as] in the query rail. Hourly active users is not supported.
* **[!UICONTROL Date]**: The starting and ending date. Rolling date range presets and previously saved custom ranges are available for your convenience, or you can use the calendar selector to choose a fixed date range.

<!--
## Example

See below for an example of the analysis.

![Enagement compare](../assets/engagement-compare.png)
-->
