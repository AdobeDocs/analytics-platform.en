---
title: Customer Journey Analytics Getting Started
description: Understand the prerequisites and workflow required to implement Customer Journey Analytics.
exl-id: cab218c0-009c-4669-9dfb-f8872a7f066b
solution: Customer Journey Analytics
feature: CJA Basics
---
# Customer Journey Analytics Getting Started

To implement Customer Journey Analytics, you need to follow this workflow. Some initial tasks are performed in Adobe Experience Platform, and some in Customer Journey Analytics.

## Prerequisites

Customer Journey Analytics is available for customers who 

* Are Adobe Analytics [Select, Prime, or Ultimate](https://www.adobe.com/analytics/compare-adobe-analytics-packages.html) customers, and 
* Are provisioned for the [Adobe Experience Platform](https://www.adobe.com/experience-platform.html), and 
* Have purchased the Customer Journey Analytics SKU

## Workflow

| Task | Details |
| --- | --- |
| **Step 1: If you are migrating from Adobe Analytics to CJA, learn what to do.** | [Utilizing Adobe Analytics report suite data in Customer Journey Analytics](/help/getting-started/aa-data-in-cja.md). |
| **Step 2: Get other data into Adobe Experience Platform** | This step, performed in Adobe Experience Platform, involves several sub steps:<ul><li>**Step 2a: Prepare your data schema**: Use [Adobe Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) to standardize customer experience data and [define schemas](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html) for customer experience management.</li><li>**Step 2b: Create a dataset based on the schema**: Data in Platform consists of data sets, such as email data sets, CRM datasets, POS data sets, the Adobe Analytics dataset, etc.. Each data sets consists of a schema and batches of data. You can [create a data set in Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/create-datasets.html).</li><li>**Step 2c: Ingest data into Experience Platform**: Here, you have several options. View the [data ingestion use cases](/help/use-cases/data-ingestion.md) for more information. |
| **Step 3: Create connections between platform datasets and Customer Journey Analytics** | A connection lets you integrate datasets from Adobe Experience Platform into Workspace. In order to report on Experience Platform datasets, you first have to establish a connection between datasets in Experience Platform and Workspace.<br>See [Create a connection](/help/connections/create-connection.md). |
| **Step 4: Create data views** | A data view is a "filtered" view of the data. You can create different data views for the same connection, with different settings for visit timeout, attribution, etc.. You can create multiple data views for a single dataset.<br>See [Create a data view](/help/data-views/create-dataview.md). |
| **Step 5: Report on your cross-channel data in Workspace** | After you have created connections and data views, analyze the data you have brought in using the power and flexibility of Analysis Workspace.<br>See [Perform basic analysis](/help/analysis-workspace/perform-basic-analysis.md) and [Perform advanced analysis](/help/analysis-workspace/perform-adv-analysis.md). |
