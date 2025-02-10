---
title: Content Analytics overview
description: An overview of Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin, User
hide: yes
hidefromtoc: yes
exl-id: 0d3be50d-c635-459b-8b01-61d6d4ef0cdf
---
# Content Analytics overview

<!-- 
This is a placeholder article for upcoming Content Analytics documentation. Currently used to set up contextual help entries for developer working on onboarding UI and workspace UI 
-->

>[!WARNING]
>
>This article is a preliminary unofficial draft version of a forthcoming final version and is part of the Content Analytics documentation. All content is subject to change and no legal obligations whatsoever can be derived from the current version of this article.  
>

{#release-limited-testing}

Content Analytics helps marketers to understand how content impacts the key performance indicators that a business has defined. On top of the traditional micro-level based functionalities to test pieces of content (for example, A/B tests), Content Analytics provides insights how content is driving impact at a macro level. For example, do customers respond better to a specific tone of voice, a specific color pallet, or specific themes?

Content Analytics uses an AI and machine learning based **featurization service** to break content down into components and attributes. By creating a structured metadata profile on all your content, you can analyze what content and what attributes of that content drives business results. 

In addition to the creation of this structured metadata profile, Content Analytics provides an **identity service** that identifies assets and experiences using a single identifier. The identity service understands whether an asset, for example, has been resized, cropped, or saved to a different file format. The service assigns all variations of that asset to the same single identifier. As a result, the identity service allows you to aggregate the performance of an asset based on its various forms and placements.

## Value

Content Analytics does provide value at an increasing level:

1. Content **usage**: With Content Analytics you get insights on which assets are receiving impressions and where assets are receiving impressions. These insights help you to see whether assets are underused or overused on your web properties.
1. Content **engagements**: Content Analytics can provide engagement insights like the average click through rate for assets with certain attributes. These insights help you to determine whether specific types of experiences are still effective.
1. Content **journeys**: Furthermore, when combined with all other data available in Experience Platform, you can gain additional insights on your content journeys. For example, whether specific content leads to conversions, on top of engagement. And with that knowledge you can determine the ROI on types of content.
1. Content **personalization**: Ultimately Content Analytics allows you to act upon your insights and use these insights to determine how to spend money on content. For example, should I send specific types of content to specific audiences? What content provides me with high-personalization opportunities?

## Terminology

Content Analytics uses the following key terms:

![Assets and experiences](/help/content-analytics/assets//content-analytics-experience-asset.png)

* **Experience**: An experience is all text on a web page that is reproducible using the URL used by the initial user visiting that web page. Each experience gets a unique identifier.
* **Asset**: An asset is an individual and unique piece of content, like an image. Each asset also gets a unique identifier.
* **Attribute**: An attribute is a descriptive metadata element associated with an experience or asset. Examples of an attribute are: style of photography, readability, persuasion strategy, object color, background color.

## How it works

Content Analytics uses web image view data collected in event datasets in Experience Platform. This data might be collected through the various methods available: Experience Platform Edge Network (Web SDK, Server API), or Analytics source connector.

![Content Analytics - How it works](assets/how-it-works.png)


1. The detection part of the featurization service is triggered upon any new snapshot of data arriving at a Content Analytics enabled event dataset. 
1. The featurization detection service determines which data in that snapshot is relevant for content analytics and revisits the experience and assets of these web image views. 
1. Upon the revisit, specific content analytics data is collected through a proper configuration of the Experience Platform Web SDK and Experience Platform Edge Network. And then the data is sent to a dedicated content analytics dataset and relevant lookup datasets. 
1. The featurization assembler service and identity service process the revisited data. 
1. The results of these services (components, attributes, and identities) are used to update the relevant specific content analytics datasets in Experience Platform.
1. The content analytics data, together with behavioral data and other lookup datasets, can then be used in a Customer Journey Analytics configuration (Connection, Data view and Workspace). That configuration provides the foundation to the unique macro-level insights on your content.

>[!MORELIKETHIS]
>
>[ Content Analytics reporting](report/report.md)
>[Configure Content Analytics](config/configuration.md)
