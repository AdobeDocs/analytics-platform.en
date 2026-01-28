---
title: Customer Journey Analytics Access Control
description: Learn about ways to implement access control in Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
mini-toc-levels: 3
role: Admin
---
# Access Control

Three levels of access or three roles govern Customer Journey Analytics: Product administrator role, Product profile administrator role, and user-level access. This topic explains these roles in more detail. 

In addition, this article discusses more granular ways to limit access, such as Workspace curation and row-level as well as value-level access control.

## Role-based access control

The following role-based access control levels are available.

### Product administrator role

Users who are assigned the Product administrator role are given the necessary permissions to perform most tasks within Customer Journey Analytics by default. However, some tasks require additional permissions.

To add a user as a Product administrator:

1. Go to the [Admin Console](https://adminconsole.adobe.com/enterprise/).

1. Select [!UICONTROL **Customer Journey Analytics**] > [!UICONTROL **Admins**] tab > [!UICONTROL **Add Admin**].

   The users that you added are given the [Product administrator default permissions](#product-admin-default-permissions). You can also grant them [additional permissions](#product-admin-additional-permissions) if needed.

#### Product administrator default permissions

Product administrators have permissions to complete most tasks within Customer Journey Analytics. 

Product administrators are granted the necessary permissions to perform the following tasks by default:

* Update and delete projects, segments, calculated metrics, audiences, annotations, or segments created by other users
* Share Workspace projects to all users
* Manage reporting activity in the [Reporting Activity Manager](/help/reporting-activity-manager/reporting-activity-overview.md)
* [Export full tables](/help/analysis-workspace/export/export-cloud.md) from Analysis Workspace

#### Product administrator additional permissions

In addition to being added as a Product administrator in the **Customer Journey Analytics Product Profile** in the [Admin Console](https://adminconsole.adobe.com/enterprise/), additional permissions are required to complete the following tasks within Customer Journey Analytics:

* Create, update, and delete [data views](/help/data-views/data-views.md).
* Create, update, and delete [connections](/help/connections/overview.md)
  
  To perform this task, users must be part of an **Experience Platform Product Profile** that provides the following permissions:

  | Category | Permission | Description |
  |---|---|---|
  | [!UICONTROL Sandboxes] | [!UICONTROL At least one] | Access to relevant sandboxes for connections. |
  | [!UICONTROL Data Modeling] | [!UICONTROL View Schemas] | Read-only access to schemas and related resources. |
  | [!UICONTROL Data Modeling] | [!UICONTROL Manage Schemas] | Access to read, create, edit, and delete schemas and related resources. |
  | [!UICONTROL Data Management] | [!UICONTROL View Datasets] | Read-only access for datasets and schemas. |
  | [!UICONTROL Identity Management] | [!UICONTROL View Identity Namespaces] | Read-only access for identity namespaces. |
    
    For more information on Experience Platform permissions, see [Manage permissions for a product profile](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/ui/permissions).


* If Journey Optimizer is integrated with Customer Journey Analytics where Journey Optimizer Connections exist, then Journeys permissions must also be added to access Connections:

  | Category | Permission | Description |
  |---|---|---|
  | [!UICONTROL Journeys] | [!UICONTROL View Journeys Events, Data Sources and Actions] | Read-only access to journey events, journey custom actions, and journey data sources. |
  | [!UICONTROL Journeys] | [!UICONTROL Manage Journeys Events, Data Sources and Actions ] | Read, create, edit, and delete events, sources, or actions. |
  | [!UICONTROL Journeys] | [!UICONTROL View Journeys] | Read-only access to journeys. |
  | [!UICONTROL Journeys] | [!UICONTROL Manage Journeys] | Read, create, edit, and delete journeys. |

* Export datasets to [destinations](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets)
  
  To perform this task, users must be part of an **Experience Platform Product Profile** that provides the following permissions:
  
  | Category | Permission | Description |
  |---|---|---|
  | [!UICONTROL Destinations] | [!UICONTROL Manage Destinations] | Access to read, create, and delete destination connections and destination accounts. |
  | [!UICONTROL Destinations] | [!UICONTROL Activate Destinations] | Allow users to activate segments to existing destinations. Enables the mapping step in the activation workflow. This permission also requires the View Destinations permission to be granted to the user who wants to activate data to destinations. |
    
    For more information on Experience Platform permissions, see [Manage permissions for a product profile](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/ui/permissions).

* Use the [BI extension](../data-views/bi-extension.md)
  
  For users to use the BI extension, a Product administrator

  * must ensure the Experience Platform permissions for the user include a role that has the Query Service resource with the Manage Queries and Manage Query Service Integration options. For more information on Experience Platform permissions, see [Manage permissions for a product profile](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/ui/permissions). 

      | Category | Permission | Description |
      |---|---|---|
      | [!UICONTROL Query Service] | [!UICONTROL Manage Queries] | Access to read, create, edit, and delete structured SQL queries for Platform data. |
      | [!UICONTROL Query Service] | [!UICONTROL Manage Query Service Integration] | Access to create, update, and delete non-expiring credentials for Query Service access. |

  * must ensure the proper Customer Journey Analytics permissions for the user:
     * permission to access to the relevant data views. See [!UICONTROL Data Views] in [User-level access](#user-level-access).
     * permission to access the Customer Journey Analytics BI extension. See [!UICONTROL Data View Tools] in [User-level access](#user-level-access).

### Product profile administrator role

A product profile is a set of permissions. Product administrators create product profiles and can assign Product profile administrators to manage one or more product profiles. A Product profile administrator can then:

* Manage the assigned product profiles. Such as adding or removing users or user groups and modify the permissions for the product profiles.

* In Customer Journey Analytics, edit data views that are part of an assigned product profile. Product profile administrators cannot create new data views.

### User-level access

The table below outlines the main access permissions for different Customer Journey Analytics capabilities that you can configure for relevant users. You can manage different level of user access through product profiles. A product profile combines a number of permissions, which you then can assign to individual users or user groups. 

The **[!UICONTROL Permissions]** tab is part of each product profile in the [Admin Console](https://adminconsole.adobe.com/enterprise/). 

![admin console permissions](assets/permissions.png)

| Category | Permission | Description |
| --- | --- | ---|
| [!UICONTROL Data Views] | *data view name* | If you toggle **[!UICONTROL Auto-Include]** to **[!UICONTROL On]**, users that are part of this product profile can view all existing and newly created data views. If this setting is set to **[!UICONTROL Off]**, you can select specific data views that users have access to.  |
| [!UICONTROL Reporting Tools] | [!UICONTROL Analysis Workspace Access] |  Let users access [Analysis Workspace](/help/analysis-workspace/home.md). |
| [!UICONTROL Reporting Tools] | [!UICONTROL Guided Analysis Access] | Let users access [Guided Analysis](/help/guided-analysis/overview.md).  |
| [!UICONTROL Reporting Tools] | [!UICONTROL Calculated Metrics Creation] | Let users create [calculated metrics](/help/components/calc-metrics/calc-metr-overview.md). Users can tag, share, delete, rename, approve, unapprove only the calculated metrics they create or the calculated metrics shared with them.  |
| [!UICONTROL Reporting Tools] | [!UICONTROL Segment Creation] | Let users create [segments](/help/components/segments/seg-overview.md). Users can tag, share, delete, rename, approve, unapprove only the segments they create or the segments shared with them. |
| [!UICONTROL Reporting Tools] | [!UICONTROL Labs Access] | Let users access the [Labs](/help/labs/labs.md) tab in Customer Journey Analytics. |
| [!UICONTROL Reporting Tools] | [!UICONTROL Annotation Creation] | Let users create [annotations](/help/components/annotations/overview.md). Users can tag, share, delete, and rename only the annotations they create or annotations shared with them. |
| [!UICONTROL Reporting Tools] | [!UICONTROL Audience View] | Let users view [audiences](/help/components/audiences/audiences-overview.md). |
| [!UICONTROL Reporting Tools] | [!UICONTROL Audience Creation] | Let users create [audiences](/help/components/audiences/audiences-overview.md). Requires [Manage Segments](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/home) in Adobe Experience Platform. |
| [!UICONTROL Reporting Tools] | [!UICONTROL Data storytelling] | Let users [generate slide presentations based on Workspace projects.](/help/analysis-workspace/curate-share/generate-slides.md) |
| [!UICONTROL Reporting Tools] | [!UICONTROL Audit Logs Access] |  Enforce the permission check on the [API](https://developer.adobe.com/cja-apis/docs/endpoints/auditlogs/) and the audit logs UI. |
| [!UICONTROL Reporting Tools] | [!UICONTROL Share Project Links With Anyone] | Let users [share projects with anyone.](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/curate-share/share-projects)  |
| [!UICONTROL Reporting Tools] | [!UICONTROL Forecasting] | Let users access the [Forecasting](../analysis-workspace/c-forecast/forecasting.md) feature in Analysis Workspace  |
| [!UICONTROL Reporting Tools] | [!UICONTROL AI Assistant: Product Knowledge]  | Let users access the [AI Assistant](../ai-assistant.md) for product knowledge. |
| [!UICONTROL Reporting Tools] | [!UICONTROL Intelligent Captions] | Let users access [Intelligent captions](/help/analysis-workspace/visualizations/intelligent-captions.md). |
| [!UICONTROL Data View Tools] | [!UICONTROL Full Table Export] | Let users [export full tables to the cloud](/help/analysis-workspace/export/export-cloud.md).  |
| [!UICONTROL Data View Tools] | [!UICONTROL CJA BI Extension] | Let users use the [BI extension](../data-views/bi-extension.md). |

{style="table-layout:auto"}

## Workspace project curation

Another level of access control can be used at the Workspace reporting level. You can limit access to specific components for certain users. For more information on how to limit components (dimensions, metrics, segments, date ranges) at the Workspace project level, and how curation is tied to data views, see [Curate projects](/help/analysis-workspace/curate-share/curate.md).

## Grant access to individual metrics or dimensions

You cannot grant or deny permissions for individual metrics or dimensions in Customer Journey Analytics like you can in traditional Adobe Analytics. Metrics and dimensions can be modified in [data views](/help/data-views/data-views.md) and are thus subject to change in Customer Journey Analytics. Changing them also retroactively changes reporting.

## Use cases

Here are a few use cases that illustrate how access control can be used in real-life scenarios.

### Third-party access

You can provide Product profile administration access to a team lead of a third party that your company works. This admin can add users on the company's team to this product profile. This Product profile administrator can give access to specific data views and add other users within the third party to this product profile. The Product profile administrator can modify data views to fit the third party team's requirements.

### Row-level access control

You want to give users access to data from one day only. Here is how you would limit access to those specific rows:

1. Create a segment in [!UICONTROL Settings] of a specific data view, where [!UICONTROL Day] equals the date you want them to have data access to. See [Create data view](/help/data-views/create-dataview.md#settings-filters) for more information.
1. Save the data view, which applies the segment to the data part of the datasets in the underlying connection. Any rows that don't fit the segment definition are automatically excluded from the data view and not available to Analysis Workspace when using this data view.
1. Create a new [Product profile](#product-profile-admin-role) in the Admin Console, add users to the product profile, and include only this specific data view to the product profile.

### Value-level access control

Users who have access to a data view can only work with the metrics and dimensions that the administrator has included in this data view. Administrators can use the [Include/Exclude functionality](/help/data-views/component-settings/include-exclude-values.md) or [Value bucketing](../data-views/component-settings/value-bucketing.md) component settings in a data views to exclude or aggregate certain dimension values from a data view.

For example: You create a metric called *Hypertension* in a data view from a component that contains individual patient data from the dataset. You use value bucketing to provide only access to bucketed values, so users of the data do not see the individual patients data.
