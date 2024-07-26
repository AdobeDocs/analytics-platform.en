---
description: Visually represent your data in Analysis Workspace.
keywords: Analysis Workspace
title: Visualizations overview
feature: Visualizations
exl-id: ca9e0561-7a54-487a-9fdc-3bcf34f9bdb1
role: User
---
# Visualizations overview

Workspace offers a number of visualizations that let you generate visual representations of your data. Such as bar charts, donut charts, histograms, line charts, maps, scatterplots, and others. 

## Types

The following visualization types are available in Analysis Workspace:

| Visualization name<br/>Visualization icon | Description |
| --- | --- | 
| [Area](/help/analysis-workspace/visualizations/area.md)<p>![GraphArea](/help/assets/icons/GraphArea.svg)</p>  | An area graph visualization. Like a line graph, but with a colored area below the line. Use an area graph when you have multiple metrics and want to visualize the area expressed by the intersection of two or more metrics. |
| [Bar](/help/analysis-workspace/visualizations/bar.md) <p>![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg)</p> | A bar graph visualization with vertical bars representing various values across one or more metrics. |
| [Bullet graph](/help/analysis-workspace/visualizations/bullet-graph.md) <p>![GraphBullet](/help/assets/icons/GraphBullet.svg)</p> | A bullet graph visualization, which shows how a value you are interested in compares to or measures against other performance ranges (goals). |
| [Cohort table](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md)<p>![TextNumbered](/help/assets/icons/TextNumbered.svg)</p> | A cohort visualization is a group of people sharing common characteristics over a specified period. A cohort table is useful for retention, churn or latency analysis. |
| [Donut](/help/analysis-workspace/visualizations/donut.md) <p>![GraphDonut](/help/assets/icons/GraphDonut.svg)</p> | Similar to a pie chart, a donut visualization shows data as parts or filters of a whole. |
| [Fallout](/help/analysis-workspace/visualizations/fallout/fallout-flow.md)<p>![ConversionFunnel](/help/assets/icons/ConversionFunnel.svg)</p> | A fallout visualization shows where persons left (fell out) and continued through (fell through) a predefined sequence of pages. |
| [Flow](/help/analysis-workspace/visualizations/c-flow/flow.md)<p>![GraphPathing](/help/assets/icons/GraphPathing.svg)</p> | A flow visualization shows exact customer paths through your websites and apps. | 
| [Freeform table](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)<p>![ViewTable](/help/assets/icons/ViewTable.svg)</p> | A freeform table visualization is an interactive visualization. The freeform table visualization is the foundation for data analysis in Workspace.|
| [Histogram](/help/analysis-workspace/visualizations/histogram.md)<p>![GraphHistogram](/help/assets/icons/GraphHistogram.svg)</p> | A histogram visualization buckets persons, visits or events into buckets based on a metric volume. |
| [Horizontal bar](/help/analysis-workspace/visualizations/horizontal-bar.md)<p>![GraphBarHorizontal](/help/assets/icons/GraphBarHorizontal.svg)</p> | A horizontal bar visualization shows horizontal bars representing various values across one or more metrics. |
| [Line](/help/analysis-workspace/visualizations/line.md)<p>![GraphTrend](/help/assets/icons/GraphTrend.svg)</p>| A line visualization represents metrics using a line to show how values change over a period of time. A line chart uses time along the x-axis. |
| [Scatterplot](/help/analysis-workspace/visualizations/scatterplot.md) <p>![GraphScatter](/help/assets/icons/GraphScatter.svg)</p> | A scatterplot visualization shows the relationship between dimension items and up to three metrics. |
| [Summary number](/help/analysis-workspace/visualizations/summary-number-change.md)<p>![123](/help/assets/icons/123.svg)</p> | A summary number visualization shows the selected cell as one large number. |
| [Summary change](/help/analysis-workspace/visualizations/summary-number-change.md)<p>![MoveUpDown](/help/assets/icons/MoveUpDown.svg)</p> | A summary change visualization shows the change between the selected cells as one large number or percentage. |
| [Text](/help/analysis-workspace/visualizations/text.md)<p>![Text](/help/assets/icons/Text.svg)</p> | A text visualization lets you add user-defined text to your Workspace. Helpful for adding additional context to your analysis and insights, in addition to leveraging panel/visualization descriptions |
| [Treemap](/help/analysis-workspace/visualizations/treemap.md)<p>![ModernGridView](/help/assets/icons/ModernGridView.svg)</p> | A treemap visualization displays hierarchical (tree-structured) data as a set of nested rectangles. |
| [Venn](/help/analysis-workspace/visualizations/venn.md)<p>![Type](/help/assets/icons/TwoDots.svg)</p> | A venn visualization uses circles to depict the metric overlap of up to 3 filters. |

## Add visualizations to a panel

1. Open the Analysis Workspace project where you want to add a visualization.

1. Use any of the following methods to add the visualization:

   ![Add visualization](assets/add-visualization.png)

   * In the left rail, select ![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg) **Visualizations**, then drag a visualization to the panel where you want to add the visualization to. 

   * On the panel where you want to add the visualization, select ![AddCircle](/help/assets/icons/AddCircle.svg), then choose the icon that represents the visualization that you want to add. Hover over the icon for each visualization to see the name.

   * Add a [blank panel](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/panels/blank-panel), then select the visualization that you want to add.

   * Right-click an existing panel in your Analysis Workspace project, then select [!UICONTROL **Duplicate visualization**] or [!UICONTROL **Copy visualization**].


## Settings {#settings}

Each visualization has its own settings. To access visualization settings, select ![Setting](/help/assets/icons/Setting.svg) **[!UICONTROL Settings]** to show a popup.

Depending on the visualization, you can 

* configure settings for the visualization through the **[!UICONTROL Settings]** tab, and 
* details for the source of data of the visualization through the **[!UICONTROL Data source]** tab. 

![Visualization Settings](assets/visualization-settings.png)

See each individual visualization for more details on what options for **[!UICONTROL Settings]** and **[!UICONTROL Data source]** are available.

You can customize the settings for all visualizations that you create. For more information, see [User preferences](/help/analysis-workspace/user-preferences.md).



<!--
| Setting | Description |
| --- | --- |
| Visualization Type | Change the type of visualization used to visualize the data. |
| Granularity | For trended visualizations, you can change the time granularity (day, week, month, etc.) from this dropdown list. This change also applies to the data source table. |
| Percentages | Displays values in percentages. |
| 100% Stacked | This setting on area stacked, bar stacked or horizontal bar stacked visualizations turns the chart into a 100% stacked visualization. Example: ![A bar chart showing the Stacked 100% option view.](assets/stacked_100_percent.png) |
| Legend Visible | Lets you hide the detailed legend text for the Summary Number/Summary Change visualization. |
| Limit Max Items | Lets you limit the number of items that a visualization displays. |
| Anchor Y Axis at Zero | If all the values plotted on the chart are considerably above zero, the chart default will make the bottom of the y-axis NON-ZERO. If you check this box, the y-axis will be forced to zero (and it will re-draw the chart). |
| Normalization | Forces metrics to equal proportions. This is helpful when plotted metrics are of very different magnitudes. |
| Display Dual Axis | Only applies if you have two metrics - you can have a y-axis on the left (for one metric) and on the right (for the other metric). This is helpful when plotted metrics are of very different magnitudes. |
| Show anomalies | Enhances line graphs and freeform tables by displaying anomaly detection. Anomaly detection in line visualizations includes an expected value (dashed line) and an expected range (shaded band). |
| Show forecast | Enhances line graphs and freeform tables by displaying forecast values. |
| Show min | Show the minimal value in the visualization. |
| Show max | Show the maximal value in the visualization. |
| Show trendline | Show a trendline in the visualization. When selected, you can select the type of trendline from the dropdown list. |

--> 



## Legend {#legend}

A visualization legend helps you to relate date in a source table to plotted series in the visualization. The legend is interactive - you can select a legend item to show/hide a series in the visualization, which is helpful if you want to simplify the data being visualized. 

Additionally, you can rename legend labels to help you make visuals more consumable. Note: legend editing does **not** apply to: Treemap, Bullet, Summary Change/Number, Text, Freeform, Histogram, Cohort or Flow visualizations.

To edit a legend label:

1. Right-click one of the legend labels.
1. Click **[!UICONTROL Edit Label]**.

   ![A legend label and the Edit label option.](assets/edit-label.png)

1. Enter the new label text.
1. Press **[!UICONTROL Enter]** to save.

## Configuration

Some visualizations (like Cohort table, Fallout, Flow, and others) have a configuration panel to assist you in building the visualization. Use ![Edit](/help/assets/icons/Edit.svg) at the top of the visualization to access that configuration and change options.

![Configuration pane](assets/configuration.png)

## Context menu {#right-click}

Use the context menu (available through alternate select, for example, right-click when using a mouse) on a visualization header to access additional functionality for a visualization. See each individual visualization for more details on what menu options are available.

![Additional visualization settings with the right-click options displayed. Options are described in the next section.](assets/right-click.png)

<!--
| Option | Description |
| --- | --- |
| **[!UICONTROL Insert copied visualization]**n| Paste (insert) a copied visualization to another place within the project, or into a completely different project. |
| **[!UICONTROL Copy data to clipboard]** | Copy data from the visualization onto the clipboard. |
| **[!UICONTROL Copy selection to clipboard]** | Copy the selection from the visualization onto the clipboard. |
| **[!UICONTROL Download items as CSV (*dimension name*)]** | Immediately download the dimension items (to a maximum of 50,000) of the visualization to your local device. A maximum of 50,000 dimension items for the selected dimension. |
| **[!UICONTROL Copy visualization]** | Copy the visualization, so that you can insert the visualization to another place within the project, or into a completely different project. |
| **[!UICONTROL Download data CSV]** | Immediately download the displayed data of the visualization to your local device. |
|**[!UICONTROL  Export full table...]** | Export the full table to a designated cloud locations. See [Exports Customer Journey Analytics reports to the cloud](../export/export-cloud.md) |
| **[!UICONTROL Duplicate visualization]** | Make an exact duplicate of the visualization. |
| **[!UICONTROL Edit description]** | Add (or edit) a text description for the visualization. See [Text](text.md). |
| **[!UICONTROL Get visualization link]** | Copy and share a link directly to the visualization. A Share link dialog displays the link. Select Copy to copy the link to your clipboard. |
| **[!UICONTROL Start over]** | Delete the configuration for the current visualization so you can re-configure it from scratch. |
-->

## Visualize

If you are not sure which visualization to pick, select ![GraphBarVerticalAdd](/help/assets/icons/GraphBarVerticalAdd.svg) **[!UICONTROL Visualize]** in any table row (available on hover). This selection is the fastest way to add a visualization. Analysis Workspace takes an educated guess at which visualization would best fit your data. For example, if you have one row selected, it creates a trended [line graph](line.md). If you have three filter rows selected, it creates a [venn](venn.md) diagram. 

![Quick visualization](assets/quick-viz.png)
