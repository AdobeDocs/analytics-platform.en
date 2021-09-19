---
title: Standard component reference
description: Details and information on all standard components that you can add to any data view.
exl-id: e23ce27a-77ab-4641-a126-93f00d4e6e14
---
# Standard component reference

Most dimensions and metrics in CJA are based on schema elements from your Adobe Experience Platform dataset. However, several components are available to add to a data view regardless of the connection that you use.

[!UICONTROL Standard components] are components that are not generated from dataset schema fields but are instead system generated. Some system components are required to facilitate reporting capabilities in Analysis Workspace, while other system components are optional.

![Standard components](assets/standard-components.png)

## Required standard components

These required standard components are added to each data view by default. They are essential to the reporting capabilities that Customer Journey Analytics offers.

| Component Name | Dimension or Metric | Notes |
| --- | --- | --- |
| [!UICONTROL People] | Metric | Based on the person ID specified in a [!UICONTROL Connection]. |
| [!UICONTROL Sessions] | Metric | Based on the data view's session settings. |
| [!UICONTROL Events] | Metric | The number of rows from all event datasets in a [!UICONTROL Connection]. |
| [!UICONTROL Minute] | Dimension | The minute that a given event happened (rounded down). The first dimension item is the first minute in the date range, and the last dimension item is the last minute in the date range. |
| [!UICONTROL Hour] | Dimension | The hour that a given event happened (rounded down). The first dimension item is the first hour in the date range, and the last dimension item is the last hour in the date range. |
| [!UICONTROL Day] | Dimension | The day that a given event happened. The first dimension item is the first day in the date range, and the last dimension item is the last day in the date range. |
| [!UICONTROL Week] | Dimension | The week that a given event happened. The first dimension item is the first week in the date range, and the last dimension item is the last week in the date range.|
| [!UICONTROL Month] | Dimension | The month that a given event happened. The first dimension item is the first month in the date range, and the last dimension item is the last month in the date range. |
| [!UICONTROL Quarter] | Dimension | The quarter that a given event happened. The first dimension item is the first quarter in the date range, and the last dimension item is the last quarter in the date range. |
| [!UICONTROL Year] | Dimension | The year that a given event happened. The first dimension item is the first year in the date range, and the last dimension item is the most recent year in the date range. |

## Optional standard components

Optional Standard components are available under **[!UICONTROL Data views]** > **[!UICONTROL Edit data view]** > **[!UICONTROL Components]** tab > **[!UICONTROL Standard Components]** tab.

| Component Name | Dimension or Metric | Notes |
| --- | --- | --- |
| [!UICONTROL Session Starts] | Metric | The number of events that were the first event of a session. When used in a filter definition (e.g. '[!UICONTROL Session Starts] exists'), it filters down to just the first event of every session. |
| [!UICONTROL Session Ends] | Metric | The number of events that were the last event of a session. Similar to [!UICONTROL Session Starts], it can also be used in a filter definition to filter things down to the last event of every session. |
| [!UICONTROL Time Spent (seconds)] | Metric | Sums the time between two different values for a dimension. |
| [!UICONTROL Time Spent per Event] | Dimension | Buckets the [!UICONTROL Time Spent] metric into [!UICONTROL Event] buckets. |
| [!UICONTROL Time Spent per Session] | Dimension | Buckets the [!UICONTROL Time Spent] metric into [!UICONTROL Session] buckets. |
| [!UICONTROL Time Spent per Person] | Dimension | Buckets the [!UICONTROL Time Spent] metric into [!UICONTROL Person] buckets. |
| [!UICONTROL Batch ID] | Dimension | Represents the Experience Platform batch that an [!UICONTROL Event] was part of. |
| [!UICONTROL Dataset ID] | Dimension | Represents the Experience Platform dataset that an [!UICONTROL Event] was part of. |
