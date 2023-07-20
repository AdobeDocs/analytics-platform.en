---
title: Cross-Channel Analytics FAQ
description: Frequently asked questions for Cross-Channel Analytics
exl-id: 2ad78c19-4b13-495b-a0aa-44e0a3c95b5e
solution: Customer Journey Analytics
feature: Cross-Channel Analytics
hide: yes
hidefromtoc: yes
---
# Frequently asked questions

## How can I use CCA to see how people move from one channel to another?

You can use a Flow visualization with the Dataset ID dimension.

1. Log in to [analytics.adobe.com](https://analytics.adobe.com) and create a blank Workspace project.
2. Click the Visualizations tab on the left, and drag a Flow visualization to the canvas on the right.
3. Click the Components tab on the left, and drag the dimension 'Dataset ID' to the center location labeled 'Dimension or Item'.
4. This flow report is interactive. Click any of the values to expand the flows to subsequent or previous pages. Use the right-click menu to expand or collapse columns. Different dimensions can also be used within the same flow report.

If you would like to rename dataset ID dimension items, you can use a lookup dataset.

## How far back does CCA rekey persons?

The lookback window for rekeying depends on your desired frequency of data [replay](replay.md). For example, if you set up CCA to replay data once every week, the lookback window for rekeying is seven days. If you set up CCA to replay data every day, the lookback window for rekeying is one day.

## How are shared devices handled?

In some situations, it is possible that multiple people log in from the same device. Examples include a shared device at home, shared PCs in a library, or a kiosk in a retail outlet.

The transient ID overrides the persistent ID, so shared devices are considered separate people (even if they originate from the same device).

## How does CCA handle situations where a single person has many persistent IDs?

In some situations, an individual user can associate with many persistent IDs. Examples include an individual frequently clearing browser cookies, or using the browser's private/incognito mode.

The number of persistent IDs is irrelevant in favor of the transient ID. A single user can belong to any number of devices without impacting CCA's ability to stitch across devices.

## Once I contact my Adobe Account Team with the desired information, how long does it take for the rekeyed dataset to become available?

Live stitching is available approximately one week after Adobe enables Cross-Channel Analytics. Backfill availability depends on the amount of existing data. Small datasets (less than 1 million events per day) typically take a couple days, while large datasets (1 billion events per day) can take a week or more.

## What is the difference between Cross-Device Analytics (a feature in Adobe Analytics) and Cross-Channel Analytics?

[Cross-Device Analytics](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html) is a feature specific to traditional Adobe Analytics that allows you to understand how people operate across devices. It offers two workflows to link device data together: field-based stitching and the device graph.

[Cross-Channel Analytics](/help/cca/overview.md) is a feature specific to Customer Journey Analytics that allows you to understand how people operate across both devices and channels. It re-key's a dataset's person ID, allowing that dataset to be seamlessly combined with other datasets. This feature operates in design similarly to CDA's field-based stitching, but implementation is different do to differing data architecture between Adobe Analytics and Customer Journey Analytics.

## How does Cross-Channel Analytics handle GDPR and CCPA requests?

Adobe handles GDPR and CCPA requests in accordance to local and international laws. Adobe offers the [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html) to submit data access and deletion requests. The requests apply to both the original and rekeyed datasets.

## What happens if the Persistent ID field in one or more events is blank?

If the `Persistent ID` field is blank on an event in a dataset being stitched with field-base stitching, CCA fills in the `Stitched ID` for that event in one of two ways:

* If the `Transient ID` field is not blank, CCA uses the value in `Transient ID` as the `Stitched ID`.
* If the `Transient ID` field is blank, CCA also leaves the `Stitched ID` blank. In this case, `Persistent ID`, `Transient ID`, and `Stitched ID` are all blank on the event. These types of events are dropped from any Customer Journey Analytics connection using the dataset being stitched where `Stitched ID` was chosen as the `Person ID`.

## How do metrics in Customer Journey Analytics stitched datasets compare with similar metrics in Customer Journey Analytics unstitched datasets and with traditional Adobe Analytics?

Certain metrics in Customer Journey Analytics are similar to metrics in Adobe Analytics, but others are quite different, depending on what you are comparing. The table below compares several common metrics:

| **Customer Journey Analytics stitched data** | **Customer Journey Analytics unstitched data** | **Traditional Adobe Analytics** | **Analytics Ultimate with CDA** |
| ----- | ----- | ----- | ----- |
| **People** = Count of distinct `Person ID`s where `Stitched ID` is chosen as `Person ID`. **People** may be higher or lower than **Unique Visitors** in traditional Adobe Analytics, depending on the outcome of the stitching process. | **People** = Count of distinct `Person ID`s based on the column selected as `Person ID`. **People** in Analytics source connector datasets is similar to **Unique Visitors** in traditional Adobe Analytics if `endUserIDs._experience.aaid.id` is chosen as `Person ID` in Customer Journey Analytics. | **Unique Visitors** = Count of distinct person IDs. **Unique Visitors** may not be the same as the count of distinct **ECID**s.| See [People](https://experienceleague.adobe.com/docs/analytics/components/metrics/people.html).  |
| **Sessions**: Defined based on the session settings in the Customer Journey Analytics data view. The stitching process may combine individual sessions from multiple devices into a single session. | **Sessions**: Defined based on the session settings specified in the Customer Journey Analytics data view.  | **Visits**: See [Visits](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html). | **Visits**: Defined based on the session settings specified in the [CDA virtual report suite](https://experienceleague.adobe.com/docs/analytics/components/cda/setup.html). |
| **Events** = count of rows in the stitched data in Customer Journey Analytics. This metric is typically close to **Occurrences** in traditional Adobe Analytics. Note, however, the FAQ above regarding rows with a blank `Persistent ID`.| **Events** = count of rows in the unstitched data in Customer Journey Analytics. This metric is typically close to **Occurrences** in traditional Adobe Analytics. Note, however, that if any events have a blank `Person ID` in the unstitched data in Experience Platform data lake, these events are not included in Customer Journey Analytics. | **Occurrences**: See [Occurrences](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html). | **Occurrences**: See [Occurrences](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html). |

Other metrics can be similar in Customer Journey Analytics and traditional Adobe Analytics. For example, the total count for Adobe Analytics [custom events](https://experienceleague.adobe.com/docs/analytics/components/metrics/custom-events.html) 1-100 is generally comparable between traditional Adobe Analytics and Customer Journey Analytics (whether stitched or unstitched). [Differences in capabilities](/help/getting-started/aa-vs-cja/cja-aa.md)) such as event de-duplication between Customer Journey Analytics vs. traditional Adobe Analytics can cause discrepancy between the two products.

## Can CCA use Identity Map fields?

No, CCA cannot currently use Identity Map fields.
