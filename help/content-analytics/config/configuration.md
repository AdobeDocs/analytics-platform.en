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


To configure Content Analytics for your organization, you use the Content Analytics [guided configuration](guided.md). The configuration wizard guides you through all steps required to setup the prerequisites for an automatic configuration of Content Analytics.

After a successful implementation you can make some changes using the guided configuration wizard. However, [manual changes](manual.md) might be required on top of that.

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

    
>
>[!MORELIKETHIS]
>
>* [Guided configuration](guided.md)
>* [Manual configuration](manual.md)
>* [Access control](/help/technotes/access-control.md)
>


