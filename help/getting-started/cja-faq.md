---
title: Customer Journey Analytics FAQ
description: Customer Journey Analytics - Frequently Asked Questions.
---

# Frequently asked questions

## Prerequisites

| Question | Answer |
| --- | --- |
| Do I need [!UICONTROL Private Device Graph] or [!UICONTROL Device Coop] for [!UICONTROL Customer Journey Analytics]? | No, [!UICONTROL Private Device Graph] or [!UICONTROL Device Coop] are not required for [!UICONTROL Customer Journey Analytics]. In fact, they are not yet supported. |
| Do I need [!UICONTROL Experience Cloud ID] (ECID) for [!UICONTROL Customer Journey Analytics]? | No, [!UICONTROL Customer Journey Analytics] supports any ID in a dataset, whether that's [!UICONTROL ECID] or any other ID you choose. |
| What if I need to ETL (Extract, Transform, Load) my data prior to [!UICONTROL Customer Journey Analytics]? | Today, you need to work with an ETL partner (Unifi or Informatica) if you need to transform your data before putting it into AEP. If you need ETL after the data has already been ingested, [!UICONTROL Adobe Experience Platform Query Services] provides some limited options. |

## Stitching data

| Question | Answer |
| --- | --- |
| Can [!UICONTROL Customer Journey Analytics] "stitch" across devices or across datasets? | Yes. [!UICONTROL Customer Journey Analytics] is a "bring-your-own-ID" analytics system. We released a stitching solution in November of 2020. Learn more. |
| Is stitching from anonymous behavior to authenticated behavior supported? | No, not yet. |

## Getting data into [!UICONTROL Customer Journey Analytics]

