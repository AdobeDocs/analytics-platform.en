---
description: Learn how to use data feeds to get raw data out of Customer Journey Analytics. Find out the prerequisites for using data feeds what to do next.
keywords: clickstream;data feed;datafeed;Data Feed
title: Analytics Data Feed Overview
feature: Data Feeds
exl-id: 2cfff9ad-cdb5-4ae9-a266-4f3d3d046f0c
---
# Data feeds overview

Data feeds are a powerful way to get raw data out of Customer Journey Analytics. This raw data can be used in other platforms outside of Adobe to use at your organization's discretion. Data is delivered in hourly batches at the conclusion of each hour, or in daily batches at the conclusion of each day.

## Prerequisites

Make sure that you meet all the following requirements before using data feeds.

* A working implementation with data being ingested into Adobe Customer Journey Analytics. For more information, see [Data ingestion overview](/help/implement/launch/validate-publish-prod.md).
* Your account is an Analytics product admin, or your account belongs to a product profile with access to data feeds. <!--???-->
* A bucket configured on Amazon S3, Google Cloud Platform, Azure RBAC, or Azure SAS.<!--Which cloud providers do we support??-->
* (Legacy: Required only for legacy FTP and SFTP destination types) Have an FTP site and credentials handy (FTP credentials provided by your organization.)<!--Delete???-->

## Compare Customer Journey Analytics and Adobe Analytics data feed functionality

Data feeds in both Customer Journey Analytics and Adobe Analytics allow you to export raw data to third-party platforms. If you previously used data feeds in Adobe Analytics, use the following table to understand important functionality differences when using data feeds in Customer Journey Analytics:


