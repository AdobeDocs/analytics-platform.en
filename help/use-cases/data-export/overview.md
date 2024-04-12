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

One of the unique differences between Adobe Analytics and Customer Journey Analytics is related to the processing of data for attribution and sessionization. See [Compare data processing across Adobe Analytics and Customer Journey Analytics](/help/getting-started/aa-vs-cja/data-processing-comparisons.md) for more information.

### Adobe Analytics: collection time attribution and sessionization.

In Adobe Analytics, all events are processed live and in order by device ID, allowing Adobe to generate, store, and export clickstream data with persisted or attributed values at collection time, including:

* Dimension persistence (for example, campaign tracking codes that expire after 90 days).
* Visit number and sessionization.
* Dimension values calculated by processing and VISTA rules.
  
This impacts the export of data from Adobe Analytics:

* Data processing is static after initial collection.
* Data feeds include "post" columns, which reflect the collection-time processing.
  

### Customer Journey Analytics: query-time attribution and sessionization

In Customer Journey Analytics, events are not collected in order and a person ID is used instead of a device ID, allowing Customer Journey Analytics to update attribution and sessionization at report time. This type of data collection introduces flexibility, like:

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

* realization of tailored data export use cases

  * export data to where you need it, including Business Intelligence (BI) tools and cloud destinations,
  * keep data synchronized with Analysis Workspace through BI tools integration,
  * no need to replicate processing logic in your own systems,
  * new support for calculated metrics, derived fields and segmentation, and

* consideration of security and data governance by design

  * monitor all data export by user and destination,
  * set limits on what data is available for export, and
  * set alerts for delivery issues and limits on scheduled delivery windows.


## Use cases and solutions

In general, data export supports a number of use cases. Each use case is different in terms of the data that it requires and how to access and export that data. Experience Platform and Customer Journey Analytics provide a number of options that either independently or combined can solve the various use cases. The table below provides an overview of identified data export use cases and the Experience Platform and Customer Journey Analytics options (or functionalities) to implement these use cases.  

| Data export use cases | Experience Platform & Customer Journey Analytics functionalities |
|---|---|
| **Data Backup**<br/>Retain a complete copy of your digital data for compliance or regulatory purposes. | [**Experience Platform Destinations Dataset Export**](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets)<br/>Egress WebSDK collected data directly from AEP to cloud destinations on a schedule or ad-hoc.<br/>*Currently limited release, full release is expected in June 2024.* |
| **Data Validation**<br/>Evaluate clickstream data for data collection accuracy. | [**Experience Platform Query Service, Data Distiller & Dataset Export**](queryservice-datadistiller-datasetexport.md)<br/> Interactive PostgreSQL interface to make ad-hoc SQL queries using your favorite SQL tool to validate the data in your datasets.<br/><br/>[**Customer Journey Analytics Full Table Export**](../../analysis-workspace/export/export-cloud.md)<br/>Validate processed data from CJA with attribution and sessionization applied. |
| **Data Lake, Data Warehouse or BI tools**<br/>Bring digital data into your own BI tools or Data Lake for use with additional datasets. | [**Customer Journey Analytics BI Extension**](../../data-views/bi-extension.md)<br/>Add Customer Journey Analytics processed metrics to data visualization tools such as Power BI and combine with additional data for custom reports<br/><br/>[**Experience Platform Query Service, Data Distiller & Dataset Export**](queryservice-datadistiller-datasetexport.md)<br>Generate customized clickstream data using SQL to be delivered to cloud destinations. |
| **Readiness for AI / ML**<br/>Enhance Artificial Intelligence / Machine Learning models and tasks with Customer Journey Analytics data. | [**Customer Journey Analytics Full Table Export**](../../analysis-workspace/export/export-cloud.md)<br/>Egress Customer Journey Analytics processed dimensions and metrics to cloud destinations one-time or recurring, including calculated metrics and segmentation.<br/><br/>[**Experience Platform Query Service, Data Distiller & Dataset Export**](queryservice-datadistiller-datasetexport.md.md)<br/>Generate customized clickstream data using SQL to enrich AI / ML models. |

