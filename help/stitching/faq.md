---
title: Stitching FAQ
description: Frequently asked questions for Stitching
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
---
# Frequently asked questions

Here are some frequently asked questions around stitching:

+++**How can I use stitching to see how people move from one channel to another?**

You can use a Flow visualization with the Dataset ID dimension.

1. Log in to [Customer Journey Analytics](https://analytics.adobe.com) and create a blank Workspace project.
2. Select the **[!UICONTROL **Visualizations**]** tab on the left, and drag a **[!UICONTROL **Flow**]** visualization to the canvas on the right.
3. Select the **[!UICONTROL **Components**]** tab on the left, and drag the dimension **[!UICONTROL **Dataset ID**]** to the center location labeled **[!UICONTROL **Dimension or Item**]**.
4. This flow report is interactive. To expand the flows to subsequent or previous pages, select any of the values. Use the right-click menu to expand or collapse columns. Different dimensions can also be used within the same flow report.

If you would like to rename dataset ID dimension items, you can use a lookup dataset.

+++

+++**How far back does stitching replay visitors?**

The lookback window for rekeying depends on your desired frequency of data [replay](explained.md). For example, if you set up stitching to replay data once every week, the lookback window for rekeying is seven days. If you set up stitching to replay data every day, the lookback window for rekeying is one day.

+++

+++**How are shared devices handled?**

In some situations, it is possible that multiple people log in from the same device. Examples include a shared device at home, shared PCs in a library, or a kiosk in a retail outlet.

The transient ID overrides the persistent ID, so shared devices are considered separate people (even if they originate from the same device).

+++

+++**How does stitching handle situations where a single person has many persistent IDs?**

In some situations, an individual user can associate with many persistent IDs. An example is an individual frequently clearing browser's cookies or using the browser's private/incognito mode.

The number of persistent IDs is irrelevant in favor of the transient ID. A single user can belong to any number of devices without impacting Customer Journey Analytics's ability to stitch across devices.

+++

+++**Once I contact my Adobe Account Team with the desired information, how long does it take for the rekeyed dataset to become available?**

Live stitching is available approximately one week after Adobe enables stitching. Backfill availability depends on the amount of existing data. Small datasets (less than 1 million events per day) typically take a couple days, while large data sets (1 billion events per day) can take a week or more.

+++

+++**What is the difference between cross-device analytics (a feature in traditional Analytics) and cross-channel analysis?**

[Cross-device analytics](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html) is a feature specific to traditional Adobe Analytics that allows you to understand how people operate across devices. It offers two workflows to link device data together: field-based stitching and the device graph.

Cross-channel analysis is a use case specific to Customer Journey Analytics that allows you to understand how people operate across both devices and channels. It stitches a dataset's person ID, allowing that dataset to be seamlessly combined with other datasets. This feature operates in design similarly to cross-device analytics field-based stitching, but the implementation is different due to differing data architecture between traditional Analytics and Customer Journey Analytics. See [Stitching](overview.md) and the [cross-channel analysis](../use-cases/cross-channel/cross-channel.md) use case for more information.

+++

+++**How does Stitching handle GDPR and CCPA requests?**

Adobe handles GDPR and CCPA requests in accordance with local and international laws. Adobe offers the [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html) to submit data access and deletion requests. The requests apply to both the original and rekeyed datasets.

+++

+++**What happens if the Persistent ID field in one or more events is blank?**

If the Persistent ID field is blank on an event in a dataset being stitched , the Stitched ID for that event in determined in one of two ways:

* If the Transient ID field is not blank, Customer Journey Analytics uses the value in Transient ID as the Stitched ID.
* If the Transient ID field is blank, Customer Journey Analytics also leaves the Stitched ID blank. In this case, Persistent ID, Transient ID, and Stitched ID are all blank on the event. These types of events are dropped from any Customer Journey Analytics connection using the dataset being stitched where Stitched ID was chosen as the Person ID.

+++

+++**How do metrics in Customer Journey Analytics stitched datasets compare with similar metrics in Customer Journey Analytics unstitched datasets and with  Adobe Analytics?**

Certain metrics in Customer Journey Analytics are similar to metrics in traditional Analytics, but others are different, depending on what you are comparing. The table below compares several common metrics:

| **Customer Journey Analytics stitched data** | **Customer Journey Analytics unstitched data** | **Adobe Analytics** | **Analytics Ultimate with CDA** |
| ----- | ----- | ----- | ----- |
| **People** = Count of distinct Person IDs where Stitched ID is chosen as Person ID. **People** may be higher or lower than **Unique Visitors** in traditional Adobe Analytics, depending on the outcome of the stitching process. | **People** = Count of distinct Person IDs based on the column selected as Person ID. **People** in Analytics source connector datasets is similar to **Unique Visitors** in traditional Adobe Analytics if `endUserIDs._experience.aaid.id` is used as Person ID in Customer Journey Analytics. | **Unique Visitors** = Count of distinct visitor IDs. **Unique Visitors** may not be the same as the count of distinct **ECID**s.| See [People](https://experienceleague.adobe.com/docs/analytics/components/metrics/people.html).  |
| **Sessions**: Defined based on the session settings in the Customer Journey Analytics data view. The stitching process may combine individual sessions from multiple devices into a single session. | **Sessions**: Defined based on the session settings specified in the Customer Journey Analytics data view.  | **Visits**: See [Visits](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html). | **Visits**: Defined based on the session settings specified in the [CDA virtual report suite](https://experienceleague.adobe.com/docs/analytics/components/cda/setup.html). |
| **Events** = count of rows in the stitched data in Customer Journey Analytics. This metric is typically close to **Occurrences** in traditional Adobe Analytics. Note, however, the FAQ above regarding rows with a blank Persistent ID.| **Events** = count of rows in the unstitched data in Customer Journey Analytics. This metric is typically close to **Occurrences** in traditional Adobe Analytics. Note, however, that if any events have a blank Person ID in the unstitched data in Experience Platform data lake, these events are not included in Customer Journey Analytics. | **Occurrences**: See [Occurrences](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html). | **Occurrences**: See [Occurrences](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html). |

Other metrics can be similar in Customer Journey Analytics and Adobe Analytics. For example, the total count for Adobe Analytics [custom events](https://experienceleague.adobe.com/docs/analytics/components/metrics/custom-events.html) 1-100 is comparable between traditional Adobe Analytics and Customer Journey Analytics (whether stitched or unstitched). [Differences in capabilities](/help/getting-started/aa-vs-cja/cja-aa.md)) such as event de-duplication between Customer Journey Analytics vs. Adobe Analytics can cause discrepancy between the two products.

+++

+++**Can Customer Journey Analytics use Identity Map fields?**

No, Customer Journey Analytics cannot currently use Identity Map fields for stitching.

+++