| **Functionality** | **Customer Journey Analytics data feeds** | **Adobe Analytics data feeds** | 
|--------|--------|--------|
| Data input | Supports cross-channel data input, including web data, call center data, point-of-sale data, and more.  | Supports web and mobile data input only. |
| Data processing | Data is processed at report time, and therefore many reporting features in Customer Journey Analytics can be used to change historical data, such as stitching, derived fields, data prep, segmentation, and the reporting window  | Data is processed at collection time, and therefore reporting features such as processing rules, VISTA rules, stitching, and segmentation do not affect historical data  |
| Segmentation | Segmets can be applied | Segments cannot be applied|
| Stitching | Stitching can be used to join multiple datasets (to support cross-channel analysis) | Stitching is not supported |
| Schema | Uses structured, hierarchical fields, potentially containing multiple dimensions and metrics within a single column (arrays; arrays within arrays) | Uses a product list with a long string of proprietary, semicolon-delimited fields.|
| Lookups | Not used<p>Browser dimensions are included in the data view.</p> | Used to match a number from a data feed column to an actual value. |
| Output file format | Parquet (supports structured fields and is accepted by modern data warehouses) | C3 |
| Delivery destinations | Cloud destinations, including Amazon S3, Azure RBAC, Azure SAS, and Google Cloud Platform. | Cloud destinations, including Amazon S3, Azure RBAC, Azure SAS, and Google Cloud Platform.<p>Also supports SFTP.</p>|
| Delivery frequency | Hourly and daily feeds<p>Late-arriving hits that occur within the **[!UICONTROL Reporting window]** are always included.</p> | Hourly, daily, and 15-minute feeds<p>Late-arriving hits are configurable.</p> |
| Late-arriving hits | Always included <p>The lookback window for these hits is controlled through the **[!UICONTROL Reporting window]** configuration option.</p><p>Hits are automatically reordered based on timestamps; original values are persisted (no change feed).</p> | Can be included or excluded. Configurable with the **[!UICONTROL Late-arriving hits]** configuration option.<p>The lookback window for these hits is configured through the **[!UICONTROL Lookback window]** configuration option that is available for this specific purpose.</p><p>Hits are shown in the order in which they are received; they are not reordered according to timestamp.</p> |
| Reporting window (Customer Journey Analytics only) | The cutoff for late or out-of-order hits that have timestamps within the **[!UICONTROL Delivery frequency]** that is selected (**[!UICONTROL Hour]** or **[!UICONTROL Day]**), but that arrive after the data feed job finishes processing for the hour or day (such as through timestamped hits or data sources). <p>When a data feed processes data, it looks at data delivered within the set delivery frequency (**[!UICONTROL Hour]** or **[!UICONTROL Day]**). The reporting window ensures that data is included even if it arrives after a feed finished processing data within the delivery frequency.</p><p>Every time a data feed processes data, it looks at any data that arrived and batches them in the next data feed file that is sent.</p><p>Required for sessions, persistence, and segments.</p><p>Not used for dimensions (dimensions are controlled per dimension based on the dimension's allocation and expiration).</p> | N/A<p>See "Lookback window"</p> |
| Lookback window (Adobe Analytics only) | N/A<p>See "Reporting window"</p> |  The cutoff for late or out-of-order hits that are delivered outside of the **[!UICONTROL Delivery frequency]** that is selected (**[!UICONTROL Hour]**, **[!UICONTROL Day]**, or **[!UICONTROL 15 minutes]**). <p>Not used for persistence, sessions, or dimensions (these are included in the raw data that is collected).</p> |
| Out-of-order hits | When hits are received, they are automatically reordered based on the timestamps of when the hits ocurred.<p>Original values are persisted (no change feed).</p> | Maintains the order of when the hit was received, regardless of the actual timestamp of when the hit ocurred. |
| Session definition | Defined in the data view | Defined at collection time <p>Uses only raw sessionization</p> |
| Segment containers |  (Person, Session, Event) Person containers use the entire reporting window; can expand DF hit output based on segment logic. | Not used |
| Calculated metrics | | Not used |
| Coverage of Reporting Window in DF Output | DF outputs only part of the reporting window (only current window), even though session/segment logic may examine the broader window. | Entire DF output is limited to the fixed window (hour/day/15-min). |
| Persistence Model | Flexible; based on reporting window evaluation. | Only "Last Touch" (Most Recent) and "First Touch" (Original). |


## Compare data processing between Adobe Analytics and Customer Journey Analytics data feeds

Use the following graphic and table to understand important differences in how data is processed for Adobe Analytics data feeds and Customer Journey Analytics data feeds:

![Data feed data processing](assets/data-feeds-data-processing.png)

| Data feed configuration | Adobe Analytics | Customer Journey Analytics |
|---------|----------|---------|
| Data feed window / Delivery frequency | 1 hour | 1 hour |
| Lookback window | 23 hours | N/A |
| Reporting window | N/A | 24 hours |
| Initial backfill window | 7 days | 7 days |
| Hits | Only Hit 5 is in the data feed window. However, because a lookback is configured and it includes Hit 4 and Hit 3, they are also included in the data feed. (If a lookback was not configured, only Hit 5 would be included in the data feed.) <p>Hits are shown in the data feed in the order they were received, as follows: Hit 4, Hit 3, Hit 5.</p> | Only Hit 5 is in the data feed window. However, because the reporting window also includes Hit 4 and Hit 3, they are also included in the data feed.<p>Hits are reordered in the data feed according to their timestamp, as follows: Hit 3, Hit 4, Hit 5.</p> |

Adobe Analytics data feeds



Delivery frequency
Late-arriving hits
Reporting window
Lookback window
Out-of-order hits




## Next steps

The following resources help you understand the basic workflow of obtaining data feeds. After you understand the basic workflow, you can work with teams within your organization to store or ingest raw data into a database.

* [Data feed best practices](/help/export/analytics-data-feed/data-feeds-best-practices.md): Best practices for creating and managing data feeds.
* [Create a data feed](create-feed.md): Technical details for creating a data feed, explaining individual fields in more detail
* [Manage data feeds](df-manage-feeds.md): Learn more about navigating the data feed interface
* [Data feed contents](c-df-contents/datafeeds-contents.md): Understand what is inside the compressed file <!-- Is this still the output users can download from the destination? I aske Jun. -->
* [Data column definitions](c-df-contents/datafeeds-reference.md): A comprehensive list of all available columns.

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Navigate the data feed interface](https://video.tv.adobe.com/v/25452?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]



>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Find your data feed id](https://video.tv.adobe.com/v/335747?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]
