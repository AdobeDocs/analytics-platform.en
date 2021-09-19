---
title: What is the Report Builder Hub in Customer Journey Analytics
description: Describes the Report Builder Hub components
role: Data Engineer, Data Architect, Admin, User
feature: Report Builder
type: Documentation
---

# Report Builder Hub

Use the Report Builder hub to create, update, or delete data blocks.

The Report Builder hub contains the COMMANDS and QUICK EDIT panels.

![](./assets/image13.png)

## COMMANDS panel

Use the COMMANDS panel to access commands that are compatible with the
selected cells or a previous action.

![](./assets/image14.png)

### Commands

| Commands displayed      | Available when…   | Purpose          |
|------|------------------|--------|
| Create data block | One or more cells is selected in the workbook. | Used to create a data block |
| Edit data block | The selected cell or cells range is part of one data block only. | Used to edit a data block                       |
| Refresh data block      | The selection contains at least one data block. The command will refresh only the data blocks in the selection. | Used to refresh one or more data blocks         |
| Refresh all data blocks | The workbook contains one or more data blocks. | Used to refresh ALL data blocks in the workbook |
| Copy data block   | The selected cell or cell range is part of one or more data blocks. | Used to copy a data block   |
| Delete data block | The selected cell or cells range is part of one data block only. | Used to delete a data block |

## QUICK EDIT panel

When you select one or more data blocks in a spreadsheet, Report Builder
displays the QUICK EDIT panel. You can use the QUICK EDIT panel to
change parameters in a single data block or to change parameters in
multiple data blocks at the same time.

![](./assets/image15.png)

The changes made using the Quick Edit sections apply to all data blocks
that are present in the selected ranges.

### Data views

Data blocks pull data from a selected Data view. If multiple data blocks
are selected in a worksheet and they don't pull data from the same data
view, the **Data views** link displays *Multiple*.

When you change the data view, all data blocks in the selection adopt
the new data view. Components in the data block are matched to the new
data view based on ID, for example, matching ```evars```). If a component isn't found in a data block, a warning message is displayed and the component is removed from the data block.

To change the data view, select a new data view from the drop-down menu.

![](./assets/image16.png)

### Date range

**Data range** shows the date range for the selected data blocks. If
multiple data blocks are selected with multiple date ranges, the **Data range** link displays *Multiple*.

### Filters

The **Filters** link displays a summary list of the filters used by the
selected data blocks. If multiple data blocks are selected with multiple
filters applied, the **Filters** link displays *Multiple*.
