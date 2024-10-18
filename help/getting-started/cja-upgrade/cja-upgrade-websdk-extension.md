---
title: Upgrade from Adobe Analytics to Customer Journey Analytics
description: Plan your upgrade from Adobe Analytics to Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
---
# Upgrade to Customer Journey Analytics from the WebSDK Extension

Use the following sections to understand the differences between your current and future implementations, and how to get started with the upgrade.

## Understand how your existing Adobe Analytics implementation compares with the new Customer Journey Analytics implementation

The following sections show the differences between a Web SDK Extension implementation that sends data only to Adobe Analytics, and an implementation after upgrading to Customer Journey Analytics. 

### WebSDK Extension implementation with Adobe Analytics only

When your Adobe Analytics environment is implemented with the WebSDK Extension, data is sent to Experience Platform Edge and then to Adobe Analytics, as depicted in the following graphic:

![Anlytics WebSDK implementation AA only](assets/websdk-extension-aa.png)

### WebSDK Extension implementation with both Adobe Analytics and Customer Journey Analytics

To upgrade to Customer Journey Analytics from an Adobe Analytics environment that is implemented with the WebSDK, Adobe recommends a two-pronged approach: First, begin sending data from Edge to Adobe Experience Platform, and from Platform to Customer Journey Analytics. Second, set up the Analytics source connector. 

This configuration is depicted in the following graphic, with changes from the original Adobe Analytics implementation shown in green:

![Analytics Extension implementation](assets/websdk-extension-cja.png)

## Upgrade to Customer Journey Analytics

Adobe recommends a two-pronged upgrade approach when upgrading from Adobe Analytics to Customer Journey Analytics: a new implementation of the Experience Platform WebSDK and the Adobe Analytics source connector.

When used together, this two-pronged approach lays the best foundation for a successful upgrade from Adobe Analytics to Customer Journey Analytics.

For more information about the benefits of using this approach when upgrading, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).

### Send data to Adobe Experience Platform

To upgrade to Customer Journey Analytics, you need to begin sending data to Adobe Experience Platform. Use the following process to send data to Platform: 

1. Begin sending data to Platform by [setting up a datastream](/help/data-ingestion/aepwebsdk.md#set-up-a-datastream).

   Because your Adobe Analytics implementation is already using the Experience Platform Web SDK, you can ignore the other sections in [Ingest data via the Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk).
   
   If you are already sending data to Platform with your Adobe Analytics implementation, this step is not required. You simply need to create a connection between Platform datasets and Customer Journey Analytics, as described later in this process.
   
1. (Optional) [Create an XDM schema for your organization](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema-and-dataset).

   Work with your data team to identify your organization's ideal schema design for Customer Journey Analytics.
   
   Note: For information about the advantages of creating an XDM schema, see [Choose your schema](/help/getting-started/cja-upgrade/cja-upgrade-path.md#choose-your-schema).
   
1. (Conditional) If you created an XDM schema, [use Data Prep to map all of the fields in the data object to your XDM schema](https://experienceleague.adobe.com/en/docs/experience-platform/data-prep/home).

### Set up the Analytics source connector

1. To set up the Adobe Analytics source connector, follow the steps in [Ingest and use data from traditional Adobe Analytics](/help/data-ingestion/analytics.md). 

