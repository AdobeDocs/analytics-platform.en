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

>[!CONTEXTUALHELP]
>id="workspace_nextorpreviousitem_panel"
>title="Next or previous item"
>abstract="Analyze what are the most common places visitors previously came from or go to next. Specify dimension, dimension item, the direction, and the container to use for the visualization."



<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

_This article documents the Next or previous item panel in_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**_.<br/>_See [Next or previous item panel](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/panels/next-previous) for the_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics** version of this article._

>[!ENDSHADEBOX]

The **[!UICONTROL Next or previous item]** panel contains a number of tables and visualizations to identify the next or previous dimension item for a specific dimension. For example, you might want to explore which pages customers went to most often after they visited the Home page.

## Use {#use}

>[!CONTEXTUALHELP]
>id="workspace_nextorpreviousitem_container"
>title="Container"
>abstract="Select the container to determine the scope of your inquiry."

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
| **[!UICONTROL Container]** | Select the container, **[!UICONTROL Global Account]** [!BADGE B2B Edition]{type=Informative}, **[!UICONTROL Account]** [!BADGE B2B Edition]{type=Informative}, **[!UICONTROL Buying Group]** [!BADGE B2B Edition]{type=Informative}, **[!UICONTROL Opportunity]** [!BADGE B2B Edition]{type=Informative}, **[!UICONTROL Session]** or **[!UICONTROL Person]**, to determine the scope of your inquiry. |

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
