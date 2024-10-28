---
description: A panel is a collection of tables and visualizations
title: Panels overview
feature: Panels
exl-id: be3e34a0-06c1-4200-b965-96084c2912fd
role: User
---
# Panels overview

A [!UICONTROL panel] is a collection of tables and visualizations. You can access panels from the top-left icon in Workspace or a [blank panel](/help/analysis-workspace/c-panels/blank-panel.md). Panels are helpful when you want to organize your projects according to time periods, data views, or analysis use case.

## Panel types

The following panel types are available in Analysis Workspace for [!UICONTROL Customer Journey Analytics]:

| Panel name | Description |
| --- | --- |
| [Blank panel](/help/analysis-workspace/c-panels/blank-panel.md) | Choose from available panels and visualizations to start your analysis. |
| [Attribution](attribution.md) | Quickly compare and visualize any number of attribution models using any dimension and conversion metric. |
| [Experimentation](experimentation.md) | Compare different user experiences, marketing, or messaging variations to determine which is best at driving a specific outcome. |
| [Freeform](freeform-panel.md) | Perform unlimited comparisons and breakdowns, then add visualizations to tell a rich data story. |
| [Media average minute audience](average-minute-audience-panel.md) | Analyze the average minute audience for a specific piece of content, or over a customized time period. | 
| [Media concurrent viewers](media-concurrent-viewers.md) | Analyze concurrent viewers over time, with details on peak concurrency and the ability to break down and compare. |
| [Media playback time spent](/help/analysis-workspace/c-panels/media-playback-time-spent.md) | Analyze playback time spent to understand where peak concurrencies occur or where drop-oﬀs happen. |
| [Next or previous item](next-previous.md) | Show the next or previous pages people go to. |
| [Quick insights](quickinsight.md) | Quickly build a freeform table and an accompanying visualization to analyze and uncover insights faster. |


[!UICONTROL Quick insights], [!UICONTROL Blank] and [!UICONTROL Freeform] panels are great places to start your analysis, while [!UICONTROL Attribution] lends itself to more advanced analyses. A ![AddCircle](/help/assets/icons/AddCircle.svg) is available at the bottom of your canvas, so you can add blank panels at any time.

