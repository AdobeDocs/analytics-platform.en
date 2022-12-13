---
title: CJA Access Control
description: Learn about ways to implement access control in CJA.
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
mini-toc-levels: 3
---
# CJA Access Control

Customer Journey Analytics (CJA) is governed by three levels of access or three roles: Product Admin role, Product Profile Admin role, and user-level access. This topic explains these roles in more detail. 

In addition, we discuss more granular ways to limit access, such as Workspace curation and row-level as well as value-level access control.

## Product Admin role

Product Admins have permissions to complete any task necessary within CJA. You must be added as an Product Admin to the **Customer Journey Analytics Product Profile** in the [Admin Console](https://adminconsole.adobe.com/enterprise/) under [!UICONTROL Customer Journey Analytics] > [!UICONTROL Admins] tab > [!UICONTROL Add Admin]. Product admins are granted the following permissions:

* Create/update/delete connections or data views
* Update/delete projects, filters, calculated metrics, audiences, annotations, or filters created by other users
* Share Workspace projects to all users

Becoming a product admin in Customer Journey Analytics alone is not enough to create, update, or delete a [connection](/help/connections/overview.md). To create a connection to an Experience Platform dataset, you also need Experience Platform permissions. Specifically, you must be part of an **Experience Platform Product Profile** that gives you the following permissions:

* Data Modeling: View Schemas, Manage Schemas
* Data Management: View Datasets, Manage Datasets
* Data Ingestion: Manage Sources
* View Identity Namespaces  

For more information on Experience Platform permissions, see [Access control in Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html).

## Product Profile Admin role

A product profile is a set of permissions. Product Profile Admins can

* Create and manage individual product profiles, such as adding new users or managing user groups and their associated product profiles.

* In CJA, edit data views that are part of a product profile that they manage. They cannot create new data views.

## User-level access

Users in Customer Journey Analytics cannot create, edit, or view data views or connections. Users can create filters, projects, audiences, and calculated metrics with special permissions in the Admin Console.

## Workspace project curation

Another level of access control can be used at the Workspace reporting level. You can limit access to specific components for certain users. For more information on how to limit components (dimensions, metrics, segments, date ranges) at the Workspace project level, and how curation is tied to data views, see [Curate projects](/help/analysis-workspace/curate-share/curate.md).

## Grant access to individual metrics or dimensions

You cannot grant or deny permissions for individual metrics or dimensions in Customer Journey Analytics like you can in traditional Adobe Analytics. Metrics and dimensions can be modified in [data views](/help/data-views/data-views.md) and are thus subject to change in CJA. Changing them also retroactively changes reporting.

## Use cases

Here are a few use cases that illustrate how access control can be used in real-life scenarios.

### Third-party access

A third party that your company works with has a team lead that can be made Product Profile admin. This admin then can add users on his team to this product profile. This admin can give access to specific data views and add other users to this product profile. They can also modify those data views over which they have control to fit their team's needs.

### Row-level access control

Let's say you wanted to give users access to data from one day only. Here is how you would limit access to those specific rows:

1. Create a filter in CJA where **[!UICONTROL Day]** equals the date you want them to have data access to.
1. In [!UICONTROL Data views] > [!UICONTROL Settings], add that filter to the data view.
1. Save the data view and it auto-applies the filter to the dataset. Any rows that don't fit the filter definition are now automatically excluded from the edited data view.
1. Create a new Product profile in Admin Console, add users to it and limit their access to this data view.

### Value-level access control

Users who have access to a data view can only work with the metrics and dimensions that the Admin has included in this data view. Admins can use the [Include/Exclude functionality](/help/data-views/component-settings/include-exclude-values.md) in data views to, for example, exclude certain dimension values from a data view.

Here is a healthcare-related example: Let's say you create a metric called "Hypertension" in a data view, from a dataset that includes this data. The fact that it's a metric would allow you to see the aggregate value of this metric, but not the individual patients who fall under it.

## CJA permissions in Admin Console

The **[!UICONTROL Permissions]** tab is part of each product profile in [Admin Console](https://adminconsole.adobe.com/enterprise/). You can add users to specific product profiles. Then you assign rights to specific data views and specify which permissions the users in a product profile have. Here are the CJA-specific permissions:

![admin console permissions](assets/permissions.png)

| Permission | Definition |
| --- | --- |
| **[!UICONTROL Data Views]** | If you toggle **[!UICONTROL Auto-Include]** to **[!UICONTROL On]**, users that are part of this product profile can view all existing and newly created data views. If this setting is set to **[!UICONTROL Off]**, you can select specific data views that users have access to.  |
| **[!UICONTROL Reporting Tools]**: |   |
| **[!UICONTROL Audit Logs Access]** |  This permission enforces the permission check on the [API](https://adobe.io/cja-apis/docs/endpoints/auditlogs/) and the audit logs UI.  |
| **[!UICONTROL Reporting Usage Admin]** | Lets users view and delete any report running in their company. |
| **[!UICONTROL Reporting Usage View]** | Lets users see all of the concurrent reporting requests. |
| **[!UICONTROL Calculated Metrics Creation]** | Lets users create [calculated metrics](/help/components/calc-metrics/calc-metr-overview.md). |
| **[!UICONTROL Filter Creation]** | Lets users create [filters](/help/components/filters/filters-overview.md). |
| **[!UICONTROL Labs Access]** | Lets users access the [Labs](/help/labs/labs.md) tab in CJA. |
| **[!UICONTROL Annotation Creation]** | Lets users create [annotations](/help/components/annotations/overview.md). |
| **[!UICONTROL Audience Creation]** | Lets users create [audiences](/help/components/audiences/audiences-overview.md). |
| **[!UICONTROL Audience View]** | Lets users view [audiences](/help/components/audiences/audiences-overview.md). |

{style="table-layout:auto"}
