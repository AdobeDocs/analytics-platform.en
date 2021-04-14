---
title: Ingest Google Analytics data into Adobe Experience Platform
description: Explains how to leverage Customer Journey Analytics (CJA) to ingest your Google Analytics and firebase data into Adobe Experience Platform. 
exl-id: 314378c5-b1d7-4c74-a241-786198fa0218
---

# Ingest Google Analytics data into Adobe Experience Platform

This use case focuses on how to ingest your Google Analytics data as a dataset into Adobe Experience Platform. We will explain how to ingest both historical and live data. Once done, you can combine both datasets in Customer Journey Analytics to achieve a cross-device view of your user's journey.

Datasets in the Experience Platform are made up of two things: a schema and the actual records in the dataset. The schema (we call this the Experience Data Model or XDM for short) is like the columns of the dataset and is like the blueprint or the rules that describe the data itself. Within the Platform, Adobe provides 2 types of schemas:

* Out-of-the-box schemas that you can map your Google Analytics data to automatically (called the Experience Event schema)
* Custom schemas that you can create and easily map the Google Analytics data to

One of the most powerful aspects of Adobe’s data model is that it allows you to standardize all of your customer interaction data into one common schema – this makes it a lot easier to stitch the data together in CJA.

## Prerequisites

In order to accomplish these tasks, you need the following access and permissions:

* Access to Adobe Experience Platform
* Access to Universal Google Analytics (Google Analytics 360 version) or Google Analytics 4 (free version or Google Analytics 360 version)
* Access to Customer Journey Analytics and its [Admin permissions](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=en#admin-access-permissions).

How you bring Google Analytics data into Adobe Experience Platform depends on which version of Google Analytics you are using:

| If you use... | You also need this license... | And do this... |
| --- | --- | --- |
| **Universal Analytics** | Google Analytics 360 |  Perform steps 1 - 5 of the instructions below |
| **Google Analytics 4** | Free GA version or Google Analytics 360 | Perform steps 1 and 3-5 of the instructions below. No need for step 2. |

## Ingest historical (backfill) data

### 1. Connect your Google Analytics data to BigQuery

Note that the following instructions are based on Universal Google Analytics. They apply to historical data. For instructions regarding live streaming data, go to [Bring live streaming data into AEP](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/ga-to-cja.html?lang=en#ingest-live-streaming-google-analytics-data).

Refer to [these instructions](https://support.google.com/analytics/answer/3416092?hl=en).

### 2. Transform Google Analytics sessions to events in BigQuery

>[!IMPORTANT]
>
>This step applies to Universal Analytics customers only

GA data stores each record in their data as a user’s session rather than individual events. You need to create a SQL query to transform the Universal Analytics data into an Experience-Platform-compliant format. You apply the “unnest” function to the “hits” field in the GA schema. Here is the  SQL example you can use:

`SELECT
   *,
   timestamp_seconds(`visitStartTime` + hit.time) AS `timestamp` 
FROM
   (
      SELECT
         fullVisitorId,
         visitNumber,
         visitId,
         visitStartTime,
         trafficSource,
         socialEngagementType,
         channelGrouping,
         device,
         geoNetwork,
         hit 
      FROM
         `your_bq_table_2021_04_*`,
         UNNEST(hits) AS hit 
   )`

Once the query completes, save the complete results into a BigQuery table.

Refer to [these instructions](https://support.google.com/analytics/answer/7029846?hl=en&ref_topic=9359001#zippy=%2Cold-export-schema%2Cuse-this-script-to-migrate-existing-bigquery-datasets-from-the-old-export-schema-to-the-new-one%2Cscript-migration-scriptsql). 

 Or, view this video:

>[!VIDEO](https://video.tv.adobe.com/v/332634)

### 3. Export Google Analytics events in JSON format to Google Cloud Storage and save them to a bucket

Next, you will export the Google Analytics events to Google Cloud Storage in JSON format. Just click **Export > Export to GCS**. Once there, the data is ready to be pulled into Adobe Experience Platform.

Refer to [these instructions](https://support.google.com/analytics/answer/3437719?hl=en&ref_topic=3416089).

### 4. Import the data from Google Cloud Storage into Experience Platform

In Experience Platform, select **[!UICONTROL Sources]** and find the **[!UICONTROL Google Cloud Storage]** option. From there, you just need to find the dataset you had saved from BigQuery. 

Keep this in mind:

* Make sure you select JSON format.
* You can select an existing dataset, or create a new dataset (recommended).
* Make sure to select the same schema for historical Google Analytics data and live streaming Google Analytics data, even if they are in separate datasets. You can subsequently merge the datasets in a [CJA connection](/help/connections/combined-dataset.md).


View this video for instructions:

>[!VIDEO](https://video.tv.adobe.com/v/332641)

### 5. Import GCS events to Adobe Experience Platform and map to XDM schema

Next, you can map the GA event data into an existing dataset that you created previously, or create a new dataset, using whichever XDM schema you choose. Once you have selected the schema, the Experience Platform applies machine learning to automatically pre-map each of the fields in the Google Analytics data to your [XDM schema](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=en#ui). 

![](assets/schema-map.png)

Mappings are very easy to change and you can even create derived or calculated fields from the Google Analytics data. Once you have finished mapping the fields into your XDM schema, you can schedule this import on a recurring basis as well as apply error validation during the ingestion process. This ensures that there aren’t any issues with the data you have imported.

**Timestamp calculated field**

For the `timestamp` field in Google Analytics data, you have to create a special calculated field in the Experience Platform schema UI. Click **[!UICONTROL Add calculated field]** and wrap the `timestamp` string in a `date` function, like this:

`date(timestamp, "yyyy-MM-dd HH:mm:ssZ")`

You then need to save this calculated field to the timestamp data structure in the schema:

![](assets/timestamp.png)

**_id XDM calculated field**

The `_id` schema field has to have a value in it - CJA does not care what the value is. You can just add a "1" to the field:

![](assets/_id.png)

## Ingest live streaming Google Analytics data

You can also capture live streaming events from Google Tag Manager directly to Adobe Experience Platform.

### 1. Add Custom Variables

After signing in to the Google Tag Manager account, you need to add Custom Constant Variables related to Adobe org ID and dataset IDs. You probably already have variables in Google Tag Manager that are being sent to Google Analytic, such as the customer email, customer name, language, and customer logged-in status. You need to define 5 new custom variables:

* Adobe Experience Cloud org ID
* DCS Streaming endpoint
* Experience Platform dataset ID
* Schema reference
* Page time stamp.

Getting these values ensures that all of the Google Analytics data gets sent to the correct dataset and has the right schema. If you don’t know your Experience Cloud Org or any of the other variables we just mentioned, your Adobe Account manager can help you track it down.

Once you have defined these custom variables, we can set up a trigger to send all the data you’re already sending to Google Analytics to the Experience Platform as well.

### 2. Set up a Trigger in Google Tag Manager

In this example, the "Account Creation" trigger has been defined, where the `pageUrl equals account-creation`. By adding some information to this trigger, you can ensure that when user successful authenticates and the account-creation page loads, data is sent to both Google Analytics and AEP.

For instructions, view this video:

>[!VIDEO](https://video.tv.adobe.com/v/332668)

## Create a Connection in CJA to the Google Analytics dataset

Once the Adobe Experience Platform has started receiving the live Google Analytics data, and you have backfilled the historical Google Analytics data from BigQuery, you are ready to jump into CJA and
[create your first connection](/help/connections/create-connection.md). This connection will stitch the GA data together with all of your other customer data using a common "Customer ID”.

## Do some amazing analysis in Workspace

More content here.