The default starting panel is the [!UICONTROL Freeform] panel, but you can make the [Blank panel](/help/analysis-workspace/c-panels/blank-panel.md) or [Quick insights](/help/analysis-workspace/c-panels/quickinsight.md) your default as well. See [Projects & Analysis preferences](/help/analysis-workspace/user-preferences.md#projects--analyses-preferences).


## Create a panel

To create a panel :

* Drag and drop a panel from the **[!UICONTROL Panels]** left panel onto your canvas.
* Select a panel from the [Blank panel](blank-panel.md).
* Use **[!UICONTROL Insert]** menu in Workspace and select your panel. Alternatively, you can use any of the [shortcuts](../build-workspace-project/fa-shortcut-keys.md) to insert a panel.

  ![Create a panel](assets/create-panel.png)

You can:

* Select ![AddCircle](/help/assets/icons/AddCircle.svg) **within** any panel to add another visualization. A popup appears that allows you to select a visualization.

  ![Popup showing possible visualizations](assets/blank-panel.png)

  | Select.. | To create a...  |
  |---|---|
  | ![Table](/help/assets/icons/Table.svg) | [Freeform table](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) |
  | ![Line](/help/assets/icons/GraphTrend.svg) | [Line](/help/analysis-workspace/visualizations/line.md) |
  | ![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg) | [Bar](/help/analysis-workspace/visualizations/bar.md) |
  | ![123](/help/assets/icons/123.svg) | [Summary number](/help/analysis-workspace/visualizations/summary-number-change.md) |
  | ![Text](/help/assets/icons/Text.svg) | [Text](/help/analysis-workspace/visualizations/text.md) |
  | ![ConversionFunnel](/help/assets/icons/ConversionFunnel.svg) | [Fallout](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) |
  | ![Workflow](/help/assets/icons/GraphPathing.svg) | [Flow](/help/analysis-workspace/visualizations/c-flow/flow.md) |
  | ![GraphAreaStacked](/help/assets/icons/GraphAreaStacked.svg) | [Area stacked](/help/analysis-workspace/visualizations/area.md) |
  | ![TextNumbered](/help/assets/icons/TextNumbered.svg) | [Cohort table](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md) |
  | ![GraphBullet](/help/assets/icons/GraphBullet.svg) | [Bullet](/help/analysis-workspace/visualizations/bullet-graph.md)|
  | ![GraphDonut](/help/assets/icons/GraphDonut.svg) | [Donut](/help/analysis-workspace/visualizations/donut.md) |
  | ![MoveUpDown](/help/assets/icons/MoveUpDown.svg) | [Summary change](/help/analysis-workspace/visualizations/summary-number-change.md) |
  | ![Histogram](/help/assets/icons/Histogram.svg) | [Histogram](/help/analysis-workspace/visualizations/histogram.md) |
  | ![GraphScatter](/help/assets/icons/GraphScatter.svg) | [Scatter](/help/analysis-workspace/visualizations/scatterplot.md) |
  | ![Type](/help/assets/icons/TwoDots.svg) | [Venn](/help/analysis-workspace/visualizations/venn.md) |
  | ![GraphTree](/help/assets/icons/GraphTree.svg) | [Treemap](/help/analysis-workspace/visualizations/treemap.md) | 

* Select ![AddCircle](/help/assets/icons/AddCircle.svg) **outside** the last panel in your workspace to add another [Blank panel](blank-panel.md).


## Data view 

Each panel is associated with a [data view](/help/data-views/data-views.md), identified by ![Data](/help/assets/icons/Data.svg) **[!UICONTROL *name of data view*]** in the dropdown menu at the top right of the panel.

When you create a Blank Workspace project, the default data view for the initial panel is the data view you last worked on in Customer Journey Analytics.

When you create a new panel, the default data view is based on the data view of the panel you last worked on in the Workspace project.

>[!IMPORTANT]
>
>The selected data view determines what dimensions, metrics, and filters are available for building visualizations in a panel.
>
>
>When you switch a data view for a panel, some of the components might not be available in that new data view. This change can cause your visualization not to render properly. You might see warnings like:
>
>* This panel contains components that are not enabled in the selected data view. Please change the data view or enable the required components in the data view. 
>* Unable to render visualization: Please check your columns and rows to ensure they contain valid components.
>

## Calendar

The panel calendar controls the reporting date range for tables and visualizations within a panel.

>[!NOTE]
>
>If a ![Calendar](/help/assets/icons/Calendar.svg) Date range component is used within a visualization or panel (for example, as a filter), the date range component overrides the panel calendar.
>


![The calendar window showing the selected date range.](assets/panel-calendar.png)

1. Select a date range by selecting first the start date and then the end date. 
   Alternatively, you can select a **[!UICONTROL Preset]** from the [!UICONTROL *Select a preset*] dropdown menu.

1. Optionally, select **[!UICONTROL Show advanced settings]** to:

   * Specify **[!UICONTROL Start time]** and **[!UICONTROL End time]** other than the default `12:00 AM` (`0:00`) and `11:59 PM` (`23:59`). End times always include 59 seconds. For a date range that spans many days, the start time applies to the first day of the date range and the end time applies to the last day in your date range. Use **[!UICONTROL (Reset time values)]** to reset start and end time to their defaults.
   * **[!UICONTROL Make date range components relative to panel calendar]**. If disabled, date range components used in the panel are relative to the current time. If enabled, date range components used in the panel are relatve to the panel calendar.
   * **[!UICONTROL Use rolling dates]**. If enabled, preset date ranges like **[!UICONTROL Last 7 full days]** dynamically update as current date and time progress. If disabled, such presets are not updated once applied.
     
     ![Rolling dates](assets/calendar-rolling.png)

     You can select the text in brackets (for exampe **[!UICONTROL fixed start - rolling daily]**) to extend the panel and specify details for **[!UICONTROL Start]** and **[!UICONTROL End]**.

       1. Select **[!UICONTROL Start of]**, **[!UICONTROL End of]**, or **[!UICONTROL Fixed day]**.
       1. When you have selected **[!UICONTROL Start of]** or **[!UICONTROL End of]**, you can build a full expression. For example: **[!UICONTROL End of]** **[!UICONTROL current year]** **[!UICONTROL plus]** `1` **[!UICONTROL day]**. Pick the appropriate value for each individual part of the expression.
          * Select a value for current. For example **[!UICONTROL current year]**.
          * Select a value for additional calculation. For example, **[!UICONTROL plus]**.
          * When you have specified additional calculation, specify a value. For example `1`.
          * When you have specified additional calculation, select the time period to use for the calculation. For example **[!UICONTROL day]**.
     
     Select **[!UICONTROL Hide details]** to hide the details for rolling dates calculation.

1. Select **[!UICONTROL Apply]** to apply the date range to the panel from which you invoked the calendar. 
   Select **[!UICONTROL Apply to all panels]** to apply the date range to all panels in the Workspace project.


## Drop zone {#dropzone}

The panel drop zone enables you to apply filters and drop-down filters to all tables and visualizations within a panel. You can apply one or many filters to a panel. 

### Filters

Drag and drop any filters from the left panel into the panel drop zone to begin filtering your panel. Repeat this process to add additional filters to the panel. Filters appear side by side at the top of the panel.

![The left panel shows available Metrics and the Mobile Customer metric dragged to the panel drop zone.](assets/segment-filter.png)

#### Quick filters 

Non-filter components can also be dragged directly into the drop zone to create quick filters, saving you the time and effort of going to the [Filter builder](/help/components/filters/filter-builder.md). Filters created in this way are automatically defined as event-level filters. This definition can be quickly modified by selecting ![Edit](/help/assets/icons/Edit.svg) next to the filter name. 


For more information, see [Quick filters](/help/components/filters/quick-filters.md).

![Ad hoc filters that are made public and dropped into the drop zone.](assets/adhoc-segment-filter.png)

### Drop-down filters

+++ View a video explaining dropdown filters.

>[!VIDEO](https://video.tv.adobe.com/v/23877?format=jpeg)

{{videoaa}}

+++

#### Static drop-down filters

Static drop-down filters enable you to interact with the data in a controlled way. For example, you can add a drop-down filter for Mobile Device Types so that you can filter the panel by Tablet, Mobile Phone, or Desktop.

Static drop-down filters can also be used to consolidate many projects into one. For example, if you have many versions of the same project with different Country filters applied, you can consolidate all versions into a single project and add a Country drop-down filter.

![Static drop-down filters showing the Market Channel "Direct" filter highlighted. ](assets/dropdown-filter-intro.png)

##### Create static drop-down filters

* For drop-down filters using dimension items, select a single dimension from the left panel and drop the dimension into the panel drop zone while holding ⇧ (*shift*). This action creates a drop-down filter with all the dimension items that are associated with that dimension. 

  Or, if you want the drop-down filter to include only specific dimension items that are associated with a dimension, select the right arrow icon next to the desired dimension in the left panel. This action exposes all available dimension items. Select multiple dimension items from this list using ⇧+![Select](/help/assets/icons/Select.svg) (*shift* + *select*) or ^+![Select](/help/assets/icons/Select.svg) (*control* + *select*), then drop them into the panel drop zone **while holding** ⇧.

* For drop-down filters using a single component type (for example, only dimensions, or only filters, or only metrics), select multiple items of the same type in the left panel using ⇧+![Select](/help/assets/icons/Select.svg) or ^+![Select](/help/assets/icons/Select.svg). Then drop the items into the panel drop zone **while holding** ⇧.

  A single drop-down filter is created with components that you selected.

* For drop-down filters using a mix of component types (such as 2 metrics and 3 filters), select multiple components using ⇧+![Select](/help/assets/icons/Select.svg) or ^+![Select](/help/assets/icons/Select.svg). Drop the selection into the panel drop zone **while holding** ⇧. In this context, all component types are treated as separate drop-down filters. For example, if you include both metrics and dimension items in your selection, two separate drop-down filters are created: one drop-down filter includes dimension items, and the other includes metrics.

A drop-down filter provides the following context menu options:

* **[!UICONTROL Delete drop-down]**: Removes the drop-down filter from the panel. 
* **[!UICONTROL Delete label]**: Remove the text displayed above a drop-down filter. To modify the label, hover over the label and select ![Edit label of drop-down filter](/help/assets/icons/Edit.svg).
* **[!UICONTROL Add label]**: When you add a drop-down filter to a project, a label is automatically set to the component name. If you delete the label, you can add it again with this option.
* **[!UICONTROL Require selection]**: Requires that a filter is set on the panel. 

##### Use static drop-down filters

Users can use the drop-down filter menu in any of the following ways to filter the panel:
     
* Apply a single filter to the panel by selecting the filter from the drop-down filter.

* Apply multiple filters to the panel by selecting more than one filter from the drop-down filter. The panel is filtered to include any of the selected filters. 


#### Dynamic drop-down filters

Dynamic drop-down filters allow you to determine available values based on data within the panel's reporting range and values in other drop-down filters. For example, you can create two dynamic drop-downs using a Countries dimension and a Cities dimension. When you select a country from the **[!UICONTROL Countries]** drop-down list, the **[!UICONTROL Cities]** drop-down list dynamically adjusts to show only cities within that country.

This same concept applies to all dimensions; only dimension items that appear within the panel's date range and selected filters are visible. Dimension items selected in static drop-down filters affect available values in dynamic drop-down filters. However, the inverse is not true; Dimension items selected in dynamic drop-down filters do not affect available values in static drop-down filters.

Manual selection of dimension items is available if you anticipate a certain dimension item to be collected in the future. You can also clear a dynamic drop-down filter so that it does not contain a value, allowing other dynamic drop-down filters to contain more values. Select **[!UICONTROL Reset all]** to clear the selection from all drop-down filters for that panel.

To create a dynamic drop-down filter:

* Drag and drop a single dimension into the panel drop zone **while holding** ⇧.

Note that Dynamic drop-down filters are not available for metrics, filters, or date ranges.

A dynamic drop-down filter provides the same context menu options as static drop-down filters.


## Context menu

Additional functionality for a panel is available through a context menu (right-click) on the panel header.

![The right-click options for a panel header.](assets/right-click-menu.png)

The following options are available:

| Option | Description |
| --- | --- |
| **[!UICONTROL Insert copied panel]** | Let you paste a copied panel to another place within the project, or into a different project.|
| **[!UICONTROL Insert copied visualization]** | Paste a copied visualization to another place within the panel, project, or into a different project. |
| **[!UICONTROL Apply Data view to all panels]** | Apply the data view for this panel to all other panels in the project. |
| **[!UICONTROL Copy panel]** | Copy a panel, so that you can insert it to another place within the project, or into a different project.|
| **[!UICONTROL Duplicate panel]** | Makes an exact duplicate of the current panel, which you can then modify. |
| **[!UICONTROL Collapse all panels]** | Collapse all project panels. |
| **[!UICONTROL Expand all panels]** | Expand all project panels. |
| **[!UICONTROL Collapse all visualizations in panel]** | Collapse all visualizations in the current panel. |
| **[!UICONTROL Expand all visualizations in panel]** | Expand all visualizations in the current panel. |
| **[!UICONTROL Edit Description]** | Add (or edit) a text description for the panel. |
| **[!UICONTROL Get Panel Link]** | Direct someone to a specific panel within a project. When the link is selected, the recipient is required to log in before being directed to the exact panel linked to. |

## Configuration

Some panels (like [!UICONTROL Attribution], [!UICONTROL Experimentation], [!UICONTROL Media average minute audience], and others) have a configuration dialog to assist you in building the visualization. Use ![Edit](/help/assets/icons/Edit.svg) at the top of the panel to access and change the configuration.

![Configure a panel](/help/analysis-workspace/c-panels/assets/configure-panel.png)
