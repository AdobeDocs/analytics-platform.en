---
title: Audience analysis overview
description: Learn about analyzing audiences from RTCDP in Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Audiences
role: Admin
exl-id: 1e962f52-6b56-4671-afea-d58dae67e8a8
---
# Audience analysis overview

>[!NOTE]
>
>Understand the difference between audience analysis and audience publishing:
>
>* **Audience analysis**: Allows you to ingest audience membership data from Experience Platform Profile datasets into a Customer Journey Analytics connection.
>* **Audience publishing**: Allows you to create and publish audiences discovered in Customer Journey Analytics to Adobe Experience Platform for customer targeting and personalization. For information about audience publishing, see [Audience publishing overview](/help/components/audiences/audiences-overview.md).

Audience analysis allows you to ingest audience membership data from Experience Platform Profile datasets into a Customer Journey Analytics connection. Audiences become available as new dimensions for use in Analysis Workspace.

The following diagram and associated table show a high-level representation of how an audience analysis configuration in Customer Journey Analytics makes Experience Platform audience data available in Analysis Workspace:

![Audience analysis overview](assets/audience-analysis-overview.png)

| Number | Feature | Function |
|---------|----------|---------|
| 1 | Audience analysis configuration | The configuration interface in Customer Journey Analytics used for configuring audience analysis. |
| 2 | Sandbox | Must contain the profile dataset that you want to add to your connection. |
| 3 | Profile dataset | Must include the Experience Platform audience data that you want to analyze. This profile dataset is added to the connection that you select. |
| 4 | Merge policy | The merge policy associated with the Experience Platform audiences that you want to analyze. |
| 5 | Profile data | The profile data associated with the merge policy that you select. This data is available within Experience Platform datasets. |
| 6 | New lookup dataset | Provides friendly names for the new audience dimensions that are created. <p>The lookup dataset is automatically created and added to the connection, along with the profile dataset you select.</p> |
| 7 | Connection | The connection where you want to add the profile dataset that you select. |
| 8 | New audience dimensions | New audience dimensions<!--and metrics?--> that represent the Experience Platform audiences that are included in the profile dataset you selected, and are available for reporting in Analysis Workspace. These dimensions are automatically created. |
| 9 | Data views | The data views you select that are associated with your connection. These are the data views that you want to use when analyzing Experience Platform audience data within Analysis Workspace. These data views are automatically configured with Experience Platform audience data for reporting. |

## Configure audience analysis

When you configure audience analysis, you select the sandbox and merge policy associated with the Experience Platform audiences that you want to analyze. Customer Journey Analytics creates a new lookup dataset, then automatically adds the lookup dataset and the profile dataset to the connection you choose. 

>[!IMPORTANT]
>
>Audience data is reprocessed and generated each night, making audience data accurate for analysis only for the previous day ("yesterday"). 
>
>Audiences are available in Customer Journey Analytics data views on the day after you create the audience analysis configuration. 

For more information, see [Configure audience analysis](/help/connections/audience-analysis/audience-analysis-configure.md).

## Manage audience analysis configurations

You can manage audience analysis configurations after they are created. You can view, edit, and delete configurations. 

For information about managing existing audience analysis configurations, see [Manage audience analysis configurations](/help/connections/audience-analysis/audience-analysis-manage.md).

## Analyze audience data in Customer Journey Analytics

With audience data available in Customer Journey Analytics, you can gain actionable insights into how audience members behave across various channels. 

For example, you can track the behavior of individual customers who were included in the same email promotion. With the audience available in Customer Journey Analytics, you can see the following kinds of information about each audience member:

* Click-throughs from the email to the site that eventually resulted in a purchase

* Audience members who eventually made an in-store purchase 

For more information, see [Analyze Experience Platform audiences in Customer Journey Analytics](/help/connections/audience-analysis/analyze-audiences.md).

## Audience analysis role and permission requirements

The following Customer Journey Analytics roles and Experience Platform permissions are required for audience analysis:

| Capability | Customer Journey Analytics role or permission requirements | Experience Platform permission requirements |
|---------|----------|----------|
| [Create audience analysis configurations](/help/connections/audience-analysis/audience-analysis-configure.md) | System administrator | <ul><li>Datasets: Read permissions</li><li>Schemas: Read, Write</li><li>Identity namespaces: Read</li></ul>  |
| [View audience analysis dimensions in the data view](/help/connections/audience-analysis/audience-analysis-configure.md#view-audience-dimensions-in-the-data-view) | Product profile administrator for the product profile that the data view is assigned to <p>For more information, see [Access control](/help/technotes/access-control.md).</p> | N/A |
| Use audience analysis dimensions in Analysis Workspace | Access to a data view where the audience analysis dimensions were added | N/A |

## Audience analysis limits

 Consider the following limits when [configuring audience analysis](/help/connections/audience-analysis/audience-analysis-configure.md):
 
* A single sandbox can support up to 100 audience analysis configurations.

* A connection can be associated with only one audience analysis configuration.
