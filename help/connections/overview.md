---
title: Customer Journey Analytics Connections overview
description: Learn about connections in Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Connections
exl-id: 012371d7-aaef-4018-95ee-5c52083e9d8f
role: Admin
---
# Connections overview

Connections allow Customer Journey Analytics product administrators to establish connections with different [!DNL Adobe Experience Platform] data sources, such as event, lookup, profile, and summary datasets. These connections enable the integration of data from a connection to a derivative data View. Connections are the foundation of Customer Journey Analytics and are created from [!DNL Experience Platform] source datasets. 

Aaccess to connections management should be restricted to a core management group. Connection configurations have contractual implications regarding volume allotments for data brought into Customer Journey Analytics. 

## Connections workflow

![Connections workflow](assets/connection-workflow.png)

<!-- Outdated interface 

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Configuring connections](https://video.tv.adobe.com/v/35111/?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

-->

On a high-level, the Connections workflow allows you to:

| Interface | Description |
|:---:|---|
| ➊ | [Manage your connections and overal usage](manage-connections.md) of Customer Journey Analytics from the Connections manager. |
| ➋ | [Inspect the details of a connection](manage-connections.md#connection-details), like dataset records ingested, skipped, or deleted. |
| ➌ | [Create or edit the configuration of a connection](create-connection.md#create-or-edit-a-connection), like rolling data window and which datasets are part of the connection. |
| ➍ | [Add datasets to a connection](create-connection.md#add-datasets). Your connection should at least have one event or summary dataset but can contain a variety of event, profile, lookup, and summary datasets. |
| ➎ | [Configure the settings](create-connection.md#dataset-settings) for datasets you add. So you can determine how to link different datasets based on a common person based or [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} account based  identifier. |
| ➏ | [Edit the settings for an existing dataset](create-connection.md#edit-a-dataset). You can always revisit the dataset settings at a later stage. |



## Required permissions

To create a Customer Journey Analytics connection, you need the following permissions. For additional details about permissions, refer to documentation for the [Adobe Admin Console](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/manage-permissions-and-roles.ug.html) and [Adobe Experience Platform Permissions](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/home).

### Within Adobe Admin Console:

* Customer Journey Analytics: Product Admin
* Adobe Experience Platform: Added to Product Profile named *AEP-Default-All-Users*

### Within Adobe Experience Platform Permissions:

* Data Modeling: View Schemas, Manage Schemas
* Data Management: View Datasets, Manage Datasets
* Data Ingestion: Manage Sources
* Identity Management: View Identity Namespaces
* Sandboxes: Sandboxes used in related Customer Journey Analytics Connections

>[!IMPORTANT]
>
>You can combine multiple [!DNL Experience Platform] datasets into a single connection.
