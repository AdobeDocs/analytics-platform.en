---
title: Manage connections
description: Describes how to manage connections to Experience Platform datasets in Customer Journey Analytics (CJA).
mini-toc-levels: 3
exl-id: 0a87518c-3608-44ad-b5e3-976f97560433
---
# Manage connections

Once Admin users have [created one or more connections](/help/connections/create-connection.md), they can manage them in the [!UICONTROL Connections] Manager. The latest update to the Connection experience adds two important capabilities within the Connection Details page, described further down on this page:

* It lets you check the **status of your connection's datasets and of the ingestion process**. This status check lets you know when your data is available so that you can go into Analysis Workspace and start analysis.

* It lets you **identify any data discrepancies** due to misconfiguration. Are you missing any rows? If yes, what rows are missing and why? Did you misconfigure connections and cause missing data in CJA?

>[!NOTE]
> This functionality will be generally available on September 20, 2021.

## Connections Manager {#connections-manager}

The Connections Manager allows you to:

* View all your connections at a glance, including the owner, the sandbox, and when they were created and modified.
* View all datasets in a connection.
* Check the status of a connection.
* Delete a connection.
* Rename a connection.
* Create a data view from a connection.

![Manage connections](assets/conn-manager.png)

| Setting | Description |
| --- | --- |
| [!UICONTROL Name] | The connection's friendly name. When you click the hyperlinked name, you get to the Connection details page described below.|
| Connection info | Click the info icon next to the connection name to view the following information:![View connection info](assets/conn-info.png) |
| Edit a connection | Click the ellipsis (...) next to the connection name, then click [!UICONTROL Edit].![Edit connection](assets/conn-edit-delete.png) For more information, see "Edit connection" below. |
| Delete a connection | Click the ellipsis (...) next to the connection name, then click [!UICONTROL Delete]. More information under the "Delete connections" heading below.|
| Create data view | Click the ellipsis (...) next to the connection name, then click [!UICONTROL Create data view]. This action creates a new data view based on this connection. [Learn more](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=en) |
| [!UICONTROL Datasets] | The datasets that are part of the connection. You can click the hyperlink to view all the datasets in the connection. Clicking on a dataset opens that dataset in Adobe Experience Platform, in a new tab. |
| [!UICONTROL Sandbox] | The [Adobe Experience Platform sandbox](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=en) from which this connection draws its datasets. This sandbox was selected when you first created the connection. It cannot be changed.|
| [!UICONTROL Owner] | The person who created the connection. |
| [!UICONTROL Import Data Sets] | Lets you enable or disable what used to be called "data streaming." |
| [!UICONTROL Date Created] | The date when the connection was first created. |
| [!UICONTROL Last Modified] | The date when the connection was last updated. |

### Delete connections {#connections-delete}

Only Admins have permission to delete a connection. This action does not show up for non-admins.

1. Click the ellipsis (...) next to the connection name.
1. Click [!UICONTROL Delete].

When you delete a connection in [!UICONTROL Customer Journey Analytics], an error message will indicate that:

* Any data views that were created based on the deleted connection no longer work.
* Similarly, any Workspace projects that depend on data views in the deleted connection will cease working.

[Learn more](/help/getting-started/cja-deletion.md) about deletion implications.
 
### Search for a connection or dataset

You can search for connections using the Search bar at the top, underneath the [!UICONTROL Connections] title.

### Sort connections

You can sort connections by clicking each column header and sorting up or down.

## Connection Details page {#connection-detail}

The new Connections Details page gives you a very detailed view of the status of a connection.

It lets you:

* Check the status of your connection's datasets and of the ingestion process.
* Identify configuration problems that lead to skipped, or deleted records.
* See when the data is available for reporting.

 Here are the widgets and settings explained:

![View connection detail](assets/conn-details.png)

