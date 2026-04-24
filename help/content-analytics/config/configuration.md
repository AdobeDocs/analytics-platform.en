---
title: Configure Content Analytics
description: An overview of how to configure Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 3ea46223-c7d0-4b1f-bc84-4f35494f13a0
TQID: https://experienceleague.adobe.com/a-Mu3MKfpRsUqgxx7JWP3NR4vji62VaNFi-hI5teDZI
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c4147b6e-073b-4d3c-9ab1-d60f2f4434ef
    internal-label: Behavioral data
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
---
# Configure Content Analytics

This article documents, on a high level, how to configure Content Analytics. 

Before you configure Content Analytics, you must ensure the [prerequisites](#prerequisites) are met, you do have the required [access control](#access-control), and you are aware of the [limitations](#limitations).


High-level steps

![Configuration of Content Analytics](../assets/aca-configuration.svg){zoomable="yes"}

1. Use the Content Analytics [guided configuration](guided.md) wizard to guide you through all steps required to set up the prerequisites for a configuration of Content Analytics. You can save your configurations at any time and return later.
1. Once you are comfortable with the configuration values, you can implement the configuration. This implementation creates all the required artifacts, based on what you have configured in the wizard. 
1. Only when you [manually publish](manual.md) the Tags property, your Content Analytics configuration is effectively deployed and data collection is started.

1. You can only make some minor changes to an implemented configuration using the [guided configuration](guided.md) wizard. For example, change the [data view](/help/data-views/data-views.md).
1. You can make other changes to an implemented configuration using the [Adobe Content Analytics extension](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview) in the associated Tags property.
1. Only when you [manually re-publish](manual.md) the Tags property, the configuration modifications are effectively deployed and data collection, based on your changes, is started.


## Prerequisites

Before you configure Content Analytics, ensure that the following prerequisites are met:

* You have allow-listed the User Agent and IP address for the featurization service that is used in Content Analytics. The User Agent string to configure is: <code>AdobeFeaturization/1.0</code>.
* If you have implemented the [Web SDK using JavaScript](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/library){target="_blank"} for regular behavioral data collection, ensure you are using the default name <code>alloy</code> for the JavaScript library.
* You have a Customer Journey Analytics Product Administrator role, with the additional permissions to manage connections and to manage data views. 
* If you consider to collect Content Analytics experiences, ensure you setup and update [Content Analytics versioning](manual.md#versioning) based on changes on your web pages.
* You must have [permissions for data collection](https://experienceleague.adobe.com/en/docs/experience-platform/collection/permissions){target="_blank"}: 
  * [Experience Platform permissions](https://experienceleague.adobe.com/en/docs/experience-platform/collection/permissions#adobe-experience-platform-permissions){target="_blank"}
  * [Experience Platform Data Collection permissions](https://experienceleague.adobe.com/en/docs/experience-platform/collection/permissions#adobe-experience-platform-data-collection-permissions){target="_blank" }
* You have carefully considered the following important configuration options:

  * Your site is suited for experience reporting. Proper experience reporting is only possible when the following conditions are met:
     * The pages on the site must be reproducible using the page URL.
     * The text content seen by any given user can be reproduced using the page URL and does not depend on cookies or other personalization mechanisms.
  * You have a clear understanding for which pages you want to capture content engagement analysis and insights.
  * You have a clear understanding for which (type of) assets you want to capture content engagement analysis and insights.


## Access control

>[!IMPORTANT]
>
>There is no Content Analytics permission that you can configure to enable or disable Content Analytics access for individual users or groups of users.
>

To provide a user or group of users access to Content Analytics, you must provide the user or group of users access to one or more [data views that are configured for Content Analytics](guided.md#data-view).

This access implies:

1. The Content Analytics enabled data view is included as part of the Data View permissions for a specific Customer Journey Analytics product profile.
1. That specific Customer Journey Analytics product profile is one of the product profiles assigned to the user or group of users.

## Limitations

The schema used for Content Analytics event data is system-owned. A system-owned schema cannot be modified, which implies:
  
* You cannot include field groups for the support of functionalities like geolocation, bot detection, or device lookup. 
* You cannot add a specific identifier to support [field-based stitching](/help/stitching/fbs.md).

>[!MORELIKETHIS]
>
>* [Guided configuration](guided.md)
>* [Manual configuration](manual.md)
>* [Access control](/help/technotes/access-control.md)
>
