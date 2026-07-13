---
description: Learn how to use row settings and how row settings vary depending on which component you have dragged into a freeform table in Analysis Workspace.
title: Row Settings
feature: Visualizations
exl-id: a9438d83-498d-4b22-9e5e-c357bd3a2680
role: User
TQID: https://experienceleague.adobe.com/qQKmobJ4J1RPezRG-hk38l7JNioIshzjMaKXWVoUWsM
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
  - id: cb6c7d24-631f-46e5-9e39-3a2705f73962
    internal-label: Calendar
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
    internal-label: Dimensions
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
---
# Row settings

Row settings vary depending on which component you have dragged into the table. To access table row settings, select ![Setting](/help/assets/icons/Setting.svg) **[!UICONTROL Settings]** next to a dimension, segment, metric, time period, or a breakdown within each of these objects.

![Freeform Table highilighting the Settings icon for Metrics](assets/row-settings.png)

| Setting | Description |
| --- | --- |
| **[!UICONTROL Breakdown by position]** | By default, this setting is disabled and breakdowns are fixed to static row items. For example, imagine you breakdown the top 3 Page dimension items (Homepage, Search Results, Checkout) by Marketing Channel. Then, you leave the project and return two weeks later. Upon opening the project again, the top 3 pages have changed, and now Homepage, Search Results and Checkout are the top 4-6 pages instead. By default, your Marketing Channel breakdowns still appear under Homepage, Search Results and Checkout, even though they are now in rows 4-6. <br> In contrast, **Breakdown by position** always breaks down the top 3 items, regardless of what they are. Referring back to the example, when you re-open your project, the Marketing Channel breakdowns are tied to the top 3 pages in the table. And not to Homepage, Search Results and Checkout, which are now in rows 4-6. |
| **[!UICONTROL Percentages]** | **Calculate percentages by column** (default): the percentages visible in a cells are calculated based on the column total. <br>**Calculate percentages by row**: the percentages in cells are calculated across the row, as opposed to down the column, with Grand total as the denominator. This calculation is useful for trending percentages. |
| **[!UICONTROL Column totals]** | These settings are available only for [static rows](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md). <br> **Show as sum of current rows** shows a client-side sum of the rows in the table, which means the total does *not* de-duplicate metrics like visits or persons. <br> **Show grand total** shows a server-side sum, which means the total of de-duplicated metrics. |

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Row and column settings in a Freeform table](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/row-and-column-settings-in-freeform-tables){target="_blank"} for a demo video.

{{videoaa}}

>[!ENDSHADEBOX]

## Change row count

To change the number of rows that are displayed:

1. Click the number next to **[!UICONTROL Rows]** at the top of the first column of the table.

   ![Freeform table showing the drop-down menu of for the number of rows displayed. 400 rows is selected.](assets/change-row-count.gif)

1. From the drop-down menu, select the number of rows you would like the table to display.


## Context-menu

The following context menu options are available when selecting the dimension header.

| Option | Description |
| --- | --- |
| **[!UICONTROL Copy selection to clipboard]** | Copy the selection from the visualization onto the clipboard. |
| **[!UICONTROL Download items as CSV (*dimension name*)]** | Immediately download the dimension items (to a maximum of 50,000) of the visualization to your local device. A maximum of 50,000 dimension items for the selected dimension. |
| **[!UICONTROL Download selection as CSV]** | Immediately download the dimension items of the visualization to your local device. |
| **[!UICONTROL Create hyperlink for all dimension items]** | Create hyperlinks for all the dimension items. See [Hyperlinks for dimensions in a freeform table](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Edit hyperlink for all dimension items]** | Edit hyperlinks for all the dimension items. See [Hyperlinks for dimensions in a freeform table](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Remove hyperlink for all dimension items]** | Remove hyperlinks for all the dimension items. See [Hyperlinks for dimensions in a freeform table](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Delete]** | Deletes the dimension from the table. |
| **[!UICONTROL Visualize]** | Visualize the dimension using any of the available visualizations. |
| **[!UICONTROL Display only selected rows]** | Display only the selected items in the visualization. |
| **[!UICONTROL Create annotation from selection]** | Open up the **[!UICONTROL Annotation details]** to add an annotation. |


