---
title: How to get Google Analytics data into Adobe Experience Platform for analysis in Customer Journey Analytics (CJA)
description: Explains how to leverage Customer Journey Analytics (CJA) to ingest your Google Analytics and firebase data into Adobe Experience Platform. 
exl-id: 314378c5-b1d7-4c74-a241-786198fa0218
---

# Ingest Google Analytics data into Adobe Experience Platform

This use case focuses on how to ingest your Google Analytics data as a dataset into Adobe Experience Platform. (This applies to both historical and live data.) Once done, you can combine both datasets to achieve a cross-device view of your user's journey.

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
| **Universal Google Analytics** | Google Analytics 360 |  Perform steps 1 - 5 of the instructions below |
| **Google Analytics 4** | Free GA version or Google Analytics 360 | Perform steps 1 and 3-5 of the instructions below. No need for step 2. |

## 1. Connect your Google Analytics data to BigQuery

Note that the following instructions are based on Universal Google Analytics.

Refer to [these instructions](https://support.google.com/analytics/answer/3416092?hl=en).

## 2. Transform Google Analytics sessions to events in BigQuery

>[!IMPORTANT]
>
>This step applies to Universal Analytics customers only

 Transforming the data makes the data compatible with Adobe Experience Platform. 
 Refer to [these instructions](https://support.google.com/analytics/answer/3437618?hl=en). 

   Details: In BigQuery, your GA data will appear as a table:

   ![](assets/ga-bigquery.png)
   You need to create a SQL query to transform the Universal Analytics data into an Experience-Platform-compliant format. View this video for instructions:

   >[!VIDEO](https://video.tv.adobe.com/v/332634)

## 3. Export Google Analytics events in JSON format to Google Cloud Storage and save them to a bucket

   Refer to [these instructions](https://support.google.com/analytics/answer/3437719?hl=en&ref_topic=3416089).

## 4. Bring the data from Google Cloud Storage into Experience Platform

   View this video for instructions:

   >[!VIDEO](https://video.tv.adobe.com/v/332641)

## 5. Import GCS events to Adobe Experience Platform and map to XDM schema

BigQuery Export schema (https://support.google.com/analytics/answer/3437719?hl=en&ref_topic=3416089)
