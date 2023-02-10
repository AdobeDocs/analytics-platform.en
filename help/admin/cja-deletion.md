---
title: Deletion implications
description: What happens when you delete connections, datasets, or batches in Customer Journey Analytics or Adobe Experience Platform.
exl-id: a89694c9-0909-440e-939c-b245fc4dd6bf
solution: Customer Journey Analytics
feature: CJA Basics
---
# Deletion implications

Consider this before you delete connections, datasets, or batches in Customer Journey Analytics or Adobe Experience Platform:

| When you... | This happens... |
| --- | --- |
| Delete a connection in [!UICONTROL Customer Journey Analytics] | An error message will indicate that:<ul><li>Any data views created for the deleted connection will no longer work.</li><li> Similarly, any Workspace projects that depend on data views in the deleted connection will cease working.</li></ul> |
| Delete a dataset in [!UICONTROL Adobe Experience Platform] (AEP) | Deleting a dataset in AEP will stop data flow from that dataset to any connections that include that dataset. Any data from that dataset is not automatically deleted from associated CJA Connections. |
| Delete a dataset in [!UICONTROL Customer Journey Analytics] | Currently, you cannot delete a dataset within a connection that has been saved. You would have to delete the whole connection and start over. (However, you can delete a dataset in [!UICONTROL Adobe Experience Platform].) |
| Delete a batch from a dataset (in [!UICONTROL Adobe Experience Platform]) | If a batch is deleted from an [!UICONTROL Adobe Experience Platform] dataset, the same batch will be removed from any [!UICONTROL Customer Journey Analytics] connections that contain that specific batch. [!UICONTROL Customer Journey Analytics] is notified of batches that were deleted in [!UICONTROL Adobe Experience Platform]. |
| Delete a batch **while it is being ingested** into [!UICONTROL Customer Journey Analytics] | If there is only one batch in the dataset, no data or partial data from that batch will appear in [!UICONTROL Customer Journey Analytics]. The ingestion will be rolled back. If, for example, there are 5 batches in the dataset and 3 of them have already been ingested when the dataset was deleted, data from those 3 batches will appear in [!UICONTROL Customer Journey Analytics]. |
| Delete lookup data sets in [!UICONTROL Adobe Experience Platform] | While deleting datasets is possible for other source connectors, it is currently not supported for [Analytics Classifications Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/classifications.html). If you do delete a dataset by mistake, please contact Adobe Customer Care. |
