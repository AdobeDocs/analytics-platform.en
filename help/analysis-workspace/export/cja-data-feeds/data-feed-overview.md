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

## Compare Customer Journey Analytics and Adobe Analytics Analytics data feed functionality

Data feeds in both Customer Journey Analytics and Adobe Analytics allow you to export raw data to third-party platforms. If you previously used data feeds in Adobe Analytics, use the following table to understand important functionality differences when using data feeds in Customer Journey Analytics:


| **Data feed functionality** | **Customer Journey Analytics** | **Adobe Analytics** |
|--------|--------|--------|
| Data input | Cross-channel data input, such as web data, call center data, point-of-sale data, and more  | Web and mobile data input only |
| Data processing |  |
| Ability to change historical data | Each of the following features can affect historical data: stitching, derived fields, data prep, segmentation, and the reporting window | Historical data cannot be changed (unaffected by processing rules and VISTA rules) |
| Segmentation | Segmets can be applied in data feed output | Segments cannot be applied in data feed output |
| Stitching | Stitching across multiple datasets (to support cross-channel analysis) | Stitching is not supported |
| Schema | Uses structured, hierarchical fields, potentially containing multiple dimensions and metrics within a single column (arrays, arrays within arrays) | Uses a product list, with a long string of proprietary semicolon-delimited fields.|
| Lookups | Not used, because browser dimensions are included in the Data View | Used to match a number from a data feed column and match it to an actual value |
| Output file format | Parquet (supports structured fields and is accepted by modern data warehouses) | C3 |
| Delivery destinations | <ul><li>Cloud destinations (Amazon S3, Azure RBAC, Azure SAS, and Google Cloud Platform)</li></ul> | <ul><li>Cloud destinations (Amazon S3, Azure RBAC, Azure SAS, and Google Cloud Platform)</li><li>SFTP</li></ul>|
| Delivery frequency | Hourly and daily feeds | Hourly, daily, and 15-minute feeds. |
| Definition of a "Feed Window" | Delivers data received in the last hour (may include older hits within the reporting window). Late-arriving hits are always enabled. | Delivers hits belonging to the hour/day, optionally including late-arriving hits if explicitly enabled. |
| Late-Arriving Hits | Always supported; controlled via configurable "reporting window." No option to disable. | Optional; only available in new UI; requires explicit configuration. |
| Reporting Window | Required for sessions, persistence, and segments. Controls lookback needed to calculate them. | Not used for DF; persistence & sessionization baked into raw data. |
| Session Definition | Defined in Data View → affects DF. | Defined at collection time; DF only uses raw sessionization. |
| Segment Containers (Person, Session, Hit) | Person containers use entire reporting window; can expand DF hit output based on segment logic. | No segment application to DF. |
| Dimension Allocation & Expiration | Controlled per dimension (independent from reporting window). | Pre-calculated; fixed in collected data. |
| Coverage of Reporting Window in DF Output | DF outputs only part of the reporting window (only current window), even though session/segment logic may examine the broader window. | Entire DF output is limited to the fixed window (hour/day/15-min). |
| Handling Out-of-Order Hits | Automatically reorders based on timestamps; persists original values (no change feed). | No support; relies on ingest-time ordering. |
| Persistence Model | Flexible; based on reporting window evaluation. | Only "Last Touch" (Most Recent) and "First Touch" (Original). |


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
