---
title: Configure streaming Google Analytics data into Adobe Experience Platform
description: Learn how to set up your implementation to send a Google data layer into Adobe Experience Platform
exl-id: 58854f4b-ae28-424e-a2cf-0e76219cb802
---
# Configure streaming Google Analytics data into Adobe Experience Platform

This page focuses on how to ingest your live Google Analytics data into Adobe Experience Platform, allowing you to reference that dataset in a Data View within Customer Journey Analytics. You can combine the steps on this page with [Ingest Google Analytics historical data into Adobe Experience Platform](backfill.md), which generates a dataset containing historical data. Combine a streaming dataset with a backfill dataset to get a seamless view of past and present data in Customer Journey Analytics.

Configuring data collection involves the following steps:

1. Implement [Tags for Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html). See the [Quickstart guide](https://experienceleague.adobe.com/docs/experience-platform/tags/get-started/quick-start.html) to get a basic implementation up and running.
1. Install the [Google Data Layer extension](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/google-data-layer/overview.html). This extension acts as an alternative to installing the Web SDK extension, geared specifically towards a Google data layer.
1. [Create a Datastream](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html) in Adobe Experience Platform Data Collection. Configure the Datastream to send data to Adobe Experience Platform. You must currently map each Google data layer object to an applicable XDM field here. Adobe plans to simplify this mapping workflow in the future.

Once you implement and publish the desired tags on your site, you can then proceed to [Create a connection](/help/connections/create-connection.md), then [Create a data view](/help/data-views/create-dataview.md).
