---
title: Data ingestion options for Customer Journey Analytics
description: Understand the different ways you can ingest data into Customer Journey Analytics
---

# Data ingestion options for Customer Journey Analytics

You have a number of options when it comes to ingesting data into Customer Journey Analytics. Some of them assume that you want to move traditional Adobe Analytics data over, some of them assume that you ingest data directly from Adobe Experience Platform. This reference provides high-level steps to follow, with links to more detailed information.

## Ingest data from traditional Adobe Analytics

This workflow utilizes the Adobe Analytics Data Connector and varies depending on whether you use DTM or Launch as a Tag Manager.

### Via Dynamic Tag Management (DTM)

1. [Create a Data Layer](https://docs.adobe.com/content/help/en/analytics/implementation/prepare/data-layer.html), if you haven't already. A data layer is a framework of JavaScript objects on your site that contains all variable values used in your implementation. It allows greater control and easier maintenance in your implementation.
1. Use [DTM](https://docs.adobe.com/content/help/en/analytics/implementation/other/dtm/dtm-implementation-overview.html) to implement code on your site for data collection, if you haven't already. Dynamic Tag Management provides a single data layer that pushes data from multiple sources.
1. Create an [Adobe Analytics source connector](https://docs.adobe.com/content/help/en/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html) in Adobe Experience Platform. This source connector will ingest your Analytics data into Experience Platform in a standardized framework called [Experience Data Model (XDM) System](https://docs.adobe.com/content/help/en/experience-platform/xdm/home.html).
1. Use [Customer Journey Analytics](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-overview/cja-getting-started.html) to create one or more connections and data views that will inform your cross-channel reporting.

### Via Launch

1. [Create a Data Layer](https://docs.adobe.com/content/help/en/analytics/implementation/prepare/data-layer.html), if you haven't already. A data layer is a framework of JavaScript objects on your site that contains all variable values used in your implementation. It allows greater control and easier maintenance in your implementation.
1. Use [Adobe Experience Platform Launch](https://docs.adobe.com/content/help/en/analytics/implementation/launch/overview.html) to implement code on your site for data collection, if you haven't already. Launch is a tag management solution that lets you deploy Analytics code alongside other tagging requirements. Launch offers integrations with other solutions and products, and lets you deploy custom code. All of these tasks can be done without relying on any development teams in your organization to update code on your site..
1. Create an [Adobe Analytics source connector](https://docs.adobe.com/content/help/en/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html) in Adobe Experience Platform. This source connector will ingest your Analytics data into Experience Platform in a standardized framework called [Experience Data Model (XDM) System](https://docs.adobe.com/content/help/en/experience-platform/xdm/home.html).
1. Use [Customer Journey Analytics](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-overview/cja-getting-started.html) to create one or more connections and data views that will inform your cross-channel reporting.

## Ingest data from the AEP Web SDK

You can do data collection via the Adobe Experience Platform Web SDK and the Adobe Experience Platform Edge Network, with or without the help of Launch.

1. 
https://docs.adobe.com/content/help/en/experience-platform/edge/home.html
https://docs.adobe.com/content/help/en/experience-platform/edge/get-started/quick-start-without-launch.html
https://docs.adobe.com/content/help/en/analytics-platform/using/cja-overview/cja-getting-started.html

### Without Launch



### Via Launch

Launch is an extensible and open platform that lets you and Adobe Partners 

## Batch ingestion and Streaming ingestion

TBD

## Ingest Google Analytics data

TBD

## Ingest data via the Bulk Ingestion API

TBD