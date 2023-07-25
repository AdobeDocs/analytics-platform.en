---
title: Compare your Adobe Analytics data to Customer Journey Analytics data
description: Learn how to compare your Adobe Analytics data to data in Customer Journey Analytics
role: Data Engineer, Data Architect, Admin
solution: Customer Journey Analytics
exl-id: dd273c71-fb5b-459f-b593-1aa5f3e897d2
feature: Troubleshooting
---
# Compare your Adobe Analytics data to Customer Journey Analytics data

As your organization adopts Customer Journey Analytics, you may notice some differences in data between Adobe Analytics and Customer Journey Analytics. This is normal and can occur for several reasons. Customer Journey Analytics is designed to allow you to improve upon some of the limitations on your data in AA. However, unexpected and unintended discrepancies can occur. This article is designed to help you diagnose and solve for those differences so that you and your team can use Customer Journey Analytics unimpeded by concerns about data integrity.

Let's assume you ingested Adobe Analytics data into Adobe Experience Platform via the [Analytics source connector](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html), and then created a Customer Journey Analytics connection using this dataset. 

![data flow](assets/compare.png)

Next, you created a data view and while subsequently reporting on this data on Customer Journey Analytics, you noticed discrepancies with the reporting results in Adobe Analytics.

Here are some steps to follow to compare your original Adobe Analytics data with the Adobe Analytics data that is now in Customer Journey Analytics.

## Prerequisites

* Make sure the Analytics dataset in Adobe Experience Platform contains data for the date range you are investigating.

* Make sure the report suite that you selected in Analytics matches the report suite that was ingested into Adobe Experience Platform.

## Step 1: Run the Occurrences metric in Adobe Analytics

The [Occurrences](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html) metric shows the number of hits where a given dimension was set or persisted.

1. In Analytics > [!UICONTROL Workspace], drag the date range you want to report on as a dimension into a [!UICONTROL Freeform] table.

1. The [!UICONTROL Occurrences] metric is automatically applied to that date range.

1. Save this project so that you can use it in the comparison.

## Step 2: Compare the results to [!UICONTROL Total records by timestamps] in Customer Journey Analytics

Now compare the [!UICONTROL Occurrences] in Analytics to the Total records by timestamps in Customer Journey Analytics.

Total Records by timestamps should match with Occurrences, provided that no records were dropped by the Analytics Source connector - see the section below. 

>[!NOTE]
>
>This works for regular mid values datasets only, not stitched dataset (via [Cross-Channel Analytics](/help/cca/overview.md)). Please note that accounting for the Person ID being used in Customer Journey Analytics is critical for making the comparison work. That may not always be easy to replicate in Adobe Analytics, especially if Stitching has been turned on. 

1. In Adobe Experience Platform [Query Services](https://experienceleague.adobe.com/docs/experience-platform/query/best-practices/adobe-analytics.html), run the following [!UICONTROL Total Records by timestamps] query:

        ```
        SELECT Substring(from_utc_timestamp(timestamp,'{timeZone}'), 1, 10) as Day, \ 
        Count(_id) AS Records 
        FROM  {dataset} \ 
        WHERE timestamp>=from_utc_timestamp('{fromDate}','UTC') \ 
        AND timestamp<from_utc_timestamp('{toDate}','UTC') \ 
        AND timestamp IS NOT NULL \ 
        AND enduserids._experience.aaid.id IS NOT NULL  \ 
        GROUP BY Day \ 
        ORDER BY Day; 

        ```

1. In [Analytics Data Feeds](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html), identify from the raw data whether some rows might have been filtered out by the Analytics Source connector. 

   The [Analytics Source connector](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html) might filter certain rows during the transformation to XDM schema. There can be multiple reasons for the whole row to be unfit for transformation. If any of the following Analytics fields have these values, the whole row will be filtered out. 

   | Analytics field | Values that cause a row to be dropped |
   | --- | --- |
   | Opt_out | y, Y |
   | In_data_only | Not 0 |
   | Exclude_hit | Not 0 |
   | Bot_id | Not 0 |
   | Hit_source | 0, 3, 5, 7, 8, 9, 10 |
   | Page_event | 53, 63 |
   
   For more information about hit\_source see: [Data column reference](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=en). For more information about page\_event see: [Page Event Lookup](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-page-event.html?lang=en).
   
1. If the connector filtered rows, subtract those rows from the [!UICONTROL Occurrences] metric. The resulting number should match the number of events in the Adobe Experience Platform datasets.

## Why records might be filtered or skipped during ingestion from Adobe Experience Platform

Customer Journey Analytics [Connections](/help/connections/create-connection.md) allow you to bring and join multiple datasets together based on a common Person ID across the datasets. On the backend, we apply deduplication: full outer join or union on event datasets based on timestamps, and then inner join on profile and lookup dataset, based on the Person ID. 

Here are some of the reasons why records might be skipped while ingesting data from Adobe Experience Platform. 

* **Missing Timestamps** – If timestamps are missing from event datasets, those records will be totally ignored or skipped during ingestion. 
 
* **Missing Person IDs** – Missing Person IDs (from the events dataset and/or from profile/lookup dataset) cause those records to be ignored or skipped. The reason is that there are no common IDs or matching keys to join the records. 
 
* **Invalid or Large Person IDs** – With invalid IDs, the system cannot find a valid common ID among the datasets to join. In some cases, the person ID column has invalid Person IDs such as "undefined", or "00000000". A Person ID (with any combination of numbers and letters) that appears in an event more than 1 million times per month cannot be attributed to any specific user or person. It will be categorized as invalid. Those records cannot be ingested into the system and result in error-prone ingestion and reporting. 
