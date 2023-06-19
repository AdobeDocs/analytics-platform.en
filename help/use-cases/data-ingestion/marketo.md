---
title: Ingest Marketo Engage data into Adobe Experience Platform and report in Customer Journey Analytics
description: Learn how to bring Marketo Engage data into Customer Journey Analytics
solution: Customer Journey Analytics
feature: Use Cases
exl-id: ef8a2d08-848b-4072-b400-7b24955a085b
---
# Ingest Marketo Engage data into Adobe Experience Platform and report in Customer Journey Analytics

You can leverage the newly-available Marketo Engage datasets in Adobe Experience Platform (Adobe Experience Platform) to provide valuable analytics and reporting solutions to B2B marketers. Then report on these datasets in Adobe Customer Journey Analytics.

## Step 1: Map Marketo source data fields to their XDM targets

Map the [Persons](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/marketo.html?lang=en#persons) and [Activities](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/marketo.html?lang=en#activities) objects to their respective XDM schema target fields.

## Step 2: Ingest Marketo data into Adobe Experience Platform

Use the [Marketo Engage connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/marketo/marketo.html?lang=en) to bring data from Marketo to Experience Platform and keep this data up to date using Platform-connected applications.

## Step 3: Set up a connection to this dataset in Customer Journey Analytics

In order to report on Experience Platform datasets, you first have to establish a connection between datasets in Experience Platform and Customer Journey Analytics. Find more information under [Create a connection](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=en).

## Step 4: Create one or more data views

A [data view](/help/data-views/data-views.md) is a container specific to Customer Journey Analytics that lets you determine how to interpret data from a connection. It specifies all dimensions and metrics available in Analysis Workspace - in this case, metrics and dimensions specific to Marketo. It also specifies which columns those dimensions and metrics obtain their data from. Data views are defined in preparation for reporting in Analysis Workspace. 

## Step 5: Report in Analysis Workspace

One use case you might explore is: How many web page visits by leads did we have in April-June 2020?

1. Open [Analytics Workspace](/help/analysis-workspace/home.md) and create a new project. 
   Customers with B2B/B2P CDP can conduct B2C-style analysis in Customer Journey Analytics. B2B objects are not yet available.

1. Create a [filter](/help/components/filters/create-filters.md) for web page views as follows - Event Type = web.webpagedetails.pageViews : 

   ![](../assets/marketo-filter.png)

1. Into the Freeform table, pull in the filter you created - Web Page Views, then pull in the Month date range. This gives you Web page visits by leads each month:

   ![](../assets/marketo-freeform.png)

1. Or pull in the following dimensions: Person Key or Work Email Address. This gives you the Web page visits by each lead:

   ![](../assets/marketo-freeform2.png)
