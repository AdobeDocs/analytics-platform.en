---
description: Use the trending topics visualization to explore trending topics in conversations.
title: Trending Topics
feature: Visualizations
role: User
---

# Trending topics

>[!CONTEXTUALHELP]
>id="workspace_trendingtopics_button"
>title="Trending topics"
>abstract="..."

>[!CONTEXTUALHELP]
>id="workspace_trendingtopics_panel"
>title="Trending topics"
>abstract="..."

The ![Feed](/help/assets/icons/Feed.svg) **[!UICONTROL Trending topics]** visualization allows you to explore and analyze the trending topics as part of Conversation insights.

You can search for specific topics and compare the number and percentage for each topics at each level with other data ranges.



## Create and configure

To create and configure a Trending topics visualization:

1. Add a ![Feed](/help/assets/icons/Feed.svg) **[!UICONTROL Trending topics]** visualization. See [Add a visualization to a panel](../freeform-analysis-visualizations.md#add-visualizations-to-a-panel).

1. In the **[!UICONTROL Trending topics]** visualization configuration:
   
   1. Select a **[!UICONTROL Ranking metric]**. For example: **[!UICONTROL Conversations]**.
   1. Optionally, select **[!UICONTROL Set attribution]**, and select **[!UICONTROL Model]**, **[!UICONTROL Container]**, and **[!UICONTROL Lookback window]**.
   1. Select a level for **[!UICONTROL Limit subtopic levels]**. Default is **[!UICONTROL Level 5]**. 

      >[!NOTE]
      >
      >The **[!UICONTROL Limit subtopic level]** defines the maximum number of levels to drill down for topics in the visualization. If no more topics are available at a level within that defined maximum number, ![DataUnavailable](/help/assets/icons/DataUnavailable.svg) **[!UICONTROL No topics found]** is displayed.

1. Select **[!UICONTROL Build]** to build the visualization. Select **[!UICONTROL Reset]** to reset the configuration values to defaults.

To reconfigure the Trending topics visualization, select ![Edit](/help/assets/icons/Edit.svg) next to **[!UICONTROL Ranking metric: _ranking metric_ | Subtopic levels: _x_]**.

## Use

To use the visualization:

* To drill and see trending subtopics for a topic at a lower level, select a topic at a specific level. 

* To compare topics against another date range, select a date range from Compare to. To use a custom date range: 
  * Select Custom date range from the dropdown menu and in the New date range dialog define and save a custom date range.
  * Select that custom date range.
  
* To show a line graph for the current selection of topics, drop a [Line](/help/analysis-workspace/visualizations/line.md) visualization on the **[!UICONTROL Trending topics]** visualization. The **[!UICONTROL Line]** visualization is automatically linked to the **[!UICONTROL Trending topics]** visualization.

## Settings 

The following specific [visualization settings](freeform-analysis-visualizations.md#settings), are available.

| Setting | Description |
|---|---|
| **[!UICONTROL Display actual value]** | Displays the actual value for a topic. |
| **[!UICONTROL Display percentage]** | Displays the precentage for a topi. |



