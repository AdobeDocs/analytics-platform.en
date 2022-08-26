---
title: Migrate data from Google Analytics to Customer Journey Analytics
description: Learn the overarching workflow around how to move data from Google Analytics to Adobe Experience Platform, and viewing reports in Customer Journey Analytics.
---
# Migrate data from Google Analytics to Customer Journey Analytics

If you recently purchased Customer Journey Analytics, it is possible that your organization has existing data on another Analytics platform, such as Google Analytics. You can follow these overarching steps to move that data into Adobe Experience Platform, allowing you to view reports in Customer Journey Analytics.

Workflows are provided for both historical data and current data collection. You can follow one or both of these workflows, depending on your organization's data needs.

## Bring historical data from Google Analytics into Adobe Experience Platform

Ingesting historical (backfill) data involves exporting data from Google and importing that data into Adobe Experience Platform. See [Ingest Google Analytics data in Adobe Experience Platform](ingest.md).

Once you successfully bring historical data into Platform, you can either configure current data collection, or [Create a connection](/help/connections/create-connection.md) in CJA to begin reporting on backfilled data.

## Configure an existing Google Analytics implementation for Adobe Experience Platform {#configure}

Configuring data collection involves the following steps:

1. Implement [Tags for Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html). See the [Quickstart guide](https://experienceleague.adobe.com/docs/experience-platform/tags/get-started/quick-start.html) to get a basic implementation up and running.
1. Install the [Google Data Layer extension](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/google-data-layer/overview.html). This extension acts as an alternative to installing the Web SDK extension, geared specifically towards a Google data layer.
1. [Create a Datastream](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html) in Adobe Experience Platform Data Collection. Configure the Datastream to send data to Adobe Experience Platform. Note that you must currently map each Google data layer object to an applicable XDM field here. Adobe plans to simplify this mapping workflow in the future.

## Create a Connection in CJA

Once you successfully ingest historical data or configure data collection to Adobe Experience Platform, you can [Create a connection](/help/connections/create-connection.md) to allow Customer Journey Analytics to reference that data.

## Create a Data View in CJA

Use the connection to create one or more [Data Views](/help/data-views/create-dataview.md) for use in Analysis Workspace.

## Create reports

After configuring dimensions and metrics within a Data View, you can begin using Analysis Workspace to generate the desired reports. See [Report on Google Analytics data in Customer Journey Analytics](report.md).
