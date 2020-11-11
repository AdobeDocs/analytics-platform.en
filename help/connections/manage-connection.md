---
title: Manage connections
description: Describes how to manage connections to Platform datasets.
---

# Manage connections

Once you have created one or more connections, you can manage them in the [!UICONTROL Connections] Manager. You can 

* Delete a connection.
* Rename a connection.
* Create a data view from a connection.
* Start and stop data streaming.

![Connections manager](assets/connections-manager.png)

1. Click the **[!UICONTROL Connections]** tab.

2. Select which connection/s you want to edit or manage.

3. Complete one of the following actions:

    |Action|Description|
    |---|---|
    |[!UICONTROL Delete]|Deleting a connection does not delete the dataset, since the data is still in [!DNL Adobe Experience Platform]. See "Delete connections" below. |
    |[!UICONTROL Rename]|You can rename the connection with a more descriptive name.|
    |[!UICONTROL Create Data View]|This link takes you to the [data view builder](/help/data-views/create-dataview.md).|
    |[!UICONTROL Start or stop data streaming]|"Streaming" means that if any new batches are added to any of the datasets in the connection, this new data will be brought into [!UICONTROL Customer Journey Analytics] for reporting.|

## Delete connections

| What if I... | This happens |
| --- | --- |
| Delete a connection in [!UICONTROL Customer Journey Analytics]? | An error message will indicate that:<ul><li>Any data views created for the deleted connection will no longer work.</li><li> Similarly, any Workspace projects that depend on data views in the deleted connection will cease working.</li></ul> |
| Delete a dataset in [!UICONTROL Adobe Experience Platform]? | Deleting a dataset in AEP will stop data flow from that dataset to any connections that include that dataset. Any data from that dataset is not automatically deleted from associated CJA Connections. |
| Delete a dataset in [!UICONTROL Customer Journey Analytics]? | Currently, you cannot delete a dataset within a connection that has been saved. You would have to delete the whole connection and start over. (However, you can delete a dataset in [!UICONTROL Adobe Experience Platform].) |
| Delete a batch from a dataset (in [!UICONTROL Adobe Experience Platform])? | If a batch is deleted from an [!UICONTROL Adobe Experience Platform] dataset, the same batch will be removed from any [!UICONTROL Customer Journey Analytics] connections that contain that specific batch. [!UICONTROL Customer Journey Analytics] is notified of batches that were deleted in [!UICONTROL Adobe Experience Platform]. |
| Delete a batch **while it is being ingested** into [!UICONTROL Customer Journey Analytics]? | If there is only one batch in the dataset, no data or partial data from that batch will appear in [!UICONTROL Customer Journey Analytics]. The ingestion will be rolled back. If, for example, there are 5 batches in the dataset and 3 of them have already been ingested when the dataset was deleted, data from those 3 batches will appear in [!UICONTROL Customer Journey Analytics]. |
