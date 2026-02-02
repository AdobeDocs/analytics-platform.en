---
title: Select A Data View In Report Builder
description: Learn how to select a data view in Report Builder.
role: User
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: bf765144-34f8-465b-b06d-53e4ca91014a
---
# Select a data view

You can select a data view from the drop-down menu or select a data view from a cell and automatically update your data block with a new data view.

## Select data view from a cell

Selecting a data view from a cell makes it easy to refresh data blocks using different data views. Instead of creating completely new reports with separate data blocks, you can refresh data blocks with a data view selected from a cell. 

Selecting a data view from a cell is helpful when you have:

* Multiple data views that are similar or identical to each other in structure.  
* Complicated data block formats that include customized components and layouts.

To select a data view from a cell, first build a data block and assign multiple data views to a cell outside of your data block. Then, use the **[!UICONTROL Data view from cell]** panel to refresh your data blocks from different data views.

1. Create a data block. For information about creating a data block, see [Create a data block](/help/report-builder/create-a-data-block.md).

1. Select ![DataViewSelector](/help/assets/icons/DataViewSelector.svg) in **[!UICONTROL Data views]**.

1. Select a cell using ![DataBlockSelector](/help/assets/icons/DataBlockSelector.svg) outside of the data block.

1. Add one or more data views from the **[!UICONTROL Select data views to add to data view from cell]** using drag and drop. Alternatively, you can double select a data view to add the data view to the **[!UICONTROL Data views included]** list. 

   * You can use ![Search](/help/assets/icons/Search.svg) **[!UICONTROL _Select data views_]** to search for data views.
   * Use ![MoreSmall](/help/assets/icons/MoreSmall.svg) to open a context menu so you can move data views up or down in the **[!UICONTROL Data views included]** list.
   * Use ![CrossSize75](/help/assets/icons/CrossSize75.svg) to delete a data view from the **[!UICONTROL Data views included]** list.

   ![Select data view from a cell](assets/dataviews-from-a-cell.png){zoomable="yes"}

1. Select **[!UICONTROL Apply]** to apply the selected data views to the selected cell.


## Change the data view from a cell

1. Select the data view cell location in your sheet.
1. In the Report Builder hub, select the **[!UICONTROL Data views from cell]** link in **[!UICONTROL Quick edit]**.
1. Select a data view from the **[!UICONTROL Data view]** drop-down menu.

   ![Change data view from a cell](assets/change-data-view-from-cell.png){zoomable="yes"}
1. Optional, select **[!UICONTROL Refresh data block(s) upon change]**.

1. Select **[!UICONTROL Apply]**. Report Builder refreshes the data block based on the selected data view.
