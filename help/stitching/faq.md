---
title: Stitching FAQ
description: Frequently asked questions for Stitching
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: f4115164-7263-40ad-9706-3b98d0bb7905
role: Admin
---
# Frequently asked questions

Here are some frequently asked questions around stitching:

## Move across channels

+++ How can I use stitching to see how people move from one channel to another?

You can use a Flow visualization with the Dataset ID dimension.

1. Log in to [Customer Journey Analytics](https://analytics.adobe.com) and create a blank Workspace project.
2. Select the **[!UICONTROL **Visualizations**]** tab on the left, and drag a **[!UICONTROL **Flow**]** visualization to the canvas on the right.
3. Select the **[!UICONTROL **Components**]** tab on the left, and drag the dimension **[!UICONTROL **Dataset ID**]** to the center location labeled **[!UICONTROL **Dimension or Item**]**.
4. This flow report is interactive. To expand the flows to subsequent or previous pages, select any of the values. Use the right-click menu to expand or collapse columns. Different dimensions can also be used within the same flow report.

If you would like to rename dataset ID dimension items, you can use a lookup dataset.

+++

## Replay

+++ How far back does stitching replay visitors?

The lookback window for rekeying depends on your desired frequency of data replay. For example, if you set up stitching to replay data once every week, the lookback window for rekeying is seven days. If you set up stitching to replay data every day, the lookback window for rekeying is one day.

+++

## Shared devices

+++ How are shared devices handled?

In some situations, it is possible that multiple people log in from the same device. Examples include a shared device at home, shared PCs in a library, or a kiosk in a retail outlet.

The transient ID overrides the persistent ID, so shared devices are considered separate people (even if they originate from the same device).

See the [Shared devices](/help/use-cases/stitching/shared-devices.md) use case for more details.

+++

## Many persistent IDs

+++ How does stitching handle situations where a single person has many persistent IDs?

In some situations, an individual user can associate with many persistent IDs. An example is an individual frequently clearing browser's cookies or using the browser's private/incognito mode.

For field-based stitching, the number of persistent IDs is irrelevant in favor of the transient ID. A single user can belong to any number of devices without impacting Customer Journey Analytics's ability to stitch across devices.

For graph-based stitching, a single person can have many persistent ID in the identity graph. Graph-based stitching uses the persistent ID based on the specified namespace. In case there are more persistent ID for the same namespace, the lexicographic first persistent ID is used.

+++

## Stitching process

+++ Once I contact my Adobe Account Team with the desired information, how long does it take for the rekeyed dataset to become available?

Live stitching is available approximately one week after Adobe enables stitching. Backfill availability depends on the amount of existing data. Small datasets (less than 1 million events per day) typically take a couple days, while large data sets (1 billion events per day) can take a week or more.

+++

## Cross-device analytics versus cross-channel analysis

+++ What is the difference between cross-device analytics (a feature in traditional Analytics) and cross-channel analysis?

[Cross-device analytics](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html) is a feature specific to traditional Adobe Analytics that allows you to understand how people operate across devices. It offers two workflows to link device data together: field-based stitching and the device graph.

Cross-channel analysis is a use case specific to Customer Journey Analytics that allows you to understand how people operate across both devices and channels. It stitches a dataset's person ID, allowing that dataset to be seamlessly combined with other datasets. This feature operates in design similarly to cross-device analytics field-based stitching, but the implementation is different due to differing data architecture between traditional Analytics and Customer Journey Analytics. See [Stitching](overview.md) and the [cross-channel analysis](../use-cases/cross-channel/cross-channel.md) use case for more information.

+++

## Privacy

+++ How does Stitching handle privacy requests?

Adobe handles privacy requests in accordance with local and international laws. Adobe offers the [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html) to submit data access and deletion requests. The requests apply to both the original and rekeyed datasets.

>[!IMPORTANT]
>
>The unstitching process, as part of privacy requests, changes at the start of 2025. The current unstitching process restitches events using the latest version of known identities. This reassignment of events to another identity might have undesirable legal consequences. To remedy these concerns, from 2025 on, the new unstitching process updates events that are subject of the privacy request with the persistent ID.
> 

To illustrate, imagine the following data for identities, events before stitching and after stitching.

| Identity Map | Id | timestamp | persistent ID | persistent namespace | transient id | transient namespace |
|---|---|---|---|---|---|---|
|| 1 | ts1 | 123 | ecid | Bob | CustId |
|| 2 | ts2 | 123 | ecid | Alex | CustId |


| Events dataset | Id | timestamp | persistent ID | persistent namespace | transient id | transient namespace |
|---|---|---|---|---|---|---|
| |1 | ts0 | 123 | ecid | | |
| |2 | ts1 | 123 | ecid | Bob | CustId |
| |3 | ts2 | 123 | ecid | Alex | CustId |


| Stitched dataset | Id | timestamp | persistent ID | persistent namespace | transient id | transient namespace | Stitched ID | Stitched namespace |
|---|---|---|---|---|---|---|---|---|
| |1 | ts0 | 123 | ecid | | | Bob | CustId |
| |2 | ts1 | 123 | ecid | Bob | CustId | Bob | CustId |
| |3 | ts2 | 123 | ecid | Alex | CustId | Alex | CustId |


**Current process for privacy request**

When a privacy request is received for customer with CustID Bob, the rows with strikethrough entries are deleted. Other events are restitched using the identity map. For example, the first stitched id in the stitched dataset is updated to **Alex**.

| Identity Map | Id | timestamp | persistent ID | persistent namespace | transient id | transient namespace |
|:---:|---|---|---|---|---|---|
|![DeleteOutline](/help/assets/icons/DeleteOutline.svg)| ~~1~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ |
|| 2 | ts2 | 123 | ecid | Alex | CustId |


| Events dataset | Id | timestamp | persistent ID | persistent namespace | transient id | transient namespace |
|:---:|---|---|---|---|---|---|
| |1 | ts0 | 123 | ecid | | |
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) |~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ |
| |3 | ts2 | 123 | ecid | Alex | CustId |


