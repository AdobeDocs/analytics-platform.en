---
description: Learn how totals in freeform tables in Analysis Workspace are calculated.
title: Totals
feature: Visualizations
exl-id: ba14b88c-44c2-45f6-b68f-f5c1263a89dd
role: User
---
# Totals {#workspace-totals}

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_grandtotal"
>title="Grand Total"
>abstract="Grand total is not supported for tables or breakdowns with static rows."


In Freeform tables, a total row appears at each breakdown level and can show two totals:

![Freeform Table highlighting the grand total and the table total.](assets/total-row.png)

* **[!UICONTROL Table total]** ➊ - This total is typically equal to or a subset of the [!UICONTROL Grand total]. The total reflects any table segments applied within the freeform table, including the [!UICONTROL Include None] option.
* **[!UICONTROL Grand total]** (**[!UICONTROL out of]** *number*) ➋ - This total represents all events that have been collected. When a segment is applied either at the panel level or within the freeform table, this total adjusts to reflect all events that match the segment criteria.




## Display totals

Under ![Setting](/help/assets/icons/Setting.svg) **[!UICONTROL Column settings]**, there are options to **[!UICONTROL Show totals]** and **[!UICONTROL Show grand total]**. If these settings are unchecked, totals are removed from the table, which may be desired in cases where totals don't make sense.


[Static row](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md) totals behave differently, and are controlled using ![Setting](/help/assets/icons/Setting.svg) **[!UICONTROL Row Settings]**.

| Option | Description |
|---|---|
| **[!UICONTROL Show sum of current rows as the total]** | Show a client-side sum of the rows in the table. This total does **not** de-duplicate metrics like sessions or persons. |
| **[!UICONTROL Show grand total]** | Show a server-side sum. This total de-duplicate metrics like sessions or persons. |

See [Dynamic vs static dimension items in freeform tables](column-row-settings/manual-vs-dynamic-rows.md).


## Frequently asked questions

|Questions|Answer|
|---|---|
| Which *total* are the gray column percentages based on? | This *total* depends on the **[!UICONTROL Percentages]** setting selection under **[!UICONTROL Row Settings]**:<ul><li>Calculate percentages by column - This setting is the default. Percentages are based on the Table total.</li><li>Calculate percentages by row - Percentages are based on the Grand total.</li></ul>|
|How does the **[!UICONTROL Include "No value"]** setting impact totals?|If the **[!UICONTROL Include "No value"]** setting is unchecked, the **[!UICONTROL No value]** row is removed from the table, the Table total, and carries through to any calculated metrics that use [*Total* metric types](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md).|
|When custom table segments are applied to a freeform table, do all of my calculated metrics and conditional formatting account for the segment?|Not currently. **[!UICONTROL Include "No value"]** is account for, but custom table segments do not impact the following:<ul><li>The column max / min range that conditional formatting uses looks across all data.</li><li>Calculated metrics that leverage **[!UICONTROL Grand total]** metric types.</li><li>Calculated metrics with functions that calculate across rows in a freeform table: Column Sum, Column max, Column min, Count, Mean, Median, Percentile, Quartile, Row Count, Standard Deviation, Variance, Cumulative, Cumulative Average, Regression variants, T-Score, T-Test, Z-Score, and Z-Test.</li></ul>|
|In Calculated Metrics, what does the **[!UICONTROL Grand total]** metric type reflect?|**[!UICONTROL Grand total]** continues to refer to the **[!UICONTROL Grand total]**, and does not reflect segments applied to a table or the **[!UICONTROL Table total]**.|
|What total is shown when data is either copied and pasted from a freeform table or downloaded via CSV?|The total row reflects the **[!UICONTROL Table total]** only and respects the column **[!UICONTROL Show totals]** setting.|
