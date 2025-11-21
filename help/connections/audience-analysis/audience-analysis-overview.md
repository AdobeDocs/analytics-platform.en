---
title: Audience analysis overview
description: Learn about analyzing audiences from RTCDP in Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Audiences
role: Admin
hide: yes
hidefromtoc: yes
---
# Audience analysis overview

<!-- add hidden text in this article when this feature releases: /help/components/audiences/audiences-overview.md -->

>[!NOTE]
>
>Audience analysis is different from audience publishing, which allows you to create and publish audiences discovered in Customer Journey Analytics to Adobe Experience Platform for customer targeting and personalization. For information about audience publishing,  see [Audience publishing overview](/help/components/audiences/audiences-overview.md).

Audience analysis allows you to ingest audience membership data from Experience Platform Profile datasets into a Customer Journey Analytics connection. Audiences become available as new dimensions for use in Analysis Workspace.

The following diagram and associated table show a high-level representation of how an audience analysis configuration in Customer Journey Analytics makes audience data from Experience Platform available in Analysis Workspace:

![Audience analysis overview](assets/audience-analysis-overview.png)


| Number | Feature | Function |
|---------|----------|---------|
| 1 | Audience analysis configuration | Configuration interface in Customer Journey Analytics used for configuring audience analysis. |
| 2 | Sandbox | Must contain the profile dataset that you want to add to your connection. |
| 3 | Profile dataset | Must include the Experience Platform audience data that you want to analyze. This profile dataset is added to the connection that you select. |
| 4 | Merge policy | The merge policy associated with the Experience Platform audiences that you want to analyze. |
| 5 | Profile data | The profile data associated with the merge policy that you select. This data is available within Experience Platform datasets. |
| 6 | New lookup dataset | Provides friendly names for the new audience dimensions that are created. The lookup dataset is automatically created and added to the connection, along with the profile dataset you select. |
| 7 | Connection | The connection where you want to add the profile dataset that you select. |
| 8 | New audience dimensions | New audience dimensions<!--and metrics?--> that represent the Experience Platform audiences that are included in the profile dataset you selected, and are available for reporting in Analysis Workspace. These dimensions are automatically created. |
| 9 | Data views | The data views you select that are associated with your connection. These are the data views that you want to use when analyzing Experience Platform audience data within Analysis Workspace. These data views are automatically configured with Experience Platform audience data for reporting. |
| 10 | Analysis Workspace | The area within Customer Journey Analytics where you create reports that include the Experience Platform audiences that are ingested. |

## Configure audience analysis

When you configure audience analysis, you select the sandbox and merge policy associated with the Experience Platform audiences that you want to analyze. Customer Journey Analytics creates a new lookup dataset, then automatically adds the lookup dataset and the profile dataset to the connection you choose. 

For more information, see [Configure audience analysis](/help/connections/audience-analysis/audience-analysis-configure.md).

## Analyze audience data in Customer Journey Analytics

With audience data available in Customer Journey Analytics, you can gain actionable insights into how audience members behave across various channels. 

For example, you can track the behavior of individual customers who were included in the same email promotion. With the audience available in Customer Journey Analytics, you can see the following kinds of information about each audience member:

* Click-throughs from the email to the site that eventually resulted in a purchase

* Audience members who eventually made an in-store purchase 

For more information, see [Analyze Experience Platform audiences in Customer Journey Analytics](/help/connections/audience-analysis/analyze-audiences.md).


 







