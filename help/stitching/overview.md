---
title: Stitching Overview
description: Learn about the concepts, benefits, prerequisites, and limitations of identity stitching.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: 1c42efac-b3d2-437b-8b0b-9c6fdfed8520
role: Admin
---
# Stitching overview

>[!NOTE]
>
>You must have the Customer Journey Analytics **Select** package or higher (for [field-based stitching](fbs.md)) or the Customer Journey Analytics **Prime** package or higher (for [graph-based stitching](gbs.md)) to use the functionality described in this section. Contact your administrator if you're unsure which Customer Journey Analytics package you have.

Identity stitching (or simply, stitching) is a powerful feature that elevates an event dataset's suitability for cross-channel analysis. Cross-channel analysis is a main use case for Customer Journey Analytics. The feature allows you to combine and run reports seamlessly on multiple datasets from different channels, based on a common identifier (person ID).

When you combine datasets with similar person IDs, attribution is carried over across devices and channels. For example, a user visits your site through an advertisement on their desktop computer. The user buys a product but then the user encounters an issue with the order. The user then gives your customer service team a call to help resolve the issue. With cross-channel analysis, you can attribute call center events to the ad that the user originally clicked.

Unfortunately, not all event-based datasets that are part of your connection in Customer Journey Analytics are sufficiently populated with data to support this attribution out of the box. Especially, web-based or mobile-based experience datasets often don't have actual person ID information available on all events.

Stitching rekeys identities within one dataset's rows to ensure the desired person ID info is available on as many events possible. Stitching looks at user data from both authenticated and unauthenticated sessions to determine the common person ID value that can be used. This rekeying resolves disparate records to a single person ID for analysis at the person level, rather than at the device or cookie level. However, if a common person ID value cannot be determined, the persistent ID value is used instead.

Customer Journey Analytics supports two types of stitching: [field-based stitching](fbs.md) and [graph-based stitching](gbs.md).

## Prerequisites

>[!IMPORTANT]
>
>Failure to meet all prerequisites can result in the inability to conduct cross-channel analysis properly.

Before using stitching, make sure that your organization is prepared with the following:

- Stitching includes merging authenticated and unauthenticated user data. Ensure that you comply with applicable laws and regulations, including obtaining necessary end-user permissions, before activating stitching on an event dataset.

- Import the desired data into Adobe Experience Platform:
  
  - For Adobe Analytics data, see [Utilizing Adobe Analytics report suite data in Customer Journey Analytics](/help/getting-started/aa-vs-cja/aa-data-in-cja.md). 
  - For other types of data, see [Create a schema](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/tutorials/create-schema-ui) and [Ingest data](https://experienceleague.adobe.com/en/docs/experience-platform/ingestion/home) in the Adobe Experience Platform documentation.

You benefit from cross-channel analysis if you combine one or more of your stitched datasets with other datasets, such as call center data, as part of defining your Customer Journey Analytics connection. This connection configuration assumes that those other datasets already contain a person ID from the same namespace on as many rows possible.

Once your organization meets generic [prerequisites](overview.md#prerequisites), understands common [limitations](overview.md#limitations), and also stitching method specific ([field-based](fbs.md) and [graph-based](gbs.md)) prerequisites and limitations, you can follow these steps to request and start using stitching in Customer Journey Analytics.

## Limitations

Stitching is a groundbreaking and robust feature, but has limitations on how it can be used. 

- Only event datasets are supported. Other datasets, such as lookup datasets, are not supported.
- Stitching does not transform the field used for stitching in any manner. Stitching uses the value in the specified field as it exists in the unstitched dataset within the data lake. 
- The stitching process is case-sensitive. For example, identity values `Bob` and `BOB` are treated as two separate people.

Ensure you do not confuse stitching with:

- The merge of two or more datasets. Stitching applies to one dataset only. Merging of datasets occurs as a result of setting up a Customer Journey Analytics connection and selecting the same person ID across the selected datasets in the connection.

- The join of two datasets. In Customer Journey Analytics, a join is often used for lookups or classifications in Analysis Workspace. Although stitching uses join functionality, the process itself involves more than joins.
  

## Options

The Customer Journey Analytics package that you are entitled to determines the available stitching methods, options for the initial backfill duration, lookback window, replay frequency, and maximum number of datasets permitted for stitching. See the [Customer Journey Analytics product description](https://helpx.adobe.com/legal/product-descriptions/customer-journey-analytics.html) for more details. Decide on the available options before you enable stitching.

| | Customer Journey Analytics<br/>Select | Customer Journey Analytics<br/>Prime | Customer Journey Analytics<br/>Ultimate |
|---|---|---|---|
| Available stitching methods | Field-based stitching | Field-based stitching<br/>Graph-based stitching | Field-based stitching<br>Graph-based stitching</li> |
| One-time stitching backfill duration | 13 months | 13 months | 25 months |
| Lookback window and replay frequency | 1 day, every day<br/>up to 7 days, weekly | 1 day, every day<br/>up to 14 days, weekly| 1 day, every day<br/>up to 30 days, weekly |
| Maximum number of datasets permitted for stitching | 5 | 15 | 50 |

## Enable stitching

You can enable stitching in two ways:

- [Request to enable stitching](/help/stitching/use-stitching.md) (deprecated). Once approved, a duplicate dataset is created for the dataset for which you have requested stitching. This duplicate dataset contains an additional column with the stitched identifier. You have to create a new or edit an existing connection that includes the stitched dataset to use the stitched data in Customer Journey Analytics.
- [Enable stitching in the Connections interface](/help/stitching/use-stitching-ui.md). When you configure stitching for a dataset in the Connections interface, the stitching occurs on the fly, during the ingestion of data from that dataset in Customer Journey Analytics.


## Journey Optimizer datasets

Stitching supports the following automatically generated Journey Optimizer datasets:

- AJO Journey Step Events
- AJO Inbound Activity Event Dataset
- AJO Surfaces Dataset
- AJO Message Feedback Event Dataset* AJO Push Tracking Experience Event Dataset
- AJO Email Tracking Experience Event Dataset
- AJO BCC Feedback Event Dataset
- AJO Live Activities Feedback Event Dataset
- AJO ExD Decision Event Dataset

>[!MORELIKETHIS]
>
>[Field-based stitching](fbs.md)
>[Graph-based stitching](gbs.md)
>[Use stitching](use-stitching.md)
>[Validate stitching](validate.md)
>[FAQ on stitching](faq.md)

