---
title: Report Builder Hub
description: Learn about the Report Builder hub.
role: User
feature: Report Builder
type: Documentation
exl-id: 119bd0b5-0d07-407f-b6e9-ef43352bad31
solution: Customer Journey Analytics
---
# Report Builder hub

The Report Builder hub is the right pane that is displayed within your Excel workbook when you select ![AdobeLogoRedonWhite](/help/assets/icons/AdobeLogoRedOnWhite.svg) **[!UICONTROL Report Builder]** from the Excel ribbon bar.

Use the Report Builder hub to create, update, delete, and manage data blocks.

The Report Builder hub contains the  ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Create]**, ![TableManage](/help/assets/icons/TableManage.svg) **[!UICONTROL Manage]** and ![Calendar](/help/assets/icons/Calendar.svg) **[!UICONTROL Schedule]** buttons, the **[!UICONTROL Commands]** panel, and the **[!UICONTROL Quick edit]** panel.

![Report Builder hub](assets/hub51.png){zoomable="yes"}


Select

* ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Create]** to [create new data blocks](create-a-data-block.md).  
* ![TableManage](/help/assets/icons/TableManage.svg) **[!UICONTROL Manage]** to [manage existing data blocks](manage-reportbuilder.md).
* ![Calendar](/help/assets/icons/Calendar.svg) **[!UICONTROL Schedule]** to [manage schedules to send your workbook by email](schedule-reportbuilder.md).

## Commands panel

Use the **[!UICONTROL Commands]** panel to access commands that are compatible with the selected cells or a previous action.

| Commands      | Available when…   | Purpose          |
|------|------------------|--------|
| ![Edit](/help/assets/icons/Edit.svg) **[!UICONTROL Edit data block]** | The selected cell or cells range is part of one data block only. | Use to edit a data block.                       |
| ![Refresh](/help/assets/icons/Refresh.svg) **[!UICONTROL Refresh data block]**      | The selection contains at least one data block. The command refreshes only the data blocks in the selection. | Use to refresh one or more data blocks.    |
| ![DocumentRefresh](/help/assets/icons/DocumentRefresh.svg) **[!UICONTROL Refresh all data blocks]** | The workbook contains one or more data blocks. | Use to refresh all data blocks in the workbook |
| ![Send](/help/assets/icons/Send.svg) **[!UICONTROL Send workbook]** | The workbook contains one or more data blocks. | Use to [send the workbook as a file by email](schedule-reportbuilder.md). |
| ![Copy](/help/assets/icons/Copy.svg) **[!UICONTROL Copy data block]**   | The selected cell or cell range is part of one or more data blocks. | Use to copy a data block.   |
| ![Cut](/help/assets/icons/Cut.svg) **[!UICONTROL Cut data block]** | The selected cell or cell range is part of one or more data blocks. | se to cut a data block. |
| ![Delete](/help/assets/icons/Delete.svg) **[!UICONTROL Delete data block]** | The selected cell or cells range is part of one data block only. | Use to delete a data block |

## Quick edit panel

When you select one or more data blocks in a spreadsheet, Report Builder displays the **[!UICONTROL Quick edit]** panel. You can use the **[!UICONTROL Quick edit]** panel to change parameters in one or more data blocks at the same time.

The changes you make when you use the **[!UICONTROL Quick Edit]** sections apply to all selected data blocks.

### Data views

Data blocks pull data from a selected data view. If multiple data blocks are selected in a worksheet and they don't pull data from the same data view, the **Data views** link displays **[!UICONTROL _Multiple_]**.

When you change the data view, all data blocks in the selection adopt the new data view. Components in the data block are matched to the new data view based on ID. If a component isn't found in a data block, the component is removed and replaced with **[!UICONTROL Invalid value]** or an ![AlertRed](/help/assets/icons/AlertRed.svg) is displayed for the specific component.

To change the data view, select a new data view from the **[!UICONTROL Data view]** drop-down menu.


### Date range

**Date range** shows the date range for the selected data blocks. If multiple data blocks are selected with multiple date ranges, the **[!UICONTROL Date range]** link displays **[!UICONTROL _Multiple_]**.

### Segments

The **Segments** link displays a summary list of the segments used by the selected data blocks. If multiple data blocks are selected with multiple segments applied, the **Segments** link displays **[!UICONTROL _Multiple_]**.

>[!MORELIKETHIS]
>
>[Select a data views](select-data-view.md)
>[Select a date range](select-date-range.md)
>[Work with filters](work-with-filters.md)
>
