---
title: Timeline analysis
description: Observe user-level session events over time to find experience patterns.
feature: Adobe Product Analytics, Guided Analysis
keywords: product analytics
role: User
exl-id: d3da9257-a133-46c8-8fac-1a33d3372bb7
---
# [!UICONTROL Timeline] analysis {#timeline}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_timeline_button"
>title="Timeline"
>abstract="Observe user-level session events over time."

<!-- markdownlint-enable MD034 -->

The ![Timeline](/help/assets/icons/Timeline.svg) **[!UICONTROL Timeline]** analysis allows you to observe user-level session events over time to find experience patterns and tell better user stories. The left rail allows you to filter the stream by property values and segments. The right rail allows you to select from a randomized list of users that match the filter criteria. The center area shows the stream for the selected user by session, consisting of timestamp, property values, and duration. Duration is not available for the last event in a given session.


>[!NOTE]
>
>The [!UICONTROL Timeline] analysis requires that the **[!UICONTROL Person ID]** standard component be available in the [data view](/help/data-views/component-reference.md#optional). The inclusion of Person ID in a data view is managed by your Customer Journey Analytics administrator, giving your organization full privacy control over who can access this data.
><br/>If a data view does not have the [!UICONTROL Person ID] component added, the following message is displayed:
>
>* **Admins**: *The PersonID property is required for this analysis. Please add Person ID to the data view.*
>* **Non-admins**: *The PersonID property is required for this analysis. Please work with your Customer Journey Analytics administrator to add Person ID to the data view.*

>[!VIDEO](https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/guided-analysis/timeline)



## Use cases

Use cases for this analysis include:

* **Friction exploration**: If you find a steep drop in the [Funnel analysis](funnel.md) analysis, you can create a segment of those users and apply the segment in this analysis to investigate potential causes.
* **Error behavior**: If users encounter a product error, you can explore what users were doing before or after seeing that error.
* **Data collection validation**: Data admins can filter this analysis to their own Person ID to validate that their organization's implementation is working as expected.

## Interface

See [Interface](../overview.md#interface) for an overview of the Guided analysis interface. The following settings are specific to this analysis:

### Query rail

The query rail allows you to configure the following components:

* **[!UICONTROL Dimension]**: The dimension that you want to view streamed values for. The stream in the center shows values for the selected dimension. You can also apply filters to narrow down the stream to more relevant data. Valid operators for the filter include [!UICONTROL Equals], [!UICONTROL Does not equal], [!UICONTROL Starts with], [!UICONTROL Ends with], [!UICONTROL Contains], [!UICONTROL Does not contain], [!UICONTROL Exists], and [!UICONTROL Does not exist].
* **[!UICONTROL Segments]**: The segment that you want to analyze. The selected segment filters your data to focus only on the individuals who match your segment criteria. If you want to narrow down the analysis to a specific Person ID, you can filter to that Person ID in the right panel. One segment is supported for this analysis. 

### Chart settings

The [!UICONTROL Timeline] analysis offers the following chart settings, which can be adjusted in the menu above the chart:

* **[!UICONTROL Show as]**: Shows the desired property values.
  * [!UICONTROL Show all]: Show all property values in a session.
  * [!UICONTROL Highlight]: Visually highlights property values in a session that match the query filters.
  * [!UICONTROL View only]: Only show property values in a session that match the query filters.

### Date range

The desired date range for your analysis. There are two components to this setting:

* **[!UICONTROL Interval]**: The date granularity that you want to view trend data by. This setting does not impact non-trended analysis such as Timeline.
* **[!UICONTROL Date]**: The starting and ending date. Rolling date range presets and previously saved custom ranges are available for your convenience, or you can use the calendar selector to choose a fixed date range.


<!--

## Example

See below for an example of the analysis.

![Timeline](../assets/timeline-new.png)

-->
