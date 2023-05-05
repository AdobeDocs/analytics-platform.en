---
title: How do you select a data view in Report Builder
description: Describes how to select data views
role: Data Engineer, Data Architect, Admin, User
feature: Report Builder
type: Documentation
exl-id: 
solution: Customer Journey Analytics
---

# Select a data view

You can select a data view from the drop-down list or select a data view from a cell and automatically update your data block with a new data view. 

Selecting a data view from a cell makes it easy to refresh data blocks using different data views. If your organization has multiple data views that are similar or identical to each other in structure, instead of creating completely new reports with separate data blocks, you can refresh data blocks with a data view selected from a cell. This is also helpful if you have complicated data block formats that include customized components and layouts.

To select a data view from a cell, first build a data block and assign multiple data views to a cell outside of your data block. Then, use the data view from cell panel to refresh your data blocks from different data views.

1. Create a data block.

1. Click the from cell icon.

   ![Cell icon](./assets/cell-icon.png)

1. Select a cell location to add the data views to the selected cell.

   You might want to select a cell far enough away from your data block cells so that they don't overlap.

1. Confirm the selected cell location.

1. Select the data views that you want to assign to the cell.

   ![Select data view](./assets/select-data-view.png)

1. Click Apply.

   When you create your data block, you can refresh the data using a different data view from the cell.

   **Change the data view from the cell**

1. Click the data view cell location that you chose in Step 3.

   The Quick edit pane shows the *Data views from cell link*.

1. Click the **Data views from cell link**.

   ![Select data view](./assets/select-data-view.png)

   The Select data view from cell pane displays a drop-down menu listing the data views that you selected previously (Step 5).

   ![Add data view from cell](./assets/add-data-view-cell.png)

1. Select a different data view from the drop-down list.

1. (Optional) Select Refresh data block(s) upon change.

1. Click Apply.

   Report Builder refreshes the data block with chosen data view.
