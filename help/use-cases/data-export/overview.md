---
title: Data export use cases
description: Understand various data export use cases for Customer Journey Analytics
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
exl-id: 8b9c164e-01da-4b43-8e2c-99904223cae5
TQID: https://experienceleague.adobe.com/ad4wWxqEZZxsnSTpus7pxFMlwNo3nNUpHeS9VfxrEdw
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: eb00932f-4d46-46bc-b1d8-10de7588db8d
    internal-label: Data governance
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
    internal-label: Metrics
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: bbbea26f-9621-49eb-9ab8-e06fb3bbce8c
    internal-label: Artificial intelligence
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
    internal-label: Governance
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
    internal-label: Machine learning
---
# Data export use cases {#data-export-use-cases}

<!-- This contextual help is for the upgrade checklist -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-data-feeds-step"
>title="Use export features similar to Data Feeds"
>abstract="An exact replacement for Data Feeds is not yet available in Customer Journey Analytics. However, similar functionality can be achieved with capabilities such as full table export, Platform dataset export, BI tool integration, and the reporting API."

<!-- markdownlint-enable MD034 -->

This section provides data export use cases and how to implement these use cases with one or more functionalities of Customer Journey Analytics or Experience Platform. Each functionality is further detailed in a separate article.

## Introduction

One of the unique differences between Adobe Analytics and Customer Journey Analytics is related to the processing of data for attribution and sessionization. See [Compare data processing across Adobe Analytics and Customer Journey Analytics](/help/getting-started/aa-vs-cja/data-processing-comparisons.md) for more information.

### Adobe Analytics: collection time attribution and sessionization.

In Adobe Analytics, all events are processed live and in order by device ID, allowing Adobe to generate, store, and export clickstream data with persisted or attributed values at collection time, including:

* Dimension persistence (for example, campaign tracking codes that expire after 90 days).
* Visit number and sessionization.
* Dimension values, calculated by processing and VISTA rules.
  
This impacts the export of data from Adobe Analytics:

* Data processing is static after initial collection.
* Data feeds include "post" columns, which reflect the collection-time processing.
  

### Customer Journey Analytics: query-time attribution and sessionization

In Customer Journey Analytics, events are not collected in order and a person ID is used instead of a device ID, allowing Customer Journey Analytics to update attribution and sessionization at report time. This type of data collection introduces flexibility, like:

* Stitching can _replay_ data daily or weekly, associating anonymous events with known events. See [Stitching](../../stitching/overview.md) for more information.
* Sessionization and persisted values change every time
  * new data is collected or 
  * stitching adds events to a person's history.

The report-time processing impacts the export of data from Customer Journey Analytics. Exports that include persisted values, will not match Customer Journey Analytics reports and values will drift away over time.

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


## Use cases and functionalities

In general, data export supports a number of use cases. Each use case is different in terms of the data that is required and how to access and export that data. Experience Platform and Customer Journey Analytics provide a number of functionalities that either independently or combined can solve the various use cases. The table below provides an overview of identified data export use cases and the Experience Platform and Customer Journey Analytics functionalities to implement these use cases.  

| Data export use cases | Experience Platform & Customer Journey Analytics functionalities |
|---|---|
| **Data Backup**<br/>Retain a complete copy of your digital data for compliance or regulatory purposes. | **Experience Platform**: [**Export datasets**](export-datasets.md)<br/>Export data collected in Experience Platform directly to cloud destinations on a schedule or ad-hoc.|
| **Data Validation**<br/>Evaluate clickstream data for data collection accuracy. | **Experience Platform**: [**Query Service (Data Distiller) & Export datasets**](queryservice-export-datasets.md)<br/> Interactive PostgreSQL interface to execute ad-hoc SQL queries using your favorite SQL tool to validate the data in your datasets.<br/><br/>**Customer Journey Analytics**: [**Export full table**](export-full-table.md)<br/>Validate processed data from CJA with attribution and sessionization applied. |
| **Data Lake, Data Warehouse or BI tools**<br/>Bring digital data into your own BI tools or Data Lake for use with additional datasets. | **Customer Journey Analytics**: [**BI Extension**](bi-extension.md)<br/>Add Customer Journey Analytics processed metrics to data visualization tools such as Power BI and combine with additional data for custom reports<br/><br/>**Experience Platform**: [**Query Service (Data Distiller) & Export datasets**](queryservice-export-datasets.md)<br>Generate customized clickstream data using SQL to be delivered to cloud destinations. |
| **Readiness for AI / ML**<br/>Enhance Artificial Intelligence / Machine Learning models and tasks with Customer Journey Analytics data. | **Customer Journey Analytics**: [**Export full table**](export-full-table.md)<br/>Export Customer Journey Analytics processed dimensions and metrics to cloud destinations one-time or recurring, including calculated metrics and segmentation.<br/><br/>**Experience Platform**: [**Query Service (Data Distiller) & Export datasets**](queryservice-export-datasets.md)<br/>Generate customized clickstream data using SQL to enrich AI / ML models. |
