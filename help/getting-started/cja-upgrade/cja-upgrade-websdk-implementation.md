---
title: Understand Web SDK implementation options when upgrading to Customer Journey Analytics
description: Learn about the Web SDK implementation options when upgrading to Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 94a2bf2f-ad84-4f35-af8f-b8a5d9e5c607
autotag-review: '2026-05-19T08:21:32.040Z'
TQID: 'https://experienceleague.adobe.com/5mjQHmjaBfxAusSR3EuDykYxJzgaR6P9jiL3HH09Bns'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
    internal-label: Administration
subfeature_v2:
  - id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
    internal-label: Upgrade
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
---
# Understand Web SDK implementation options when upgrading to Customer Journey Analytics {#web-sdk-implementation-options}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-js"
>title="Web SDK JavaScript library (alloy.js)"
>abstract="Include the Web SDK library (alloy.js) on each page your site."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-tags"
>title="Web SDK tag extension"
>abstract="(Recommended) If you are not yet using Tags, install the tag loader on your site. If you are already using Tags, you can add the Web SDK extension to your tag property. This option includes implementations using tags within Adobe Experience Platform Data Collection and third-party tag management systems."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-api"
>title="NPM package"
>abstract="Use the data collection API to send data directly to a datastream. Both non-authenticated (client-to-server) and authenticated (server-to-server) types are supported."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-no-selection"
>title="Implement the Web SDK for your given property"
>abstract="Select the desired implementation type in the upgrade guide for more detailed instructions."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-third-party"
>title="Add the Web SDK library to your third-party tag management system"
>abstract="Work with the admin over your tag management system to add the Web SDK library to your site.<br><br>Completion time for this task heavily depends on the responsiveness of the individual responsible for your tag management system. Adding the Web SDK library might be bundled with associated implementation logic, and deployed during your organization's standard release cycles."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

The recommended process of upgrading from Adobe Analytics to Customer Journey Analytics is a new implementation of the Experience Platform Web SDK, which is the preferred data collection method for Customer Journey Analytics.

There are three supported ways to use Adobe Experience Platform Web SDK:

* [Web SDK tag extension](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/extension): Adobe recommends using this method. Install a tag loader on your site, then use the Adobe Experience Platform Data Collection UI to configure your implementation.

* [Web SDK JavaScript library](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/library): Reference a CDN-hosted library file, or host the library file using your own infrastructure. Make calls to the library within code on your site.

* [NPM](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/npm): Install the Web SDK on your site using the NPM package manager.

For more information, see [Web SDK installation overview](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/overview) in the Experience Platform Web SDK Guide.
