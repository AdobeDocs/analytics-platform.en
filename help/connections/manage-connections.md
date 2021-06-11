---
title: Manage connections
description: Describes how to manage connections to Platform datasets.
---
# Manage connections

Once Admin users have created one or more connections, they can manage them in the [!UICONTROL Connections] Manager. The latest update to the Connection experience adds two important capabilities within the Connections Detail page:

* It lets you check the **status of your connection's datasets and of the ingestion process**. This status check lets you know when your data is available so that you can go into Analysis Workspace and start analysis.

* It lets you **identify any discrepancies in the ingestion process**. Are you missing any rows? If yes, what rows are missing and why? Did you misconfigure connections and cause missing data in CJA?

## Connections Manager

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
| Edit a connection | Click the ellipsis (...) next to the connection name, then click [!UICONTROL Edit].![Edit connection](assets/conn-edit-delete.png)  |
| Delete a connection | Click the ellipsis (...) next to the connection name, then click [!UICONTROL Delete]. More information under the "Delete connection" heading below.|
| Create data view | Click the ellipsis (...) next to the connection name, then click [!UICONTROL Create data view]. This action creates a new data view based on this connection. [Learn more](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=en) |
| [!UICONTROL Datasets] | The datasets that are part of the connection. You can click the hyperlink to view all the datasets in the connection. |
| [!UICONTROL Sandbox] | The [Adobe Experience Platform sandbox](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=en) from which this connection draws its datasets. This sandbox was selected when you first created the connection. It cannot be changed.|
| [!UICONTROL Owner] | The person who created the connection. |
| [!UICONTROL Import Data Sets] | Lets you enable or disable what used to be called "data streaming."  To change this from |
| [!UICONTROL Date Created] | The date when the connection was first created. |
| [!UICONTROL Last Modified] | The date when the connection was last updated. |

### Delete connections

1. Click the ellipsis (...) next to the connection name.
1. Click [!UICONTROL Delete].

Here are a few things to consider before you delete a connection:

| If you... | This happens... |
| --- | --- |
| Delete a connection in [!UICONTROL Customer Journey Analytics] | An error message will indicate that:<ul><li>Any data views created for the deleted connection will no longer work.</li><li> Similarly, any Workspace projects that depend on data views in the deleted connection will cease working.</li></ul> |
| Delete a dataset in [!UICONTROL Adobe Experience Platform] (AEP) | Deleting a dataset in AEP will stop data flow from that dataset to any connections that include that dataset. Any data from that dataset is not automatically deleted from associated CJA Connections. |
| Delete a dataset in [!UICONTROL Customer Journey Analytics] | Currently, you cannot delete a dataset within a connection that has been saved. You would have to delete the whole connection and start over. (However, you can delete a dataset in [!UICONTROL Adobe Experience Platform].) |
| Delete a batch from a dataset (in [!UICONTROL Adobe Experience Platform]) | If a batch is deleted from an [!UICONTROL Adobe Experience Platform] dataset, the same batch will be removed from any [!UICONTROL Customer Journey Analytics] connections that contain that specific batch. [!UICONTROL Customer Journey Analytics] is notified of batches that were deleted in [!UICONTROL Adobe Experience Platform]. |
| Delete a batch **while it is being ingested** into [!UICONTROL Customer Journey Analytics] | If there is only one batch in the dataset, no data or partial data from that batch will appear in [!UICONTROL Customer Journey Analytics]. The ingestion will be rolled back. If, for example, there are 5 batches in the dataset and 3 of them have already been ingested when the dataset was deleted, data from those 3 batches will appear in [!UICONTROL Customer Journey Analytics]. |

### Search for a connection or dataset

You can search for connections using the Search bar at the top, underneath the [!UICONTROL Connections] title.

### Sort connections

You can sort connections by clicking each column header and sorting up or down.

## View connection details

The new Connections Detail page gives you a very detailed view of the status of a connection.

