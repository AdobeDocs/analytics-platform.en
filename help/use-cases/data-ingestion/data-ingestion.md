---
title: Data ingestion options for Customer Journey Analytics
description: Understand the different ways you can ingest data into Customer Journey Analytics
exl-id: 4a47c587-f48e-4e29-b97f-00c7d7e6972c
solution: Customer Journey Analytics
feature: Use Cases
---
# Data ingestion options for Customer Journey Analytics

You have a number of options when it comes to ingesting data into Customer Journey Analytics. Some of them assume that you want to move traditional Adobe Analytics data over, some of them assume that you ingest data directly from Adobe Experience Platform. This reference provides high-level steps to follow, with links to more detailed information.

## Ingest data from traditional Adobe Analytics

This workflow utilizes the Analytics source connector and varies depending on whether you use DTM or Launch as a Tag Manager.

### Via tags in Adobe Experience Platform (formerly called [!UICONTROL Launch])

1. [Create a Data Layer](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/data-layer.html), if you haven't already. A data layer is a framework of JavaScript objects on your site that contains all variable values used in your implementation. It allows greater control and easier maintenance in your implementation.
1. Use [Adobe Experience Platform tags](https://experienceleague.adobe.com/docs/analytics/implementation/launch/overview.html) to implement code on your site for data collection, if you haven't already. This tag management solution lets you deploy Analytics code alongside other tagging requirements. Tags offer integrations with other solutions and products, and let you deploy custom code. All of these tasks can be done without relying on any development teams in your organization to update code on your site..
1. Create an [Adobe Analytics source connector](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html) in Adobe Experience Platform. This source connector will ingest your Analytics data into Experience Platform in a standardized framework called [Experience Data Model (XDM) System](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html). See also [Utilizing Adobe Analytics report suite data in Customer Journey Analytics](/help/getting-started/aa-vs-cja/aa-data-in-cja.md).
1. Use [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html) to create one or more connections and data views that will inform your cross-channel reporting.

## Ingest data via the Adobe Experience Platform Web SDK and the Edge Network

[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html) is a client-side JavaScript library that allows customers of Adobe Experience Cloud to interact with the various services in the Experience Cloud through the Adobe Experience Platform Edge Network. 

1. [Configure the Adobe Experience Platform Web SDK extension in tags](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/sdk/overview.html) to send data to the Adobe Experience Cloud from web properties, through the Adobe Experience Platform Edge Network.
1. Use [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html) to create one or more [connections](/help/connections/create-connection.md) and [data views](/help/data-views/data-views.md) that will inform your cross-channel reporting.

## Ingest data with batch ingestion and streaming ingestion

Adobe Experience Platform brings data from multiple sources together in order to help marketers better understand the behavior of their customers. Adobe Experience Platform Data Ingestion represents the multiple methods by which Platform ingests data from these sources, as well as how that data is persisted within the Data Lake for use by downstream Platform services.

### Batch ingestion

1. Set up [Batch Ingestion](https://experienceleague.adobe.com/docs/experience-platform/ingestion/batch/overview.html#batch) to allow you to ingest data into Adobe Experience Platform as batch files. Data being ingested can be the profile data from a flat file in a CRM system (such as a parquet file), or data that conforms to a known schema in the Experience Data Model (XDM) registry.
1. Use [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html) to create one or more [connections](/help/connections/create-connection.md) and [data views](/help/data-views/data-views.md) that will inform your cross-channel reporting.

### Streaming ingestion

1. Set up [Streaming ingestion](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/overview.html#streaming) to send data from client and server-side devices to Experience Platform in real time.
1. Use [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html) to create one or more [connections](/help/connections/create-connection.md) and [data views](/help/data-views/data-views.md) that will inform your cross-channel reporting.

## Bring in Google Analytics data to analyze in Customer Journey Analytics

Review this tutorial on how to [Analyze Google Analytics Data using Customer Journey Analytics](https://experienceleague.adobe.com/docs/platform-learn/comprehensive-technical-tutorial-v22/module12/ex5.html?lang=en) for detailed steps.

## Use Bulk Data Insertion API to get data into Analytics, then ingest via Adobe Source Connector in Experience Platform

1. [Use Bulk Data Insertion API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md) to submit server-side collection data to Adobe Analytics. It lets you submit CSV-formatted files containing event data.
1. [Create an Adobe Analytics source connector](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html) to bring this consumer data into Adobe Experience Platform.
1. Use [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html) to create one or more [connections](/help/connections/create-connection.md) and [data views](/help/data-views/data-views.md) that will inform your cross-channel reporting.
