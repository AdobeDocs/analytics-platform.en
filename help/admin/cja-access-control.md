---
title: Customer Journey Analytics Access Control
description: Learn about ways to implement access control in Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
mini-toc-levels: 3
role: Admin
---
# Customer Journey Analytics Access Control

Customer Journey Analytics is governed by three levels of access or three roles: Product Admin role, Product Profile Admin role, and user-level access. This topic explains these roles in more detail. 

In addition, we discuss more granular ways to limit access, such as Workspace curation and row-level as well as value-level access control.

## Product Admin role

Users who are assigned the Product Admin role are given the necessary permissions to perform most tasks within Customer Journey Analytics by default. However, some tasks require additional permissions.

To add a user as a Product Admin:

1. Go to the [Admin Console](https://adminconsole.adobe.com/enterprise/).

1. Select [!UICONTROL **Customer Journey Analytics**] > [!UICONTROL **Admins**] tab > [!UICONTROL **Add Admin**].

   The users that you added are given the [Product Admin default permissions](#product-admin-default-permissions). You can also grant them [additional permissions](#product-admin-additional-permissions) if needed.

### Product Admin default permissions

Product Admins have permissions to complete most tasks within Customer Journey Analytics. 

Product admins are granted the necessary permissions to perform the following tasks by default:

* Create, update, and delete data views
* Update and delete projects, filters, calculated metrics, audiences, annotations, or filters created by other users
* Share Workspace projects to all users
* Manage reporting activity in the [Reporting Activity Manager](/help/reporting-activity-manager/reporting-activity-overview.md)
* [Export full tables](/help/analysis-workspace/export/export-cloud.md) from Analysis Workspace

### Product Admin additional permissions

In addition to being added as a Product Admin in the **Customer Journey Analytics Product Profile** in the [Admin Console](https://adminconsole.adobe.com/enterprise/), additional permission are required in order to complete the following tasks within Customer Journey Analytics:

* Create, update, and delete data [Connections](/help/connections/overview.md)
  
  In order to perform this task, users must be part of an **Experience Platform Product Profile** that provides the following permissions:
  * Data Modeling: View Schemas, Manage Schemas
  * Data Management: View Datasets, Manage Datasets
  * Data Ingestion: Manage Sources
  * View Identity Namespaces  
    
    For more information on Experience Platform permissions, see [Access control in Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html).

* Export datasets to cloud [Destinations](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en)

  >[!AVAILABILITY]
  >
  >The ability to export datasets to the cloud is in the Limited Testing phase of release and might not be available yet in your environment. This note will be removed when the functionality is generally available. For information about the Customer Journey Analytics release process, see [Customer Journey Analytics feature releases](/help/release-notes/releases.md).
  
  In order to perform this task, users also need the following Experience Platform permissions:
  * Manage Destinations
  * Activate Destinations
    
    For more information on Experience Platform Destinations permissions, see [Destinations overview](https://experienceleague.adobe.com/docs/experience-platform/destinations/home.html?lang=en#access-controls).

## Product Profile Admin role

A product profile is a set of permissions. Product Profile Admins can

* Create and manage individual product profiles, such as adding new users or managing user groups and their associated product profiles.

* In Customer Journey Analytics, edit data views that are part of a product profile that they manage. They cannot create new data views.

## User-level access

The matrix below outlines the main access permissions for different Customer Journey Analytics capabilities for non-product admins and CJA product admins. Understanding these permissions helps users effectively navigate and utilize CJA based on their role and responsibilities within the organization.

| CJA Product Functionality | Non-Product Admins (Users) | Product Admins |
| --- | --- | --- |
| **Data views** | Cannot view/update/create/delete | Can create/update/delete |
| **Connections**| Cannot view/update/create/delete | Can create/update/delete |
| **Filters** | Can create | Can create |
| **Projects** | Can create | Can create/update/delete |
| **Audiences** | Can create with special permissions in Admin Console | Can create |
| **Calculated metrics** | Can create with special permissions in Admin Console | Can create |

{style="table-layout:auto"}

## Workspace project curation

Another level of access control can be used at the Workspace reporting level. You can limit access to specific components for certain users. For more information on how to limit components (dimensions, metrics, filters, date ranges) at the Workspace project level, and how curation is tied to data views, see [Curate projects](/help/analysis-workspace/curate-share/curate.md).

## Grant access to individual metrics or dimensions

You cannot grant or deny permissions for individual metrics or dimensions in Customer Journey Analytics like you can in traditional Adobe Analytics. Metrics and dimensions can be modified in [data views](/help/data-views/data-views.md) and are thus subject to change in Customer Journey Analytics. Changing them also retroactively changes reporting.

## Use cases

Here are a few use cases that illustrate how access control can be used in real-life scenarios.

### Third-party access

A third party that your company works with has a team lead that can be made Product Profile admin. This admin then can add users on his team to this product profile. This admin can give access to specific data views and add other users to this product profile. They can also modify those data views over which they have control to fit their team's needs.

### Row-level access control

Let's say you wanted to give users access to data from one day only. Here is how you would limit access to those specific rows:

1. Create a filter in Customer Journey Analytics where **[!UICONTROL Day]** equals the date you want them to have data access to.
1. In [!UICONTROL Data views] > [!UICONTROL Settings], add that filter to the data view.
1. Save the data view and it auto-applies the filter to the dataset. Any rows that don't fit the filter definition are now automatically excluded from the edited data view.
1. Create a new Product profile in Admin Console, add users to it and limit their access to this data view.

### Value-level access control

Users who have access to a data view can only work with the metrics and dimensions that the Admin has included in this data view. Admins can use the [Include/Exclude functionality](/help/data-views/component-settings/include-exclude-values.md) in data views to, for example, exclude certain dimension values from a data view.

Here is a healthcare-related example: Let's say you create a metric called "Hypertension" in a data view, from a dataset that includes this data. The fact that it's a metric would allow you to see the aggregate value of this metric, but not the individual patients who fall under it.

## Customer Journey Analytics permissions in Admin Console

The **[!UICONTROL Permissions]** tab is part of each product profile in [Admin Console](https://adminconsole.adobe.com/enterprise/). You can add users to specific product profiles. Then you assign rights to specific data views and specify which permissions the users in a product profile have. Here are the Customer Journey Analytics-specific permissions:

![admin console permissions](assets/permissions.png)

| Permission | Definition |
| --- | --- |
| **[!UICONTROL Data Views]** | If you toggle **[!UICONTROL Auto-Include]** to **[!UICONTROL On]**, users that are part of this product profile can view all existing and newly created data views. If this setting is set to **[!UICONTROL Off]**, you can select specific data views that users have access to.  |
| **[!UICONTROL Reporting Tools]**: |   |
| **[!UICONTROL Audit Logs Access]** |  This permission enforces the permission check on the [API](https://adobe.io/cja-apis/docs/endpoints/auditlogs/) and the audit logs UI.  |
| **[!UICONTROL Analysis Workspace Access]** |  Lets users access Analysis Workspace in Customer Journey Analytics.  |
| [!UICONTROL **Guided Analysis Access**] | Lets users create [Guided Analysis projects](/help/guided-analysis/overview.md).  |
| [!UICONTROL **Forecasting**] | Lets users access Forecasting feature in Analysis Workspace  |
| **[!UICONTROL Reporting Usage Admin]** | Lets users view and delete any report running in their company. |
| **[!UICONTROL Reporting Usage View]** | Lets users see all of the concurrent reporting requests. |
| [!UICONTROL **Full Table Export**] | Lets users [export full tables to the cloud](/help/analysis-workspace/export/export-cloud.md).  |
| **[!UICONTROL Calculated Metrics Creation]** | Lets users create [calculated metrics](/help/components/calc-metrics/calc-metr-overview.md). |
| **[!UICONTROL Filter Creation]** | Lets users create [filters](/help/components/filters/filters-overview.md). |
| **[!UICONTROL Labs Access]** | Lets users access the [Labs](/help/labs/labs.md) tab in Customer Journey Analytics. |
| **[!UICONTROL Annotation Creation]** | Lets users create [annotations](/help/components/annotations/overview.md). |
| **[!UICONTROL Audience Creation]** | Lets users create [audiences](/help/components/audiences/audiences-overview.md). |
| **[!UICONTROL Audience View]** | Lets users view [audiences](/help/components/audiences/audiences-overview.md). |
| [!UICONTROL **Share Project Links With Anyone**] | Lets users [share projects with anyone.](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/share-projects.html?lang=en#share-public-link)  |
| **[!UICONTROL Data View Tools]**: |   |
| [!UICONTROL **Full Table Export**] | Lets users [export full tables to the cloud](/help/analysis-workspace/export/export-cloud.md).  |
| [!UICONTROL **SQL Query Service Access**] | Lets users access [Query Service in AEP](https://experienceleague.adobe.com/docs/experience-platform/query/home.html). |

{style="table-layout:auto"}