It lets you:

* Identify problems in the data ingestion stage.
* Start and stop importing new data. (Formerly known as "data streaming".)

 Here are the panels and settings explained:

![View connection detail](assets/conn-details.png)

| Panel/Setting | Description |
| --- | --- |
| Dataset selector | Lets you pick one or all datasets in the connection. Defaults to [!UICONTROL All datasets]. |
| Calendar |  |
| [!UICONTROL Records available] panel | Represents the total number of rows ingested for the datasets, for the particular time period selected through the calendar. There is a latency of 1-2 hours to get the data to appear in reporting, once it is ingested.  |
| [!UICONTROL Metrics] panel | Summarizes the records added/skipped/deleted, and the number of batches ingested. |
| [!UICONTROL Records added] panel | How many rows were added in the selected time period. |
| [!UICONTROL Records skipped] panel | How many rows were skipped in the selected time period. Reasons for skipping records include:... |
| [!UICONTROL Records deleted] panel | How many rows were deleted in the selected time period. |
| Dataset search box | You can search by dataset name or dataset ID. |
| [!UICONTROL Datasets] | The datasets that are part of the connection. You can click the hyperlink to view all the datasets in the connection.  |
| [!UICONTROL Dataset ID] |  This ID is automatically generated. |
| [!UICONTROL Batches] | How many data batches have been ingested into this connection. |
| [!UICONTROL Last added] | The timestamp for the last added batch.  |
| [!UICONTROL Dataset type] | This can be Event, Lookup, or Profile. [Learn more](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=en#configure-dataset)  |
| **Right-hand rail if you are viewing an entire connection with multiple datasets** |  |
| [!UICONTROL Refresh] | Refresh the connection to allow recently added records to be reflected.  |
| [!UICONTROL Delete] | Delete this dataset???  |
| [!UICONTROL Create data view] | This action creates a new data view based on this connection. [Learn more](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=en) |
| [!UICONTROL Connection Name] | The friendly name of the connection. |
| [!UICONTROL Connection description] | A more detailed description that ideally describes the purpose of this connection. |
| [!UICONTROL Person ID] | This identity was defined in the dataset schema in the Experience Platform. The Person ID you chose during the creation of the connection. |
| [!UICONTROL Sandbox] |  The [Adobe Experience Platform sandbox](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=en) from which this connection draws its datasets. This sandbox was selected when you first created the connection. It cannot be changed. |
| [!UICONTROL Connection ID] | This ID is system generated. |
| [!UICONTROL IMS Org ID] | Also known as the Experience Cloud ID (ECID). |
| [!UICONTROL Data views using connection] | Lists all the data views that use this connection. |
| [!UICONTROL Import new data] |  |
| **Right-hand rail if you are viewing details about a single dataset** |  |
| [!UICONTROL Dataset description] | Describes the parameters of each dataset in this connection. |
| [!UICONTROL Records available] | Represents the total number of rows ingested for this dataset, for the particular time period selected through the calendar. There is a latency of 1-2 hours to get the data to appear in reporting, once it is ingested. |
| [!UICONTROL Records added] | How many rows were added in the selected time period. |
| [!UICONTROL Records skipped] | How many rows were skipped in the selected time period. Reasons for skipping records include:... |
| [!UICONTROL Record skipped errors] |  |
| [!UICONTROL Batches ingested] | How many data batches were ingested into this dataset???  |
| [!UICONTROL Last added] | When the last batch was added. |
| [!UICONTROL Dataset type] | This can be Event, Lookup, or Profile. [Learn more](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=en#configure-dataset)  |
| [!UICONTROL Schema] | The Adobe Experience Platform schema that this dataset is based on. |
| [!UICONTROL Dataset ID] | This ID is system generated. |

### View backfill data states

How do they get to this screen?

Backfill (historical) data is tracked in 3 states:

* In queue

* In progress, with progress percentage indicated.

* Complete
