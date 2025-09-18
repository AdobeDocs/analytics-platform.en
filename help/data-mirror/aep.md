---
title: Configure Experience Platform
description: Understand how to confgure schemas and datasets for Experience Platform Data Mirror for Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
role: Admin
hide: yes
hidefromtoc: yes
badgePremium: label="Beta"
---
# Configure Experience Platform

The Experience Platform Data Mirror feature for Customer Journey Analytics requires the proper configuration of several Experience Platform components:

* schema
* dataset
* source connector

## Schema

You need to create a model-based schema that models the data warehouse native table you want to mirror. When you construct the model-based schema, ensure the following requirements are met:

* Select the appropriate schema for the type of data. For time series data (event data like call-center interactions), select Time series. For record data (profiles, product info, and more).
  
  ![Create schema](assets/platform-schema-create.png)

* Define the fields in your schema and their attributes
* Configure the required attributes for fields: a primary key, a version identifier, and a timestamp identifier.

>[!BEGINTABS]

>[!TAB Id]

The id field is configured as version identifier.

![Version identifier](assets/platform-schema-id.png)

>[!TAB Person Id]

The personid field is configured, together with timestamp as the primary key. To do this, select ![Add](/help/assets/icons/Add.svg) Create composite key and select both personid and timestamp. 

![Composite key](assets/platform-schema-compositekey.png)

The personid field is also configured as an identity, with CRMID as the namespace.

![Version identifier](assets/platform-schema-personid.png)

>[!TAB Timestamp]

The timestamp field is configured, together with personid field as the primary key. And the timestamp field is also configured as timestamp identifier.

![Version identifier](assets/platform-schema-timestamp.png)

>[!ENDTABS]

