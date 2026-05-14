---
title: Dynamic And Static Dimension Items
description: Learn how to use dynamic versus static dimension items in freeform tables in Analysis Workspace.
feature: Visualizations
exl-id: 7806f535-15c7-40f4-955a-724d9752969d
role: User
TQID: https://experienceleague.adobe.com/q9X-MNr4r3Xrs16gAgH6-F3yrRDJP73xfXdd8BcFg84
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: bcaa1b08-8269-4ff3-a0c2-f599783b6107
    internal-label: Filters
  - id: d3c978ee-1ff0-4475-968a-721e2dd99ef1
    internal-label: Freeform tables
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
    internal-label: Dimensions
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
---
# Dynamic and static dimension items

In Freeform tables, the rows and columns can contain various component values. These values can be dynamic (change over time) or static (do not change over time), depending on the analysis that you want to build.

## Dynamic dimension items

Dynamic dimension items change over time and are dependent on the metric being sorted by in the freeform table. Dynamic dimension items are preferred when you want to analyze the top items for a given time period.

When you drop a dimension into a freeform table, dynamic rows are returned. Dynamic rows represent the top items that correspond to the dimension for a given metric and time period. You can also drop a dimension into freeform table columns and the dimension automatically expands into the top 5 dimension items.

For example, when you drag the Browser Type dimension into the table, the top Browser Type dimension items (e.g. Microsoft, Apple, Google, etc.) dynamically return to the table rows. If dropped into a column, the top 5 Browser Type dimension items dynamically return.

Dynamic dimension items have the row filter option ![Filter](/help/assets/icons/Filter.svg) and a ![Close](/help/assets/icons/Close.svg), and do **not** have a lock ![LockClosed](/help/assets/icons/LockClosed.svg) present. <!--do they have the lock icon? --> When you click ![Close](/help/assets/icons/Close.svg) next to a dynamic dimension item, a filter is automatically applied. For more information about applying filters to tables, see [Filter and sort tables](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).


![A Freeform Table highlighting the filter icon.](assets/dynamic-items.png)

## Static dimension items

Static dimension items do not change with time; they are fixed components that are always returned in a freeform table. Static dimension items are preferred when you want to always analyze the same item, whether it be specific campaigns or specific days in the week.

Any time you manually select and drop specific component values (dimension, metric, segment, date range) into a table, the result is a static list of rows or columns. 

For example, when you drag over specific Browser Type items such as Microsoft and Apple, those 2 specific items always get pulled into the table. 

Static dimension items can also be created if you choose to select **[!UICONTROL Display only selected rows]** from the context menu for selected rows.

Static dimension items do **not** have the row filter option. Instead, a ![LockClosed](/help/assets/icons/LockClosed.svg) and ![Close](/help/assets/icons/Close.svg) are present on each item. Select ![Close](/help/assets/icons/Close.svg) to remove that dimension item from the table.

![A Freeform Table showing the Browser Type and the Microsoft row with a lock icon note: This dimension item is static and will not change with time.](assets/static-items.png)

## Mixed dimension items

Dimension items from different dimensions can be added to the same table. The row header say **[!UICONTROL Mixed Dimensions]** in these cases. These dimension items are static. For example, adding specific dimension items from the Browser Group dimension and other dimension items from the Browser Name dimension.

![A Freeform Table highlighting the Mixed Dimensions column.](assets/mixed-dimensions.png)

## Freeform total rows

Dynamic and static rows behave differently in the freeform total row. By default:

* Dynamic rows are summed server-side and de-duplicate metrics such as sessions or persons.
* Static rows are summed client-side and do **not** de-duplicate metrics. To calculate the total row server-side, change the Row setting to **Show grand total**. [Learn more](/help/analysis-workspace/visualizations/freeform-table/workspace-totals.md)
