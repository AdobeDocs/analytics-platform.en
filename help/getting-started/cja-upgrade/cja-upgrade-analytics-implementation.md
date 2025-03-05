---
title: Understand your Adobe Analytics implementation and how it affects your upgrade to Customer Journey Analytics
description: Learn about the recommended path when upgrading from Adobe Analytics to Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: yes
hidefromtoc: yes
exl-id: b9cff809-6df7-4d75-9bc1-0cc12074d355
---
# Understand your Adobe Analytics implementation and how it affects your upgrade to Customer Journey Analytics {#implementation-affects-upgrade}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-appmeasurement"
>title="AppMeasurement (Manual JS file)"
>abstract="A JavaScript implementation that loads AppMeasurement.js on a page, and sends data to Adobe using the s object (for example, s.eVar1)."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-analyticsextension"
>title="Adobe Analytics extension (Tags)"
>abstract="A tags implementation that loads Adobe Experience Platform Data Collection (formerly known as Launch). The tag has the Adobe Analytics extension installed."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk"
>title="Web SDK (alloy.js)"
>abstract="A JavaScript implementation that loads the Web SDK library (alloy.js) on a page, and sends data to Adobe using a JSON payload."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdkextension"
>title="Web SDK extension (Tags)"
>abstract="A tags implementation that loads Adobe Experience Platform Data Collection (formerly known as Launch). The tag has the Web SDK extension installed."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-api"
>title="Data Insertion API"
>abstract="An implementation that uses the data insertion API or bulk data insertion API."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-mobilesdk"
>title="Mobile SDK"
>abstract="An implementation that uses the Adobe Experience Platform Mobile SDK."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-unknown"
>title="Unknown implementation"
>abstract="If you're not the person that manages your implementation, you can temporarily select this option."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-determine-implementation"
>title="Determine your existing implementation type"
>abstract="Work internally within your organization to determine what type of implementation that you currently use to send data to Adobe Analytics. Partnering with the individual or team that knows this information is likely, when you're ready to migrate to Customer Journey Analytics.<br><br>After you determine the type of implementation that your organization uses, modify your answer in the questionnaire."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

There are various ways that Adobe Analytics can be implemented. When upgrading to Customer Journey Analytics, not all upgrade paths are available for all Adobe Analytics implementations. However, the recommended upgrade path is available regardless of how Adobe Analytics is implemented in your organization.

Use the information below to learn about your current Adobe Analytics implementation and which upgrade paths are available to your organization. 

Contact your Adobe representative if you need more specific advice, guidance, or support.

|Existing Adobe Analytics implementation | Description | Available upgrade paths |
|---------|----------|----------|
| AppMeasurement | AppMeasurement for JavaScript has historically been a common method to implement Adobe Analytics.<p>For more information about this implementation type, see [Implement Adobe Analytics with AppMeasurement for JavaScript](https://experienceleague.adobe.com/en/docs/analytics/implementation/js/overview).</p> |<ul><li>[(Recommended) New implementation of the Experience Platform Web SDK for ongoing data collection; the Analytics source connector for historical data](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[New implementation of the Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) </li><li>Migrate Adobe Analytics to the Web SDK</li><li>[Analytics source connector](/help/getting-started/cja-upgrade/cja-upgrade-alternative-source-connector.md)</li></ul>  | 
| Adobe Analytics extension (tags) | <p>Tags in Adobe Experience Platform is a tag management solution that lets you deploy Analytics code alongside other tagging requirements. Adobe offers integrations with other solutions and products, and lets you deploy custom code. All of these tasks can be done without relying on any development teams in your organization to update code on your site.</p><p>For more information about this implementation type, see [Implement Adobe Analytics using the Analytics extension](https://experienceleague.adobe.com/en/docs/analytics/implementation/launch/overview).</p> | <ul><li>[(Recommended) New implementation of the Experience Platform Web SDK for ongoing data collection; the Analytics source connector for historical data](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[New implementation of the Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) </li><li>Migrate Adobe Analytics to the Web SDK</li><li>[Analytics source connector](/help/getting-started/cja-upgrade/cja-upgrade-alternative-source-connector.md)</li></ul> | 
| Experience Platform Web SDK (alloy.js) | The Experience Platform Web SDK is Adobe's current recommended method to implement Adobe Analytics. The Adobe Experience Platform Edge Network allows you to send data destined to multiple products to a centralized location. <p>For more information about this implementation type, see [Implement Adobe Analytics with the Adobe Experience Platform Edge Network](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/overview).</p> | <ul><li>[(Recommended) New implementation of the Experience Platform Web SDK for ongoing data collection; the Analytics source connector for historical data](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[New implementation of the Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) </li><li>Configure the Adobe Analytics Web SDK implementation to send data to Platform</li></ul> | 
| Experience Platform Web SDK extension (tags) | The Experience Platform Web SDK is Adobe's current recommended method to implement Adobe Analytics for web data. The Adobe Experience Platform Edge Network allows you to send data destined to multiple products to a centralized location. <p>For more information about this implementation type, see [Implement Adobe Analytics using the Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/overview)</p> | <ul><li>[(Recommended) New implementation of the Experience Platform Web SDK for ongoing data collection; the Analytics source connector for historical data](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[New implementation of the Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md)</li><li>Configure the Adobe Analytics Web SDK implementation to send data to Platform</li></ul> | 
| Experience Platform Mobile SDK | The Experience Platform Mobile SDK is Adobe's current recommended method to implement Adobe Analytics for mobile data. The Adobe Experience Platform Edge Network allows you to send data destined to multiple products to a centralized location.<p>The Adobe Experience Platform Mobile SDK helps power Adobe's Experience Cloud solutions and services in your mobile apps. </p><p>For more information about this implementation type, see [Implement Adobe Analytics using the Adobe Experience Platform Mobile SDK](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/mobile-sdk/overview)</p> | <ul><li>[(Recommended) New implementation of the Experience Platform Web SDK for ongoing data collection; the Analytics source connector for historical data](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[New implementation of the Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) </li><li>Configure the Adobe Analytics Web SDK implementation to send data to Platform</li></ul> | 
| Bulk Data Insertion API | The Bulk Data Insertion API (BDIA) is an Adobe Analytics capability that lets you upload server call data in batches of files instead of using client-side libraries such as AppMeasurement. </p><p>For more information about this implementation type, see [Bulk Data Insertion API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/).</p> | <ul><li>[(Recommended) New implementation of the Experience Platform Web SDK for ongoing data collection; the Analytics source connector for historical data](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[New implementation of the Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md)</li><li>[Adobe Experience Platform Edge Network Server API and Edge Network](/help/data-ingestion/serverapi.md)</li></ul> | 

{style="table-layout:auto"}
