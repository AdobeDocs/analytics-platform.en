---
title: How to create a data block using Report Builder in Customer Journey Analytics
description: Describes how to create a data block.
role: User
feature: Report Builder
type: Documentation
exl-id: 46382621-d5e1-41d6-865c-782ec28a21fa
solution: Customer Journey Analytics
---
# Create a Data Block

A *data block* is the table of data created by a single data request. A Report Builder workbook can contain multiple data blocks. When you create a data block, first configure the data block and then build the data block.

## Configure the data block

Configure the initial data block parameters for the Data block location, Data views, and a Date range.

1. Select ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Create]**.

    ![Screenshot showing the Create data block option.](./assets/create-datablock.png)

1. Set the **[!UICONTROL Data block location]**.

    The data block location option defines the worksheet location where report builder adds the data to your worksheet.

    To specify the data block location, select a single cell in the worksheet or enter a cell address such as `a3`, `\\\$a3`, `a\\\$3` or `sheet1!a2`. The cell specified will be the upper-left corner of the data block when the data is retrieved.

    Use ![DataBlockSelector](/help/assets/icons/DataBlockSelector.svg) to pick a Data block location from the current selected cell in the sheet.

1. Choose the **[!UICONTROL Data views]**.

    The Data views option allows you to choose a data view from a drop-down menu or to reference a data view from a cell location.

    Select ![DataViewSelector](/help/assets/icons/DataViewSelector.svg) to create a data view from a cell.

1. Set the **[!UICONTROL Date range]**.

    The Date range option allows you to choose a date range. Date ranges may be fixed or rolling. For information about date range options, see [Select a Date Range](select-date-range.md).

    Select **[!UICONTROL Calendar]** to pick a data range using ![Calendar](/help/assets/icons/Calendar.svg) or enter a date range manually. Optionally, you can pick a preset drom the Search Presets drop-down menu.

    Select **[!UICONTROL From Cell]** to define a start and end data based on a cell in the current sheet.

1. Select **Next**.

    ![Screenshot showing the date range option and the active Next button.](./assets/choose_date_data_view3.png)

    After you configure the data block, you can select dimensions, metrics, and segments to build your data block. The Dimensions, Metrics, and Segments tabs are displayed above the Table builder pane.

## Build the data block

To build the data block, select report components, and then customize the layout.

1. Add Dimensions, Metrics, and Segments.

    Scroll the component lists or use the **search** field to locate components. Drag and drop components to the Table pane or double-click a component name in the list to automatically add the component to the Table pane.

    Double-click a component to add the component to a default section of the table.

    - Dimension components are added to the Row section or to the Column section if you have a dimension already in the columns.
    - Date components are added to the Column section.
    - Segment components are added to the Segments section.

### Start date as a Dimension

Set the Start date as a dimension to clearly identify the start date of your data block. This is helpful if you have a regularly scheduled report that has a rolling date range or if you have an unconventional date range and you need to be clear of the start date.

![Screenshot showing the Start date in the list of dimensions.](./assets/start-date-dimension.png)

1. Arrange the items in the Table pane to customize the layout of your data block.

    Drag and drop components in the Table pane to reorder components or right-click a component name and select from the options menu.

    When you add components to the table, a preview of the data block is displayed at the Data block location in the worksheet. The layout of the data block preview automatically updates as you add, move, or remove items in the table.

    ![Screenshot showing the added components and updated worksheet.](./assets/image10.png)

### Display or hide row and column headers

1. Select the **[!UICONTROL Table]** ![Setting](/help/assets/icons/Setting.svg)settings icon.

    ![Screenshot showing the Table settings option.](./assets/table-settings.png)

1. Check or uncheck the option to Display row and column headers. The headers are displayed by default.

### Hide or show dimension labels and metric headers

Select the ellipsis icon on either the dimensions or the column headers to display the settings.

![The ellipsis icon in the Row section.](./assets/row-heading.png)

1. Select ![VisibilityOff](/help/assets/icons/VisibilityOff.svg) **[!UICONTROL Hide]** or ![Visibility](/help/assets/icons/Visibility.svg) **[!UICONTROL Show]** to toggle the dimension labels or column headers. All labels are displayed by default.

1. Select **[!UICONTROL Finish]**.


A processing message is displayed while the analytics data is retrieved.

![The processing message.](./assets/image11.png)

Report Builder retrieves the data and displays the completed data block in the worksheet.

![The completed data block.](./assets/image12.png)
