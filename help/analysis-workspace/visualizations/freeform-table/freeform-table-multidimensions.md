---
title: Include multiple dimensions in a freeform table
description: Learn how to include multiple dimensions in a freeform table
feature: Visualizations
role: User
hide: yes
hidefromtoc: yes
---
# Include multiple dimensions in a freeform table

{{release-limited-testing}}

You can include up to 5 dimension columns in a freeform table, allowing you to view multiple dimension items side by side. Each row of dimension items act as a single concatenated item. 

You can sort dimension columns (together with metric columns) for a more complete and custom analysis. 

## Multiple dimension columns and breakdowns

Analysis Workspace provides the following ways to add multiple dimensions within a freeform table: 

* Include multiple dimension columns (as described in this article)

* [Add breakdowns](/help/components/dimensions/t-breakdown-fa.md)

Both of these methods allow you to analyze dimensions against other dimensions. However, there are important differences, and both methods can be used in the same table for an even deeper analysis.

Multiple dimension columns allow you to:

* Correlate rows of data across multiple dimensions and metrics.

* Show data only when it applies to each dimension column in the table. To accomplish this, use the column filter to deselect the **[!UICONTROL Include "No value"]** setting on each dimension column. 

  For more information, see [Filter and sort tables](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md). 

* Sort data by multiple dimension and metric columns.

  For more information, see [Filter and sort tables](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md). 

Breakdowns allow you to:

* Show dimension items for only one 

* Show the top dimension items for a single

## Add dimension columns

You can add dimension columns one at a time or in bulk.

1. In Analysis Workspace, create a freeform table. 

   For more information, see [Add visualizations to a panel](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel) in [Visualizations overview](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md).

1. Add dimensions to the freeform table. You can add multiple dimensions at once or you can add dimensions one at a time. 

   * Select up to 5 dimensions in the component menu and drag them into the freeform table. Dimensions are added to the table from left to right in the order you select them.

     To select multiple dimensions, hold the ***Command*** key (on Mac) or the ***Ctrl*** key (on Windows).

     ![Drag multiple dimensions](assets/dimensions-add-multiple.png)

   * Drag dimensions one at a time into the freeform table. Place additional dimension columns to the left or right of existing dimension columns in the table. A blue vertical **[!UICONTROL Add]** line displays where the new column will be created. 

     ![Drag individual dimensions](assets/dimensions-add-individually.png)

## Filter and sort table columns

You can sort the data of a freeform table by any columns in Analysis Workspace that are either a dimension or a metric. You can sort data by a single column or by multiple columns. For more information, see [Filter and sort tables](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).

## Add breakdowns to a table with multiple dimension columns

When you add a breakdown to a table that has multiple dimension columns, the breakdown spans all dimension items on the row where it's added. 

You can add a breakdown as described in [Break down dimensions](/help/components/dimensions/t-breakdown-fa.md).

## Unsupported dimensions

The following dimensions are not supported, and Analysis Workspace prompts you to remove them from your table when performing a full-table export:

