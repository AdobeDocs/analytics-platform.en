---
description: Visually represent your data in Analysis Workspace.
keywords: Analysis Workspace
title: Visualizations overview
feature: Visualizations
exl-id: ca9e0561-7a54-487a-9fdc-3bcf34f9bdb1
role: User
---
# Visualizations overview

Workspace offers a number of visualizations that let you generate visual representations of your data, such as bar charts, donut charts, histograms, line charts, maps, scatterplots, and others. Most visualization types will be familiar to you if you use Customer Journey Analytics. However, Analysis Workspace provides visualization settings and many new or unique visualizations types with interactive capabilities.

## Visualization types

The following visualization types are available in Analysis Workspace:

| Visualization name | Description |
| --- | --- | 
| [Area](/help/analysis-workspace/visualizations/area.md)<p>![Area icon](assets/Smock_GraphArea_18_N.svg)</p>  | Like a line graph, but with a colored area below the line. Use an area graph when you have multiple metrics and want to visualize the area expressed by the intersection of two or more metrics. | Answers questions like: <ul><li> |
| [Bar](/help/analysis-workspace/visualizations/bar.md) <p>![Bar icon](assets/Smock_GraphBarVertical_18_N.svg)</p> | Shows vertical bars representing various values across one or more metrics. |
| [Bullet graph](/help/analysis-workspace/visualizations/bullet-graph.md) <p>![Bullet icon](assets/Smock_GraphBullet_18_N.svg)</p> | Shows how a value you are interested in compares to or measures against other performance ranges (goals). |
| [Cohort table](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md)<p>![Cohort table icon](assets/Smock_TextNumbered_18_N.svg)</p> | A *`cohort`* is a group of people sharing common characteristics over a specified period. Cohort Analysis is useful for retention, churn or latency analysis. |
| [Donut](/help/analysis-workspace/visualizations/donut.md) <p>![Donut icon](assets/Smock_GraphDonut_18_N.svg)</p> |  Similar to a pie chart, this visualization shows data as parts or filters of a whole. |
| [Fallout](/help/analysis-workspace/visualizations/fallout/fallout-flow.md)<p>![Fallout icon](assets/Smock_ConversionFunnel_18_N.svg)</p> | Fallout reports show where persons left (fell out) and continued through (fell through) a predefined sequence of pages. Can be set to eventual or exact sequences |
| [Flow](/help/analysis-workspace/visualizations/c-flow/flow.md)<p>![Flow icon](assets/flow-icon.png)</p> | Shows exact customer paths through your websites and apps. | 
| [Freeform table](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)<p>![Freeform table icon](assets/Smock_ViewTable_18_N.svg)</p> | A Freeform table is not merely a data table, but also an interactive visualization. It is the foundation for data analysis in Workspace.|
| [Histogram](/help/analysis-workspace/visualizations/histogram.md)<p>![Histogram icon](assets/Smock_GraphHistogram_18_N.svg)</p> | A histogram buckets persons, visits or events into buckets based on a metric volume. |
| [Horizontal bar](/help/analysis-workspace/visualizations/horizontal-bar.md)<p>![Horizontal bar icon](assets//Smock_GraphBarHorizontal_18_N.svg)</p> | Shows horizontal bars representing various values across one or more metrics. |
| [Line](/help/analysis-workspace/visualizations/line.md)<p>![Line icon](assets/Smock_GraphTrend_18_N.svg)</p>| Represents metrics using a line in order to show how values change over a period of time. A line chart uses time along the x-axis. |
| [Scatterplot](/help/analysis-workspace/visualizations/scatterplot.md) <p>![Scatterplot icon](assets/Smock_GraphScatter_18_N.svg)</p> | Shows the relationship between dimension items and up to three metrics. |
| [Summary number](/help/analysis-workspace/visualizations/summary-number-change.md)<p>![Summary number icon](assets/summary-number-icon.png)</p> | Shows the selected cell as 1 large number. |
| [Summary change](/help/analysis-workspace/visualizations/summary-number-change.md)<p>![Summary change icon](assets/summary-change-icon.png)</p> | Shows the change between the selected cells as 1 large number/percent. |
| [Text](/help/analysis-workspace/visualizations/text.md)<p>![Scatterplot icon](assets/Smock_Text_18_N.svg)</p> | Lets you add user-defined text to your Workspace. Helpful for adding additional context to your analysis and insights, in addition to leveraging panel/visualization descriptions |
| [Treemap](/help/analysis-workspace/visualizations/treemap.md)<p>![Treemap icon](assets/Smock_GraphTree_18_N.svg)</p> | Displays hierarchical (tree-structured) data as a set of nested rectangles. |
| [Venn](/help/analysis-workspace/visualizations/venn.md)<p>![Venn icon](assets/venn-icon.png)</p> | Uses circles to depict the metric overlap of up to 3 filters. |

## Add visualizations to a panel

1. Open the Analysis Workspace project where you want to add a visualization.

1. Use any of the following methods to add the visualization:

   * In the left rail, select the **Visualizations** icon <!-- add icon -->, then drag a visualization to the panel where you want to add it. 

     ![Visualizations panel](assets/viz-rail.png)

   * On the panel where you want to add the visualization, select the **Plus** icon, then choose the icon that represents the visualization that you want to add. Hover over the icon for each visualization to see its name.

     ![Button for adding a visualization](assets/visualization-add-to-panel.png)

   * Add a [blank panel](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/blank-panel.html), then choose the visualization that you want to add.

     ![Blank panel](assets/blank_panel.png)

   * Right-click an existing panel in your Analysis Workspace project, then select [!UICONTROL **Duplicate visualization**] or [!UICONTROL **Copy visualization**].

## Customize visualization settings

You can customize visualization settings for an individual visualization, or for all visualizations that you create. 

### Customize visualization settings for a single visualization

To access [!UICONTROL Visualization Settings] for an individual visualization:

1. In Analysis Workspace, hover over the visualization whose settings you want to customize.

1. Click the gear icon.

   Each type of visualization has unique settings that you can customize. For information about available settings, see [Settings](#settings).

### Customize visualization settings for all visualizations you create

You can customize settings for all visualizations that you create. For more information, see [User preferences](/help/analysis-workspace/user-preferences.md).

## Settings {#settings}

Each visualization has its own settings that you can manage. To access [!UICONTROL Visualization Settings], click the [!UICONTROL Visualization Settings] gear icon.

![Visualizations Settings showing the setting options described in the next section.](assets/settings.png)

| Setting | Description |
| --- | --- |
| Visualization Type | Change the type of visual used to depict the data. |
| Granularity | For trended visualizations, you can change the time granularity (day, week, month, etc.) from this drop-down list. This change also applies to the data source table. |
| Percentages | Displays values in percentages. |
| 100% Stacked | This setting on area stacked, bar stacked or horizontal bar stacked visualizations turns the chart into a "100% stacked" visualization. Example: ![A bar chart showing the Stacked 100% option view.](assets/stacked_100_percent.png) |
| Legend Visible | Lets you hide the detailed legend text for the Summary Number/Summary Change visualization. |
| Limit Max Items | Lets you limit the number of items that a visualization displays. |
| Anchor Y Axis at Zero | If all the values plotted on the chart are considerably above zero, the chart default will make the bottom of the y-axis NON-ZERO. If you check this box, the y-axis will be forced to zero (and it will re-draw the chart). |
| Normalization | Forces metrics to equal proportions. This is helpful when plotted metrics are of very different magnitudes. |
| Display Dual Axis | Only applies if you have two metrics - you can have a y-axis on the left (for one metric) and on the right (for the other metric). This is helpful when plotted metrics are of very different magnitudes. |
| Show Anomalies | Enhances line graphs and freeform tables by displaying anomaly detection. Anomaly detection in line visualizations includes an expected value (dashed line) and an expected range (shaded band). |

## Legend {#legend}

A visualization legend helps you to relate date in a source table to plotted series in the visualization. The legend is interactive - you can click a legend item to show/hide a series in the visualization. This is helpful if you want to simplify the data being visualized. 

Additionally, you can rename legend labels to help you make visuals more consumable. Note: legend editing does **not** apply to: Treemap, Bullet, Summary Change/Number, Text, Freeform, Histogram, Cohort or Flow visualizations.

To edit a legend label:

1. Right-click one of the legend labels.
1. Click **[!UICONTROL Edit Label]**.

   ![A legend label and the Edit label option.](assets/edit-label.png)

1. Enter the new label text.
1. Press **[!UICONTROL Enter]** to save.

## Right-click menu {#right-click}

Additional functionality for a visualization is available by right-clicking on the visualization header. Settings will vary by visualization. Some of the settings available are:

![Additional visualization settings with the right-click options displayed. Options are described in the next section.](assets/right-click.png)

| Setting | Description |
| --- | --- |
| Insert Copied Panel/Visualization|Lets you paste ("insert") a copied panel or visualization to another place within the project, or into a completely different project. |
| Copy Visualization | Lets you right-click and copy a visualization, so that you can insert it to another place within the project, or into a completely different project. |
| [Download project data](/help/analysis-workspace/export/download-send.md) | Download up to 50,000 dimension items for the selected dimension as a CSV. |
| [Download project data](/help/analysis-workspace/export/download-send.md) | Download visualization data source as a CSV. |
| Duplicate Visualization | Makes an exact duplicate of the current visualization, which you can then modify. |
| Edit Description | Add (or edit) a text description for the visualization. |
| Get Visualization Link | Lets you direct someone to a specific visualization within a project. When the link is clicked, the recipient will be required to login before being directed to the exact visualization linked to. |
| Start Over | (Works for Flow, Venn, Histogram) Deletes the configuration for the current visualization so you can re-configure it from scratch. |

## Create Visual icon {#quick-viz}

If you are not sure which visualization to pick, click the **[!UICONTROL Create Visual]** icon in any table row (available on hover). This is the fastest way to add a visualization. Clicking it prompts Analysis Workspace to take an educated guess at which visualization would best fit your data. For example, if you have 1 row selected, it will create a trended line graph. If you have 3 filter rows selected, it will create a Venn diagram. 

![Quick visualization](assets/quick-viz.png)
