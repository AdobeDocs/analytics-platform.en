---
title: Data Mirror Overview
description: Understand how to synchronize data between data warehouse native solutions and Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
role: Admin
badgePremium: label="Beta"
exl-id: f40e1263-1f4a-416c-a045-15fbe68ce509
---
# Experience Platform Data Mirror overview

{{release-limited-testing}}

Data Mirror is an Experience Platform capability that enables row-level change ingestion from external databases into the data lake using model-based schemas. It preserves data relationships, enforces uniqueness, and supports versioning without requiring upstream extract, transform, and load (ETL) processes.

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
>The Experience Platform Data Mirror capability for Customer Journey Analytics is available in a **public beta** until March 25, 2026. Customers may ingest up to 2 million change rows per day into Adobe Experience Platform Data Lake via source connectors. Adobe reserves the right to terminate beta access to Experience Platform Data Mirror functionality should your organization exceed these limits. <br/>To request access to this capability, please contact your Adobe account team.
>

Experience Platform Data Mirror for Customer Journey Analytics is available for selected data warehouse native solutions ([!DNL Azure Databricks], [!DNL Google BigQuery], and [!DNL Snowflake]). The Customer Journey Analytics version of Experience Platform Data Mirror requires proper configuration of the following applications or components:

* [Data warehouse native solutions](datawarehouse.md)
* [Experience Platform](aep.md)
* [Customer Journey Analytics](cja.md)

>[!MORELIKETHIS]
>
>[Data Mirror quick start guide: Mirror and use model-based data](model-based.md)
>[Data Mirror (Experience Platform documentation)](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/data-mirror/overview)
>[Model-based schemas (Experience Platform documentation)](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/model-based)
