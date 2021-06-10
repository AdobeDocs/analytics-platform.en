---
title: Manage connections
description: Describes how to manage connections to Platform datasets.
---
# Manage connections

Once Admin users have created one or more connections, they can manage them in the [!UICONTROL Connections] Manager. The latest update to the Connection experience adds two important capabilities:

* It lets you check the **status of your connection's datasets and of the ingestion process**. This status check lets you know when your data is available so that you can go into Analysis Workspace and start analysis.

* It lets you **identify any discrepancies in the ingestion process**. Are you missing any rows? If yes, what rows are missing and why? Did you misconfigure connections and cause missing data in CJA?

The Connections Manager allows you to:

* View all your connections at a glance, including the owner, the sandbox, and when they were created and modified.
* View all datasets in a connection.
* Check the status of a connection.
* Identify problems in the data ingestion stage.
* Start and stop importing new data. (Formerly known as "data streaming".)
* Delete a connection.
* Rename a connection.
* Create a data view from a connection.

![Manage connections](assets/conn-manager.png)

## View information about a connection

Click the info icon next to the connection name to view the following information:

![View connection info](assets/conn-info.png)

## View details about a connection

The new Connections Detail page 

## Edit a connection

1. Click the ellipsis (...) next to the connection name.
1. Click [!UICONTROL Edit].

![Edit connection](assets/conn-edit-delete.png)

You can edit the following elements of a connection:

* Name?
* ?

## View included datasets

Click the link to the datasets for the respective connection. You may get a long list:

![Edit connection](assets/conn-datasets.png)

## Delete connections

1. Click the ellipsis (...) next to the connection name.
1. Click [!UICONTROL Delete].

Here are a few things to consider before you delete a connection:

| If I... | This happens... |
| --- | --- |
| Delete a connection in [!UICONTROL Customer Journey Analytics] | An error message will indicate that:<ul><li>Any data views created for the deleted connection will no longer work.</li><li> Similarly, any Workspace projects that depend on data views in the deleted connection will cease working.</li></ul> |
| Delete a dataset in [!UICONTROL Adobe Experience Platform] | Deleting a dataset in AEP will stop data flow from that dataset to any connections that include that dataset. Any data from that dataset is not automatically deleted from associated CJA Connections. |
| Delete a dataset in [!UICONTROL Customer Journey Analytics] | Currently, you cannot delete a dataset within a connection that has been saved. You would have to delete the whole connection and start over. (However, you can delete a dataset in [!UICONTROL Adobe Experience Platform].) |
| Delete a batch from a dataset (in [!UICONTROL Adobe Experience Platform]) | If a batch is deleted from an [!UICONTROL Adobe Experience Platform] dataset, the same batch will be removed from any [!UICONTROL Customer Journey Analytics] connections that contain that specific batch. [!UICONTROL Customer Journey Analytics] is notified of batches that were deleted in [!UICONTROL Adobe Experience Platform]. |
| Delete a batch **while it is being ingested** into [!UICONTROL Customer Journey Analytics] | If there is only one batch in the dataset, no data or partial data from that batch will appear in [!UICONTROL Customer Journey Analytics]. The ingestion will be rolled back. If, for example, there are 5 batches in the dataset and 3 of them have already been ingested when the dataset was deleted, data from those 3 batches will appear in [!UICONTROL Customer Journey Analytics]. |

## Search for a connection

You can search for connections using the Search bar at the top, underneath the [!UICONTROL Connections] title.

## Sort connections

jdkfjslfj

## Refresh a connection

dhakhfakshf
