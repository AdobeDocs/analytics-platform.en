---
title: Customer Journey Analytics Connections Overview
description: Learn about connections in Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Connections
exl-id: 012371d7-aaef-4018-95ee-5c52083e9d8f
role: Admin
---
# Connections overview

Connections allow Customer Journey Analytics product administrators to define what [!DNL  Experience Platform] data sources, such as event, lookup, profile, and summary datasets, are ingested. Connections are the foundation of Customer Journey Analytics and determine the availability of data (fields) that you can define in a [data view](/help/data-views/data-views.md) as dimension or metrics. 

>[!IMPORTANT]
>
>You can combine multiple [!DNL Experience Platform] datasets into a single connection.


## Connections workflow

![Connections workflow](assets/connection-workflow.png)

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Connect to data sources](https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/connections/connecting-customer-journey-analytics-to-data-sources-in-platform){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

On a high-level, the Connections workflow allows you to:

| Interface | Description |
|:---:|---|
| ➊ | [Manage your connections and overall usage](manage-connections.md) of Customer Journey Analytics from the Connections manager. |
| ➋ | [Inspect the details of a connection](manage-connections.md#connection-details), like dataset records ingested, skipped, or deleted. |
| ➌ | [Create or edit the configuration of a connection](create-connection.md#create-or-edit-a-connection), like a rolling data window, the sandbox to use, which datasets are part of the connection, and more.  |
| ➍ | [Add datasets to a connection](create-connection.md#add-datasets). Your connection should at least have one event or summary dataset but can contain a variety of event, profile, lookup, and summary datasets. |
| ➎ | [Configure the settings](create-connection.md#dataset-settings) for datasets that you add. You can determine how to link different datasets based on a common person-based or [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} account-based identifier. |
| ➏ | [Edit the settings for an existing dataset](create-connection.md#edit-a-dataset). You can always revisit the dataset settings at a later stage. |



## Access control

Access to connections management should be restricted to a core management group. Connection configurations have contractual implications regarding volume allotments for data brought into Customer Journey Analytics. 

>[!MORELIKETHIS]
>
>[Access control](/help/technotes/access-control.md).

