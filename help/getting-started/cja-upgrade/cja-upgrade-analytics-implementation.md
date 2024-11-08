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
# Understand your Adobe Analytics implementation and how it affects your upgrade to Customer Journey Analytics

>[!NOTE]
> 
>Follow the steps on this page only after you complete all previous upgrade steps. You can follow the [recommended upgrade steps](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations), or you can follow the upgrade steps that were dynamically generated for your organization with the [Adobe Analytics to Customer Journey Analytics upgrade questionnaire](https://gigazelle.github.io/cja-ttv/). 
>
>After you complete the steps on this page, continue following the recommended upgrade steps or the dynamically generated upgrade steps. 

There are various ways to upgrade to Customer Journey Analytics, but not all upgrade paths are available for each type of Adobe Analytics implementation. However, the recommended upgrade path is available regardless of how Adobe Analytics is implemented in your organization.

Use the information below to help you understand your current Adobe Analytics implementation and which upgrade paths are available to your organization. 

Contact your Adobe representative if you need more specific advice, guidance, or support.

|Existing Adobe Analytics implementation | Description | Available upgrade paths |
|---------|----------|----------|
| AppMeasurement | AppMeasurement for JavaScript has historically been a common method to implement Adobe Analytics.<p>For more information about this implementation type, see [Implement Adobe Analytics with AppMeasurement for JavaScript](https://experienceleague.adobe.com/en/docs/analytics/implementation/js/overview)</p> |<ul><li>(Recommended) New implementation of the Experience Platform Web SDK with the Analytics Source Connector</li><li>New implementation of the Experience Platform Web SDK</li><li>Migrate Adobe Analytics to the Web SDK</li><li>Analytics Source Connector</li></ul>  | 
| Adobe Analytics extension (tags) | <p>Tags in Adobe Experience Platform is a tag management solution that lets you deploy Analytics code alongside other tagging requirements. Adobe offers integrations with other solutions and products, and lets you deploy custom code. All of these tasks can be done without relying on any development teams in your organization to update code on your site.</p><p>For more information about this implementation type, see [Implement Adobe Analytics using the Analytics extension](https://experienceleague.adobe.com/en/docs/analytics/implementation/launch/overview)</p> | <ul><li>(Recommended) New implementation of the Experience Platform Web SDK with the Analytics Source Connector</li><li>New implementation of the Experience Platform Web SDK</li><li>Migrate Adobe Analytics to the Web SDK</li><li>Analytics Source Connector</li></ul> | 
| Experience Platform Web SDK (alloy.js) | The Experience Platform Web SDK is Adobe's current recommended method to implement Adobe Analytics. The Adobe Experience Platform Edge Network allows you to send data destined to multiple products to a centralized location. <p>For more information about this implementation type, see [Implement Adobe Analytics with the Adobe Experience Platform Edge Network](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/overview)</p> | <ul><li>(Recommended) New implementation of the Experience Platform Web SDK with the Analytics Source Connector</li><li>Configure the Adobe Analytics Web SDK implementation to send data to Platform</li></ul> | 
| Experience Platform Web SDK extension (tags) | The Experience Platform Web SDK is Adobe's current recommended method to implement Adobe Analytics for web data. The Adobe Experience Platform Edge Network allows you to send data destined to multiple products to a centralized location. <p>For more information about this implementation type, see [https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/overview](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/overview)</p> | <ul><li>(Recommended) New implementation of the Experience Platform Web SDK with the Analytics Source Connector</li><li>Configure the Adobe Analytics Web SDK implementation to send data to Platform</li></ul> | 
| Experience Platform Mobile SDK | The Experience Platform Mobile SDK is Adobe's current recommended method to implement Adobe Analytics for mobile data. The Adobe Experience Platform Edge Network allows you to send data destined to multiple products to a centralized location.<p>The Adobe Experience Platform Mobile SDK helps power Adobe's Experience Cloud solutions and services in your mobile apps. </p><p>For more information about this implementation type, see [Implement Adobe Analytics using the Adobe Experience Platform Mobile SDK](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/mobile-sdk/overview)</p> | <ul><li>(Recommended) New implementation of the Experience Platform Web SDK with the Analytics Source Connector</li><li>Configure the Adobe Analytics Web SDK implementation to send data to Platform</li></ul> | 

{style="table-layout:auto"}