| Stitched dataset | Id | timestamp | persistent ID | persistent namespace | transient id | transient namespace | Stitched ID | Stitched namespace |
|:---:|---|---|---|---|---|---|---|---|
| |1 | ts0 | 123 | ecid | | | **Alex** | CustId |
|![DeleteOutline](/help/assets/icons/DeleteOutline.svg)|~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ | ~~Bob~~ | ~~CustId~~ |
| |3 | ts2 | 123 | ecid | Alex | CustId | Alex | CustId |


**New process for privacy request**

When a privacy request is received for customer with CustID Bob, the rows with strikethrough entries are deleted. Other events are restitched using the persistent id. For example, the first stitched id in the stitched dataset is updated to **123**.

| Identity Map | Id | timestamp | persistent ID | persistent namespace | transient id | transient namespace |
|:---:|---|---|---|---|---|---|
|![DeleteOutline](/help/assets/icons/DeleteOutline.svg)| ~~1~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ |
|| 2 | ts2 | 123 | ecid | Alex | CustId |


| Events dataset | Id | timestamp | persistent ID | persistent namespace | transient id | transient namespace |
|:---:|---|---|---|---|---|---|
| |1 | ts0 | 123 | ecid | | |
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) |~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ |
| |3 | ts2 | 123 | ecid | Alex | CustId |


| Stitched dataset | Id | timestamp | persistent ID | persistent namespace | transient id | transient namespace | Stitched ID | Stitched namespace |
|:---:|---|---|---|---|---|---|---|---|
| |1 | ts0 | 123 | ecid | | | **123** | ecid |
|![DeleteOutline](/help/assets/icons/DeleteOutline.svg)|~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ | ~~Bob~~ | ~~CustId~~ |
| |3 | ts2 | 123 | ecid | Alex | CustId | Alex | CustId |

+++

## Blank persistent ID values

+++ What happens if the Persistent ID field in one or more events is blank?

If the Persistent ID field is blank on an event in a dataset being stitched , the Stitched ID for that event in determined in one of two ways:

* If the Transient ID field is not blank, Customer Journey Analytics uses the value in Transient ID as the Stitched ID.
* If the Transient ID field is blank, Customer Journey Analytics also leaves the Stitched ID blank. In this case, Persistent ID, Transient ID, and Stitched ID are all blank on the event. These types of events are dropped from any Customer Journey Analytics connection using the dataset being stitched where Stitched ID was chosen as the Person ID.

+++


## Undefined transient ID values

+++ What happens if the Transient ID field in one or more events has placeholder values, like `Undefined`?

Be cautious of 'person collapse', which occurs when stitching is applied to data that uses placeholder values for Transient IDs. In the example table below, undefined person IDs originating from a dataset sourced from a CRM system are populated with the value 'Undefined' resulting in incorrect representation of persons.

