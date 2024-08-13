---
description: A panel that shows the next or previous dimension items for a specific dimension.
title: Next or previous item panel
feature: Panels
role: User, Admin

---
# Next or previous item panel

This panel contains a number of tables and visualizations to identify the next or previous dimension item for a specific dimension. For example, you might want to explore which pages customers went to most often after they visited the Home page.

## Use

To use a [!UICONTROL Next or previous item] panel:

1. Create a [!UICONTROL Next or previous item] panel. For information about how to create a panel, see [Create a panel](panels.md#create-a-panel).  

1. Specify the [input](#panel-input) for the panel.

1. Observe the [output](#panel-output) for the panel.

### Panel input

You can configure the [!UICONTROL Next or previous item] panel using these input settings:

![Next or previous item panel](assets/next-or-previous-item.png)

| Input | Description |
| --- | --- |
| **[!UICONTROL Dimension]** | Select the dimension for which you want to explore next or previous items. |
| **[!UICONTROL Dimension item]** | Select the specific dimension item at the center of your next / previous inquiry. |
| **[!UICONTROL Direction]** | Specify whether you are looking for the [!UICONTROL Next] or the [!UICONTROL Previous] dimension item. |
| **[!UICONTROL Container]** | Select the container, [!UICONTROL Session] or [!UICONTROL Person] (default), to determine the scope of your inquiry. |

{style="table-layout:auto"}

Select **[!UICONTROL Build]** to build the panel.

### Panel output

The [!UICONTROL Next or previous item] panel returns a rich set of data and visualizations to help you better understand what occurrences follow or precede specific dimension items.


![Next/Previous panel output](assets/next-or-previous-item-output.png)


| Visualization | Description |
| --- | --- |
| **[!UICONTROL Horizontal bar]** | Lists the next (or previous) items based on the dimension item that you select. Hovering over an individual bar highlights the corresponding item in the Freeform table. |
| **[!UICONTROL Summary number]** | High-level summary number of all next or previous dimension item occurrences for the current month (so far.) |
| **[!UICONTROL Freeform table]** | Lists the next (or previous) items based on the dimension item that you select, in a table format. For example, which were the most popular pages (by occurrences) that people went to after (or before) the home page or the workspace page. |

{style="table-layout:auto"}


>[!MORELIKETHIS]
>
>[Create a panel](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>