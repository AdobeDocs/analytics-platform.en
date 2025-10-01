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

* **Experience**: An experience is defined as the text content on a whole web page. For data collection, Content Analytics records the Experience ID which is based on the page url. Later, the text on the page is captured via the retrieval service.
* **Experience ID**: A unique combination of relevant URL (base URL plus any parameters that drive content on the page) and [experience version](manual.md#versioning).
  * You specify, as part of the [configuration](configuration.md), which parameters are relevant for any given full URL. 
  * You define a [version identifier](manual.md#versioning) to use, so you properly collect changes to your experiences.
* **Asset**: An image. Content Analytics records the asset URL.
* **Asset ID**: The URL of the asset.
* **Relevant URL**: The base URL plus any parameters that drive content on the page.


## Functionality

Content Analytics requires the Experience Platform Edge Network Web SDK to collect content event data. That event data collection is combined with the (existing) data collection of behavioral event data through mechanisms like Experience Platform Edge Network (Web SDK, Server API) or Analytics source connector (for example, using AppMeasurement).

The Content Analytics library collects data when:

* Content Analytics is included in the Tags library that is loaded on the page.
* The page URL is configured in the [Content Analytics extension](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview){target="_blank"}, part of the included Tags library.


## Content Analytics event

A Content Analytics event consists of:

* Standard fields
  * Timestamp
  * Identity
* Experience views (if any, and if configured)
* Experience clicks (if any, and if configured)
* Asset views (if any, and if configured)
* Asset clicks (if any, and if configured)

Content Analytics events are collected as a sequence of:

1. [A recorded view or click](#recorded-view-or-click).
1. [A trigger to send a Content Analytics event](#trigger-to-send-a-content-analytics-event). 

Content Analytics does collect data this way to reflect that sequence, instead of collecting a view or click separately from collecting the event immediately following that view or click. This way of collecting Content Analytics data also reduces the amount of data collected.

### Recorded view or click 

An asset view is recorded when:

* The asset has not been excluded per Content Analytics extension configuration.
* The asset is 75% in view.
* That asset has not already been recorded for this page.

An asset click is recorded when:

* The asset has been viewed. 
* The asset has not been excluded per Content Analytics extension configuration.
* A click directly on the asset, which is a link, that leads to another page.

An experience view is recorded when:

* Experiences are enabled in the Content Analytics configuration.

An experience click is recorded when:

* Any click occurs on a link on the page for which experiences are enabled.


### Trigger to send a Content Analytics event

To reduce the number of calls leaving the page, Content Analytics collects information but does not send that information immediately. Content interaction information is collected and an event containing that information is only sent when one of the following triggers occurs:

* Web SDK or AppMeasurements sends an event.
* Visibility changes to hidden, for example:
  * Page unloads
  * Switch tab
  * Minimize browser
  * Close browser
  * Lock screen
* The URL changes, which results in a modified relevant URL.
* Asset views recorded and ready to be sent exceed the number of 32.

>[!NOTE]
>
>The additional Content Analytics events most likely affect any bounce rate definition that is based on the number of events in a session or a page. 
>


## Schemas

Content Analytics data is collected in datasets in Experience Platform, based on specific Content Analytics schemas. Reference schemas are publicly available:

* [Digital Asset schema](https://github.com/adobe/xdm/blob/master/components/classes/digital-asset.schema.json)
* [Digital Experience schema](https://github.com/adobe/xdm/blob/master/components/classes/digital-experience.schema.json)
* [Experience Event Content schema](https://github.com/adobe/xdm/blob/master/components/fieldgroups/experience-event/experienceevent-content.schema.json)
