---
title: Data Ingestion Overview
description: Understand the different ways that you can ingest data into Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
exl-id: ead96b72-40f1-4ce9-8d91-c8ceea6c4458
---
# Data Ingestion Overview

You have several options when ingesting data into Customer Journey Analytics. Some of them assume that you want to move traditional Adobe Analytics data over, some of them assume that you use data ingested into Adobe Experience Platform.

>[!IMPORTANT]
>
>In all scenarios, the data you want to _use_ in Customer Journey Analytics is actually _ingested_ in Adobe Experience Platform.


See the high-level Customer Journey Analytics architecture shown earlier in [Overview](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=en):

![Customer Journey Analytics](./assets/cja-architecture.png)

The dataset in the architecture above can originate from various sources: 

- batch data, 

- streaming data, 

- data from a current Adobe Analytics deployment, 

- data from tracking your website / mobile app using the Adobe Experience Platform Web/Mobile SDK,

- data from tracking a desktop application, console game, set-top box or IoT device using the Adobe Experience Platform Edge Network Server API, or

- data coming from a third-party data provider for which Adobe provides a source connector. 

And you can have many of these datasets.

This section of the documentation provides quick start guides for various scenarios.

## Ingest and use data from traditional Adobe Analytics

You already have Adobe Analytics deployed and want to ingest this data in Adobe Experience Platform and use, combine, and analyze it with data from other channels and data sources in Customer Journey Analytics.

See [Ingest and use data from traditional Adobe Analytics](./analytics.md) for more information.


## Ingest and use data via the Edge Network 

### Using the Adobe Experience Platform Web SDK

You want to analyze your website with Adobe technology, potentially migrating from another solution or start tracking your person's behavior. You want to follow Adobe's best practices for implementation, which is using the Adobe Experience Platform SDKs and Edge Network, to ingest the data. Then you can use, combine, and analyze the ingested data with data from other channels and data sources in Customer Journey Analytics.

See [Ingest and use data via the Adobe Experience Platform Web SDK](./aepwebsdk.md) for more information.

### Using the Adobe Experience Platform Mobile SDK

You want to analyze your mobile app with Adobe technology, potentially migrating from another solution or start tracking a person's behavior in the app from scratch. You want to follow Adobe's best practices for implementation, which is using the Adobe Experience Platform SDKs and Edge Network, to ingest the data. Then you can use, combine, and analyze the ingested data with data from other channels and data sources in Customer Journey Analytics.

See [Ingest and use data via the Adobe Experience Platform Mobile SDK](./aepmobilesdk.md) for more information.

### Using the Adobe Experience Platform Edge Network Server API

You want to analyze your desktop application, game as played on a game console, usage of a video streaming application on a set-top box or your IoT device with Adobe technology. Potentially migrating from another solution or start tracking a person's behavior on these devices from scratch. You want to follow Adobe's best practices for implementation, which is using the Adobe Experience Platform Edge Network Server APIs and Edge Network, to ingest the data. Then you can use, combine, and analyze the ingested data with data from other channels and data sources in Customer Journey Analytics.

See [Ingest and use data via the Adobe Experience Platform Edge Network Server API](./serverapi.md) for more information.

## Ingest and use batch data

You have relevant batch data available which provides details that can help you to better understand customer behavior and analyze customer interactions. Examples of such batch data are flat files in CSV, JSON, or Parquet format from a CRM system, loyalty application, or other solution for which Adobe currently does not provide a source connector. Ingesting this batch data into Adobe Experience Platform allows you to use, combine, and analyze it with data from other channels and data sources in Customer Journey Analytics.

See [Ingest and use batch data](./batch.md) for more information.

## Ingest and use streaming data

You have a relevant data source like a CRM system, ERP system, or any other source which provides details that can help you to better understand customer behavior and analyze customer interactions. That data source is able to communicate over HTTP or public cloud streaming infrastructure but for which Adobe currently does not provide a source connector. Ingesting this streaming data into Adobe Experience Platform in real time allows you to use, combine, and analyze it with data from other channels and data sources in Customer Journey Analytics.

See [Ingest and use streaming data](./streaming.md) for more information.

## Ingest and use data using source connectors

You have data available from a source that is supported by a source connector. Source connectors are configurable configurations that allow you to ingest data from Adobe, first-party and third-party application into Adobe Experience Platform. See [Source connectors overview](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=en) for an overview of available source connectors. Using the source connector you can easily ingest data from the source into Adobe Experience Platform and then use, combine and analyze it with data from other channels and data sources in Customer Journey Analytics.

See [Ingest and use data using source connectors](./sources.md) for more information.
