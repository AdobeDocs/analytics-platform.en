---
title: Standard Component Reference
description: Learn about details and information on all standard components that you can add to any data view.
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

### Standard dimensions

{{standard-dimensions}}


### Standard metrics

{{standard-metrics}}


## Optional standard components {#optional}

Optional Standard components are available under **[!UICONTROL Data views]** > **[!UICONTROL Edit data view]** > **[!UICONTROL Components]** tab > **[!UICONTROL Standard Components]** tab.

| Component Name | Dimension or Metric | Notes and values |
| --- | --- | --- |
| [!UICONTROL AM/PM] | Time-parting dimension | AM or PM |
| [!UICONTROL Batch ID] | Dimension | Identifier for the Experience Platform batch that an [!UICONTROL Event] was part of. |
| [!UICONTROL Dataset ID] | Dimension | Identifier for the Experience Platform dataset that an [!UICONTROL Event] was part of. |
| [!UICONTROL Day of Month] | Time-parting dimension | 1-31 |
| [!UICONTROL Day of Week]| Time-parting dimension | Monday, Tuesday, Wednesday, Thursday, Friday, Saturday, Sunday |
| [!UICONTROL Day of Year] | Time-parting dimension | 1-366 |
| [!UICONTROL Hour of Day] | Time-parting dimension | 0-23 |
|[!UICONTROL  Month of Year] | Time-parting dimension | January - December |
| [!UICONTROL First-time Sessions] | Metric | A person's defined first session within the reporting window. [Learn more](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html#new-repeat) |
| [!UICONTROL Return Sessions] | Metric | The number of sessions that were not a person's first-time session. [Learn more](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html#new-repeat) |
| [!UICONTROL Person ID] | Dimension | Each dataset schema defined in the Experience Platform can have its own set of one or more identities defined and associated with an Identity Namespace. Any of these identities can be used as the Person ID. Examples include Cookie ID, Stitched ID, User ID, Tracking Code, and so on. The [!UICONTROL Person ID] dimension is the foundation of combining datasets and identifying unique persons in Customer Journey Analytics.<p>Possible use cases include:<ul><li>Create a segment on a specific person ID value to segment everything down to that user's behavior.</li><li>Debugging: making sure that the data for a specific cookie ID (or a specific customer ID) is there.</li><li>Identifying the users who called in to a call center.</li></ul>  |
| [!UICONTROL Person ID namespace] | Dimension | Which type of ID the [!UICONTROL Person ID] consists of. Examples are: `email address`, `cookie ID`, `Analytics ID` |
| [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>[!UICONTROL Global Account ID] | Dimension | The [!UICONTROL Global Account ID], when you use the Global Account container in your connection. |
| [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>[!UICONTROL Account ID ] | Dimension | The [!UICONTROL Account ID], when you use the Account container in your connection. |
| [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>[!UICONTROL Opportunity ID] | Dimension | The [!UICONTROL Opportunity ID], when you use the Opportunity container in your connection.  |
| [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>[!UICONTROL Buying Group ID] |  Dimension | The [!UICONTROL Buying Group ID], when you use the Buying group container in your connection. |
| [!UICONTROL Quarter of Year] | Time-parting dimension | Q1, Q2, Q3, Q4 |
| [!UICONTROL Repeat session] | Metric | The number of sessions that were not a person's first-ever session. [Learn more](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html#new-repeat) |
| [!UICONTROL Session Type] | Dimension | This dimension has two values: 1. [!UICONTROL First-Time] and 2. Returning. The [!UICONTROL First-time] line item includes all behavior (metrics against this dimension) from a session that has been determined to be a person's defined first session. Everything else is included in the [!UICONTROL Returning] line item (assuming everything belongs to a session). Where metrics are not part of any session, they would fall into the 'Not applicable' bucket for this dimension. [Learn more](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html#new-repeat) |
| [!UICONTROL Time Spent per Event] | Dimension | Buckets the [!UICONTROL Time Spent] metric into [!UICONTROL Event] buckets. |
| [!UICONTROL Time Spent per Session] | Dimension | Buckets the [!UICONTROL Time Spent] metric into [!UICONTROL Session] buckets. |
| [!UICONTROL Time Spent per Person] | Dimension | Buckets the [!UICONTROL Time Spent] metric into [!UICONTROL Person] buckets. |
| [!UICONTROL Weekend]/[!UICONTROL Weekday] | Time-parting dimension | Weekend or Weekday |

{style="table-layout:auto"}


>[!MORELIKETHIS]
>
>[Discover Deeper Customer Insights with the Event Depth Feature](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/discover-deeper-customer-insights-with-adobe-customer-journey/ba-p/753947#M576)
>