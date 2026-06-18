---
title: Data Mirror Overview
description: Understand how to synchronize data between data warehouse native solutions and Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
role: Admin
exl-id: f40e1263-1f4a-416c-a045-15fbe68ce509
autotag-review: '2026-05-19T08:55:53.979Z'
TQID: 'https://experienceleague.adobe.com/10YCh2cnMTVriKKVOyYfzFfngvGQ2VVHOxzedE5NpWA'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: b3197353-f189-4932-8378-3f3bc40e6071
    internal-label: Data management
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
  - id: eb00932f-4d46-46bc-b1d8-10de7588db8d
    internal-label: Data governance
subfeature_v2:
  - id: bfef374d-acfd-4c57-bf74-a2b36053c545
    internal-label: Data ingestion
  - id: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7
    internal-label: Connections
  - id: e1471301-a189-438e-8d48-264a8db508a6
    internal-label: Data views
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
    internal-label: Governance
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
    internal-label: Data management
---
# Experience Platform Data Mirror overview

Data Mirror is an Experience Platform capability that enables row-level change ingestion from external databases into the data lake using relational schemas. It preserves data relationships, enforces uniqueness, and supports versioning without requiring upstream extract, transform, and load (ETL) processes.

Use Experience Platform Data Mirror to synchronize inserts, updates, and deletes (mutable data) from external data warehouse native solutions ([!DNL Snowflake], [!DNL Azure Databricks], or [!DNL Google BigQuery]) directly with data in Experience Platform. Data Mirror helps you preserve your existing database model structure and data integrity as you bring data into Experience Platform.

## Capabilities and benefits

Data Mirror provides the following essential capabilities for database synchronization:

* **Primary key enforcement.** Ensures uniqueness within datasets and prevents duplicate records during ingestion.
* **Row-level change ingestion.** Supports granular data changes including upserts and deletes with precision control.
* **Schema relationships.** Enables foreign and primary key relationships between datasets through descriptors.
* **Out-of-order event handling.** Processes change events using version and timestamp descriptors, even when they arrive out of sequence.
* **Direct warehouse integration.** Connects with supported cloud data warehouses for real-time change synchronization.

Use Data Mirror to ingest changes directly from your source systems, enforce schema integrity, and make the data available for analytics, journey orchestration, and compliance workflows. Data Mirror eliminates complex upstream ETL processes and accelerates implementation by enabling direct mirroring of existing database models. This elimination can enhance data governance through precise control over deletions and data hygiene operations.

See also the [Experience Platform documentation on Data Mirror](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/data-mirror/overview){target="_blank"}.

## Data Mirror for Customer Journey Analytics

>[!NOTE]
>
>Data Mirror is a feature that supports the synchronization of data from select data warehouses using change data capture (CDC) for analysis in Customer Journey Analytics.<br/>Refer to the applicable Product Description to understand how the feature can impact annual ingestion limit consumption.
>

>[!IMPORTANT]
>
>The change data capture datasets that you create in Experience Platform for the purpose of Data Mirror for Customer Journey Analytics should not be reused in other Experience Platform solutions like Real-Time Customer Data Platform or Journey Optimizer. If you want to use the same data for these solutions, consider to create alternative datasets with that same data.
>



Experience Platform Data Mirror for Customer Journey Analytics is available for selected data warehouse native solutions ([!DNL Azure Databricks], [!DNL Google BigQuery], and [!DNL Snowflake]). The Customer Journey Analytics version of Experience Platform Data Mirror requires proper configuration of the following applications or components:

* [Data warehouse native solutions](datawarehouse.md)
* [Experience Platform](aep.md)
* [Customer Journey Analytics](cja.md)

>[!MORELIKETHIS]
>
>[Data Mirror quick start guide: Mirror and use relational data](relational.md)
>[Data Mirror (Experience Platform documentation)](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/data-mirror/overview)
>[Relational schemas (Experience Platform documentation)](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/relational)
