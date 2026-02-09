---
title: Manage Data Views
description: Learn how to manage data views.
solution: Customer Journey Analytics
feature: Data Views
role: Admin
---

# Manage data views


Once you have [created or edited one or more data views](/help/data-views/create-dataview.md), you can manage them in **[!UICONTROL Data views]**. 

Select **[!UICONTROL Data Management]** > **[!UICONTROL Data views]** from the main menubar in Customer Journey Analytics.

The **[!UICONTROL Data views]** interface shows a table of all data views available.

![Data views interface](/help/data-views/assets/data-views.png)

The following columns and icons are available in the table:

| Column or Icon | Description |
| --- | --- |
| **[!UICONTROL Name]** | The name of the data view. |
| ![Information](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) | To view information about the data view, select ![InfoOutline](/help/assets/icons/InfoOutline.svg) next to the data view name.<br/>A pop-up window displays details about the data view. |
| ![More](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) | Select ![More](/help/assets/icons/More.svg) to open a context menu. You can select:<br/>![Edit](/help/assets/icons/Edit.svg) **[!UICONTROL Edit]** to [edit](#edit-data-views) a data view.<br/>![Copy](/help/assets/icons/Copy.svg) **[!UICONTROL Copy]** to [copy a data view](#copy-data-views).<br/>![Delete](/help/assets/icons/Delete.svg) **[!UICONTROL Delete]** to [delete](#delete-data-views) a data view.<br/>![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Export to CSV]** to [export the details of the data view to a CSV file](#export-data-views-to-csv).<br/>![ProjectAdd](/help/assets/icons/ProjectAdd.svg) **[!UICONTROL Create project]** to [create a new Workspace project](#create-project-from-data-views) for the data view. |
| **[!UICONTROL Connection]** | The name of the connection that is associated with the data view. |
| **[!UICONTROL Sandbox]** | The name of the sandbox that is associated with the data view. |
| **[!UICONTROL Owner]** | The owner of the data view. |
| **[!UICONTROL Data Insights Agent]** ![InfoOutline](/help/assets/icons/InfoOutline.svg) | Indicates whether the [Data Insights Agent](/help/data-analysis-ai.md) is **[!UICONTROL Enabled]** or **[!UICONTROL Disabled]** for the data view. <br/>Select ![InfoOutline](/help/assets/icons/InfoOutline.svg) to show a pop-up with **[!UICONTROL Data Insights Agent Status]** across your data views. <br/>![Data Insights Agent usage](/help/data-views/assets/data-views-dia-status.png) |
| **[!UICONTROL Integrations]** | List integrations with other solutions. For example: Adobe Audience Analysis, Content Analytics, Brand Concierge, Journey Optimizer, GenStudio, and Usage Analytics. |
| **[!UICONTROL Use in CJA]** | Indicate whether the data view is used in Customer Journey Analytics. This value is only **[!UICONTROL Off]** for data views that are automatically generated as part of the Adobe Journey Optimizer integration. |
| **[!UICONTROL Date created]** | The timestamp when the data view was created. |
| **[!UICONTROL Last modified]** | The timestamp when the data view was most recently modified. | 

To configure which columns to display in the table, select ![ColumnSetting](/help/assets/icons/ColumnSetting.svg). In the **[!UICONTROL Customize table]** dialog, select the columns to show. Then select **[!UICONTROL Apply]**.


## Search data views

You can quickly search for a data view using the Search ![Search](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) box.

## Filter data views

To apply a filter to the list of data views, select the ![Filter](/help/assets/icons/Filter.svg) icon, then select from the following filter options:

| Filter option | Description |
|---------|----------|
| **[!UICONTROL Connections]** | Only data views that are associated with the connections you select are displayed. |
| **[!UICONTROL Owner]** | Only data views owned by the people you select are displayed. |
| **[!UICONTROL Sandbox]** | Only data views available in the sandboxes you select are displayed. |
| **[!UICONTROL Integrations]** | Only data views with selected integrations are displayed. |
| **[!UICONTROL Use in CJA]** | Select **[!UICONTROL On]** to show only data views that are enabled for use with Customer Journey Analytics. Select **[!UICONTROL Off]** to show only data views that are not yet enabled for use with Customer Journey Analytics. |


## Create a data view

To [create a new data view](/help/data-views/create-dataview.md), select **[!UICONTROL Create new data view]**.


## Edit data views

If you want to [edit a data view](/help/data-views/create-dataview.md):

1. Select ![More](/help/assets/icons/More.svg) next to the data view name.
1. Select ![Edit](/help/assets/icons/Edit.svg) **[!UICONTROL Edit]** from the context menu.

Alternatively, you can:

1. Select the data view row.
1. Select ![Edit](/help/assets/icons/Edit.svg) **[!UICONTROL Edit]** from the blue action bar.


## Copy data views

If you want to copy a data view: 

1. Select ![More](/help/assets/icons/More.svg) next to the data view name.
1. Select ![Copy](/help/assets/icons/Copy.svg) **[!UICONTROL Copy]** from the context menu.

Alternatively, you can:

1. Select one or more data view rows.
1. Select ![Copy](/help/assets/icons/Copy.svg) **[!UICONTROL Copy]** from the blue action bar.

The data view is copied and added to the list with **[!UICONTROL (Copy)]** appended to the name.


## Delete data views

If you want to delete a data view:

1. Select ![More](/help/assets/icons/More.svg) next to the data view name.
1. Select ![Delete](/help/assets/icons/Delete.svg) **[!UICONTROL Delete]** from the context menu.

Alternatively, you can:

1. Select one or more data view rows.
1. Select ![Delete](/help/assets/icons/Delete.svg) **[!UICONTROL Delete]** from the blue action bar.

When you delete one or more data views, a **[!UICONTROL Delete data view]** panel indicates which projects are affected.

![Delete data view](/help/data-views/assets/delete-data-view.png)


* In ➊ **[!UICONTROL Confirmation]**, the implications of the deletion of the data views are shown.
* Select **[!UICONTROL Delete]** to delete the data views permanently. Select **[!UICONTROL Cancel]** to cancel.


## Export data views to CSV

You can export a data view to a CSV file.

1. Select ![More](/help/assets/icons/More.svg) next to the data view name.
1. Select ![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Export to CSV]** from the context menu.

Alternatively, you can:

1. Select one or more data view rows.
1. Select ![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Export to CSV]** from the blue action bar.

Details of the selected data views are exported to a CSV file named `Data views List (x).csv` in the Downloads folder of your browser.


## Create project from data views

You can create a Workspace project directly from the Data views interface. 

1. Select ![More](/help/assets/icons/More.svg) next to the data view name.
1. Select ![ProjectAdd](/help/assets/icons/ProjectAdd.svg) **[!UICONTROL Create project]** from the context menu.

Alternatively, you can:

1. Select a data view row.
1. Select ![ProjectAdd](/help/assets/icons/ProjectAdd.svg) **[!UICONTROL Create project]** from the blue action bar.


## Enable or disable data views for Data Insights Agent

You can enable or disable a data view for the [Data Insights Agent](/help/data-analysis-ai.md).

1. Select ![More](/help/assets/icons/More.svg) next to the data view name.
1. Select ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Enable for Data Insights Agent]** or ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) **[!UICONTROL Disable for Data Insights Agent]** from the context menu.

Alternatively, you can:

1. Select one or more data view rows that are either disabled or enabled for the Data Insights Agent.
1. Select ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Enable for Data Insights Agent]** or ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) **[!UICONTROL Disable for Data Insights Agent]** from the blue action bar.

