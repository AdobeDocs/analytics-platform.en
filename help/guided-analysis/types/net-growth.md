---
title: Net growth analysis
description: Are you gaining or losing users?
feature: Adobe Product Analytics, Guided Analysis
keywords: product analytics
exl-id: a4f97458-9934-4a98-8005-fa1ba7831101
role: User
---
# [!UICONTROL Net growth] analysis {#net-growth}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_netgrowth_button"
>title="Net growth"
>abstract="Are you gaining or losing users?"

<!-- markdownlint-enable MD034 -->

The ![NetGrowth](/help/assets/icons/NetGrowth.svg) **[!UICONTROL Net growth]** analysis provides insights around the rate at which you gain or lose users over a specific period. The horizontal axis is a time interval, while the vertical axis is the measurement of growth.

Each data point represents net growth, which is calculated using the following formula:

`([New users] + [Return users]) / [Dormant users]`

The result of this formula is a ratio. A net growth of `1` represents an equilibrium; the product gained the same number of users it lost. A net growth greater than `1` represents positive growth; there were more new + return users than dormant users. Likewise, a net growth less than `1` represents a loss; there were more dormant users than new + return users.

Similar to the [Active](active-growth.md) analysis, users are defined as the following:

* **[!UICONTROL New]**: The user was active during the current period, but not previously. See how far the analysis looks back to determine a new user by hovering over '[!UICONTROL New users]' in the chart legend. The lookback range is dynamically determined based on the selected date range and interval.
* **[!UICONTROL Return]**: The user was active in the current period and not active in the immediately previous period, but were formerly active at some point. See how far the analysis looks back to determine a return user by hovering over '[!UICONTROL Return users]' in the chart legend. The lookback range is dynamically determined based on the selected date range and interval.
* **[!UICONTROL Dormant]**: The user was active in the immediately previous period, but is not active in the current period. Dormant users do not count toward the total number of active users.

>[!NOTE]
>
>Repeat users are not factored into this calculation, as they do not represent any gain or loss of users.

>[!VIDEO](https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/guided-analysis/net-growth)


## Use cases

Use cases for this analysis include:

* **Performance evaluation**: Allows you to assess the overall performance of your product in terms of acquiring new users. By tracking growth trends, you can better understand if your product is attracting and retaining users at a desired pace.
* **User acquisition analysis**: Allows you to assess the effectiveness of your user acquisition strategies. Analyzing the sources of user growth, such as search engines, campaigns, or other marketing channels, allows you to identify the most significant sources of growth so you can allocate resources accordingly.
* **Churn analysis**: Net growth includes attrition in its formula (dormant users). You can assess the overall health of your user base over time. If net growth is consistently below `1`, it indicates a high amount of attrition which could prompt implementing retention strategies.

## Interface

See [Interface](../overview.md#interface) for an overview of the Guided analysis interface. The following settings are specific to this analysis:

### Query rail

The query rail allows you to configure the following components:

* **[!UICONTROL View]**: Switch between this analysis and [Active growth](active-growth.md).
* **[!UICONTROL Events]**: The event that you want to measure. Since this analysis is user-based, a user who interacts with the event once within the period is counted as an active user. You can include one event in a query.
* **[!UICONTROL Counted as]**: The counting method that you want to apply to the selected events. <ul><li>**[!UICONTROL Options]** include [!UICONTROL Number of users] and [!UICONTROL Percentage of users].</li><li>[!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} Additional **[!UICONTROL B2B options]** are available for Customer Journey Analytics B2B Edition: [!UICONTROL Global accounts], [!UICONTROL Accounts], [!UICONTROL Buying groups], [!UICONTROL Opportunities], [!UICONTROL Percentage of global accounts], [!UICONTROL Percentage of accounts], [!UICONTROL Percentage of buying groups], and [!UICONTROL Percentage of opportunities].</li></ul>
* **[!UICONTROL Segments]**: The segment that you want to measure. You can include one segment in a query.

### Time comparison

{{apply-time-comparison}}

### Date range

The desired date range for your analysis. There are two components to this setting:

* **[!UICONTROL Interval]**: The date granularity that you want to view trended data by. Valid options include Hourly, Daily, Weekly, Monthly, and Quarterly. The same date range can have different intervals which affect the number of data points in the chart and the number of columns in the table. For example, viewing an analysis spanning three days with daily granularity would show only three data points, while an analysis spanning three days with hourly granularity would show 72 data points.
* **[!UICONTROL Date]**: The starting and ending date. Rolling date range presets and previously saved custom ranges are available for your convenience, or you can use the calendar selector to choose a fixed date range.

<!-- 
## Example

See below for an example of the analysis.

![Net growth compare](../assets/net-growth-compare.png)

-->
