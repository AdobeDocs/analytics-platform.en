---
title: Content Analytics data collection
description: An overview of how data is collected in Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 584587e6-45fd-4fc3-a7a6-6685481ddee7
---

# Content Analytics data collection

This article explains in detail how Content Analytics collects data

## Definitions

The following definitions are used in the context of this article:

* **Experience**: 
  * For the **web** channel, an experience is defined as the text content on a whole web page. For data collection, Content Analytics records the Experience ID which is based on the page URL. Later, the text on the page is captured via the retrieval service.
  * For the **mobile** channel, an experience is defined and tracked in the mobile app using the Content Analytics extension for the Adobe Experience Platform Mobile SDK. 
* **Experience ID**: 
  * For the web channel, the experience ID is a unique combination of relevant URL (base URL plus any parameters that drive content on the page) and [experience version](manual.md#versioning).
    * You specify, as part of the [configuration](configuration.md), which parameters are relevant for any given full URL. 
    * You define a [version identifier](manual.md#versioning) to use, so you properly collect changes to your experiences.
  * For the **mobile** channel, the experience ID is the return value of using the `registerExperience` API call. 
* **Asset**: An image. Content Analytics records the asset URL.
* **Asset ID**: The URL of the asset.
* **Relevant URL**: The base URL plus any parameters that drive content on the page.


## Functionality

Content Analytics requires the Experience Platform Edge Network Web SDK (for the web channel) and the Experience Platform Edge Network Mobile SDK (for the mobile channel) to collect content event data. This event data is combined with existing behavioral data using the Experience Platform Edge Network (Web SDK, Mobile SDK, or Server API) or an Analytics source connector, such as Adobe AppMeasurement.

The Content Analytics library collects data when:

* Content Analytics is included in the Tags library that is loaded on the page or used within the mobile app.
* The page URL and asset URL are configured in the [Content Analytics web extension](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview){target="_blank"}, part of the included Tags library.
* The asset URL, asset location or experience location are not excluded in the [Content Analytics mobile extension](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/).


## Content Analytics event

This section details the specifics for web Content Analytics events. See [Experience tracking](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/experience-tracking/) for details on mobile Content Analytics events. 
A Content Analytics event consists of:

* Standard fields
  * Timestamp
  * Identity
* Experience views (if any, and if configured)
* Experience clicks (if any, and if configured)
* Asset views (if any, and if configured)
* Asset clicks (if any, and if configured)

Content Analytics events are collected as a sequence of:

1. A [recorded view or click](#recorded-view-or-click).
1. A [trigger to send a Content Analytics event](#trigger-to-send-a-content-analytics-event). 

Content Analytics does collect data this way to reflect that sequence, instead of collecting a view or click separately from collecting the event immediately following that view or click. This way of collecting Content Analytics data also reduces the amount of data collected.

### Recorded view or click 

An asset view is recorded when:

* The asset has not been excluded per Content Analytics extension configuration.
* The asset is 75% in view.
* That asset has not already been recorded for this page.

An asset click is recorded when:

* The asset has been viewed. 
* The asset has not been excluded per Content Analytics extension configuration.
* A click directly on the asset, which is a link, leads to another page.

An experience view is recorded when:

* Experiences are enabled in the Content Analytics configuration.

An experience click is recorded when:

* Any click on an enabled link triggers an experience.


### Trigger to send a Content Analytics event

To reduce the number of network requests sent from the page, Content Analytics collects information but does not send that information immediately. Content interaction information is collected and an event containing that information is only sent when one of the following triggers occurs:

* Web SDK or Adobe AppMeasurement send an event.
* Visibility changes to hidden, for example:
  * Page unloads
  * Switch tab
  * Minimize browser
  * Close browser
  * Lock screen
* The URL changes, which results in a modified relevant URL.
* Asset views recorded and ready to be sent exceed 32.

>[!NOTE]
>
>The additional Content Analytics events most likely affect any bounce rate definition that is based on the number of events in a session or a page. 
>

## Identities

This sections explains how Content Analytics handles identities.

### Web

Content Analytics handles identities for the web channel in the following way:

* ECID is automatically populated in the `identityMap` portion of the Content Analytics schema.
* If you require other identity values in the `identityMap`, you need to set these values in the `onBeforeEventSend` callback within the Web SDK extension.
* Field-based stitching is not supported because the schema is system-owned. So, you cannot add another field to the schema to support field-based stitching


To ensure Content Analytics identity data and Web SDK data identity data are stitched correctly at the field level, modify the Web SDK [on before event send](https://experienceleague.adobe.com/en/docs/experience-platform/collection/js/commands/configure/onbeforeeventsend){target="_blank"} callback.

1. Navigate to your **[!UICONTROL Tags]** property that contains the Adobe Experience Platform Web SDK extension and Adobe Content Analytics extension.
1. Select ![Plug](/help/assets/icons/Plug.svg) **[!UICONTROL Extensions]**.
1. Select the **[!UICONTROL Adobe Experience Platform Web SDK]** extension.
1. Select **[!UICONTROL Configure]**.
1. In the **[!UICONTROL SDK instances]** section, scroll down to **[!UICONTROL Data collection]** - **[!UICONTROL On before event send callback]**.

   ![On before event send callback](/help/content-analytics/assets/onbeforeeventsendcallback.png)

1. Select **[!UICONTROL </> Provide on before event send callback code]**.
1. Add the following code:

   ```JavaScript
   window.adobeContentAnalytics?.forwardEvent(content);

   content.xdm.identityMap = _satellite.getVar('identityMap');
   if ((content.xdm.eventType === "content.contentEngagement") && (_satellite.getVar('identityMap') != null)) {
      return true;
   }
   ```

   ![On before event send callback](/help/content-analytics/assets/onbeforeeventsendcallbackcode.png)

1. Select **[!UICONTROL Save]** to save the code.
1. Select **[!UICONTROL Save]** to save the extension.
1. [Publish](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview) the updates for your Tags property.
   

### Mobile

See the [Identity for Experience Cloud ID Service extension](https://developer.adobe.com/client-sdks/home/base/mobile-core/identity/) and the [Identity for Edge Network mobile extension](https://developer.adobe.com/client-sdks/edge/identity-for-edge-network/) for more information on how to work with identities in your mobile app.

As soon as the identity changes in the mobile app, the current [batch](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/#batching-settings) of Content Analytics data is reset to start a fresh collection of Content Analytics data for the new identity.

## Schemas

Experience Platform collects Content Analytics data in datasets based on specific Content Analytics schemas. Reference schemas are publicly available:

* [Digital Asset schema](https://github.com/adobe/xdm/blob/master/components/classes/digital-asset.schema.json)
* [Digital Experience schema](https://github.com/adobe/xdm/blob/master/components/classes/digital-experience.schema.json)
* [Experience Event Content schema](https://github.com/adobe/xdm/blob/master/components/fieldgroups/experience-event/experienceevent-content.schema.json)
