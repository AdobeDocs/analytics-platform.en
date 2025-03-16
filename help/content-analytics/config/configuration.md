---
title: Configure Content Analytics
description: An overview of how to configure Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: yes
hidefromtoc: yes
exl-id: 3ea46223-c7d0-4b1f-bc84-4f35494f13a0
---
# Configure Content Analytics

>[!WARNING]
>
>This article is a preliminary unofficial draft version of a forthcoming final version and is part of the Content Analytics documentation. All content is subject to change and no legal obligations whatsoever can be derived from the current version of this article.  
>

{{release-limited-testing}}

The configuration of Content Analytics consists of the following steps:

![Configuration of Content Analytics](../assets/aca-configuration.svg)

1. Use the Content Analytics [guided configuration](guided.md) wizard to guide you through all steps required to setup the prerequisites for a configuration of Content Analytics. You can save your configurations and return later.
1. Once you are comfortable with the configuration values, you can implement the configuration. This implementation creates all required artefacts, based on what you have configured in the wizard. The following artefacts are created, updated or selected:
   * Custom Journey Analytics
     * A [data view](/help/data-views/data-views.md) is selected.
     * A [connection](/help/connections/overview.md) is selected, automatically derived from the selected data view.
   * Experience Platform
     * The sandbox is selected, automatically derived from the connection. The necessary workflows and services are enabled on the sandbox.
     * Content Analytics schemas are selected on the sandbox. If not available, the necessary schemas are created.
     * Content Analytics datasets selected on the sandbox. If not available, the necessary datasets are created.
   * Data Collection
     * A datastream is created and an Experience Platform service is configured within the datastream to stream data to the Content Analytics experience event dataset.
     * A Tag property is created with the Adobe Content Analytics extension configured for the correct sandbox, datastream and other configuration options from the configuration wizard.
1. Only when you [manually publish](manual.md) the Tag property, Content Analytics is effectively deployed and activated.

1. You can only make some limited changes to an implemented configuration using the [guided configuration](guided.md) wizard. For example, change the [data view](/help/data-views/data-views.md).
1. You can make other changes to an implemented configuration through the [Adobe Content Analytics extension](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview) in the associated Tag property.
1. Only when you [manually re-publish](manual.md) the Tag property, the configuration modifications from step 4 and 5 are effectively deployed and activated.


## Prerequisites

Before you configure Content Analytics, ensure you the following prerequisites are met:



* You have allow-listed the User Agent and IP address for the featurization service that is used in Content Analytics. The User Agent string is `AdobeFeaturization/1.0`.
* You have a Customer Journey Analytics Product Administrator role, with the additional permissions to manage connections and to manage data collections. The required Experience Platform permissions are:
  
   | Category | Permission | Description |
   |---|---|---|
   | [!UICONTROL Data Collection] | View Datastreams | Read-only access to datastreams. |
   | [!UICONTROL Data Collection] | Manage Datastreams | Acces to read, create, edit and delete datastreams. |
   | [!UICONTROL Data Modeling] | [!UICONTROL View Schemas] | Read-only access to schemas and related resources. |
   | [!UICONTROL Data Modeling] | [!UICONTROL Manage Schemas] | Access to read, create, edit, and delete schemas and related resources. |
   | [!UICONTROL Data Management] | [!UICONTROL View Datasets] | Read-only access for datasets and schemas. |
   | [!UICONTROL Data Management] | [!UICONTROL Manage Datasets] | Access to read, create, edit, and delete datasets. Read-only access for schemas. |
   | [!UICONTROL Data Ingestion] | [!UICONTROL Manage Sources] | Access to read, create, edit, and disable sources. |
   | [!UICONTROL Identity Management] | [!UICONTROL View Identity Namespaces] | Read-only access for identity namespaces. |

* You have carefully considered the following important configuration options:

   * You site is suited for experience reporting? Proper eperience reporting is only possible when the following conditions are met:
   * The site content is driven by URLs only.
   * The pages on your site are reproducible using the page URL, and you understand what optional URL parameters drive experiences.
* You have a clear understanding for which pages you want to capture content engagement analysis and insights.
* You have a clear understanding for which (type of) assets you want to capture content engagement analysis and insights.


## Access Control

>[!IMPORTANT]
>
>There is no Content Analytics permission you can configure to enable or disable Content Analytics access for individual users or groups of users.
>

To provide a user or group of users access to Content Analytics, you must provide the user or group of users access to one or more data views that are configured for Content Analytics.

This implies:

1. The Content Analytics enabled data view is included as part of the Data View permissions for a specific Customer Journey Analytics product profile.
1. That specific Customer Journey Analytics product profile is one of the product profiles assigned to the user or group of users.

>[!MORELIKETHIS]
>
>* [Guided configuration](guided.md)
>* [Manual configuration](manual.md)
>* [Access control](/help/technotes/access-control.md)
>