| Widget/Setting | Description |
| --- | --- |
| Dataset selector | Lets you pick one or all datasets in the connection. You cannot multi-select datasets. Defaults to [!UICONTROL All datasets]. |
| Calendar/Date Ranges | The date range indicates when you added data to the connection. All standard calendar presets are included. You can customize the date range, but no custom date ranges show up in the dropdown. |
| [!UICONTROL Records available] widget | Represents the total number of rows available for reporting, **for the entire connection**. This count is independent of any calendar settings. It changes if you select a dataset from the dataset selector or by selecting a dataset in the table. ( Note that there is a latency of 1-2 hours to get the data to appear in reporting, once it is added.)   |
| [!UICONTROL Metrics] widget | Summarizes the records added/skipped/deleted, and the number of batches added, **for the dataset and date range you have selected**. |
| [!UICONTROL Records added] widget | Indicates how many rows were added in the selected time period, **for the dataset and date range you have selected**. Updated every 10 minutes.|
| [!UICONTROL Records skipped] widget | Indicates how many rows were skipped in the selected time period, **for the dataset and date range you have selected**. Reasons for skipping records include: Missing timestamps, missing person ID, etc. Updated every 10 minutes. |
| [!UICONTROL Records deleted] widget | Indicates how many rows were deleted in the selected time period, **for the dataset and date range you have selected**. Someone might have deleted a dataset in Experience Platform, for example. Updated every 10 minutes. |
| Dataset search box | You can search by dataset name or [!UICONTROL Dataset ID]. |
| [!UICONTROL Datasets] | Shows the datasets that are part of the connection. You can click the hyperlink to view all the datasets in the connection.  |
| [!UICONTROL Dataset ID] |  This ID is automatically generated by Adobe Experience Platform. |
| [!UICONTROL Batches] | Indicates how many data batches have been added to this dataset. |
| [!UICONTROL Last added] | Shows the timestamp for the last added batch to this dataset.  |
| [!UICONTROL Dataset type] | The dataset type for this dataset can be [!UICONTROL Event], [!UICONTROL Lookup], or [!UICONTROL Profile]. [Learn more](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=en#configure-dataset)  |
| Schema | The Adobe Experience Platform schema that the datasets in this connection are based on.  |
| **Right-hand rail at the connection level** |  |
| [!UICONTROL Refresh] | Refresh the connection to allow recently added records to be reflected.  |
| [!UICONTROL Delete] | Delete this connection.  |
| [!UICONTROL Create data view] | Create a new data view based on this connection. [Learn more](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=en) |
| [!UICONTROL Connection Name] | Shows the friendly name of the connection. |
| [!UICONTROL Connection description] | Shows a more detailed description that ideally describes the purpose of this connection. |
| [!UICONTROL Person ID] |  Shows an identity that was defined in the dataset schema in the Experience Platform. This is the [!UICONTROL Person ID] you chose during the creation of the connection. If you create a connection that includes datasets with different IDs, the reporting will reflect that. To really merge datasets, you need use the same [!UICONTROL Person ID]. |
| [!UICONTROL Sandbox] | The [Adobe Experience Platform sandbox](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=en) from which this connection draws its dataset/s. This sandbox was selected when you first created the connection. It cannot be changed. |
| [!UICONTROL Connection ID] | This ID is system generated in Adobe Experience Platform. |
| [!UICONTROL IMS Org ID] | The [organization ID](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=en) associated with your provisioned Experience Cloud company. Formerly called "login company". |
| [!UICONTROL Data views using connection] | Lists all the data views that use this connection. |
| [!UICONTROL Import new data] | Indicates whether new batches of data should or should not be added to the historical (backfill) data. |
| **Right-hand rail at the dataset level** |  |
| [!UICONTROL Dataset description] | Describes the parameters of each dataset in this connection. |
| [!UICONTROL Records available] | Represents the total number of rows ingesed for this dataset, for the particular time period selected through the calendar. There is no latency in terms of getting the data to appear in reporting, once it is added. (The exception is that when you create a brand-new connection, there will be [latency](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=en#3.-getting-data-into-customer-journey-analytics). |
| [!UICONTROL Records added] | How many rows were added in the selected time period. |
| [!UICONTROL Records skipped] | How many rows were skipped during ingestion in the selected time period. |
| [!UICONTROL Record skipped errors] | The reason why records were skipped is indicated here. They could include missing time stamps, missing Person ID, etc. |
| [!UICONTROL Batches ingested] | How many data batches were added into this dataset.  |
| [!UICONTROL Last added] | When the last batch was added. |
| [!UICONTROL Dataset type] | Either [!UICONTROL Event], [!UICONTROL Lookup], or [!UICONTROL Profile]. [Learn more](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=en#configure-dataset)  |
| [!UICONTROL Schema] | The Adobe Experience Platform schema that this dataset is based on. |
| [!UICONTROL Dataset ID] | This ID is system generated in Adobe Experience Platform. |
| [!UICONTROL Backfill data] | Backfill (historical) data is tracked in 3 states: [!UICONTROL In queue], [!UICONTROL In progress] (with progress percentage indicated), and [!UICONTROL Complete]. |

### Edit connection

Allows Admins to edit the connection. Select a connection, then click [!UICONTROL Edit Connection] to get to this dialog. Here, you can do the following:

* Start and stop importing new data. This process was formerly known as "data streaming".
* Rename a connection.
