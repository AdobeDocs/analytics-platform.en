---
title: Deletion implications
description: What happens when you delete connections, datasets, or batches in Customer Journey Analytics or Adobe Experience Platform.
exl-id: a89694c9-0909-440e-939c-b245fc4dd6bf
solution: Customer Journey Analytics
feature: Basics
---
# Deletion implications

Consider this before you delete connections, datasets, or batches in Customer Journey Analytics or Adobe Experience Platform:

| When you... | This happens... |
| --- | --- |
| Delete a connection in [!UICONTROL Customer Journey Analytics] | An error message will indicate that:<ul><li>Any data views created for the deleted connection will no longer work.</li><li> Similarly, any Workspace projects that depend on data views in the deleted connection will cease working.</li></ul>Note that you cannot delete Customer Journey Analytics connections that are tied to Adobe Experience Platform sandboxes for which you do not have permissions. Even if you have permissions to the data views built on those connections, you cannot delete the connections until you are granted permissions to the underlying Adobe Experience Platform sandboxes.|
| Delete a dataset in [!UICONTROL Adobe Experience Platform] | Deleting a dataset in AEP will stop data flow from that dataset to any connections that include that dataset. Any data from that dataset is automatically deleted from associated Customer Journey Analytics Connections. |
| Delete a dataset in [!UICONTROL Customer Journey Analytics] | When you delete a dataset from a connection in Customer Journey Analytics, any data views and projects that relied on that dataset will no longer work. |
| Delete a batch from a dataset (in [!UICONTROL Adobe Experience Platform]) | If a batch is deleted from an [!UICONTROL Adobe Experience Platform] dataset, the same batch will be removed from any [!UICONTROL Customer Journey Analytics] connections that contain that specific batch. [!UICONTROL Customer Journey Analytics] is notified of batches that were deleted in [!UICONTROL Adobe Experience Platform]. |
| Delete a batch **while it is being ingested** into [!UICONTROL Customer Journey Analytics] | If there is only one batch in the dataset, no data or partial data from that batch will appear in [!UICONTROL Customer Journey Analytics]. The ingestion will be rolled back. If, for example, there are 5 batches in the dataset and 3 of them have already been ingested when the dataset was deleted, data from those 3 batches will appear in [!UICONTROL Customer Journey Analytics]. |
| Delete lookup datasets in [!UICONTROL Adobe Experience Platform] | While deleting datasets is possible for other source connectors, it is currently not supported for [Analytics Classifications Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/classifications.html). If you do delete a dataset by mistake, please contact Adobe Customer Care. |
