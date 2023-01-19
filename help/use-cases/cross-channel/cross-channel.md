---
title: Cross Channel Journey Analysis
description: Analyze and extract insights from customer interactions across the customer journey.
exl-id: 285532b1-eb37-4984-9559-054a18515ddf
solution: Customer Journey Analytics
feature: Use Cases
---
# Cross Channel Journey Analysis

Have a single consolidated view of customer behavior across various channels by unifying data from various web, mobile, and offline properties. For example, you can use this consolidated view to analyze customer interactions across desktop and mobile to understand customer behavior and extract insights to optimize digital customer experiences. You can also analyze customer interactions across channels, including digital and offline channels such as support interactions and in-store purchases to better understand and optimize the customer journey.

## Architecture

![Cross channel architecture](../assets/cross-channel-architecture.svg)

## Implementation Steps

1. [Create schemas](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html) for data to be ingested.
1. [Create datasets](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/create-datasets-and-ingest-data.html) for data to be ingested.
1. [Ingest data into Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/understanding-data-ingestion.html).
1. Use a common namespace ID across datasets, or use [Cross-Channel Analytics](/help/cca/overview.md) to link people together. Note that Customer Journey Analytics does not currently use the Experience Platform Profile or Identity services for stitching.
1. Perform any custom data preparation to ensure a common key across time series datasets to be ingested into Customer Journey Analytics.
1. Give lookup data a primary ID that can join to a field in the event data. Counts as rows in licensing.
1. Set the same primary ID for profile data as the primary ID of the event data.
1. Configure a data connection to ingest data from Experience Platform to Customer Journey Analytics.
1. [Create a data view](/help/data-views/create-dataview.md) on the connection to select the specific dimensions and metrics to be included in the view. Attribution and allocation settings are also configured in the data view. These settings are computed at report time.
1. Create a project to configure dashboards and reports within Analysis Workspace.

## Considerations

When establishing this workflow, make sure that you take the following points into consideration.

* Analyzing data across channels requires the same ID namespace on every record.
* The union process of unifying disparate datasets requires a common primary person/entity key across the datasets.
* Secondary key-based unions are currently not supported.
* The field-based identity stitching process allows for rekeying identities in rows based on subsequent transient ID records, such as an authentication ID. This allows for resolving disparate records to a single ID for analysis at the person level rather than at the device or cookie level.
* Objects and attributes of the same XDM field merge into one dimension in Customer Journey Analytics. To  merge multiple attributes from various datasets into the same Customer Journey Analytics dimension, the datasets should reference the same XDM field or schema.
