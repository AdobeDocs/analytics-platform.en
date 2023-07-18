---
title: Release view
description: Compare performance across equal periods pre- and post-release.
feature: Guided Analysis
---
# [!UICONTROL Release] view

The **[!UICONTROL Release]** view shows a comparison of how key indicators performed before and after a given date. The horizontal axis of this report is a time interval, while the vertical axis measures the desired key indicators. A vertical bar in the middle of the chart represents the date that you want to compare before and after. This date typically represents a notable change to the product that you want to measure against, such as an update to the product or a campaign launch.

>[!VIDEO](https://video.tv.adobe.com/v/3421665/?learn=on)

## Use cases

Use cases for this view type include:

* **Overall performance evaluation:** Comparing overall key indicators, such as engagement measures, can help you determine if a given release was overall successful.
* **Monitoring**: If there are certain measures you expect to remain flat when changes are made, such as web vitals like load time or logins, compare them before and after to ensure your release didn't have any unintended consequences.
* **Feature adoption**: If a product update is focused on improving a certain feature, you can use this view to directly compare that feature's usage before and after the product update.
* **Bug detection**: Tracking the number of errors before and after a release can provide an early indicator of customer issues. If you notice an increase of errors immediately following a release, you can work with engineering or development teams to identify and correct the issue, preventing further impact to customers.

## Query rail

The query rail allows you to configure the following components:

* **[!UICONTROL Key indicators]**: The events that you want to measure per user. Each selected key indicator is represented as a colored line. A row representing the event is added to the table. You can include up to three events.
* **[!UICONTROL Factors]**: The date that you want to compare before and after.
* **[!UICONTROL People]**: The segment that you want to measure. The selected segment filters your data to focus only on the individuals who match your segment criteria.

## Chart settings

The Release view offers the following chart settings, which can be adjusted in the menu above the chart:

* **[!UICONTROL Metric]**: The metric that you want to measure. Options include [!UICONTROL Events per user], [!UICONTROL Percentage of users], [!UICONTROL Events], [!UICONTROL Sessions], and [!UICONTROL Users].
* **[!UICONTROL Chart type]**: The type of visualization that you want to use. Options include Line.

## Date range

Date selection in Impact analysis operates differently than other analysis types, since the report revolves around the date specified in the query rail. The following options are available:

* **[!UICONTROL Interval]**: The date granularity that you want to view trended data by. Valid options include [!UICONTROL Daily], [!UICONTROL Weekly], [!UICONTROL Monthly], and [!UICONTROL Quarterly]. Changing the interval affects the options available for the Before and after period.
* **[!UICONTROL Before and after period]**: The amount of time to analyze before and after the date specified in the query rail. Available options depend on the [!UICONTROL Interval] selection.
