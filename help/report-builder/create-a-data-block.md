---
title: Create A Data Block In Report Builder
description: Learn how to create a data block.
role: User
feature: Report Builder
type: Documentation
exl-id: 46382621-d5e1-41d6-865c-782ec28a21fa
solution: Customer Journey Analytics
TQID: https://experienceleague.adobe.com/MdIYz3KjKm6YUCTNT31LGIvEvfezHyOpemy7xg1FCvE
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
    internal-label: Segments, Segments (CJA)
  - id: bcaa1b08-8269-4ff3-a0c2-f599783b6107
    internal-label: Filters
  - id: cb6c7d24-631f-46e5-9e39-3a2705f73962
    internal-label: Calendar
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
    internal-label: Dimensions
  - id: f2ef16dc-055a-4bb7-baa5-7039653f3966
    internal-label: Report Builder
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
---
# Create a data block

A *data block* is the table of data created by a single data request. A Report Builder workbook can contain multiple data blocks. When you create a data block, first configure the data block and then build the data block.

## Configure the data block

Configure the initial data block parameters for the Data block location, Data views, and a Date range.

1. Select ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Create]**.

   ![Screenshot showing the Create data block option](./assets/create-data-block.png){zoomable="yes"}


1. Set the **[!UICONTROL Data block location]**.

    The data block location option defines the worksheet location where Report Builder adds the data to your worksheet.

    To specify the data block location, select a single cell in the worksheet or enter a cell address, such as `a3`, `\\\$a3`, `a\\\$3` or `sheet1!a2`. The cell specified becomes the upper-left corner of the data block when the data is retrieved.

    Use ![DataBlockSelector](/help/assets/icons/DataBlockSelector.svg) to pick a data block location from the current selected cell in the sheet.

1. Choose the **[!UICONTROL Data views]**.

    The Data views option allows you to choose a data view from a drop-down menu or to reference a data view from a cell location.

    Select ![DataViewSelector](/help/assets/icons/DataViewSelector.svg) to create a data view from a cell.

1. Set the **[!UICONTROL Date range]**.

    The **[!UICONTROL Date range]** option allows you to choose a date range. Date ranges may be fixed or rolling. 

    Select **[!UICONTROL Calendar]** to pick a data range using ![Calendar](/help/assets/icons/Calendar.svg) or enter a date range manually. Optionally, you can pick a preset from the **[!UICONTROL _Search Presets_]** drop-down menu.

    Select **[!UICONTROL From cell]** to define a start and end data based on a cell in the current sheet.

    For information about date range options, see [Select a date range](select-date-range.md).

1. Select **[!UICONTROL Next]**.

    ![Screenshot showing the date range option and the active Next button.](./assets/choose_date_data_view3.png)

    After you configure the data block, you can select dimensions, metrics, and segments to build your data block. The **[!UICONTROL Dimensions]**, **[!UICONTROL Metrics]**, and **[!UICONTROL Segments]** tabs are displayed above the **[!UICONTROL Table]** pane.

## Build the data block

To build the data block, select report components, and then customize the layout.

1. Add **[!UICONTROL Dimensions]**, **[!UICONTROL Metrics]**, and **[!UICONTROL Segments]** components.

    Scroll the component lists or use the ![Search](/help/assets/icons/Search.svg) **[!UICONTROL _Search components_]** field to locate components. Drag and drop components to the [!UICONTROL Table] pane or Double select a component name in the list to add the component to the [!UICONTROL Table] pane.

    Double select a component to add the component to a default section of the table.

    - Dimension components are added to the ![TableSelectRow](/help/assets/icons/TableSelectRow.svg) **[!UICONTROL Row]** section or to the ![TableSelectColumn](/help/assets/icons/TableSelectColumn.svg) **[!UICONTROL Column]** section if you have a dimension already in the columns.
    - Date components are added to the ![TableSelectColumn](/help/assets/icons/TableSelectColumn.svg) **[!UICONTROL Column]** section.
    - Segment components are added to the ![Segmentation](/help/assets/icons/Segmentation.svg) **[!UICONTROL Segments]** section.
    - Metrics components are added to the ![Event](/help/assets/icons/Event.svg) **[!UICONTROL Values]** section.

1. Arrange the items in the Table pane to customize the layout of your data block.

    Drag and drop components within each list in the Table pane to reorder components or select ![MoreSmall](/help/assets/icons/MoreSmall.svg) and select ![ArrowUp](/help/assets/icons/ArrowUp.svg) Move up, ![ArrowDown](/help/assets/icons/ArrowDown.svg) Move down, and more to move components within a list.

    When you add components to the table, a preview of the data block is displayed at the Data block location in the worksheet. The layout of the data block preview automatically updates as you add, move, or remove items in the table.

    ![Screenshot showing the added components and updated worksheet.](./assets/image10.png)


1. Optionally set the **[!UICONTROL Start date]** as a dimension to identify the start date of your data block. Adding the start data as a dimension is helpful if you have a regularly scheduled report that has a rolling date range. Or if you have an unconventional date range and you need to be explicit about the start date.

   ![Screenshot showing the Start date in the list of dimensions.](./assets/start-date-dimension.png)

1. Optionally, display or hide row and column headers. To do so:

   1. Select the **[!UICONTROL Table]** ![Setting](/help/assets/icons/Setting.svg)settings icon.

      ![Screenshot showing the Table settings option.](./assets/table-settings.png)

   1. Check or uncheck the option to **[!UICONTROL Display row and column headers]**. The headers are displayed by default.

1. Optionally, you can also hide or show dimension labels and metric headers. To do so:

   1. Select ![MoreSmall](/help/assets/icons/MoreSmall.svg) on the dimension label or the column header to display the context menu.

      ![The ellipsis icon in the Row section.](./assets/row-heading.png)

   1. Select ![VisibilityOff](/help/assets/icons/VisibilityOff.svg) **[!UICONTROL Hide]** or ![Visibility](/help/assets/icons/Visibility.svg) **[!UICONTROL Show]** to toggle the dimension label or column header. All labels are displayed by default.

1. Select **[!UICONTROL Finish]** to finish the configuration of your data block.

1. A processing message **[!UICONTROL #BUSY]** is displayed while the analytics data is retrieved.

   ![The processing message.](./assets/image11.png)

1. Report Builder retrieves the data and displays the completed data block in the worksheet.

   ![The completed data block.](./assets/image12.png)


>[!MORELIKETHIS]
>
>[Select a data view](select-data-view.md)
>[Select a date range](select-date-range.md)
>[Filter dimensions](filter-dimensions.md)
>[Work with segments](work-with-filters.md)
>
