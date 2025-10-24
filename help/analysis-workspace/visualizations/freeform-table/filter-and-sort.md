---
description: Learn how to filter and sort freeform tables in Analysis Workspace.
title: Filter And Sort
feature: Visualizations
exl-id: 3af637ec-bb6c-49b7-a7b3-e1d310e71101
role: User
---
# Filter and sort

Freeform tables in Analysis Workspace are the foundation for interactive data analysis. As such, they can contain thousands of rows of information. Filtering and sorting the data can be a critical part of efficiently surfacing the most important information. 

<!--The following video covers filter and sort options in Analysis Workspace, in addition to pagination options:

>[!VIDEO](https://video.tv.adobe.com/v/23968)-->

## Filter tables

Filters in Analysis Workspace help you surface the most important information.

>[!NOTE]
>
> Only dynamic dimension items can be filtered as described in this section. Static dimension items cannot be filtered. For more information, see [Dynamic vs static dimension items in freeform tables](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md).

You can use several methods to filter rows from a freeform table.

* Exclude specific rows from a table
* Apply filters to a table 
* Use audience segments

Be sure to read how each method impacts [freeform table totals](/help/analysis-workspace/visualizations/freeform-table/workspace-totals.md).

### Exclude specific rows from a table

You can quickly exclude specific rows from the table without the need to use ![Filter](/help/assets/icons/Filter.svg)  **[!UICONTROL Filter]**. 

>[!NOTE]
>
>When you exclude rows as described in this section, an [!UICONTROL Always exclude items] rule is added automatically in the [!UICONTROL Advanced] filter dialog. You can view the applied rule by selecting the ![Filter](/help/assets/icons/Filter.svg) Filter icon, then [**[!UICONTROL Show advanced]**](#apply-a-simple-or-advanced-filter-to-a-table).

To exclude specific rows from a freeform table:

1. Hover over the row that you want to exclude, then select ![Close](/help/assets/icons/Close.svg). 

   Hold the ***shift*** to select a range of rows, or hold the ***cmd*** key (on Mac) or the ***ctrl*** key (on Windows) to select multiple rows.

<!--### Right-click > Delete selected rows

Note: this option does not seem to work. AN-338422

1. Select 1 or more rows. 
1. Right-click and select **[!UICONTROL Delete Selected Rows]**. 

   This action will remove the rows from the table and apply a table filter.-->


### Apply a simple or advanced filter to a table
 
 To filter data in freeform tables:
 
 1. Hover over the column that contains the data you want to filter. <!--only some types of columns show the filter... Which? Just Dimensions?-->
 
 1. Select  ![Filter](/help/assets/icons/Filter.svg) **Filter** when it appears.

    ![Freeform table highlighting the Filter icon.](assets/table-filter-icon.png)

    The following options are available in the **[!UICONTROL Search]** dialog:

    ![Filter simple](assets/filter-simple.png){width="500"}

    |Option | Function | 
    |---------|----------|
    | [!UICONTROL **Include "No value"**] | Select this option to show a **[!UICONTROL No value]** row in the table for data that has no value for the selected dimension. Unselect this option to hide the **[!UICONTROL No value]** row. |
    | [!UICONTROL **Search word or phrase**] | Specify a word or phrase that you want to filter by. Only rows that contain the word or exact phrase specified are shown. |
    

 1. (Optional) To filter by different criteria or by multiple criteria, select [!UICONTROL **Show advanced**]. 

    The following advanced filter options are available:

    ![Filter simple](assets/filter-advanced.png){width=500}

    |Option | Function | 
    |---------|----------|
    | [!UICONTROL **Include "No value"**] | Select this option to show a **[!UICONTROL No value]** row in the table for data that has no value for the selected dimension. Unselect this option to hide the **[!UICONTROL No value]** row. |
    | [!UICONTROL **Match**] | Choose [!UICONTROL **If all criteria are met**] to show only data that meets all the criteria that you specify. This option typically results in more refined data.<br/><br/>Choose [!UICONTROL **If any criteria are met**] to show data that meets any one of the filter criteria that you specify. This option typically results in less refined data.  |
    | [!UICONTROL **Criteria**] | Select from the following filter options:<br/><ul><li>[!UICONTROL **Contains the phrase**] (default): Only data that contain the exact phrase that you specify are included in the filtered results. Words must be in the order specified in the [!UICONTROL **Search word or phrase field**].</li><li>[!UICONTROL **Contains any term**]: Only data that contain one or more words from the phrase that you specify are included in the filtered results. </li><li>[!UICONTROL **Contains all terms**]: Only data that contain all words from the phrase that you specify are included in the filtered results. Words do not have to be in the order specified in the [!UICONTROL **Search word or phrase field**].</li><li>[!UICONTROL **Does not contain any term**]: Only data that contain none of the words from the phrase that you specify are included in the filtered results. </li><li>[!UICONTROL **Does not contain the phrase**]: Only data that does not contain the exact phrase that you specify are included in the filtered results. Words must be in the order specified in the [!UICONTROL **Search word or phrase field**].</li><li>[!UICONTROL **Equals**]: Only data that exactly matches the phrase that you specify is included in the filtered results. </li><li>[!UICONTROL **Does not equal**]: Only data that does not exactly match the phrase that you specify are included in the filtered results. </li><li>[!UICONTROL **Starts with**]: Only data that starts with the word or exact phrase that you specify are included in the filtered results. </li><li>[!UICONTROL **Ends with**]: Only data that ends with the word or exact phrase that you specify are included in the filtered results. </li></ul>Select ![Add](/help/assets/icons/Add.svg) [!UICONTROL **Add row**] to add multiple filter criteria. The option you select for [!UICONTROL **Match**] determines **[!UICONTROL If all criteria are met]** or **[!UICONTROL If any criteria are met]**. | 
    | [!UICONTROL **Always exclude items**] | Specify the name of any items that you want to exclude from the filtered data. |

 1. Select **[!UICONTROL Apply]** to filter the data. Select **[!UICONTROL Clear]** to clear all input. Select **[!UICONTROL Cancel]** to cancel and close the dialog. <br/>A colored ![Filter](/help/assets/icons/FilterColored.svg) **Filter** icon indicates and displays details when a filter is applied to the table. 

### Include filter criteria in trended data in sparklines and line visualizations {#include-filter-criteria}

Any search filter criteria applied to the table dimension to a freeform table is always included in sparklines. 

In addition to sparklines, you can configure filter criteria to be included in connected line visualizations. (By default, filter criteria is not included in line visualizations. Line visualizations display data for the row that is selected in the connected table. If no row is selected, data for the first dimension only of the connected table is shown.)

For more information about sparklines and line visualizations, see [View trended data for a freeform table](/help/analysis-workspace/visualizations/freeform-table/freeform-table-trended-data.md).

#### Configure line visualizations to include filter criteria

1. Select the sparkline in the metric column header. 

   When the sparkline cell is selected, it displays as dark gray. This indicates that filter criteria is included in the connected line visualization. The filter criteria is applied as a segment on the column. <!--show how to see it? Show what the segment looks like when it's applied? -->

   ![sparkline selected](assets/table-sparkline-selected.png)

#### Understand when column totals might be inaccurate

Column totals might not be exact in the following scenarios:

* When static components are used in the left column and [column totals are calculated as a sum of the rows](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)

  If row items contain overlapping data in this scenario, column totals will be inaccurate. 
  
  For example, if you add static segments to the left column, and then you add Users as a metric in the right column, some of those users might be part of more than one of the static segments. In this case, Workspace does not deduplicate the users for each static segment. This can result in a higher number of total users because some users might be counted more than once.  

* When using multi-valued dimensions

>[!NOTE]
>
>The sparkline and line chart still reflect the accurate totals in these scenarios.

### Use audience segments

See [Segmentation overview](/help/components/segments/seg-overview.md) for more details.

## Sort tables {#sort-tables}

You can sort the data of a freeform table by any columns in Analysis Workspace that are either a dimension or a metric. 

By default, dimensions are sorted in ascending order and metrics are sorted in descending order.

### Sort tables by a single column 

When you sort data for a single column as described in this section, any [advanced sorting](#sort-tables-by-multiple-columns-advanced-sorting) that is applied to the table is removed.

To sort data in tables by a single column:

1. Mouse over the header of the column you want to sort, then select the **Sort** icon ![Sort](/help/assets/icons/SortOrderDown.svg) when it appears.

   <!-- Add screenshot of sort drop-down -->

1. Select **[!UICONTROL Ascending]** or **[!UICONTROL Descending]**. 

   The sort icon remains visible when sorting is applied to the column. An arrow indicates how the data is sorted (![Sort](/help/assets/icons/SortOrderUp.svg) for ascending or ![Sort](/help/assets/icons/SortOrderDown.svg) for descending).

### Sort tables by multiple columns (Advanced sorting)

You can sort data for multiple columns. When you do, data is sorted according to the priority you assign to each column. 

#### Sort priority

When sorting multiple columns, the column with the primary priority decides the main order, the column with the secondary priority decides the order when rows have the same value in the primary column, the column with the tertiary priority decides the order when rows have the same value in the primary and secondary columns, and so forth.  

For example, consider a table with the following columns:

* Page URL (dimension)

* Organization name (dimension)

* Month (dimension)

* Event (metric)

You can assign a sort priority to each column, as follows:

| Column (component) name | Component type | Sort priority |
|---------|----------|---------|
| Page URL | Dimension | 1 |
| Organization name | Dimension | 2 |
| Month | Dimension | 3 |
| Event | Metric | 4 |

By assigning a sort priority to each column, you can control exactly how data is displayed in the table. In this example, information is sorted first by Page URL, then by organization, then my month, and finally by Event. 

<!--update screenshot-->

![multi-sort example](assets/freeform-sort-advanced.png)

#### Apply sorting to multiple columns

To sort data in tables by multiple columns:

1. Mouse over the header of any column that you want to sort, then select the **Sort** icon ![Sort](/help/assets/icons/SortOrderDown.svg) when it appears.

   <!-- Add screenshot of sort drop-down -->

1. Select **[!UICONTROL Advanced sorting]**. 

1. In the Advanced sorting dialog, do any of the following:

   * Add columns that aren't yet being sorted by selecting the **[!UICONTROL Add sort column]** button.

   * Remove columns that you no longer want to sort by selecting the **Remove** icon ![Remove](/help/assets/icons/Close.svg).  

   * Drag columns higher or lower in the list to adjust the sort priority. 
   
     For more information, see [Sort priority](#sort-priority).
   
   * Change the sort value by selecting **[!UICONTROL Ascending]** or **[!UICONTROL Descending]** in the drop-down menu. 

   * Select a different column by selecting the column name drop-down menu. 

1. Select **[!UICONTROL Apply]**.

The sort icon remains visible when sorting is applied to a column. An arrow indicates how the data is sorted (![Sort](/help/assets/icons/SortOrderUp.svg) for ascending or ![Sort](/help/assets/icons/SortOrderDown.svg) for descending). 


