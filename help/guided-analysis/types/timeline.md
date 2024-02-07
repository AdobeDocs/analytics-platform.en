---
title: Timeline view
description: Explore patterns in session activity.
feature: Guided Analysis
keywords: product analytics
role: User
---
# [!UICONTROL Timeline] view

The **[!UICONTROL Timeline]** view allows you to analyze individual sessions to determine patterns in behavior. The right rail allows you to select the person ID that you want to analyze. The center area shows the time, selected property value, and duration for each event of that person.

This analysis requires that you add the **[!UICONTROL Person ID]** standard component to the [data view](/help/data-views/component-reference.md#optional). If you do not have the [!UICONTROL Person ID] component added to the data view, the following message is displayed:

> The PersonID property is required for this analysis. Please add PersonID to the data view.

## Use cases

Use cases for this view type include:

* **Friction exploration**: If you find a steep drop in the [Friction](friction.md) view, you can investigate potential causes of that drop using this view.
* **Error behavior**: If users encounter an error in your product, you can explore what users do before or after seeing that error.
* **Data collection validation**: Data admins can filter this view to isolate themselves. This view provides a solid way to make sure that your organization's implementation is working as expected.

## Query rail

The query rail allows you to configure the following components:

* **[!UICONTROL Property]**: The property that you want to view values for. The session analysis in the center shows values for the property selected here. You can also filter data by the selected property. Valid operators for the filter include [!UICONTROL Equals], [!UICONTROL Does not equal], [!UICONTROL Starts with], [!UICONTROL Ends with], [!UICONTROL Contains], [!UICONTROL Does not contain], [!UICONTROL Exists], and [!UICONTROL Does not exist].
* **[!UICONTROL Segments]**: The segment that you want to measure. The selected segment filters your data to focus only on the individuals who match your segment criteria. One segment is supported for this view.

## Chart settings

The [!UICONTROL Timeline] view offers the following chart settings, which can be adjusted in the menu above the chart:

* **[!UICONTROL Show as]**: Shows desired property values.
  * [!UICONTROL Show all]
  * [!UICONTROL Highlight]
  * [!UICONTROL View only]

## Date range

The desired date range for your analysis. There are two components to this setting:

* **[!UICONTROL Interval]**: The date granularity that you want to view trend data by. This setting does not impact non-trended views such as Timeline.
* **[!UICONTROL Date]**: The starting and ending date. Rolling date range presets and previously saved custom ranges are available for your convenience, or you can use the calendar selector to choose a fixed date range.
