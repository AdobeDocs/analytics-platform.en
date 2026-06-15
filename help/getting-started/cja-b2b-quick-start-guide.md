---
title: Customer Journey Analytics B2B quick start guide
description: Quick start guide for the B2B Edition of Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
role: User, Admin
badgePremium: label="B2B Edition"
exl-id: ff8d419e-5cc6-4e1b-8cf8-9dbaa8054179
TQID: https://experienceleague.adobe.com/SjixkRCOmeUYuhZCVO7-7tLHalpnXO6QCVE1BiG9h2E
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
    internal-label: Administration
subfeature_v2:
  - id: a67cb189-a535-41f6-afa2-448f39c4759f
    internal-label: Access control
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
---
# B2B Edition quick start guide

To implement Customer Journey Analytics B2B Edition, ensure you first do understand the B2B specific concepts and features. Also, you should be familiar with the traditional workflow to implement Customer Journey Analytics. 

This document focuses on the workflow specific to the implementation of Customer Journey Analytics.

## Prerequisites

To implement Customer Journey Analytics B2B Edition, the following prerequisites do apply:

* You do have the necessary [access control and permissions](/help/technotes/access-control.md) to provide administration tasks in Customer Journey Analytics.
* You have puchased the Customer Journey Analytics B2B Edition add-on package.


## Workflow

| Task | Details |
| --- | --- |
| **Step 1: Get B2B data into Experience Platform** | This step, performed in Experience Platform, involves several sub steps:<ul><li>**Step 1a: Prepare your data schema**: Use [Adobe Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) to standardize B2B data and [define schemas](https://experienceleague.adobe.com/en/docs/experience-platform/rtcdp/schemas/b2b) for your B2B data.<br/>You can use the [Adobe Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) to standardize B2B data and define schemas for your B2B data. You can base your schemas on the [standard classes that are provided in Real-Time CDP B2B Edition](https://experienceleague.adobe.com/en/docs/experience-platform/rtcdp/schemas/b2b). Then follow the tutorial and use the scripts to generate the schemas. You do not have to be entitled to Real-Time CDP B2B Edition to make use of this documentation, tutorial or scripts. Alternatively, you can use work with your own custom schemas that you have build to support your business-to-business use cases.</li><li>**Step 1b: Create a dataset based on the schema**: Data in Platform consists of datasets, such as account data, opportunity data, buying group data, campaign data, marketing list data, email datasets, CRM datasets, POS datasets, and more. Each dataset consists of a schema and batches of data. You can [create a dataset in Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/create-datasets.html).</li><li>**Step 1c: Ingest data into Experience Platform**: You have [several options](https://experienceleague.adobe.com/en/docs/experience-platform/ingestion/home).</li></ul> |
| **Step 2: Create connections between platform datasets and Customer Journey Analytics** | A connection lets you integrate datasets from Adobe Experience Platform into Workspace. In order to report on Experience Platform datasets, you first have to establish a connection between datasets in Experience Platform and Workspace. You have additional options when you configure a connection with the B2B Edition. <br>See [Create or edit a connection](/help/connections/create-connection.md).  |
| **Step 3: Create data views** | A data view is a *filtered* view of the data. You can create different data views for the same connection, with different settings for visit timeout, attribution, and more. You can create multiple data views for a single dataset. You have additional options when you configure a data view when you have the B2B Edition.<br>See [Create a data view](/help/data-views/create-dataview.md). |
| **Step 4: Report on your cross-channel data in Workspace** | After you have created connections and data views, analyze the B2B data you have brought in using the power and flexibility of Analysis Workspace.<br>See [Perform basic analysis](/help/analysis-workspace/perform-basic-analysis.md) and [Perform advanced analysis](/help/analysis-workspace/perform-adv-analysis.md). |

<!--

## Use Case

The [B2B Use Case ](../data-ingestion/data-ingestion.md) document provides an example use case on how to implement Customer  Journey Analytics B2B Edition.

-->