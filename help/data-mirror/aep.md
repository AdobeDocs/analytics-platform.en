---
title: Configure Experience Platform
description: Understand how to configure schemas and datasets for Experience Platform Data Mirror for Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
role: Admin
badgePremium: label="Beta"
exl-id: 87593d7d-9456-48f8-8d39-5c3d95fe51ec
---
# Configure Experience Platform

{{release-limited-testing}}

Experience Platform Data Mirror for Customer Journey Analytics requires the proper configuration of several Experience Platform components:

* schema
* dataset
* source connector

Find below details that you should consider when configuring each of these components.

## Schema

You need to create a [relational schema](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/relational){target="_blank"} that s the data warehouse native table you want to mirror. When you construct the relational schema, ensure that the following requirements are met:

* When prompted for the type of relational schema, ensure you select the manual option.
* Select the appropriate schema for the type of data. Note that Experience Platform Data Mirror is mostly used for time series data (for example, event data).
  
* Define the fields in your schema and their attributes
* Configure the required attributes for fields in a relational schema: 
 
  * primary key 
  * version identifier 
  * timestamp identifier (for time series data).

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
