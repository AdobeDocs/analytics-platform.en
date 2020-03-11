---
title: Customer Journey Analytics Getting Started
description: Customer Journey Analytics Getting Started.
---

# Customer Journey Analytics Getting Started

To implement Customer Journey Analytics, you need to follow this workflow. Some initial tasks are performed in Adobe Experience Platform, and some in Customer Journey Analytics.

|Task|Where performed|Details|
|---|---|---|
|**Step 1: Get your data into Adobe Experience Platform**|Adobe Experience Platform|There are several ways of ingesting data for both streaming and batch use cases including APIs and a graphical interface for data upload. Experience Platform can bring in data from things like:<ul><li>S3 storage</li><li>Azure Blob Storage</li><li>Kafka Streams</li><li>SFTP Transfers</li><li>CSV File Uploads</li><li>JSON File Uploads</li></ul>|
|**Step 2: Prepare your data schema**|Adobe Experience Platform|Use [Adobe Experience Data Model (XDM)](https://www.adobe.io/apis/experienceplatform/home/xdm.html) to standardize customer experience data and define schemas for customer experience management.|
|**Step 3: Create a dataset based on the schema**|Adobe Experience Platform|Data in Platform consists of data sets, such as email data sets, CRM datasets, POS data sets, the Adobe Analytics dataset, etc.. Each data sets consists of a schema and batches of data. You can create a data set [in Experience Platform](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/creating_a_dataset_tutorial/creating_a_dataset_tutorial.md).<br>Although the schema for datasets that can be imported into Customer Journey Analytics is flexible, it must conform to some basic rules. It is best to make sure your data meets these requirements before uploading them into Platform. (Note that schema includes both metrics and dimensions.)<br>There are three types of data that are compatible with Customer Journey Analytics:<ul><li>**Event data**: Data that represents events in time (e.g., web visits, interactions, transactions, POS data, survey data, ad impression data, etc.). This is typical clickstream data, with a customer ID or a cookie ID, and a timestamp. With Event data, we allow you to use whatever ID you want.</li><li>**Lookup data**: This data is used to lookup values or keys found in your Event or Profile data. For example, you might upload lookup data that maps numeric IDs in your event data to product names.</li><li>**Profile data**: Data that is applied to your visitors, users, or customers in the Event data. For example, allows you to upload CRM data about your customers.</li></ul>|
|**Step 4:Create connections between platform datasets and Customer Journey Analytics**|Customer Journey Analytics|See [Create a connection](/help/connections/create-connection.md).|
|**Step 5: Create data views**|Customer Journey Analytics|See [Create a data view](/help/data-views/create-dataview.md).|
|**Step 6: Report on your cross-channel data in Workspace**|Customer Journey Analytics|See [Perform basic analysis](/help/projects/perform-basic-analysis.md) and [Perform advanced analysis](/help/projects/perform-adv-analysis.md).|

## Prerequisites

Customer Journey Analytics is available for customers who 

* Are Adobe Analytics [Select, Prime, or Ultimate](https://www.adobe.com/analytics/compare-adobe-analytics-packages.html) customers, and 
* Are provisioned for the [Adobe Experience Platform](https://www.adobe.com/experience-platform.html), and 
* Have purchased the Customer Journey Analytics SKU

## Prepare your data schema

[Create a schema using the Schema Editor](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/schema_editor_tutorial/schema_editor_tutorial.md)

## Step 1: Get your data into Adobe Experience Platform

Before you can leverage Experience Platform data in CJA, you have to ingest that data into Platform. There are several ways of doing this:

* If you want to bring in your existing Adobe Analytics data, use the Adobe Analytics Platform Connector.
* To ingest other data, use formats like: S3 Storage, Azure Blob Storage, Kafka Streams, SFTP Transfers, CSV File Uploads, JSON File Uploads

### Step 1a: Bring your existing Analytics data into Adobe Experience Platform

Use the out-of-the-box Adobe Analytics Platform Connector to bring traditional Adobe Analytics data into Platform. You can create one source connection per report suite. See [Create a source connection with Adobe Analytics](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/sources_tutorial/adobe-analytics-ui-tutorial.md) in the Adobe Experience Platform documentation.

Once the connection is created, a target schema and dataset is automatically created to contain the incoming data. Furthermore, data back-filling occurs and ingests up to 13 months of historical data. When the initial ingestion completes, you can proceed with `Step 4` to create a connection between this Analytics dataset and Customer Journey Analytics.

### Step 1b: Ingest other data types

[Batch ingestion](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/ingest_architectural_overview/ingest_architectural_overview.md) lets you ingest data into Experience Platform as batch files. Batches are units of data that consist of one or more files to be ingested as a single unit. Once ingested, batches provide metadata that describes the number of records successfully ingested, as well as any failed records and associated error messages. Manually uploaded data files such as flat .CSV files (mapped to XDM schemas) and Parquet dataframes must be ingested using this method.

[Streaming ingestion](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/streaming_ingest/streaming_ingest_overview.md) lets you send data from client and server-side devices to Experience Platform in real time.

[Other Source connectors](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/acp-connectors-overview.md) let you ingest data from external sources while providing you with the ability to structure, label, and enhance incoming data using Platform services. You can ingest data from a variety of sources such as Adobe applications (Adobe Analytics, Audience Manager, Experience Platform Launch, Target), cloud-based storage (Azure Blob, Amazon S3, FTP/SFTP, Google Cloud Storage), third-party software, and your CRM (Microsoft Dynamics 365, Salesforce).

## Step 2: Prepare your data schema

bnbnbnbn
