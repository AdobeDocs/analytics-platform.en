---
title: Standard component reference
description: Details and information on all standard components that you can add to any data view.
exl-id: e23ce27a-77ab-4641-a126-93f00d4e6e14
solution: Customer Journey Analytics
feature: Data Views
role: Admin
---
# Standard component reference

Most dimensions and metrics in Customer Journey Analytics are based on schema elements from your Adobe Experience Platform dataset. However, several components are available to add to a data view regardless of the connection that you use.

[!UICONTROL Standard components] are components that are not generated from dataset schema fields but are instead system generated. Some system components are required to facilitate reporting capabilities in Analysis Workspace, while other system components are optional.

![Standard components](assets/dataview-standard-components.png)

## Required standard components {#required}

These required standard components are added to each data view by default. They are essential to the reporting capabilities that Customer Journey Analytics offers.

| Component Name | Dimension or Metric | Notes |
| --- | --- | --- |
| [!UICONTROL People] | Metric | Based on the person ID specified in a [!UICONTROL Connection]. |
| [!UICONTROL Sessions] | Metric | Based on the data view's session settings. |
| [!UICONTROL Events] | Metric | The number of rows from all event datasets in a [!UICONTROL Connection]. |
| [!UICONTROL Seconds] | Dimension | The second that a given event happened (rounded down). The first dimension item is the first second in the date range, and the last dimension item is the last second in the date range. |
| [!UICONTROL Minute] | Dimension | The minute that a given event happened (rounded down). The first dimension item is the first minute in the date range, and the last dimension item is the last minute in the date range. |
| [!UICONTROL Hour] | Dimension | The hour that a given event happened (rounded down). The first dimension item is the first hour in the date range, and the last dimension item is the last hour in the date range. |
| [!UICONTROL Day] | Dimension | The day that a given event happened. The first dimension item is the first day in the date range, and the last dimension item is the last day in the date range. |
| [!UICONTROL Week] | Dimension | The week that a given event happened. The first dimension item is the first week in the date range, and the last dimension item is the last week in the date range.|
| [!UICONTROL Month] | Dimension | The month that a given event happened. The first dimension item is the first month in the date range, and the last dimension item is the last month in the date range. |
| [!UICONTROL Quarter] | Dimension | The quarter that a given event happened. The first dimension item is the first quarter in the date range, and the last dimension item is the last quarter in the date range. |
| [!UICONTROL Year] | Dimension | The year that a given event happened. The first dimension item is the first year in the date range, and the last dimension item is the most recent year in the date range. |
| [!UICONTROL Session Starts] | Metric | The number of events that were the first event of a session. When used in a filter definition (for example, '[!UICONTROL Session Starts] exists'), it filters down to just the first event of every session.<p>This component must be included in your data view for the following [calculated metric](/help/components/calc-metrics/default-calcmetrics.md) to be available in Workspace: <ul><li>Session Start Rate</li></p> |
| [!UICONTROL Session Ends] | Metric | The number of events that were the last event of a session. Similar to [!UICONTROL Session Starts], it can also be used in a filter definition to filter things down to the last event of every session.<p>This component must be included in your data view for the following [calculated metric](/help/components/calc-metrics/default-calcmetrics.md) to be available in Workspace: <ul><li>Session End Rate</li></p> |
| [!UICONTROL Time Spent (seconds)] | Metric | Sums the time between two different values for a dimension.<p>This component must be included in your data view for the following [calculated metrics](/help/components/calc-metrics/default-calcmetrics.md) to be available in Workspace: <ul><li>Time Spent Per Person</li><li>Time Spent Per Session</li></p> |

{style="table-layout:auto"}

## Optional standard components {#optional}

Optional Standard components are available under **[!UICONTROL Data views]** > **[!UICONTROL Edit data view]** > **[!UICONTROL Components]** tab > **[!UICONTROL Standard Components]** tab.

| Component Name | Dimension or Metric | Notes and values |
| --- | --- | --- |
| [!UICONTROL AM/PM] | Time-parting dimension | AM or PM |
| [!UICONTROL Batch ID] | Dimension | Represents the Experience Platform batch that an [!UICONTROL Event] was part of. |
| [!UICONTROL Dataset ID] | Dimension | Represents the Experience Platform dataset that an [!UICONTROL Event] was part of. |
| [!UICONTROL Day of Month] | Time-parting dimension | 1-31 |
| [!UICONTROL Day of Week]| Time-parting dimension | Monday, Tuesday, Wednesday, Thursday, Friday, Saturday, Sunday |
| [!UICONTROL Day of Year] | Time-parting dimension | 1-366 |
| [!UICONTROL Hour of Day] | Time-parting dimension | 0-23 |
|[!UICONTROL  Month of Year] | Time-parting dimension | January - December |
| [!UICONTROL First-time Sessions] | Metric | A person's defined first session within the reporting window. [Learn more](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=en#new-repeat) |
| [!UICONTROL Return Sessions] | Metric | The number of sessions that were not a person's first-time session. [Learn more](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=en#new-repeat) |
| [!UICONTROL Person ID] | Dimension | Each dataset schema defined in the Experience Platform can have its own set of one or more identities defined and associated with an Identity Namespace. Any of these identities can be used as the Person ID. Examples include Cookie ID, Stitched ID, User ID, Tracking Code, and so on. The [!UICONTROL Person ID] dimension is the foundation of combining datasets and identifying unique persons in Customer Journey Analytics.<p>Possible use cases include:<ul><li>Creating a filter on a specific person ID value to filter everything down to that user's behavior.</li><li>Debugging: making sure that the data for a specific cookie ID (or a specific customer ID) is there.</li><li>Identifying the users who called in to a call center.</li></ul>  |
| [!UICONTROL Person ID namespace] | Dimension | Which type of ID the [!UICONTROL Person ID] consists of. Examples are: `email address`, `cookie ID`, `Analytics ID` |
| [!UICONTROL Quarter of Year] | Time-parting dimension | Q1, Q2, Q3, Q4 |
| [!UICONTROL Repeat session] | Metric | The number of sessions that were not a person's first-ever session. [Learn more](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=en#new-repeat) |
| [!UICONTROL Session Type] | Dimension | This dimension has two values: 1) [!UICONTROL First-Time] and 2) Returning. The [!UICONTROL First-time] line item includes all behavior (metrics against this dimension) from a session that has been determined to be a person's defined first session. Everything else is included in the [!UICONTROL Returning] line item (assuming everything belongs to a session). Where metrics are not part of any session, they would fall into the 'Not applicable' bucket for this dimension. [Learn more](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=en#new-repeat) |
| [!UICONTROL Time Spent per Event] | Dimension | Buckets the [!UICONTROL Time Spent] metric into [!UICONTROL Event] buckets. |
| [!UICONTROL Time Spent per Session] | Dimension | Buckets the [!UICONTROL Time Spent] metric into [!UICONTROL Session] buckets. |
| [!UICONTROL Time Spent per Person] | Dimension | Buckets the [!UICONTROL Time Spent] metric into [!UICONTROL Person] buckets. |
| [!UICONTROL Weekend]/[!UICONTROL Weekday] | Time-parting dimension | Weekend or Weekday |

{style="table-layout:auto"}
