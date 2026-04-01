---
description: Lean how to configure and specify the touchpoints to create a multi-dimensional fallout sequence.
title: Configure A Fallout Visualization
feature: Visualizations
exl-id: 3d888673-d7b1-45ef-bd3a-97b98466fb0e
role: User
---
# Configure a fallout visualization {#configure-fallout-visualization}


You can specify **touchpoints** to create a multi-dimensional fallout sequence. In many cases, a touchpoint is a page on your site. However, touchpoints are not limited to pages. For example, you can add events, such as units, as well as unique persons and return visits. You can also add dimensions, such as a category, browser type, or internal search term.

You can even add segments within a touchpoint. For example, you might want to compare segments, such as iOS and Android users. Drag the desired segments to the top of the fallout and information about those segments is added to the fallout report. If you want to show only those segments, you can remove the All People baseline.

Fallout visualizations have no limitation on the number of touchpoints you can add or the number of components you can use.

You can do pathing on dimensions, metrics, and segments. For example, suppose that someone is looking at `shoes, shirt` on one page, and on the next page they're looking at `shirt, socks`. The next product flow report from shoes will be shirt and socks, NOT shirt.

## Use

1. Add a ![ConversionFunnel](/help/assets/icons/ConversionFunnel.svg) **[!UICONTROL Fallout]** visualization. See [Add a visualization to a panel](../freeform-analysis-visualizations.md#add-visualizations-to-a-panel).

1. Drag a component to the **[!UICONTROL Add touchpoint]** drop-down menu.

   >[!TIP]
   >
   >You can add a single page to the fallout report, rather than the entire dimension. Click the right arrow ![ChevronRight](/help/assets/icons/ChevronRight.svg) on the page dimension to pick a specific page, such as **[!UICONTROL home]**, to add to the Fallout report.

   ![The home page from the Home page dimension dragged to the Add Touchpoint field.](assets/fallout-drag.png)

1. Continue adding touchpoints until your sequence is complete.

   The circled numbers in the gray portion of the bar show the fallout between touchpoints (not the overall fallout to that point). The circled numbers in the green portion of the bar show the successful fall through from the previous touchpoint to the current touchpoint.

   ![Fallout visualization](assets/fallout-visualization.png)

   When adding touchpoints, you can do any of the following:

   * Combine multiple components by dragging one or more additional components onto a single touchpoint.

     >[!NOTE]
     >
     >Multiple segments are joined with AND, but multiple items such as dimension items and metrics are joined with OR.

   * Reorder touchpoints by dragging them to a different level within the fallout hierarchy.
   
   * Combine two touchpoints by dragging one touchpoint onto another. Drop the touchpoint when you see the word **[!UICONTROL Combine]**.

   * Constrain individual touchpoints to the next event (as opposed to *eventually*) within the path. Beneath each touchpoint, there is a selector with the options **[!UICONTROL Eventual path]** and **[!UICONTROL Next event]**, as shown here:

     | Option | Description |
     |---|---|
     | **[!UICONTROL Eventual path]** (default) | Persons are counted that will *eventually* land on the next page in the path, but not necessarily on the next event. |
     | **[!UICONTROL Next event]** | Persons are counted that will land on the next page in the path on the very next event. |

   * Hover over a touchpoint to see the fallout and other information about that level. Information includes the touchpoint's name, the person count, and success rate. You can also compare the success rate to other touchpoints.

## Settings {#settings}

>[!CONTEXTUALHELP]
>id="workspace_fallout_container"
>title="Fallout container"
>abstract="Select a container to analyze pathing. This selection helps you to understand engagement and constraints the analysis to the selected container."

As part of the visualization, specific settings are available.

| Fallout container | Description |
|--- |--- |
| **[!UICONTROL Session]** or **[!UICONTROL Person]**|  Switch between [!UICONTROL Session] and [!UICONTROL Person] to analyze person pathing. The default is [!UICONTROL Person]. These settings help you understand person engagement at the person level (across sessions), or constrain the analysis to a single session. |


## Context menu

As part of the visualization, specific context menu options are available. 

### Access the context menu

You can access the context menu in either of the following ways:

* Hover over a touchpoint in the visualization, then select **[!UICONTROL Click to analyze]**. 

  ![Access context menu from hover](assets/fallout-tooltip-analyze.png)

* Right-click a touchpoint in the visualization.

  ![Fallout options](assets/fallout-options.png)

### Context menu options

The following context menu options are available:

| Option | Description |
|--- |--- |
|**[!UICONTROL Trend touchpoint]**|See trend data for a touchpoint in a line graph, with some pre-built anomaly detection data.|
|**[!UICONTROL Trend touchpoint (%)]**|Trends the total fallout percentage.|
|**[!UICONTROL Trend all touchpoints (%)]**|Trends all the touchpoint percentages in the fallout (except **[!UICONTROL All People]**, if it's included), on the same chart.|
|**[!UICONTROL Break down fallthrough at this touchpoint]**|View what persons did between two touchpoints (this touchpoint and the next touchpoint) if they continued to the next touchpoint. This creates a freeform table showing your dimensions. You can replace dimensions and other elements of the table. For example, a table that is labeled **[!UICONTROL Fallthrough: All People > Page equals any of home]** and contains **[!UICONTROL Page]** as the dimension and **[!UICONTROL People]** segmented by the [project-only quick segment](/help/components/segments/seg-quick.md) **[!UICONTROL Fallthrough: All People > Page equals any of home]** as the metric. Inspect the segment to understand how the fallthrough segment is determined.|
|**[!UICONTROL Break down fallout at this touchpoint]**| View what people who did not make it through the funnel did immediately after the selected step. This creates a freeform table showing your dimensions. You can replace dimensions and other elements of the table. For example, a table that is labeled **[!UICONTROL Fallout: People > Page equals any of home]** and contains **[!UICONTROL Page]** as the dimension and **[!UICONTROL People]** segmented by the [project-only quick segment](/help/components/segments/seg-quick.md) **[!UICONTROL Fallthrough: All Visitors > Page equals any of home]** segment as the metric. Inspect the segment to understand how the fallout segment is determined.|
|**[!UICONTROL Create segment from touchpoint]**|Create a new segment from the selected touchpoint.|

>[!MORELIKETHIS]
>
>[Add a visualization to a panel](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Visualization settings](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Visualization context menu](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>