The following additional context menu options are available when selecting one or more dimension items (first column) or one or more individual cells in the freeform table.

| Option | Description |
| --- | --- |
| **[!UICONTROL Copy selection to clipboard]** | Copy the information in the selected cells of the freeform table. | 
| **[!UICONTROL Download items as CSV (*dimension name*)]** | Immediately download the dimension items (to a maximum of 50,000) of the visualization to your local device. A maximum of 50,000 dimension items for the selected dimension. |
| **[!UICONTROL Create hyperlink]** | Create a hyperlink for the item. See [Hyperlinks for dimensions in a freeform table](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Edit hyperlink]** | Edit a hyperlink for the item. See [Hyperlinks for dimensions in a freeform table](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Remove hyperlink]** | Remove a hyperlink for the item. See [Hyperlinks for dimensions in a freeform table](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Download selection as CSV]** | Immediately download the dimension items of the visualization to your local device. |
| **[!UICONTROL Delete selected]** | Delete selected rows. |
| **[!UICONTROL Create alert from selection]** | Open up the [Alert builder](/help/components/c-intelligent-alerts/alert-builder.md) to build an alert from the selection. |
| **[!UICONTROL Breakdown]** | Break down the dimension item. Select from the list of **[!UICONTROL Dimensions]**, **[!UICONTROL Metrics]**, **[!UICONTROL Segments]** or **[!UICONTROL Date ranges]**. Alternative search for a component, using *Search*. |
| **[!UICONTROL Visualize]** | Visualize the selection using any of the available visualizations. |
| **[!UICONTROL Trend selection]** | Create a trended line chart visualization for the selection. |
| **[!UICONTROL Display only selected rows]** | Display only the selected rows in the visualization. |
| **[!UICONTROL Display all rows]** | Display all rows in the visualization. |
| **[!UICONTROL Rename selected row]** | Rename the selected row. Enter a **[!UICONTROL Name]** in the **[!UICONTROL Rename selected row]** dialog. Select **[!UICONTROL OK]** to confirm or **[!UICONTROL Cancel]** to cancel. Once a row in a freeform table is renamed, the dimension name in the header column is appended with **[!UICONTROL (modified)]** and a ![Gear](/help/assets/icons/Gear.svg) icon is available to reset renamed rows in the dimension header column. See [Classify example](#classify-example) |
| **[!UICONTROL Combine selected rows]** | Combine the selected rows. Enter a **[!UICONTROL Name]** in the **[!UICONTROL Combine selected rows]** dialog. Select **[!UICONTROL OK]** to confirm or **[!UICONTROL Cancel]** to cancel. Once rows in a freeform table are combined, the dimension namein the header column is appended with **[!UICONTROL (modified)]** and a ![Gear](/help/assets/icons/Gear.svg) icon is available to reset renamed rows in the dimension header column. See [Classify example](#classify-example). |
| **[!UICONTROL Create as derived field]** | *You must be a Customer Journey Analytics product administrator to see this context menu option.*<br/>Available on any selected row of a freeform table which is modified as the result of renaming or combining rows. When selected, the [Derived field interface](/help/data-views/derived-fields/derived-fields.md#create-a-derived-field) opens with the modifications you have made to the freeform table already prefilled. See [Classify example](#classify-example). |
| **[!UICONTROL Create annotation from selection]** | Open up the [Annotation builder](/help/components/annotations/create-annotations.md#annotation-builder) to build an annotation for the selection. | 
| **[!UICONTROL Create segment from selection]** | Open up the [Segment builder](/help/components/segments/seg-builder.md) to build a segment from the selection. |
| **[!UICONTROL Create audience from selection]** | Open up the [Audience builder](/help/components/audiences/publish.md#audience-builder) to build an audience from the selection. |

The following additional context menu options are available when selecting a metric column header.

| Option | Description |
|---|---|
| **[!UICONTROL Create metric from selection]** | Create a new metric from the selected metric. Metric can be Mean, Media, Column max, Column min, Column sum. You can also select Open in calculated metric builder to create a calculated metric. |
| **[!UICONTROL Add time period column]** | Add a time period column. You are offered several options, where the calendar range of the panel determines the *date range*: <ul><li>**[!UICONTROL Prior *date range* to this date range]**</li><li>**[!UICONTROL These *date range* to this date range]**.</li><li>**[!UICONTROL Custom date range to this date range]**. Opens up the **[!UICONTROL Date range builder]** to specify the date range.</li></ul>See [Date comparison](/help/components/date-ranges/time-comparison.md) for more information. |
| **[!UICONTROL Compare time periods]** | Adds compare time period columns. Only available when the dimension is not based on time. You are offered several options determines the *date range*: <ul><li>**[!UICONTROL Prior *date range* to this date range]**</li><li>**[!UICONTROL Custom date range to this date range]**. Opens up the **[!UICONTROL Date range builder]** to specify the date range.</li></ul>See [Date comparison](/help/components/date-ranges/time-comparison.md) for more information. |
| **[!UICONTROL Modify attribution models]** | Modify the attribution model for the column. |
| **[!UICONTROL Compare attribution model]** | Specify a new attibution model and compare it to the attribution model for the selected column. A new column is added with the new attribution model metrics. Also, a Percent change column is added for comparison. |
| **[!UICONTROL Reset column widths]** | Reset the column widths to the default width. |
| **[!UICONTROL Create annotation from selection]** | Open up the **[!UICONTROL Annotation details]** to add an annotation. |
| **[!UICONTROL Create segment from selection]** | Open up the **[!UICONTROL Segment builder]** to build a segment from the selection. |
| **[!UICONTROL Create audience from selection]** | Open up the **[!UICONTROL Create audience]** dialog to build an audience from the selection. |


## Change row height

You can set the [view density](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/build-workspace-project/view-density) of a project to **[!UICONTROL Compact]**, **[!UICONTROL Comfortable]**, and **[!UICONTROL Expanded]**.


## Classify example

This example illustrated how to use the **[!UICONTROL Rename selected row]**, **[!UICONTROL Combine selected rows]**, and **[!UICONTROL Create as derived field]** context menu options. And how to reset the modified freeform table.

* Rename **[!UICONTROL No value]** row to **[!UICONTROL Other]**.

  1. Select **[!UICONTROL Rename selected row]** from the context menu in the selected **[!UICONTROL No value]** row.
   
     ![Select Rename selected row context menu option](assets/context-rename.png)

  1. In the **[!UICONTROL Rename selected row]** dialog: 
     
     ![Rename selected row dialog](assets/dialog-rename.png)

     1. Enter <code>Other</code> for **[!UICONTROL Name]**.
     1. Select **[!UICONTROL OK]**.

* Combine **[!UICONTROL Men]** and **[!UICONTROL Women]** rows to one **[!UICONTROL Adults]** row.

  1. Select **[!UICONTROL Men]** and **[!UICONTROL Women]** row.
  1. Select **[!UICONTROL Combine selected rows]** from the context menu from any of the selected rows.

     ![Select Combine selected rows menu option](assets/context-combine.png)

  1. In the **[!UICONTROL Combine selected rows]** dialog: 
      
     ![Combine selected row dialog](assets/dialog-combine.png)
 
     1. Enter <code>Adults</code> for **[!UICONTROL Name]**.
     1. Select **[!UICONTROL OK]**.

* Create a derived field from the modifications in the freeform table.

  1. Select **[!UICONTROL Create as derived field]** from the context menu for any selected row in the modified table.

     ![Select Create as derived field menu option](assets/context-derived.png)

  1. Inspect, optionally modify, and save the definition of the derived field based on all modifications made in the table.

     ![Create derived field dialog](assets/dialog-derived.png)

* Reset the freeform table to the state before modifications.

  1. Select ![Gear](/help/assets/icons/Gear.svg) next to **[!UICONTROL _dimension name_ (modified)]**.
  1. Select **[!UICONTROL Reset renamed rows]** from the **[!UICONTROL Rows renamed]** popup.

     ![Reset freeform table](assets/popup-reset.png)

