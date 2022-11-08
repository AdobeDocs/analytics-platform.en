---
title: Migrate data from Google Analytics to Customer Journey Analytics
description: Learn the overarching workflow around how to move data from Google Analytics to Adobe Experience Platform, and viewing reports in Customer Journey Analytics.
exl-id: 10c485c9-66ab-4925-a357-a66a374d4c6f
---
# Migrate data from Google Analytics to Customer Journey Analytics

If you are new to Customer Journey Analytics, it is possible that your organization has existing data on another Analytics platform, such as Google Analytics. You can follow these overarching steps to move that data into Adobe Experience Platform, allowing you to view reports in Customer Journey Analytics.

Workflows are provided for both historical data and current data collection. You can follow one or both of these workflows, depending on your organization's data needs.

## Bring historical data from Google Analytics into Adobe Experience Platform

Ingesting historical (backfill) data involves exporting data from Google and importing that data into Adobe Experience Platform. See [Ingest Google Analytics data in Adobe Experience Platform](backfill.md).

Once you successfully bring historical data into Platform, you can either [Configure streaming current data](streaming.md), or immediately start reporting on backfilled data in CJA by [Creating a connection](/help/connections/create-connection.md).

## Configure an existing Google Analytics implementation for Adobe Experience Platform {#configure}

Ingesting current (streaming) data involves sending data to Adobe Experience Edge, which then forwards that data to Adobe Experience Platform. See [Set up streaming Google Analytics data in Adobe Experience Platform](streaming.md).

## Configure a Connection and Data View in CJA

Once you successfully ingest historical data and/or configure data collection to Adobe Experience Platform, you can [Create a connection](/help/connections/create-connection.md) to allow Customer Journey Analytics to reference that data.

Use the connection to create one or more [Data Views](/help/data-views/create-dataview.md) for use in Analysis Workspace.

## Create reports

After configuring dimensions and metrics within a Data View, you can begin using Analysis Workspace to generate the desired reports. See [Report on Google Analytics data in Customer Journey Analytics](report.md).
