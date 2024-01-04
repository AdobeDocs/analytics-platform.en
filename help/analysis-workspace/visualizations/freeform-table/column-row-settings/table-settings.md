---
description: Row settings vary depending on which component you have dragged into the table.
title: Row settings
feature: Visualizations
exl-id: a9438d83-498d-4b22-9e5e-c357bd3a2680
role: User
---
# Row settings

View a video on row and column settings here:

>[!VIDEO](https://video.tv.adobe.com/v/40382/?quality=12)

Row settings vary depending on which component you have dragged into the table. To access table row settings, click the [!UICONTROL Settings] icon next to a dimension, filter, metric, time period, or a breakdown within each of these:

![Freeform Table highilighting the Settings icon for Metrics](assets/row-settings.png)

| Setting | Description |
| --- | --- |
| Align dates | This is a table-level setting that aligns dates from each column to all start on the same row. Date aligning is enabled by default when a time dimension is used in the rows of the table, and different date ranges are applied in the columns. For example, in a daily table with October and September applied to the columns, the left column starts with October 1 and the right column starts with September 1.  |
| Breakdown by position | By default, this setting is disabled and breakdowns are fixed to static row items. For example, let's say you breakdown the top 3 Page dimension items (Homepage, Search Results, Checkout) by Marketing Channel. Then, you leave the project and return two weeks later. Upon opening the project again, the top 3 pages have changed, and now Homepage, Search Results and Checkout are the top 4-6 pages instead. By default, your Marketing Channel breakdowns will still appear under Homepage, Search Results and Checkout, even though they are now in rows 4-6. <br> In contrast, **Breakdown by position** always breaks down the top 3 items, regardless of what they are. Referring back to our example, when you re-open your project, the Marketing Channel breakdowns will be tied to the top 3 pages in the table, not Homepage, Search Results and Checkout which are now in rows 4-6. |
| Percentages | **Calculate percentages by column** is the default setting; the percentages visible in a column are calculated based on the column total. <br>**Calculate percentages by row** forces the Freeform table to calculate the cell percentages across the row as opposed to down the column, with Grand total as the denominator. This is especially useful for trending percentages. This setting is enabled by default when using the Visualize icon. |
| Column Totals | These settings are available only for [static rows](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md). <br> **Show as sum of current rows** shows a client-side sum of the rows in the table which means the total will *not* de-duplicate metrics like visits or persons. <br> **Show grand total** shows a server-side sum which means the total will de-duplicate metrics. |

## Change row count

To change the number of rows that are displayed:

1. Click the number next to [!UICONTROL Rows] at the tops of the table.

   ![Freeform table showing the drop-down list of for the number of rows displayed. 400 rows is selected.](assets/row-number.png)

1. From the drop-down list, select the number of rows you would like the table to display.