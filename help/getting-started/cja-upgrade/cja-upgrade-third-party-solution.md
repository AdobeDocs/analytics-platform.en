---
title: Upgrade from a third-party analytics solution to Customer Journey Analytics
description: Learn how to upgrade from a third-party analytics solution to Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: bc79ba1a-1153-4fe8-b265-9703a323c977
---
# Upgrade from a third-party analytics solution to Customer Journey Analytics {#upgrade-from-third-party}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-third-party"
>title="A non-Adobe Analytics product"
>abstract="An implementation that collects data for a product other than Adobe Analytics, such as Google Analytics. Selecting this option disables several options in the upgrade guide that don't apply when upgrading to Customer Journey Analytics from a non-Adobe Analytics product."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

The recommended process of upgrading from an analytics solution other than Adobe Analytics to Customer Journey Analytics is a new implementation of the Experience Platform Web SDK, which is the preferred data collection method for Customer Journey Analytics. In conjunction with the Web SDK, Adobe also recommends ingesting historical data from the third-party analytics solution into Adobe Experience Platform. 

<!-- After you have enough historical data using the Experience Platform Web SDK and you have fully transitioned to Customer Journey Analytics, the Analytics source connector can be turned off and the Web SDK can be used exclusively. -->

Use the following process when moving to Customer Journey Analytics from a third-party analytics solution, such as Google Analytics: 

1. Follow the [Detailed recommended upgrade steps](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#detailed-recommended-upgrade-steps).

   These steps are intended for organizations upgrading from Adobe Analytics. When following these steps, understand the following:
   
   * You must create a datastream.

   * You cannot migrate projects and components from a non-Adobe Analytics solution.

   * Depending on your analytics solution, a source connector might be available for ingesting historical data. For more information see [Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/sources/home#analytics) in [Source connectors overview](https://experienceleague.adobe.com/en/docs/experience-platform/sources/home) in the Experience Platform documentation.


Contact your Adobe representative if you need more specific advice, guidance, or support.

