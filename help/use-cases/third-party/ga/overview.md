---
title: Migrate data from Google Analytics
description: Learn the overarching workflow around how to move data from Google Analytics to Adobe Experience Platform, and viewing reports in Customer Journey Analytics.
exl-id: 10c485c9-66ab-4925-a357-a66a374d4c6f
feature: Use Cases
role: Admin
TQID: https://experienceleague.adobe.com/C9rt1pyuM6ykLUlXCHc0ITwGeGcuLw6qisXnJxwX4uU
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
    internal-label: Metrics
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
---
# Migrate data from Google Analytics

>[!BEGINSHADEBOX]

This guide covers data migration for administrators. If you are an analyst looking to find your GA4 reports in Customer Journey Analytics, see [Transitioning from Google Analytics 4 to Customer Journey Analytics](/help/getting-started/ga-to-cja/home.md) and [GA4 reports in Customer Journey Analytics](/help/getting-started/ga-to-cja/reports.md).

>[!ENDSHADEBOX]

If you are new to Customer Journey Analytics, it is possible that your organization has existing data on another Analytics platform, such as Google Analytics. You can follow these overarching steps to move that data into Adobe Experience Platform, allowing you to view reports in Customer Journey Analytics.

Workflows are provided for both historical data and current data collection. You can follow one or both of these workflows, depending on your organization's data needs.

## Bring historical data from Google Analytics into Adobe Experience Platform

Ingesting historical (backfill) data involves exporting data from Google and importing that data into Adobe Experience Platform. See [Ingest Google Analytics data in Adobe Experience Platform](backfill.md).

Once you successfully bring historical data into Platform, you can either [Configure streaming current data](streaming.md), or immediately start reporting on backfilled data in Customer Journey Analytics by [Creating a connection](/help/connections/create-connection.md).

## Configure an existing Google Analytics implementation for Adobe Experience Platform {#configure}

Ingesting current (streaming) data involves sending data to the Adobe Experience Platform Edge Network, which then forwards that data to Adobe Experience Platform. See [Set up streaming Google Analytics data in Adobe Experience Platform](streaming.md).

## Configure a Connection and Data View in Customer Journey Analytics

Once you successfully ingest historical data and/or configure data collection to Adobe Experience Platform, you can [Create a connection](/help/connections/create-connection.md) to allow Customer Journey Analytics to reference that data.

Use the connection to create one or more [Data Views](/help/data-views/create-dataview.md) for use in Analysis Workspace.

## Create reports

After configuring dimensions and metrics within a Data View, you can begin using Analysis Workspace to generate the desired reports. See [Report on Google Analytics data in Customer Journey Analytics](report.md).
