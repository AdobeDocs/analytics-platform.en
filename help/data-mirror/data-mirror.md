---
title: Data Mirror Overview
description: Understand how to synchronize data betweeen data warehouse native solutions and Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
role: Admin
hide: yes
hidefromtoc: yes
badgePremium: label="Beta"
---
# Experience Platform Data Mirror overview

{{release-limited-testing}}

Data Mirror is an Experience Platform capability that enables row-level change ingestion from external databases into the data lake using model-based schemas. It preserves data relationships, enforces uniqueness, and supports versioning without requiring upstream extract, transform, load (ETL) processes.

Use Data Mirror to synchronize inserts, updates, and deletes (mutable data) from external data warehouse native solutions such as [!DNL Snowflake], [!DNL Azure Databricks], or [!DNL Google BigQuery] directly into Experience Platform. This helps you preserve your existing database model structure and data integrity as you bring data into Platform.


## Capabilities and benefits

Data Mirror provides the following essential capabilities for database synchronization:

* **Primary key enforcement**: Ensures uniqueness within datasets and prevents duplicate records during ingestion.
* **Row-level change ingestion**: Supports granular data changes including upserts and deletes with precision control.
* **Schema relationships**: Enables foreign and primary key relationships between datasets through descriptors.
* **Out-of-order event handling**: Processes change events using version and timestamp descriptors, even when they arrive out of sequence.
* **Direct warehouse integration**: Connects with supported cloud data warehouses for real-time change synchronization.

Use Data Mirror to ingest changes directly from your source systems, enforce schema integrity, and make the data available for analytics, journey orchestration, and compliance workflows. Data Mirror eliminates complex upstream ETL processes and accelerates implementation by enabling direct mirroring of existing database models. This can enhance data governance through precise control over deletions and data hygiene operations.

See also the [Experience Platform documentation on Data Mirror](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/data-mirror/overview){target="_blank"}.


## Data Mirror for Customer Journey Analytics

>[!NOTE]
>
>The Experience Platform Data Mirror capability for Customer Journey Analytics is available in a **public beta** until March 25, 2026. During the beta period, change data capture (CDC) updates are limited to 0.5% of your organization's rows of data entitlement for Customer Journey Analytics, applied monthly (for example, 0.5% of the rows of data entitlement divided by 12, each month). Adobe reserves the right to terminate beta access to the Experience Platform Data Mirror feature should your organization exceed this limit.
>

The Experience Platform Data Mirror capability for Customer Journey Analytic is available for selected data warehouse native solutions ([!DNL Azure Databricks], [!DNL Google BigQuery], and [!DNL Snowflake]). The capability requires specifically for Customer Journey Analytics a proper setup and configuration of several components in the data warehouse native solution, Experience Platform, and Customer Journey Analytics itself.

* [Data warehouse native solution](datawarehouse.md)
* [Experience Platform](aep.md)
* [Customer Journey Analytics](cja.md)


