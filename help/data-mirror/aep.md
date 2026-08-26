---
title: Configure Experience Platform
description: Understand how to configure schemas and datasets for Experience Platform Data Mirror for Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
role: Admin
exl-id: 87593d7d-9456-48f8-8d39-5c3d95fe51ec
autotag-review: '2026-05-19T07:18:47.007Z'
TQID: 'https://experienceleague.adobe.com/nAfDMtaQvsVRAEm31fRwleirW8LaS-yS0tGTdReux0Y'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
    internal-label: Administration
  - id: b3197353-f189-4932-8378-3f3bc40e6071
    internal-label: Data management
subfeature_v2:
  - id: bfef374d-acfd-4c57-bf74-a2b36053c545
    internal-label: Data ingestion
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
---
# Configure Experience Platform

Experience Platform Data Mirror for Customer Journey Analytics requires the proper configuration of several Experience Platform components:

* schema
* dataset
* source connector

Find below details that you should consider when configuring each of these components.

## Schema

You need to create a [relational schema](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/relational){target="_blank"} that s the data warehouse native table you want to mirror. When you construct the relational schema, ensure that the following requirements are met:

* When prompted for the type of relational schema, ensure you select the manual option.
* Select the appropriate schema for the type of data. Note that Experience Platform Data Mirror is mostly used for time series data (for example, event data) but can also be used for record-based (lookup and profile) data.
  
* Define the fields in your schema and their attributes
* Configure the required attributes for fields in a relational schema: 
 
  * **Primary key**. 
  * **Version descriptor**, which must be configured as a sequential number (Integer field type) or as a DateTime field type. When you use a DateTime field type, the version descriptor defines the timestamp of a modification of the data, for example to contain a last modified timestamp.
  * **Timestamp descriptor** (for time series data), which defines the immutable timestamp at the moment that an event is captured. The timestamp descriptor is not required for a record-based relational schema.
  


## Dataset

You can set up a dataset for your schema in advance, or create a dataset when you set up your source connector. 
When you create a dataset in advance or select a dataset, ensure you the data uses a relational [schema](#schema) you created earlier.


## Source connector

To set up the source connector to the supported data warehouse native solutions, you use the Sources workflow that guide you through the setup. That workflow consists of the following steps:

### Authentication

For authentication against the supported data warehouse native solution, see the relevant Experience Platform documentation:

* [Azure Databricks](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/databases/databricks)
* [Google BigQuery](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/databases/bigquery)
* [Snowflake](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/databases/snowflake)


### Select data

Once successfully connected to your data warehouse native solution, select the table from the data warehouse native solution you want to use for data mirror. Once selected, a preview of the contents of the data is shown.


### Dataflow detail

Ensure you enable change data capture. You see an information panel, explaining the requirements for change data capture.

Specify a new or existing dataset that is based on the relational schema you created earlier. Specify and select other options in the Dataflow detail interface.


### Mapping

Map the fields of the table in the data warehouse native solution to the fields that you have specified for the relational schema.


### Scheduling

Define a schedule to mirror the data from the table in the data warehouse native solution to the dataset in Experience Platform.


### Review

Review the settings for the source connector to the data warehouse native solution that supports data mirror and change data capture.


Once you finished the setup of the source connector, a dataflow is created. From that moment on data changes (inserts, updates, deletions) in the data warehouse native solution are mirrored to the specified dataset.


>[!MORELIKETHIS]
>
>[Data Mirror quick start guide: Mirror and use relational data](relational.md)
>[Data Mirror (Experience Platform documentation)](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/data-mirror/overview)
>[Relational schemas (Experience Platform documentation)](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/relational)