| Question | Answer |
| --- | --- |
| Can I combine data from different [!UICONTROL Adobe Experience Platform] sandboxes in one [!UICONTROL Customer Journey Analytics] connection? | No, you cannot access data across sandboxes. You can combine only datasets that are located within the same sandbox. [Learn more...](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-connections/create-connection.html#select-sandbox-and-datasets) |
| What is the expected latency for [!UICONTROL Customer Journey Analytics] on [!UICONTROL Adobe Experience Platform]? | <ul><li>Under normal load: < 60 minutes<br>**Note:** In case of an unusually high volume of data flow through the pipeline, it could take up to 24 hours.</li><li>Backfill data (up to 13 months of data, irrespective of size): < 4 weeks</li></ul> |
| How do I connect online data to offline data in [!UICONTROL Customer Journey Analytics]? | [!UICONTROL Customer Journey Analytics] is a "bring your own ID" analytics system. As long as the person ID matches between datasets, [!UICONTROL Customer Journey Analytics] can connect segments, attribution, flow, fallout, etc. across datasets. |
| How do I bring my offline data into [!UICONTROL Customer Journey Analytics]? | You must first bring any data to Experience Platform before you can use it with [!UICONTROL Customer Journey Analytics]. The Experience Platform's data on-boarding team can help provide recommendations or consulting for you, if needed. |
| How do I get [!UICONTROL Adobe Analytics] data into [!UICONTROL Customer Journey Analytics]? | [!UICONTROL Adobe Analytics] data can be connected to Experience Platform through the [Adobe Analytics Source Connector](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/analytics.html). Most [!UICONTROL Adobe Analytics] fields are brought over in XDM format, but other fields are not yet available (like [!UICONTROL Marketing Channels] dimensions). |
| How long does it take to assemble dataset elements into a data view? | A few hours to get started, and a few days to backfill the last 13 months of data. |
| Is it necessary to bring PII data to establish connections between the data? | No, you can use any ID, including a hash of a customer ID, which is not PII. |

## Traditional [!UICONTROL Adobe Analytics] components

| Question | Answer |
| --- | --- |
| What does this mean for our traditional [!UICONTROL Adobe Analytics] product? | [!UICONTROL Customer Journey Analytics] is our next-generation analytics product. Evolving from our current products to [!UICONTROL Customer Journey Analytics] will take years and a lot of coordination. For more information, review [Customer Journey Analytics feature support](/help/getting-started/cja-aa.md). |
| Can I share segments from [!UICONTROL Customer Journey Analytics] to AEP or other solutions? | Not yet. We’re looking at new, innovative ways to share segments from [!UICONTROL Customer Journey Analytics] to AEP in the future that don’t have such a long delay. That said, you can share the output of Query Services to Unified Profile as a potential workaround. |
| What happened to my old eVar setting? | eVars, props, and events in the traditional Adobe Analytics sense no longer exist in [!UICONTROL Customer Journey Analytics]. You have unlimited schema elements (dimensions, metrics, list fields). So all of the attribution settings you used to apply during the data collection process are now applied at query time. |
| Where are all my session and variable persistence settings now? | [!UICONTROL Customer Journey Analytics] applies all of these settings at report time, and these settings now live in Data Views. Changes to these settings are now retroactive, and you can have multiple versions by using multiple Data Views! |
| What happens to our existing segments/calculated metrics? | [!UICONTROL Customer Journey Analytics] no longer uses eVars, props, or events and instead uses any AEP schema. This means none of the existing segments or calc metrics are compatible with [!UICONTROL Customer Journey Analytics]. |
| How does [!UICONTROL Customer Journey Analytics] handle `Uniques Exceeded` limitations? | [!UICONTROL Customer Journey Analytics] has no unique value limitations, so no need to worry about them! |
| If I am an existing [!DNL Data Workbench] customer, can I move to [!UICONTROL Customer Journey Analytics] right now? | It depends. If you rely heavily on the Unified Customer Process (UCP), you will want to wait until we have stitching implemented. If you already have high customer authentication rates, or if you want all your data in one place, or would like to get rid of eVars, Customer Journey Analytics might be a good fit. |

## Implications of deleting data components

When it comes to deletion, we are concerned with 6 components: sandbox, schema, dataset, connection, data view, and Workspace projects. Here are some possible scenarios around deleting any of these components:

| What if I... | This happens... |
| --- | --- |
| Delete a sandbox in [!UICONTROL Adobe Experience Platform]? | Deleting a sandbox will stop data flow to any [!UICONTROL Customer Journey Analytics] connections to datasets in that sandbox. Currently, Connections in CJA tied to that sandbox will not automatically be deleted. |
| Delete a schema in [!UICONTROL Adobe Experience Platform], but not the dataset/s associated with this schema? | [!UICONTROL Adobe Experience Platform] does not allow for the deletion of schemas that have one or more datasets associated with them. However, an Admin with the appropriate set of rights can delete the datasets first and then delete the schema.  |
| Delete a dataset in [!UICONTROL Adobe Experience Platform]? | Deleting a dataset in AEP will stop data flow from that dataset to any Connections that include that dataset. Any data from that dataset is not automatically deleted from associated CJA Connections. |
| Delete a dataset in [!UICONTROL Customer Journey Analytics]? | Currently, you cannot delete a dataset within a connection that has been saved. You would have to delete the whole connection and start over. (However, you can delete a dataset in [!UICONTROL Adobe Experience Platform].) |
| Delete a batch from a dataset (in [!UICONTROL Adobe Experience Platform])? | If a batch is deleted from an [!UICONTROL Adobe Experience Platform] dataset, the same batch will be removed from any CJA Connections that contain that specific batch.  CJA is notified of batch deletions in [!UICONTROL Adobe Experience Platform]. |
| Delete a batch **while it is being ingested** into [!UICONTROL Customer Journey Analytics]? | If there is only one batch in the dataset, no data or partial data from that batch will appear in [!UICONTROL Customer Journey Analytics]. The ingestion will be rolled back. If, for example, there are 5 batches in the dataset and 3 of them have already been ingested when the dataset was deleted, data from those 3 batches will appear in [!UICONTROL Customer Journey Analytics]. |
| Delete a connection in [!UICONTROL Customer Journey Analytics]? | An error message will indicate that:<ul><li>Any data views created for the deleted connection will no longer work.</li><li> Similarly, any Workspace projects that depend on data views in the deleted connection will cease working.</li></ul> |
| Delete a data view in [!UICONTROL Customer Journey Analytics]? | An error message will indicate that any Workspace projects that depend on this deleted data view will cease working. | 
| Delete a Workspace project in [!UICONTROL Customer Journey Analytics]? | You can either recreate the project or you can use a workaround to recover the project. Just go to [!UICONTROL Admin > Logs > Usage and Access Log], find the deleted project and copy its ID. Then open any Workspace project and update the ID in the URL with the copied one. Then save the project. |
