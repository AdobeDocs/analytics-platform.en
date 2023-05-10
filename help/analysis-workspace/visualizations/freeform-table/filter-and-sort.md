---
description: Documentation describing how to filter and sort tables in Analysis Workspace.
title: Filter and sort tables
feature: Visualizations
exl-id: 3af637ec-bb6c-49b7-a7b3-e1d310e71101
---
# Filter and sort tables

Freeform tables in Analysis Workspace are the foundation for interactive data analysis. As such, they can contain thousands of rows of information. Filtering and sorting the data can be a critical part of efficiently surfacing the most important information. 

<!--The following video covers filter and sort options in Analysis Workspace, in addition to pagination options:

>[!VIDEO](https://video.tv.adobe.com/v/23968)-->

## Filter tables {#section_36E92E31442B4EBCB052073590C1F025}

 Filters in Analysis Workspace help you surface the most important information.

>[!NOTE]
>
> Only dynamic dimension items can be filtered as described in this section. Static dimension items cannot be filtered. For more information, see [Dynamic vs static dimension items in freeform tables](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md).

### Quickly exclude specific rows from a table

You can quickly exclude specific rows from the table without needing to open the Filter dialog. 

>[!NOTE]
>
>When you exclude rows as described in this section, a [!UICONTROL **Does not equal**] rule is automatically applied in the [**[!UICONTROL Advanced filtering]**](#apply-a-simple-or-advanced-filter) dialog.

To quickly exclude specific rows from a Freeform table:

1. Hover over the row you want to exclude, then select the x icon. 

   Hold the Shift key to select a range rows, or hold the Command key (on Mac) or the Ctrl key (on Windows) to select multiple rows.

### Apply a simple or advanced filter to a table
 
 To filter data in Freeform tables:
 
 1. Hover over the column that contains the data you want to filter. <!--only some types of columns show the filter... Which? Just Dimensions?-->
 
 1. Select the **Filter** icon when it appears.

    ![Filter icon in a table](assets/table-filter-icon.png)

    The following options are available:

    |Option | Function | 
    |---------|----------|
    | [!UICONTROL **Search word or phrase**] | Specify a word or phrase that you want to filter by. Only rows that contain the word or exact phrase specified are shown. |
    | [!UICONTROL **Include unspecified (none)**] | Select this option to show data in the table that does not fall into any of the dimensions of the table. <!--what is this?--> |

 1. (Optional) To filter by different criteria or by multiple criteria, select [!UICONTROL **Advanced filtering**]. 

    The following options are available

    |Option | Function | 
    |---------|----------|
    | [!UICONTROL **Include unspecified (none)**] | Select this option to show data in the table that does not fall into any of the dimensions of the table. <!--what is this?--> |
    | [!UICONTROL **Match**] | <p>Choose [!UICONTROL **If all criteria are met**] to show only data that meets all the criteria that you specify. This option typically results in more refined data.</p> <p>Choose [!UICONTROL **If any criteria are met**] to show data that meets any one of the filter criteria that you specify. This option typically results in less refined data.</p>  |
    | [!UICONTROL **Criteria**] | <p>Select from the following filter options:</p><p>(Select [!UICONTROL **Add row**] to add multiple filter criteria. The option you select in the [!UICONTROL **Match**] section determines whether all or any of the criteria that you add must be met.)</p><ul><li><p>[!UICONTROL **Contains the phrase**]: Only data that contain the exact phrase that you specify are included in the filtered results. Words must be in the order specified in the [!UICONTROL **Search word or phrase field**].<p>This is the default setting when doing a simple search.</p></p></li><li><p>[!UICONTROL **Contains any term**]: Only data that contain one or more words from the phrase that you specify are included in the filtered results. </p></li><li><p>[!UICONTROL **Contains all terms**]: Only data that contain all words from the phrase that you specify are included in the filtered results. Words do not have to be in the order specified in the [!UICONTROL **Search word or phrase field**].</p></li><li><p>[!UICONTROL **Does not contain any term**]: Only data that contain none of the words from the phrase that you specify are included in the filtered results. </p></li><li><p>[!UICONTROL **Does not contain the phrase**]: Only data that does not contain the exact phrase that you specify are included in the filtered results. Words must be in the order specified in the [!UICONTROL **Search word or phrase field**].</p></li><li><p>[!UICONTROL **Equals**]: Only data that exactly matches the phrase that you specify are included in the filtered results. </p></li><li><p>[!UICONTROL **Does not equal**]: Only data that does not exactly match the phrase that you specify are included in the filtered results. </p></li><li><p>[!UICONTROL **Starts with**]: Only data that starts with the word or exact phrase that you specify are included in the filtered results. </p></li><li><p>[!UICONTROL **Ends with**]: Only data that ends with the word or exact phrase that you specify are included in the filtered results. </p></li></ul>| 
    | [!UICONTROL **Always exclude items**] | Specify the name of any items that you want to exclude from the filtered data. |

 1. Select [!UICONTROL **Apply**] to filter the data.

    The **Filter** icon ![Blue filter icon filtered table](assets/table-filter-blue-icon.png) turns blue when a filter is applied to the table. 

## Sort tables

You can sort the data of a Freeform table by any column in Analysis Workspace that is either a Dimension or a Metric. 

A down arrow icon ![Down arrow icon sorted table column](assets/table-sort-arrow-icon.png) is visible in the header of the column that data is currently being sorted by. 

1. In any Freeform table in Analysis Workspace, click the arrow next to the name of the Dimension or Metric.

   Consider the following when sorting:

   * The down-arrow sorts in descending order and the up-arrow (default) in ascending order.
   * You can sort Dimensions alphabetically or numerically. For example, you may have numbered steps in a workflow and may want to sort by the step number. You might sort a date-related dimension by date. Or you could sort data sources alphabetically, as in the following image.

   ![](assets/sort-dimensions.png)


