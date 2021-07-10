---
title: What is the Report Builder Hub in Customer Journey Analytics
description: Describes the Report Builder Hub components
role: Data Engineer, Data Architect, Admin, User
feature-set: Report Builder
type: Documentation
---

# Report Builder Hub

The Report Builder hub is shown when you successfully log in to Report
Builder. The hub is displayed on the right-side panel of the Excel
window.

**\<\< NEED: full spreadsheet screen shot \>\>**

![image file](./assets/image13.png)

Use the Report Builder hub to create, update, or delete data blocks. 

### Commands panel

After you create a data block, the Report Builder hub displays the Command panel and the Quick Edit panel.

The Commands panel is used to access commands that are compatible with the selected cells or the previous action.

You can select several distinct cell ranges by using the Ctrl key
(Windows) or the Command key (macOS) as you click and drag. The changes
made using the Command panel apply to all the data blocks that are
included in all the selected ranges.

**\<\< NEED -- screenshot that shows part of the worksheet with one data
block in the cell selection \>\>**

![image file](./assets/image14.png)

Commands are displayed based on the content of the selected cells.


| Commands displayed      | Available when… | Purpose |
| ------------------ | ------------------ | ------------------ |
| Create data block  | One or more cells is selected in the workbook. | Used to create a data block |
| Edit data block | The selected cell or cells range is part of one data block only. | Used to edit a data block |
| Refresh data block | The selection contains at least one datablock. The command will refresh only the datablocks in the selection. | Used to refresh one or more data blocks |
| Refresh all data blocks | The workbook contains one or more datablocks. | Used to refresh ALL datablocks in the workbook. |
| Copy data block | The selected cell or cells range is part of one or more datablocks.| Used to copy a data block |
| Paste data blocks | The previous action taken in Report Builder was Cut Data Block(s) or Copy Data Block(s) AND if the selected location has enough cell- area to paste the copied data blocks without overlapping with pre-existing data blocks | Used to paste a copied or cut data block |

### Quick Edit panel

When you select one or more data blocks in a spreadsheet, the Quick Edit panel is displayed. You can use the Quick Edit panel to change parameters across all the selected data blocks.

![](./assets/image15.png)

You can select several distinct cell ranges by using the Ctrl key (Windows) or the Command key (macOS) as you click and drag. The changes made using the Quick Edit sections apply to all data blocks that are present in the selected ranges. 

#### Data View

If multiple data blocks are selected and they are not assigned to the same data view, the Data View link display shows *Multiple*.

When you change the data view, all data blocks in the selection adopt the new data view.

You can choose a data view from a list of available data views.

![](./assets/image16.png)

The list displayed depends on whether you are creating a new data block, editing an existing data block, or editing multiple data blocks.

#### Date Range

If multiple data blocks are selected and they are not assigned to the same date range, the Date Range link displays *Multiple*.

#### Filters

The Filters link displays a summary list of the filters used by the selected data blocks.
![](./assets/image17.png)

If multiple data blocks are selected and that are not assigned dto the same filters, the Filters link displays *Multiple*.

### Components

When you create a new data block or edit an existing data block, the Components pane is displayed.

This Components tabs allows you to choose elements to include in the data block.

- Dimensions

- Metrics

- Filters

\<\< need new screen shot \>\>

![](./assets/image18.png)

When you are editing a data block, if you make changes to a component and then switch to another component without saving the change, you're prompted to save or discard the changes.

![image file](./assets/image19.png)

### Pivot Table

Use the Pivot Table to configure how the data block elements are organized and displayed in your report.

![image file](./assets/image20.png)

The pivot table allows you to easily organize data in a meaningful way:

- Drag components to the pivot tables
- Display components in rows and columns
- Reuse the same metric multiple times
- Move components to order them within pivot table lists

Double click an item in the Components pane to add it to the
Pivot table at its preferred section.

- A Dimension component is moved to the Row section or to the Column
  section if you have a dimension already in the columns.
- A Date component is moved to the Column section.
- A Filter component is moved to the Filters section.

### Data Block Output

When you add, move, or remove items in the Pivot Table, the data block is pasted in the spreadsheet at the selected Data Block anchor location.

The list of available metrics, dimensions, and filters is dependent on the selected data view. Each time a new data view is selected, the Component tabs are updated to reflect the new list of available items.

![image file](./assets/image21.png)
