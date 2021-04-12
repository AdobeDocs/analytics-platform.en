---
title: Set up Google Analytics reporting in Customer Journey Analytics
description: 
---

# Set up Google Analytics reporting in Customer Journey Analytics

setting up the Google Cloud Storage Connector,

configure Google Tag Manager

BigQuery Export schema (https://support.google.com/analytics/answer/3437719?hl=en&ref_topic=3416089)

1. Convert GA sessions to events in Big Query
1. Export Google Analytics events to Google Cloud Storage
1. Import GCS events to Adobe Experience Platform and map to XDM schema

## Prerequisites

* Access to Adobe Experience Platform
* Access to Universal Google Analytics (Google Analytics 360 version) or Google Analytics 4 (free version or Google Analytics 360 version)
* Access to Customer Journey Analytics

## 1. Connect Google Analytics data to Adobe Experience Platform

How you bring Google Analytics data into Adobe Experience Platform depends on which version of Google Analytics you are using:

| If you use... | You also need this license... | And do this... |
| --- | --- | --- |
| **Universal Google Analytics** | Google Analytics 360 |  Perform steps 1 - x of the instructions below |
| **Google Analytics 4** | Free GA version or Google Analytics 360 | No need for step x in the instructions below. |

The following instructions are based on Universal Google Analytics.

1. Connect your Google Analytics data to BigQuery and 
Refer to [these instructions](https://support.google.com/analytics/answer/3416092?hl=en).
1. (Universal Analytics customers only) Transform Google Analytics sessions to events in BigQuery. This makes the data compatible with Adobe Experience Platform. Refer to [these instructions](https://support.google.com/analytics/answer/3437618?hl=en). 

   Details: In BigQuery, your GA data will appear as a table:

   ![](assets/ga-bigquery.png)
   You need to create a SQL query to transform the Universal Analytics data into an Experience-Platform-compliant format. 
   * View this video for instructions.

1. Export Google Analytics events in JSON format to Google Cloud Storage and save them to a bucket.
Refer to [these instructions](https://support.google.com/analytics/answer/3437719?hl=en&ref_topic=3416089).
1. Bring the data from Google Cloud Storage into Experience Platform. (get slide 10 video from Trevor.)

