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

## Connection Details page

The new Connections Details page gives you a very detailed view of the status of a connection.

It lets you:

* Identify problems in the data ingestion stage.
* Start and stop importing new data. (Formerly known as "data streaming".)

 Here are the panels and settings explained:

![View connection detail](assets/conn-details.png)

| Widget/Setting | Description |
| --- | --- |
| Dataset selector | Lets you pick one or all datasets in the connection. You cannot multi-select datasets. Defaults to [!UICONTROL All datasets]. |
| Calendar/Date Ranges | The date range indicates when you ingested data into the connection. Presets include: [!UICONTROL Today], [!UICONTROL Yesterday], [!UICONTROL Last 7 days], [!UICONTROL Last 30 days]. You can also customize the date range. |
| [!UICONTROL Records available] widget | Represents the total number of rows ingested **for the entire connection**, for the time period selected through the calendar. This count does not change when you change the dataset in the dataset selector. ( Note that there is a latency of 1-2 hours to get the data to appear in reporting, once it is ingested.)   |
| [!UICONTROL Metrics] widget | Summarizes the records added/skipped/deleted, and the number of batches ingested, **for the dataset and date range you have selected**. |
| [!UICONTROL Records added] widget | Indicates how many rows were added in the selected time period, **for the dataset and date range you have selected**. Updated every 10 minutes.|
| [!UICONTROL Records skipped] widget | Indicates how many rows were skipped in the selected time period, **for the dataset and date range you have selected**. Reasons for skipping records include: Missing timestamps, missing person ID, etc. Updated every 10 minutes. |
| [!UICONTROL Records deleted] widget | Indicates how many rows were deleted in the selected time period, **for the dataset and date range you have selected**. Someone might have deleted a dataset in Experience Platform, for example. Updated every 10 minutes. |
| Dataset search box | You can search by dataset name or [!UICONTROL Dataset ID]. |
| [!UICONTROL Datasets] | Shows the datasets that are part of the connection. You can click the hyperlink to view all the datasets in the connection.  |
| [!UICONTROL Dataset ID] |  This ID is automatically generated. |
| [!UICONTROL Batches] | Indicates how many data batches have been ingested into this dataset. |
| [!UICONTROL Last added] | Shows the timestamp for the last added batch to this dataset.  |
| [!UICONTROL Dataset type] | The dataset type for this dataset can be [!UICONTROL Event], [!UICONTROL Lookup], or [!UICONTROL Profile]. [Learn more](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=en#configure-dataset)  |
| Schema |   |
| **Right-hand rail if you are viewing an entire connection with all datasets** |  |
| [!UICONTROL Refresh] | Refresh the connection to allow recently added records to be reflected.  |
| [!UICONTROL Delete] | Lets you delete this dataset???  |
| [!UICONTROL Create data view] | Creates a new data view based on this connection. [Learn more](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=en) |
| [!UICONTROL Connection Name] | Shows the friendly name of the connection. |
| [!UICONTROL Connection description] | Shows a more detailed description that ideally describes the purpose of this connection. |
| [!UICONTROL Person ID] |  Shows an identity that was defined in the dataset schema in the Experience Platform. This is the [!UICONTROL Person ID] you chose during the creation of the connection. If you create a connection that includes datasets with different IDs, the reporting will reflect that. To really merge datasets, you need use the same [!UICONTROL Person ID]. |
| [!UICONTROL Sandbox] |  The [Adobe Experience Platform sandbox](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=en) from which this connection draws its datasets. This sandbox was selected when you first created the connection. It cannot be changed. |
| [!UICONTROL Connection ID] | This ID is system generated. |
| [!UICONTROL IMS Org ID] | Also known as the Experience Cloud ID (ECID). |
| [!UICONTROL Data views using connection] | Lists all the data views that use this connection. |
| [!UICONTROL Import new data] | Indicates whether new batches of data should or should not be added to this connection.???? |
| **Right-hand rail if you are viewing details about a single dataset** |  |
| [!UICONTROL Dataset description] | Describes the parameters of each dataset in this connection. |
| [!UICONTROL Records available] | Represents the total number of rows ingested for this dataset, for the particular time period selected through the calendar. There is no latency in terms of getting the data to appear in reporting, once it is ingested. (The exception is that when you create a brand-new connection, there will be [latency](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=en#3.-getting-data-into-customer-journey-analytics). |
| [!UICONTROL Records added] | How many rows were added in the selected time period. |
| [!UICONTROL Records skipped] | How many rows were skipped during ingestion in the selected time period. |
| [!UICONTROL Record skipped errors] | The reason why records were skipped is indicated here. They could include missing time stamps, missing Person ID, etc. |
| [!UICONTROL Batches ingested] | How many data batches were ingested into this dataset???  |
| [!UICONTROL Last added] | When the last batch was added. |
| [!UICONTROL Dataset type] | This can be [!UICONTROL Event], [!UICONTROL Lookup], or [!UICONTROL Profile]. [Learn more](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=en#configure-dataset)  |
| [!UICONTROL Schema] | The Adobe Experience Platform schema that this dataset is based on. |
| [!UICONTROL Dataset ID] | This ID is system generated. |

### View backfill data states

How do they get to this screen?

Backfill (historical) data is tracked in 3 states:

* In queue

* In progress, with progress percentage indicated.

* Complete
