---
title: Cross Channel Journey Analysis
description: Analyze and extract insights from customer interactions across the customer journey.
exl-id: 285532b1-eb37-4984-9559-054a18515ddf
solution: Customer Journey Analytics
feature: Use Cases, Cross-Channel Analysis
---
# Cross-channel analysis

Cross-channel analysis enables a single consolidated view of customer behavior across various channels by unifying data from various web, mobile, and offline properties. For example, you can use this consolidated view to analyze customer interactions across desktop and mobile to understand customer behavior and extract insights to optimize digital customer experiences. You can also analyze customer interactions across channels, including digital and offline channels such as support interactions and in-store purchases to better understand and optimize the customer journey.

## Workflow

![Cross channel architecture](../assets/cca-architecture.png)

## Implementation Steps

1. [Create schemas](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html) for data to be ingested.
1. [Create datasets](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/create-datasets-and-ingest-data.html) for data to be ingested.
1. [Ingest data into Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/understanding-data-ingestion.html):
   1. Event-based data ![event](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg) from website or mobile app through the Edge Network or Analytics Data Connector.
   2. Profile data ![profile](https://spectrum.adobe.com/static/icons/workflow_18/Smock_User_18_N.svg) (for example from a CRM system, call center application, loyalty application).
   3. Lookup data ![lookup](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) (for example product name, category from a product information system).

1. Use a common namespace ID across datasets. Use [Stitching](../../stitching/overview.md) to elevate any event-based dataset ![data refresh](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataRefresh_18_N.svg) in respect to providing the common ID on each row. Note that Customer Journey Analytics does not currently use the Experience Platform Profile or Identity services for stitching.
1. Perform any custom data preparation to ensure a common key across time series datasets to be ingested into Customer Journey Analytics.
1. Give lookup data a primary ID that can join to a field in the event data. Counts as rows in licensing.
1. Set the same primary ID for profile data as the primary ID of the event data.
1. [Create a connection](../../connections/overview.md) to ingest the relevant datasets from Experience Platform to Customer Journey Analytics.
1. [Create a data view](/help/data-views/create-dataview.md) on the connection to select the specific dimensions and metrics to be included in the view. Attribution and allocation settings are also configured in the data view. These settings are computed at report time.
1. [Create a project](/help/analysis-workspace/home.md) to configure dashboards and reports within Analysis Workspace.

## Considerations

When establishing this workflow, make sure that you take the following points into consideration.

* Analyzing data across channels requires the same ID namespace on every record.
* The union process of unifying disparate datasets requires a common primary person/entity key across the datasets.
* Secondary key-based unions are currently not supported.
* The stitching process allows for rekeying identities in rows based on subsequent transient ID records, such as an authentication ID. This allows for resolving disparate records to a single ID for analysis at the person level rather than at the device or cookie level.
* Objects and attributes of the same XDM field merge into one dimension in Customer Journey Analytics. To  merge multiple attributes from various datasets into the same Customer Journey Analytics dimension, the datasets should reference the same XDM field or schema.

