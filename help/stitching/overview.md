---
title: Stitching overview
description: Overview of stitching
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: 1c42efac-b3d2-437b-8b0b-9c6fdfed8520
role: Admin
---
# Stitching overview

>[!NOTE]
>
>You must have the **Select** package or higher (for [field-based stitching](fbs.md)) or **Prime** package or higher (for [graph-based stitching](gbs.md)) to use the functionality described in this section. Contact your administrator if you're unsure which Customer Journey Analytics package you have.

Identity stitching (or simply, stitching) is a powerful feature that elevates an event dataset's suitability for cross-channel analysis. Cross-channel analysis is a main use case that Customer Journey Analytics can handle, allowing you to combine and run reports seamlessly on multiple datasets from different channels, based on a common identifier (person ID).

When you combine datasets with similar person IDs, attribution is carried over across devices and channels. For example, a user first visits your site through an advertisement on their desktop computer. That user encounters an issue with their order, then gives your customer service team a call to help resolve it. With cross-channel analysis, you can attribute call center events to the ad that they originally clicked.

Unfortunately, not all event-based datasets that are part of your connection in Customer Journey Analytics are sufficiently populated with data to support this attribution out of the box. Especially, web-based or mobile-based experience datasets often don't have an actual person ID information available on all events.

Stitching allows rekeying identities within one dataset's rows, making sure the person ID (stitched ID) is available on each event. Stitching looks at user data from both authenticated and unauthenticated sessions to determine the common transient ID (person ID) value that can be used as stitched ID. This rekeying allows for resolving disparate records to a single stitched ID for analysis at the person level, rather than at the device or cookie level.

Customer Journey Analytics supports two types of stitching: [field-based stitching](fbs.md) and [graph-based stitching](gbs.md).

## Prerequisites

>[!IMPORTANT]
>
>Failure to meet all prerequisites can result in the inability to conduct cross-channel analysis properly.

Before using stitching, make sure that your organization is prepared with the following:

- Stitching includes merging authenticated and unauthenticated user data. Ensure that you comply with applicable laws and regulations, including obtaining necessary end-user permissions, before activating stitching on an event dataset. See [Define identity fields in the UI](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/ui/fields/identity) for more information.

- Import the desired data into Adobe Experience Platform:
  
  - For Adobe Analytics data, see [Utilizing Adobe Analytics report suite data in Customer Journey Analytics](/help/getting-started/aa-vs-cja/aa-data-in-cja.md). 
  - For other types of data, see [Create a schema](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/tutorials/create-schema-ui) and [Ingest data](https://experienceleague.adobe.com/en/docs/experience-platform/ingestion/home) in the Adobe Experience Platform documentation.

You benefit from cross-channel analysis if you combine one or more of your stitched datasets with other datasets, such as call center data, as part of defining your Customer Journey Analytics connection. This connection configuration assumes that those other datasets already contain a person ID on every row, similar to the stitched ID.


## Limitations

>[!IMPORTANT]
>
>- No support for using `identityMap` as the persistent ID. You have to define a specific identifier in the dataset (for example, `ECID`) as the persistent ID.
>
>- Apply any change that you make to the source event dataset schema also to the new stitched dataset schema, otherwise it breaks the stitched dataset.
>
>- If you remove the source dataset, the stitched dataset stops processing and gets removed by the system.
>
>- Data usage labels are not automatically propagated to the stitched dataset schema. If you have data usage labels applied to the source dataset schema, you need to apply these data usage labels manually to the stitched dataset schema. See [Managing data usage labels in Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/data-governance/labels/overview) for more information.

Stitching is a groundbreaking and robust feature, but has limitations on how it can be used. 

- Only event datasets are supported. Other datasets, such as lookup datasets, are not supported.
- Stitching does not transform the field used for stitching in any manner. Stitching uses the value in the specified field as it exists in the unstitched dataset within the data lake. 
- The stitching process is case-sensitive. For example, if sometimes the word 'Bob' appears in the field, and sometimes the word 'BOB' appears, these ids are treated as two separate people.

Ensure you do not confuse stitching with:

- The merge of two or more datasets. Stitching applies to one dataset only. Merging of datasets occurs as a result of setting up a Customer Journey Analytics connection and selecting the same person ID across the selected datasets in the connection.

- The join of two datasets. In Customer Journey Analytics, a join is often used for lookups or classifications in Analysis Workspace. Although stitching uses join functionality, the process itself involves more than joins.

>[!MORELIKETHIS]
>
>[Field based stitching](fbs.md)
>[Graph based stitching](gbs.md)
>[Use stitching](use-stitching.md)
>[FAQ on stitching](faq.md)

