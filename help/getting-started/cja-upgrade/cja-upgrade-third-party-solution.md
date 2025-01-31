---
title: Upgrade from a third-party analytics solution to Customer Journey Analytics
description: Learn how to upgrade from a third-party analytics solution to Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: yes
hidefromtoc: yes
exl-id: bc79ba1a-1153-4fe8-b265-9703a323c977
---
# Upgrade from a third-party analytics solution to Customer Journey Analytics {#upgrade-from-third-party}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-third-party"
>title="A third-party analytics product"
>abstract="An implementation that collects data for a third-party analytics product, such as Google Analytics. Selecting this option disables several options in the questionnaire that don't apply when upgrading to Customer Journey Analytics from a third-party analytics product."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>Use the information on this page when answering questions in the [Customer Journey Analytics upgrade checklist](https://gigazelle.github.io/cja-ttv/).

The recommended process of upgrading from a third-party analytics solution to Customer Journey Analytics is a new implementation of the Experience Platform Web SDK, which is the preferred data collection method for Customer Journey Analytics. In conjunction with the Web SDK, Adobe also recommends ingesting historical data from the third-party analytics solution into Adobe Experience Platform. 

<!-- After you have enough historical data using the Experience Platform Web SDK and you have fully transitioned to Customer Journey Analytics, the Analytics source connector can be turned off and the Web SDK can be used exclusively. -->

Use the following process when moving to Customer Journey Analytics from a third-party analytics solution, such as Google Analytics: 

1. ...


Contact your Adobe representative if you need more specific advice, guidance, or support.

|Existing analytics solution | Description | Available upgrade paths |
|---------|----------|----------|
| AppMeasurement | AppMeasurement for JavaScript has historically been a common method to implement Adobe Analytics.<p>For more information about this implementation type, see [Implement Adobe Analytics with AppMeasurement for JavaScript](https://experienceleague.adobe.com/en/docs/analytics/implementation/js/overview).</p> |<ul><li>[(Recommended) New implementation of the Experience Platform Web SDK for ongoing data collection; the Analytics Source Connector for historical data](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[New implementation of the Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) </li><li>Migrate Adobe Analytics to the Web SDK</li><li>[Analytics Source Connector](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-exclusively.md)</li></ul>  | 
| Adobe Analytics extension (tags) | <p>Tags in Adobe Experience Platform is a tag management solution that lets you deploy Analytics code alongside other tagging requirements. Adobe offers integrations with other solutions and products, and lets you deploy custom code. All of these tasks can be done without relying on any development teams in your organization to update code on your site.</p><p>For more information about this implementation type, see [Implement Adobe Analytics using the Analytics extension](https://experienceleague.adobe.com/en/docs/analytics/implementation/launch/overview).</p> | <ul><li>[(Recommended) New implementation of the Experience Platform Web SDK for ongoing data collection; the Analytics Source Connector for historical data](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[New implementation of the Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) </li><li>Migrate Adobe Analytics to the Web SDK</li><li>[Analytics Source Connector](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-exclusively.md)</li></ul> | 
| Experience Platform Web SDK (alloy.js) | The Experience Platform Web SDK is Adobe's current recommended method to implement Adobe Analytics. The Adobe Experience Platform Edge Network allows you to send data destined to multiple products to a centralized location. <p>For more information about this implementation type, see [Implement Adobe Analytics with the Adobe Experience Platform Edge Network](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/overview).</p> | <ul><li>[(Recommended) New implementation of the Experience Platform Web SDK for ongoing data collection; the Analytics Source Connector for historical data](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[New implementation of the Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) </li><li>Configure the Adobe Analytics Web SDK implementation to send data to Platform</li></ul> | 
| Experience Platform Web SDK extension (tags) | The Experience Platform Web SDK is Adobe's current recommended method to implement Adobe Analytics for web data. The Adobe Experience Platform Edge Network allows you to send data destined to multiple products to a centralized location. <p>For more information about this implementation type, see [Implement Adobe Analytics using the Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/overview)</p> | <ul><li>[(Recommended) New implementation of the Experience Platform Web SDK for ongoing data collection; the Analytics Source Connector for historical data](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[New implementation of the Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md)</li><li>Configure the Adobe Analytics Web SDK implementation to send data to Platform</li></ul> | 
| Experience Platform Mobile SDK | The Experience Platform Mobile SDK is Adobe's current recommended method to implement Adobe Analytics for mobile data. The Adobe Experience Platform Edge Network allows you to send data destined to multiple products to a centralized location.<p>The Adobe Experience Platform Mobile SDK helps power Adobe's Experience Cloud solutions and services in your mobile apps. </p><p>For more information about this implementation type, see [Implement Adobe Analytics using the Adobe Experience Platform Mobile SDK](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/mobile-sdk/overview)</p> | <ul><li>[(Recommended) New implementation of the Experience Platform Web SDK for ongoing data collection; the Analytics Source Connector for historical data](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[New implementation of the Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) </li><li>Configure the Adobe Analytics Web SDK implementation to send data to Platform</li></ul> | 
| Bulk Data Insertion API | The Bulk Data Insertion API (BDIA) is an Adobe Analytics capability that lets you upload server call data in batches of files instead of using client-side libraries such as AppMeasurement. </p><p>For more information about this implementation type, see [Bulk Data Insertion API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/).</p> | <ul><li>[(Recommended) New implementation of the Experience Platform Web SDK for ongoing data collection; the Analytics Source Connector for historical data](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[New implementation of the Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md)</li><li>[Adobe Experience Platform Edge Network Server API and Edge Network](/help/data-ingestion/serverapi.md)</li></ul> | 

{style="table-layout:auto"}
