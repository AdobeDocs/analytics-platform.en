---
title: Compare Analytics Source Connector data to Adobe Analytics
description: Understand differences in data when viewing similar reports in Adobe Analytics and Customer Journey Analytics.
role: Data Engineer, Data Architect, Admin
solution: Customer Journey Analytics
exl-id: dd273c71-fb5b-459f-b593-1aa5f3e897d2
feature: Troubleshooting
keywords: query service;Query service;sql syntax
---
# Compare Analytics Source Connector data to Adobe Analytics

As your organization adopts Customer Journey Analytics, it is possible to notice some differences in data between Adobe Analytics and Customer Journey Analytics. These differences are normal and can happen for several reasons. Customer Journey Analytics is designed to allow you to improve upon some of the limitations on your data in Adobe Analytics. This flexibility can cause some differences in how Customer Journey Analytics interprets data. Use this article to understand potential differences in how Customer Journey Analytics and Adobe Analytics treats your data.

This page assumes that you ingest Adobe Analytics data into Adobe Experience Platform using the [Analytics source connector](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html), then created a [connection](/help/connections/overview.md) and [data view](/help/data-views/data-views.md) in Customer Journey Analytics.

![The data flow from Adobe Analytics through the data connector to Adobe Experience Platform and to Custoer Journey Analytics using CJA connections.](assets/compare.png)

Consider the following possible reasons why data might differ between reporting platforms:

* **Different datasets or report suites**: Make sure that the report suite in Adobe Analytics and the report suite that the Source Connector derives data from are the same.
* **Calendar settings**: Report suites in Adobe Analytics contain a time zone and other calendar settings that you can configure. Similarly, data views in Customer Journey Analytics have a separate setting that you can control. Make sure that these settings match between products if parity is desired.
* **Additional datasets**: Customer Journey Analytics provides the capability to include multiple datasets within a single connection. These differences include additional event datasets, profile datasets, or lookup datasets. This capability is a key differentiator between Adobe Analytics and Customer Journey Analytics, allowing insight into cross-channel data.
* **Stitched datasets**: Adobe provides the ability to analyze person IDs between two datasets, resulting in a new dataset containing stitched IDs. These [stitched datasets](/help/stitching/overview.md) contain additional data beyond what an Adobe Analytics report suite offers.
* **Data Sources**: Customer Journey Analytics does not include any type of [Data Sources](https://experienceleague.adobe.com/en/docs/analytics/import/data-sources/overview) uploaded to an Adobe Analytics report suite, including summary data sources or transaction ID data sources.
* **Dimension and metric settings**: Within a data view, every dimension and metric contains its own settings that your organization can alter. These changes apply at the time the report is run, and is therefore applied retroactively. Dimension and metric settings in Adobe Analytics change how data is collected, making those changes apply from that point forward. If you changed component settings in either product, they can create reporting differences. If focusing on a specific dimension, make sure that the attribution and persistence settings match between Adobe Analytics and Customer Journey Analytics.

   >[!TIP]
   >
   >Adobe highly recommends that dimensions in Adobe Analytics use an allocation of '[!UICONTROL Most recent (last)]'. This allocation setting allows much more attribution flexibility in Customer Journey Analytics.

* **Visit definition**: In addition to individual dimension and metric settings, the data view itself contains settings that fundamentally change how vistor data is interpreted. For example, you can apply a segment to an entire data view (similar to a [Virtual report suite](https://experienceleague.adobe.com/en/docs/analytics/components/virtual-report-suites/vrs-about) in Adobe Analytics). You can also change the definition of a visit duration, or automatically start a new visit on any desired event. Any of these settings can have a notable impact on reporting differences between Customer Journey Analytics and Adobe Analytics.

## Checking record count between products

If all of the above settings appear similar and you want to at least validate the number of records between products, you can use the following steps:

1. In Adobe Experience Platform [Query Services](https://experienceleague.adobe.com/en/docs/experience-platform/query/home), run the following Total Records by timestamps query:

   ```sql
   SELECT
     Substring(from_utc_timestamp(timestamp,'{timeZone}'), 1, 10) AS Day,
     Count(_id) AS Records
   FROM  {dataset}
   WHERE   timestamp >= from_utc_timestamp('{fromDate}','UTC')
     AND timestamp < from_utc_timestamp('{toDate}','UTC')
     AND timestamp IS NOT NULL
     AND enduserids._experience.aaid.id IS NOT NULL
   GROUP BY Day
   ORDER BY Day;
   ```

1. In Adobe Analytics [Data feeds](https://experienceleague.adobe.com/en/docs/analytics/export/analytics-data-feed/data-feed-overview), generate feed files for the desired date range. Count the number of rows within each file, identifying and excluding the following rows:

   * `exclude_hit` is not `0` (Data excluded from Analysis Workspace in both products)
   * `hit_source` is `0`, `3`, `5`, `7`, `8`, `9`, or `10` (Data Sources and other non-hit data)
   * `page_event` is `53` or `63` (Streaming Media keep-alive hits)

   Rows matching any of the above criteria are excluded from the Analytics Source Connector ingestion workflow, and therefore should also be excluded when counting data feed rows.

1. The total records in Query Services should match the number of rows in a data feed for the same time period.
