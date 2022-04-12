---
title: Customer Journey Analytics FAQ
description: Customer Journey Analytics - Frequently Asked Questions.
exl-id: 778ed2de-bc04-4b09-865e-59e386227e06
solution: Customer Journey Analytics
feature: FAQ
---
# Frequently asked questions

[!UICONTROL Customer Journey Analytics] (CJA) is our next-generation analytics product. Following are answers to frequently asked questions about CJA. For more information, review [Customer Journey Analytics feature support](/help/getting-started/cja-aa.md).

## 1. Prerequisites {#prerequisites}

| Question | Answer |
| --- | --- |
| Do I need [!UICONTROL Private Device Graph] or [!UICONTROL Device Coop] for [!UICONTROL Customer Journey Analytics]? | No, [!UICONTROL Private Device Graph] or [!UICONTROL Device Coop] are not required for [!UICONTROL Customer Journey Analytics]. In fact, they are not yet supported. |
| Do I need [!UICONTROL Experience Cloud ID] (ECID) for [!UICONTROL Customer Journey Analytics]? | No, [!UICONTROL Customer Journey Analytics] supports any ID in a dataset, whether that's [!UICONTROL ECID] or any other ID you choose. |
| What if I need to ETL (Extract, Transform, Load) my data prior to [!UICONTROL Customer Journey Analytics]? | Customer Journey Analytics includes [Data Prep](https://experienceleague.adobe.com/docs/experience-platform/data-prep/api/overview.html) capabilities to help transform your data before putting it into Adobe Experience Platform data lake. If you need ETL after the data has already been ingested, [Adobe Experience Platform Query Service](https://experienceleague.adobe.com/docs/platform-learn/tutorials/queries/understanding-query-service.html?lang=en#queries) provides some limited options, although there may be extra fees involved. |

{style="table-layout:auto"}

## 2. Stitching data (Cross-Channel Analytics) {#stitching}

| Question | Answer |
| --- | --- |
| Can [!UICONTROL Customer Journey Analytics] "stitch" across devices or across datasets? | Yes. [!UICONTROL Customer Journey Analytics] has a stitching solution called [Cross-Channel Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html) (CCA). It lets you re-key a dataset’s person ID, which enables a seamless combination of multiple datasets. |
| Is stitching from anonymous behavior to authenticated behavior supported? | Yes. [Cross-Channel Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html) looks at user data from both authenticated and unauthenticated sessions to generate a stitched ID. |
| How does 'replay' work in CCA? | CCA “replays” data based on unique identifiers it has learned. Replay causes new devices to the connection to become stitched. [Learn more](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/replay.html?lang=en#step-1%3A-live-stitching) |
| How does stitching historical data (backfill) work in CCA? | When first turned on, Adobe provides a backfill of stitched data that goes back as far as the beginning of the previous month (up to 60 days.) In order to do this backfill, the transient ID must exist in the unstitched data that far back in time. [Learn more](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html?lang=en#enable-cross-channel-analytics) |

{style="table-layout:auto"}

## 3. Getting data into [!UICONTROL Customer Journey Analytics] {#ingest}

| Question | Answer |
| --- | --- |
| Can I combine data from different [!UICONTROL Adobe Experience Platform] sandboxes in one [!UICONTROL Customer Journey Analytics] connection? | No, you cannot access data across sandboxes. You can combine only datasets that are located within the same sandbox. [Learn more](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html#select-sandbox-and-datasets) |
| How do I connect online data to offline data in [!UICONTROL Customer Journey Analytics]? | As long as the person ID matches between datasets, [!UICONTROL Customer Journey Analytics] can connect filters, attribution, flow, fallout, etc. across datasets. |
| How do I bring my offline data into [!UICONTROL Customer Journey Analytics]? | Your entitlement to Customer Journey Analytics allows you to ingest data into Experience Platform. You can then create connections to that data and data views in [!UICONTROL Customer Journey Analytics], for reporting in Analysis Workspace. The Experience Platform's data on-boarding team can help provide recommendations or consulting for you, if needed. |
| How do I get [!UICONTROL Adobe Analytics] data into [!UICONTROL Customer Journey Analytics]? | [!UICONTROL Adobe Analytics] data can be connected to Experience Platform through the [Adobe Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html). Most [!UICONTROL Adobe Analytics] fields are brought over in XDM format, but other fields are not yet available. |
| How long does it take to assemble dataset elements into a data view? | A few hours to get started, and a few days to backfill the last 13 months of data. |
| Is it necessary to bring PII data to establish connections between the data? | No, you can use any ID, including a hash of a customer ID, which is not PII. |
| What are the limits for ingesting past or future dates/timestamps into CJA event datasets? |<ul><li>Regarding past dates/timestamps: Event data up to 10 years old.</li><li>Regarding future dates/timestamps: Event data (predictive) up to 1 month in the future.</li></ul> |

{style="table-layout:auto"}

## 4. Latency considerations {#latency}

>[!NOTE]
>There is no fixed data size in CJA and thus Adobe cannot commit to a standard ingestion time. We are actively working to reduce these latencies through new updates and ingestion optimization.

| Question | Answer |
| --- | --- |
| What is the expected latency for [!UICONTROL Customer Journey Analytics] on [!UICONTROL Adobe Experience Platform]? | <ul><li>Live data or events: Processed and ingested within 90 minutes, once data is available in AEP. (Batch size > 50 million rows: longer than 90 mins.)</li><li>Small backfills - For example, a lookup dataset of 10 million rows: within 7 days<li>Large backfills - For example, 500 billion rows: 30 days</li></ul> |

## 5. Set rolling window for [!UICONTROL Connection] data retention {#data-retention}

>[!IMPORTANT]
>Please contact Customer Care or your Adobe account manager to have this setting implemented. It is not yet available via the CJA UI.

This setting lets you define CJA data retention as a rolling window in months (3 months, 6 months, etc.), at a [!UICONTROL connection] level (not at a [!UICONTROL dataset] level). Data retention is based on event dataset timestamps and applies to event datasets only. No data retention setting exists for profile or lookup datasets since there are no applicable timestamps.

The main benefit is that you store or report only on data that is applicable and useful and delete older data that is no longer useful. It helps you stay under your contract limits and reduces the risk of overage cost. 

## 6. Implications of deleting data components {#deletion}

When it comes to data deletion, we are concerned with 6 types of components: sandbox, schema, dataset, connection, data view, and Workspace project. Here are some possible scenarios around deleting any of these components:

| If you... | This happens... |
| --- | --- |
| Delete a sandbox in [!UICONTROL Adobe Experience Platform] | Deleting a sandbox will stop data flow to any [!UICONTROL Customer Journey Analytics] connections to datasets in that sandbox. Currently, [!UICONTROL Connections] in CJA tied to the deleted sandbox will not automatically be deleted. |
| Delete a schema in [!UICONTROL Adobe Experience Platform], but not the dataset/s associated with this schema | [!UICONTROL Adobe Experience Platform] does not allow for the deletion of [!UICONTROL schemas] that have one or more [!UICONTROL datasets] associated with them. However, an Admin with the appropriate set of rights can delete the datasets first and then delete the schema. |
| Delete a dataset in [!UICONTROL Adobe Experience Platform] data lake | Deleting a dataset in AEP data lake will stop data flow from that dataset to any CJA Connections that include that dataset. Any data from that dataset is automatically deleted from associated CJA Connections. |
| Delete a dataset in [!UICONTROL Customer Journey Analytics] | Contact your Adobe Account Manager to set in motion the process for deleting a dataset within a connection that has been saved. |
| Delete a batch from a dataset (in [!UICONTROL Adobe Experience Platform]) | If a batch is deleted from an [!UICONTROL Adobe Experience Platform] dataset, the same batch will be removed from any CJA Connections that contain that specific batch.  CJA is notified of batch deletions in [!UICONTROL Adobe Experience Platform]. |
| Delete a batch **while it is being ingested** into [!UICONTROL Customer Journey Analytics] | If there is only one batch in the dataset, no data or partial data from that batch will appear in [!UICONTROL Customer Journey Analytics]. The ingestion will be rolled back. If, for example, there are 5 batches in the dataset and 3 of them have already been ingested when the dataset was deleted, data from those 3 batches will appear in [!UICONTROL Customer Journey Analytics]. |
| Delete a connection in [!UICONTROL Customer Journey Analytics] | An error message will indicate that:<ul><li>Any data views created for the deleted connection will no longer work.</li><li> Similarly, any Workspace projects that depend on data views in the deleted connection will cease working.</li></ul> |
| Delete a data view in [!UICONTROL Customer Journey Analytics] | An error message will indicate that any Workspace projects that depend on this deleted data view will cease working. |

## 7. Considerations when merging report suites in CJA {#merge-reportsuite}

If you plan to ingest Adobe Analytics data through the [Adobe Analytics source connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=en), consider these ramifications when merging 2 or more Adobe Analytics report suites.

| Issue | Consideration |
| --- | --- |
| Variables | Variables such as [!UICONTROL eVars] may not line up across report suites. For example, eVar1 in report suite 1 may point to **[!UICONTROL Page]**. In report suite 2, eVar1 may point to **[!UICONTROL Internal Campaign]**, leading to mixed and inaccurate reporting. |
| [!UICONTROL Sessions] and [!UICONTROL People] counts | They get deduplicated across report suites. As a result, counts may not match. |
| Metric deduplication | Deduplicates instances of a metric (for example, [!UICONTROL Orders]) if multiple rows have the same transaction ID (for example, [!UICONTROL Purchase ID]). This prevents over-counting of key metrics. As a result, metrics like [!UICONTROL Orders] may not add up across report suites. |
| Currency | Currency conversion is not yet supported in CJA. If the report suites you are trying to merge use different base currencies, problems may arise. | 
| [!UICONTROL Persistence]| [Persistence](../data-views/component-settings/persistence.md) extends across report suites, which impacts [!UICONTROL filters], [!UICONTROL attribution], and so on. Numbers may not add up properly. |
| [!UICONTROL Classifications] | [!UICONTROL Classifications] do not automatically get deduplicated when merging report suites. When combining multiple classifications files into a single [!UICONTROL lookup] data set, you could encounter problems. |


## 8. Traditional [!UICONTROL Adobe Analytics] components

| Question | Answer |
| --- | --- |
| Can I share/publish [!UICONTROL filters] ([!UICONTROL segments]) from [!DNL Customer Journey Analytics] to Experience Platform Unified Profile, or other Experience Cloud applications? | Not yet, but we are actively working to deliver this capability. |
| What happened to my old [!UICONTROL eVar] setting? | [!UICONTROL eVars], [!UICONTROL props], and [!UICONTROL events] in the traditional Adobe Analytics sense no longer exist in [!UICONTROL Customer Journey Analytics]. You have unlimited schema elements (dimensions, metrics, list fields). So all of the attribution settings you used to apply during the data collection process are now applied at query time. |
| Where are all my session and variable persistence settings now? | [!UICONTROL Customer Journey Analytics] applies all of these settings at report time, and these settings now live in Data Views. Changes to these settings are now retroactive, and you can have multiple versions by using multiple Data Views! |
| What happens to our existing segments/calculated metrics? | [!UICONTROL Customer Journey Analytics] no longer uses eVars, props, or events and instead uses any AEP schema. This means none of the existing segments or calc metrics are compatible with [!UICONTROL Customer Journey Analytics]. |
| How does [!UICONTROL Customer Journey Analytics] handle `Uniques Exceeded` limitations? | [!UICONTROL Customer Journey Analytics] has no unique value limitations, so no need to worry about them! |
| If I am an existing [!DNL Data Workbench] customer, can I move to [!UICONTROL Customer Journey Analytics] right now? | It depends on your use case - please work with your Adobe Account team. Your current use cases may already be a good fit for Customer Journey Analytics! |

{style="table-layout:auto"}

## 9. Estimate connection size {#estimate-size}

You may need to know how many rows of data you currently have in [!UICONTROL Customer Journey Analytics]. To get an accurate account of your organization's event data records (data rows) usage, do the following **for each of the connections created by your organization**.

1. In [!UICONTROL Customer Journey Analytics], click the **[!UICONTROL Connections]** tab. 

    You can now see a list of all your current connections.

1. Click each connection name to get to the Connections Manager.

1. Add up the **[!UICONTROL Records of event data available]** for all connections created. (Depending on the size of your connection, the number may take awhile to appear.)

    ![event data](assets/event-data.png)

1. Once you have a sum of all event data rows, look up the "Rows of Data" entitlement in the Customer Journey Analytics contract that your company signed with Adobe. 

    This gives you the maximum number of rows of data authorized in the Sales Order. If the number of rows of data that resulted from Step 3 is larger than this number, you are incurring an overage.

1. To remedy this situation, you have several options:

    * Change your [data retention settings](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/manage-connections.html?lang=en#set-rolling-window-for-connection-data-retention).
    * [Delete any unused connections](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=en#implications-of-deleting-data-components).
    * [Delete a dataset in AEP](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=en#implications-of-deleting-data-components).
    * Contact your Adobe Account Manager to license additional capacity. 

## 10. Regarding usage overages {#overage}

Usage limits are regularly monitored and enforced by Adobe. “Rows of data” means the daily average rows of data available for analysis within Customer Journey Analytics.

For example, let’s say your contract entitles you to one million rows of data. Suppose that on day 1 of using Customer Journey Analytics, you upload two million rows of data. On day 2, you delete 1 million rows and keep your usage at that committed maximum (i.e., one million row of data) for the remainder of your License Term. Depending on your contractual terms, you may still incur prorated over-usage fees for day 1, since you exceeded your "rows of data" license entitlement.

## 11. Diagnose data discrepancies {#discrepancies}

In some cases, you may notice that the total number of events ingested by your connection is different than the number of rows in the dataset in [!UICONTROL Adobe Experience Platform]. In this example, the dataset "B2B Impression" has 7650 rows, but the dataset contains 3830 rows in [!UICONTROL Adobe Experience Platform]. There are several reasons why discrepancies can happen, and the following steps can be taken to diagnose:

1. Break down this dimension by **[!UICONTROL Platform Dataset ID]** and you will notice two datasets with same size but different **[!UICONTROL Platform Dataset IDs]**. Each dataset has 3825 records. That means [!UICONTROL Customer Journey Analytics] ignored 5 records due to missing person IDs or missing timestamps:

    ![breakdown](assets/data-size2.png)

1. In addition, if we check in [!UICONTROL Adobe Experience Platform], there is no dataset with Id "5f21c12b732044194bffc1d0", hence someone deleted this particular dataset from [!UICONTROL Adobe Experience Platform] when the initial connection was being created. Later it got added to Customer Journey Analytics again, but a different [!UICONTROL Platform Dataset ID] was generated by [!UICONTROL Adobe Experience Platform]. 

Read more about the [implications of dataset and connection deletion](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=en#implications-of-deleting-data-components) in [!UICONTROL Customer Journey Analytics] and [!UICONTROL Adobe Experience Platform].