| Event | Timestamp | Persistent ID (Cookie ID) | Transient ID (Login ID) | Stitched ID (after replay) | 
|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | 123 | - | **Cory** |
| 2 | 2023-05-12 12:02 | 123 | Cory  | **Cory** |
| 3 | 2023-05-12 12:03 | 456 | Undefined | **Undefined** | 
| 4 | 2023-05-12 12:04 | 456 | - | **Undefined**|
| 5 | 2023-05-12 12:05 | 789 | Undefined | **Undefined** |
| 6 | 2023-05-12 12:06 | 012 | Undefined | **Undefined** | 
| 7 | 2023-05-12 12:07 | 012 | - | **Undefined** | 
| 8 | 2023-05-12 12:03 | 789 | Undefined | **Undefined** |
| 9 | 2023-05-12 12:09 | 456 | - | **Undefined** |
| 10 | 2023-05-12 12:02 | 123 | - | **Cory** |
| | | **4 devices** | **2 people**:<br/>Events 1, 4, 7, 9, 10 dropped| **2 people**:<br/>Cory, Unauthenticated (collapsed to one person) |

+++

## Metrics comparison

+++ How do metrics in Customer Journey Analytics stitched datasets compare with similar metrics in Customer Journey Analytics unstitched datasets and with Adobe Analytics?

Certain metrics in Customer Journey Analytics are similar to metrics in traditional Analytics, but others are different, depending on what you are comparing. The table below compares several common metrics:

| **Customer Journey Analytics stitched data** | **Customer Journey Analytics unstitched data** | **Adobe Analytics** | **Analytics Ultimate with CDA** |
| ----- | ----- | ----- | ----- |
| **People** = Count of distinct Person IDs where Stitched ID is chosen as Person ID. **People** may be higher or lower than **Unique Visitors** in traditional Adobe Analytics, depending on the outcome of the stitching process. | **People** = Count of distinct Person IDs based on the column selected as Person ID. **People** in Analytics source connector datasets is similar to **Unique Visitors** in traditional Adobe Analytics if `endUserIDs._experience.aaid.id` is used as Person ID in Customer Journey Analytics. | **Unique Visitors** = Count of distinct visitor IDs. **Unique Visitors** may not be the same as the count of distinct **ECID**s.| See [People](https://experienceleague.adobe.com/docs/analytics/components/metrics/people.html).  |
| **Sessions**: Defined based on the session settings in the Customer Journey Analytics data view. The stitching process may combine individual sessions from multiple devices into a single session. | **Sessions**: Defined based on the session settings specified in the Customer Journey Analytics data view.  | **Visits**: See [Visits](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html). | **Visits**: Defined based on the session settings specified in the [CDA virtual report suite](https://experienceleague.adobe.com/docs/analytics/components/cda/setup.html). |
| **Events** = count of rows in the stitched data in Customer Journey Analytics. This metric is typically close to **Occurrences** in traditional Adobe Analytics. Note, however, the FAQ above regarding rows with a blank Persistent ID.| **Events** = count of rows in the unstitched data in Customer Journey Analytics. This metric is typically close to **Occurrences** in traditional Adobe Analytics. Note, however, that if any events have a blank Person ID in the unstitched data in Experience Platform data lake, these events are not included in Customer Journey Analytics. | **Occurrences**: See [Occurrences](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html). | **Occurrences**: See [Occurrences](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html). |

Other metrics can be similar in Customer Journey Analytics and Adobe Analytics. For example, the total count for Adobe Analytics [custom events](https://experienceleague.adobe.com/docs/analytics/components/metrics/custom-events.html) 1-100 is comparable between traditional Adobe Analytics and Customer Journey Analytics (whether stitched or unstitched). [Differences in capabilities](/help/getting-started/aa-vs-cja/cja-aa.md)) such as event de-duplication between Customer Journey Analytics vs. Adobe Analytics can cause discrepancy between the two products.

+++

## Identity Map

+++ Can Customer Journey Analytics use Identity Map fields?

No, Customer Journey Analytics cannot currently use Identity Map fields for stitching.

+++

## Switch to graph based stitching

+++ Will data need to be reingested to switch from field based stitching to graph based stitching?

Data does not have to be reingested into Experience Platform, however it will need to be reconfigured in Customer Journey Analytics. Please follow these steps:

1. Setup the new graph-based stitched dataset. 
1. Configure the new dataset as part of a new connection in Customer Journey Analytics. 
1. Switch your existing Data View to use the new connection (and as such the new graph-based stiched dataset
1. Remove the old connection that was using the field-based stitched dataset.

+++

## Disruption in reporting

+++ Would there be any disruption to existing reports?

Not if you follow the steps outlined above. Otherwise, please ask Adobe Consulting for additional support.

+++


