---
description: A panel that shows the next or previous dimension items for a specific dimension.
title: Next or previous item panel
feature: Panels
role: User, Admin
exl-id: a5f6ce97-6720-4129-9ece-e2e834289d45
---
# Next or previous item panel {#next-or-previous-item-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_nextorpreviousitem_button"
>title="Next or previous item"
>abstract="Create a panel to understand the previous dimensions people come from or next dimension people go to."

<!-- markdownlint-disable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_nextorpreviousitem_panel"
>title="Nest or previous item"
>abstract="Analyze what are the most common places visitors previously came from or go to next.<br/><br/>**Dimension**: Select a dimension. For example **Page**.<br/>**Dimension item**: Select a specific dimension item. For example **Homepage**.<br/>**Direction**: Select **Next** to see the dimension items immediately next following your selected dimension item. Select **Previous** to see the dimension items leading up to your selected dimension item.<br/>**Container**: Select **Session** to see the next/previous dimension items within the same session, or select **Person** to see the next/previous dimension item for the same person."

<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

*This article documents the Next or previous item panel in **Customer Journey Analytics**. See [Next or previous item panel](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/panels/next-previous) for the **Adobe Analytics** version of this article.*

>[!ENDSHADEBOX]

The **[!UICONTROL Next or previous item]** panel contains a number of tables and visualizations to identify the next or previous dimension item for a specific dimension. For example, you might want to explore which pages customers went to most often after they visited the Home page.

## Use

To use a **[!UICONTROL Next or previous item]** panel:

1. Create a **[!UICONTROL Next or previous item]** panel. For information about how to create a panel, see [Create a panel](panels.md#create-a-panel).  

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
