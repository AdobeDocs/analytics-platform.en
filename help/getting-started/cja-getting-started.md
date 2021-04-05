---
title: Customer Journey Analytics Getting Started
description: Understand the prerequisites and workflow required to implement Customer Journey Analytics.
exl-id: cab218c0-009c-4669-9dfb-f8872a7f066b
---
# Customer Journey Analytics Getting Started

To implement Customer Journey Analytics, you need to follow this workflow. Some initial tasks are performed in Adobe Experience Platform, and some in Customer Journey Analytics.

## Prerequisites

Customer Journey Analytics is available for customers who 

* Are Adobe Analytics [Select, Prime, or Ultimate](https://www.adobe.com/analytics/compare-adobe-analytics-packages.html) customers, and 
* Are provisioned for the [Adobe Experience Platform](https://www.adobe.com/experience-platform.html), and 
* Have purchased the Customer Journey Analytics SKU

## Workflow

|Task|Details|
|---|---|
|**Step 1: Get your data into Adobe Experience Platform**|This step, performed in Adobe Experience Platform, involves several sub steps:<ul><li>**Step 1a: Prepare your data schema**: Use [Adobe Experience Data Model (XDM)](https://www.adobe.io/apis/experienceplatform/home/xdm.html) to standardize customer experience data and [define schemas](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/schema_editor_tutorial/schema_editor_tutorial.md) for customer experience management.</li><li>**Step 1b: Create a dataset based on the schema**: Data in Platform consists of data sets, such as email data sets, CRM datasets, POS data sets, the Adobe Analytics dataset, etc.. Each data sets consists of a schema and batches of data. You can create a data set [in Experience Platform](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/creating_a_dataset_tutorial/creating_a_dataset_tutorial.md).</li><li>**Step 1c: Ingest data into Experience Platform**: Use the out-of-the-box Adobe Analytics Platform Connector to bring traditional Adobe Analytics data into Platform. You can create one source connection per report suite. See [Create a source connection with Adobe Analytics](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/sources_tutorial/adobe-analytics-ui-tutorial.md) in the Adobe Experience Platform documentation. Once the connection is created, a target schema and dataset is automatically created to contain the incoming data. Furthermore, data back-filling occurs and ingests up to 13 months of historical data. When the initial ingestion completes, you can proceed with `Step 2` to create a connection between this Analytics dataset and Customer Journey Analytics. Or, you can ingest other data types via [Batch ingestion](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/ingest_architectural_overview/ingest_architectural_overview.md),[Streaming ingestion](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/streaming_ingest/streaming_ingest_overview.md), or via [other Source Connectors](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/acp-connectors-overview.md).</li></ul>|
|**Step 2: Create connections between platform datasets and Customer Journey Analytics**|A connection lets you integrate datasets from Adobe Experience Platform into Workspace. In order to report on Experience Platform datasets, you first have to establish a connection between datasets in Experience Platform and Workspace.<br>See [Create a connection](/help/connections/create-connection.md).|
|**Step 3: Create data views**| A data view is a "filtered" view of the data. You can create different data views for the same connection, with different settings for visit timeout, attribution, etc.. You can create multiple data views for a single dataset.<br>See [Create a data view](/help/data-views/create-dataview.md).|
|**Step 4: Report on your cross-channel data in Workspace**|After you have created connections and data views, analyze the data you have brought in using the power and flexibility of Analysis Workspace.<br>See [Perform basic analysis](/help/analysis-workspace/perform-basic-analysis.md) and [Perform advanced analysis](/help/analysis-workspace/perform-adv-analysis.md).|
