---
title: Data collection in Content Analytics
description: An overview of how data is collected in Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
hide: yes
hidefromtoc: yes
role: Admin
---

# Data collection in Content Analytics

This article explains in detail how data is collected for Content Analytics.


## Definitions

The following definitions are used in the context of this article:

* **Experience**: An experience is defined as the text content on a whole web page. For data collection, Content Analytics records the Experience ID. Content Analytics does not record the text on the page.
* **Asset**: An image. Content Analytics records the asset URL.
* **Relevant URL**: The base URL plus any parameters that drive content on the page.
* **Experience ID**: A unique combination of relevant URL and experience version.  
  * You specify, as part of the [configuration](configuration.md), which parameters are relevant for any given full URL. 
  * You can define the [version identifier](manual.md#versioning) that is used. For data collection, the version is not considered. Only the relevant url is collected.

## Functionality

The Content Analytics library collects data when:

* Content Analytics is included in the Tags library that is loaded on the page.
* The page URL is configured in the [Content Analytics extension](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview){target="_blank"}, part of the included Tags library.


### Content Analytics event

A Content Analytics event consists of:

* Standard fields
  * Timestamp
  * Identity
* Experience views (if any, and if configured)
* Experience clicks (if any, and if configured)
* Asset views (if any, and if configured)
* Asset clicks (if any, and if configured)

#### Views or clicks recorded

An asset view is recorded when:

* The asset has not been excluded per ACA extension configuration.
* The asset is 75% in view.
* That asset has not already been recorded for this page.

An asset click is recorded when:

* The asset has been viewed. 
* The asset has not been excluded per ACA extension configuration.
* A click directly on the asset, which is a link, that leads to another page.

An experience view is recorded when:

* Experiences are enabled in the Content Analytics configuration.

An experience click is recorded when:

* Any click occurs on a link on the page for which experiences are enabled.


#### Events sent

Content Analytics events are sent when the following two conditions occur:

* Content is sent, which occurs when:

  * An asset view or click is recorded.
  * An experience view or click is recorded.

* Trigger to send an event is fired, which occurs when:

  * Web SDK or AppMeasurements sends an event.
  * Visibility changes to hidden, for example:
    * Page unloads
    * Switch tab
    * Minimize browser
    * Close browser
    * Lock screen
  * The URL changes, which results in a modified relevant URL.
  * An asset views exceeds the batch limit of 32.


## Schemas

Content Analytics data is collected in datasets in Experience Platform, based on specific Content Analytics schemas. Reference schemas are publicly available and are used in a default implementation of Content Analytics

* [Digital Asset](https://github.com/adobe/xdm/blob/master/components/classes/digital-asset.schema.json)
* [Digital Experience](https://github.com/adobe/xdm/blob/master/components/classes/digital-experience.schema.json)
* [Experience Event Content](https://github.com/adobe/xdm/blob/master/components/fieldgroups/experience-event/experienceevent-content.schema.json)

