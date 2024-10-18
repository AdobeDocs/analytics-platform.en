---
title: Upgrade from Adobe Analytics to Customer Journey Analytics
description: Plan your upgrade from Adobe Analytics to Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
---
# Upgrade to Customer Journey Analytics from the WebSDK Extension

## WebSDK Extension implementation with Adobe Analytics only

When your Adobe Analytics environment is implemented with the WebSDK Extension, data is sent to Experience Platform Edge and then to Adobe Analytics, as depicted in the following graphic:

![Anlytics WebSDK implementation AA only](assets/websdk-extension-aa.png)

## WebSDK Extension implementation with both Adobe Analytics and Customer Journey Analytics

To upgrade to Customer Journey Analytics from an Adobe Analytics environment that is implemented with the WebSDK, Adobe recommends a two-pronged approach: First, begin sending data from Edge to Adobe Experience Platform, and from Platform to Customer Journey Analytics. Second, set up the Analytics source connector. 

This configuration is depicted in the following graphic, with changes from the original Adobe Analytics implementation shown in green:

![Analytics Extension implementation](assets/websdk-extension-cja.png)

