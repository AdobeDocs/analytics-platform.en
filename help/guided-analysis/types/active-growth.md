---
title: Active growth analysis
description: Identify who is new, retained, returning, or dormant.
exl-id: 53ef7485-9cae-4663-bf61-4eb77c126830
feature: Adobe Product Analytics, Guided Analysis
keywords: product analytics
role: User
---
# [!UICONTROL Active growth] analysis {#active-growth}

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_activegrowth_button"
>title="Active growth"
>abstract="Identify who is new, retained, returning, or dormant."



The ![PeopleGroup](/help/assets/icons/PeopleGroup.svg) **[!UICONTROL Active growth]** analysis provides insights into the growth and acquisition of users over a specific period. The horizontal axis is a time interval, while the vertical axis is a measurement of users. Users are split into four categories:

* **[!UICONTROL New]**: The user was active during the current period, but not previously. See how far that the analysis looks back by hovering over _[!UICONTROL New users]_ in the chart legend. The lookback range is dynamically determined based on the selected date range and interval.
* **[!UICONTROL Repeat]**: The user was active in the current and immediately previous period.
* **[!UICONTROL Return]**: The user was active in the current period and not active in the immediately previous period, but were formerly active at some point. See how far that the analysis looks back by hovering over _[!UICONTROL Return users]_ in the chart legend. The lookback range is dynamically determined based on the selected date range and interval.
* **[!UICONTROL Dormant]**: The user was active in the immediately previous period, but is not active in the current period. Dormant users do not count toward the total number of active users.

All active users (new + repeat + return) appear as a shade of teal above the horizontal axis, while all dormant users appear in orange below the horizontal axis.


>[!VIDEO](https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/guided-analysis/active-growth)

## Use cases

Use cases for this analysis include:

* **User retention and churn:** Provides a clear visualization of periods of high or low user retention. Recognizing these periods of high or low retention can help you make product decisions to encourage high retention or help minimize churn.
* **Campaign assessment**: Viewing a specific campaign can help you understand how much traffic it generated, and how well it helped users remain engaged.
* **User lifecycle analysis**: Analyzing active user growth throughout the user lifecycle can help identify specific stages where user engagement dips. For example, if there is a high ratio of dormant users for individuals in an onboarding stage, it can indicate usability issues or a need for better in-product guidance.

## Interface

See [Interface](../overview.md#interface) for an overview of the Guided analysis interface. The following settings are specific to this analysis:

### Query rail

The query rail allows you to configure the following components:

* **[!UICONTROL View]**: Switch between this analysis and [Net growth](net-growth.md).
* **[!UICONTROL Events]**: The event that you want to measure. Since this analysis is user-based, a user who interacts with the event once within the period is counted as an active user. You can include one event in a query.
* **[!UICONTROL Counted as]**: The counting method that you want to apply to the selected events. <ul><li>**[!UICONTROL Options]** include [!UICONTROL Number of users] and [!UICONTROL Percentage of users].</li><li>[!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} Additional **[!UICONTROL B2B options]** are available for Customer Journey Analytics B2B Edition: [!UICONTROL Global accounts], [!UICONTROL Accounts], [!UICONTROL Buying groups], [!UICONTROL Opportunities], [!UICONTROL Percentage of global accounts], [!UICONTROL Percentage of accounts], [!UICONTROL Percentage of buying groups], and [!UICONTROL Percentage of opportunities].</li></ul>
* **[!UICONTROL Segments]**: The segment that you want to segment data by. You can include one segment in a query.

### Chart settings

The [!UICONTROL Active growth] analysis offers the following chart settings, which can be adjusted in the menu above the chart:

* **[!UICONTROL Chart type]**: The type of visualization that you want to use. Options include [!UICONTROL Stacked bar] and [!UICONTROL Stacked area].

### Time comparison

{{apply-time-comparison}}

### Date range

The desired date range for your analysis. There are two components to this setting:

* **[!UICONTROL Interval]**: The date granularity that you want to view trended data by. Valid options include Hourly, Daily, Weekly, Monthly, and Quarterly. The same date range can have different intervals, which affect the number of data points in the chart and the number of columns in the table. For example, viewing an analysis spanning three days with daily granularity would show only three data points, while an analysis spanning three days with hourly granularity would show 72 data points.
* **[!UICONTROL Date]**: The starting and ending date. Rolling date range presets and previously saved custom ranges are available for your convenience, or you can use the calendar selector to choose a fixed date range.

<!--
## Example

See below for an example of the analysis.

![Active time compare](../assets/active-growth-compare.png)

--> 
