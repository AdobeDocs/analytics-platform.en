---
title: Content Analytics overview
description: An overview of Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin, User
exl-id: 0d3be50d-c635-459b-8b01-61d6d4ef0cdf
---
# Content Analytics overview

{{release-limited-testing}}

Content Analytics helps marketers to understand how content impacts the key performance indicators that a business has defined. On top of the behavioral data, Content Analytics collects data on how content is consumed and how content drives impact. For example, do customers respond better to a specific tone of voice, a specific color palette, or specific themes? This information, together with specifically designed reporting workflows and templates, can help you to perform even better analysis and gain deeper insights on customer journey data in Customer Journey Analytics. 

Content Analytics uses an AI and machine learning based **featurization service** to break content down into components and attributes. By creating a structured metadata profile on all your content, you can analyze what content and what attributes of that content drives business results. 

In addition to the creation of this structured metadata profile, Content Analytics provides an **identity service** that identifies assets and experiences using a single identifier. The identity service can recognize when the exact same asset appears in more than one place. When that happens, the instances of this asset are treated as the same asset, allowing for a more holistic view of content usage and consumption.

## Value

Content Analytics does provide value at an increasing level:

1. Content **usage**: With Content Analytics you get insights on which assets are receiving impressions and where assets are receiving impressions. These insights help you to see whether assets are underused or overused on your web properties.
1. Content **engagements**: Content Analytics can provide engagement insights like the average click through rate for assets with certain attributes. These insights help you to determine whether specific types of experiences are still effective.
1. Content **journeys**: Furthermore, when combined with all other data available in Experience Platform, you can gain additional insights on your content journeys. For example, whether specific content leads to conversions, on top of engagement. And with that knowledge you can determine the ROI on types of content.
1. Content **personalization**: Ultimately Content Analytics allows you to act upon your insights and use these insights to determine how to spend money on content. For example, should I send specific types of content to specific audiences? What content provides me with high-personalization opportunities?

## Terminology

Content Analytics uses the following key terms:

![Assets and experiences](/help/content-analytics/assets/content-analytics-experience-asset.png)

* **Experience**: An experience is all text on a web page that is reproducible using the URL that is used by the initial user who visited the web page. Each experience gets a unique identifier. Changes to the page resulting in changes to the HTML of the page results in a new experience.
* **Asset**: An asset is an individual and unique piece of content, like an image. Each asset also gets a unique identifier and a perceptual ID. A perceptual ID is an identifier that is shared with assets that are visually identical. Perceptual IDs help to deduplicate assets that may have a different asset URL and therefor a different asset ID, but are perceptually identical.
* **Attribute**: An attribute is a descriptive metadata element associated with an experience or asset. Examples of an attribute are: style of photography, readability, persuasion strategy, object color, background color.

## How it works

Content Analytics uses web image view data collected in event datasets in Experience Platform. These content experience events requires the data to be collected with the Experience Platform Edge Network (Web SDK, Server API). Behavioral data can be collected with Web SDK or the Analytics Source Connector.

![Content Analytics - How it works](assets/aca-overview.gif)


1. When a user visits a site, [configured for Content Analytics](config/configuration.md), the Experience Platform Web SDK records impressions and interactions with content.
1. The identity and featurization service process these interactions. That process consists of a retrieval service that revisits the public-facing versions of the configured URLs that define the interactions. For all of these retrieved URLs, the identity service uniquely identifies the experiences and assets. And the featurization service applies AI/ML services to discover experiences and assets metadata and attributes.
1. The results of these services ([components, attributes, and identities](/help/content-analytics/report/components.md)) are used to update the relevant specific content analytics datasets in Experience Platform.
1. The content analytics data, together with behavioral data and other lookup data, you can use in a Customer Journey Analytics setup ([Connection](/help/connections/overview.md), [Data view](/help/data-views/data-views.md) and [Workspace](/help/analysis-workspace/home.md)). That setup provides the foundation to the unique macro-level insights on your content. <br/>You can jump start your Content Analytics reports and analysis using the [Content Analytics template](/help/content-analytics/report/report.md#template).

>[!NOTE]
>
>Content Analytics leverages AI/ML services which may produce inaccurate or misleading results. As a result, please use your judgment to review and validate AI/ML generated outputs.
>
>You can use the **[!UICONTROL Feedback]** tab, available from ![InfoOutline](/help/assets/icons/InfoOutline.svg) on the main interface, to provide feedback on the AI/ML generated outputs.
>

>[!NOTE]
>
>If you have licensed the Privacy and Security Shield add-on, be aware that (any data generated from) experiences and assets, subject to Content Analytics, are not covered by DULE labeling or Customer Managed Keys.
>


>[!MORELIKETHIS]
>
>[Content Analytics reporting](report/report.md)
>[Configure Content Analytics](config/configuration.md)
>

