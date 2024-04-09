---
title: Data feed use cases
description: Understand Customer Journey Analytics alternatives for Adobe Analytics data feed functionality
solution: Customer Journey Analytics
feature: Use Cases
hide: yes
hidefromtoc: yes
role: Admin
---

# Data export use cases

This section provides data export use cases. Each use case is described in its own article. For some of the use cases, more than one solution is provided.

## Introduction

One of the unique differences between Adobe Analytics and Customer Journey Analytics is related to the processing of data for attribution and sessionization. See [Compare data processing across Adobe Analytics and Customer Journey Analytics](/help/getting-started/aa-vs-cja/data-processing-comparisons.md) for more information

### Adobe Analytics: collection time attribution and sessionization.

In Adobe Analytics, all events are processed live and in order by device ID, allowing Adobe to generate, store, and export clickstream data with persisted or attributed values at collection time, including:

* Dimension persistence (e.g., campaign tracking codes that expire after 90 days).
* Visit number and sessionization.
* Dimension values calculated by processing and VISTA rules.
  
This impacts the export of data from Adobe Analytics:

* Data processing is static after initial collection.
* Data Feeds include "post" columns, which reflect the collection-time processing.
  

### Customer Journey Analytics: query-time attribution and sessionization

In Customer Journey Analytics, events are not collected in order and a person ID is used instead of of a device ID, allowing Customer Journey Analytics to update attribution and sessionization at report time. This introduces flexibility, like:

* Stitching can _replay_ data daily or weekly, associating anonymous events with known events. See [Stitching](../../stitching/overview.md) for more information.
* Sessionization and persisted values change every time
  * new data is collected or 
  * stitching adds events to a person's history.

The report-time collection impacts the export of data from Customer Journey Analytics. Exports that include persisted values, will not match Customer Journey Analytics reports and will drift away over time.

For metric consistency, use of the new features in Customer Journey Analytics is preferred. In general, Experience Platform and Customer Journey Analytics data export functionality exceeds the data feed functionality of Adobe Analytics. Experience Platform and Customer Journey Analytics do provide:

* new data sources and processing subject to data export

  * include non-digital data sources,
  * apply custom attribution and sessionization based on business rules, and
  * keep customer journeys updated with stitching.

* realization of tailored data exports use cases

  * export data to where you need it, including Business Intelligence (BI) tools and cloud destinations,
  * keep data synchronized with Analysis Workspace through BI tools integration,
  * no need to replicate processing logic in your own systems,
  * new support for calculated metrics, derived fields and segmentation, and

* consideration of security and data governance by design

  * monitor all data export by user and destination,
  * set limits on what data is available for export, and
  * set alerts for delivery issues and limits on scheduled delivery windows.

See table below for overview of use cases and the solutions recommended.



