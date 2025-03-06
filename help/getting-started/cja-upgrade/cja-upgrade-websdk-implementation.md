---
title: Understand Web SDK implementation options when upgrading to Customer Journey Analytics
description: Learn about the Web SDK implementation options when upgrading to Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: yes
hidefromtoc: yes
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
>abstract="Select the desired implementation type in the questionnaire for more detailed instructions."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

The recommended process of upgrading from Adobe Analytics to Customer Journey Analytics is a new implementation of the Experience Platform Web SDK, which is the preferred data collection method for Customer Journey Analytics.

There are three supported ways to use Adobe Experience Platform Web SDK:

* [Web SDK tag extension](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/extension): Adobe recommends using this method. Install a tag loader on your site, then use the Adobe Experience Platform Data Collection UI to configure your implementation.

* [Web SDK JavaScript library](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/library): Reference a CDN-hosted library file, or host the library file using your own infrastructure. Make calls to the library within code on your site.

* [NPM](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/npm): Install the Web SDK on your site using the NPM package manager.

For more information, see [Web SDK installation overview](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/overview) in the Experience Platform Web SDK Guide.



