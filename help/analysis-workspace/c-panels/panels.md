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
| [Quick Insights panel](quickinsight.md) | Quickly build a freeform table and an accompanying visualization in order to analyze and uncover insights faster. |
| [Attribution panel](attribution.md) | Quickly compare and visualize any number of attribution models using any dimension and conversion metric. |
| [Freeform panel](freeform-panel.md) | Perform unlimited comparisons and breakdowns, then add visualizations to tell a rich data story. |
| [Media Concurrent Viewers panel](media-concurrent-viewers.md) | Analyze concurrent viewers over time, with details on peak concurrency and the ability to break down and compare. |
| [Media Playback Timespent panel](/help/analysis-workspace/c-panels/media-playback-time-spent.md) | Analyze playback time spent to understand where peak concurrency occurred or where drop-oﬀs happened. |

![The Customer Journey Analytics panel listing the available panel types..](assets/panel-overview.png)

[!UICONTROL Quick Insights], [!UICONTROL Blank] and [!UICONTROL Freeform] panels are great places to start your analysis, while [!UICONTROL Attribution IQ] lends itself to more advanced analyses. A `"+"` button is available in projects so you can add blank panels at any time.

The default starting panel is the [!UICONTROL Freeform] panel, but you can make the [blank panel](/help/analysis-workspace/c-panels/blank-panel.md) your default as well.

## Calendar {#calendar}

The panel calendar controls the reporting range for tables and visualizations within a panel.

Note: If a (purple) date range component is used within a table, visualization or panel dropzone, it will override the panel calendar.

![The calendar window showing the selected date range.](assets/panel-calendar.png)

You can apply a minute-level date range under the advanced settings of your panel calendar. If you are reporting on a date range that spans many days, start time applies to the first day and end time applies to the last day in your range.

## Dropzone {#dropzone}

The panel dropzone enables you to apply filters and drop-down filters to all tables and visualizations within a panel. You can apply one or many filters to a panel. The title above each filter can be modified by clicking the edit pencil, or you can right-click to remove it altogether.

### Filters

Drag and drop any Filters from the left rail into the panel drop zone to begin filtering your panel.

![The left rail shows available Metrics and the Mobile Customer metric dragged to the panel drop zone.](assets/segment-filter.png)

### Ad hoc filters 

Non-filter components can also be dragged directly into the dropzone to create ad hoc filters, saving you the time and effort of going to the Filter Builder. Filters created in this way are automatically defined as event-level filters. This definition can be modified by clicking the information icon (i) next to the filter, then the pencil-shaped edit icon and editing it in the Filter Builder.

Ad hoc filters are a type of quick filter, and are local to the project. They do not show up in the left rail unless you make them public.

For more information, see [Quick filters](/help/components/filters/quick-filters.md).

![Ad hoc filters that are made public and dropped into the drop zone.](assets/adhoc-segment-filter.png)

### Static drop-down filters

Drop-down filters enable you to interact with the data in a controlled way. For example, you can add a drop-down filter for Mobile Device Types so that you can filter the panel by Tablet, Mobile Phone or Desktop.

Drop-down filters can be used to consolidate many projects into one as well. For example, if you have many versions of the same project with different Country filters applied, you can consolidate all versions into a single project and add a Country drop-down filter.

![Static drop-down filters showing the Market Channel "Direct" filter highlighted. ](assets/dropdown-filter-intro.png)

To create a static drop-down filter:

* For drop-down filters using dimension items, click the right arrow icon next to the desired dimension in the left rail. This action exposes all available dimension items. Select multiple dimension items from this list using `[Shift + Click]` or `[Ctrl + Click]`, then drop them into the panel dropzone **while holding `[Shift]`**.
* For drop-down filters using other components such as metrics, filters, or date ranges, select multiple components using `[Shift + Click]` or `[Ctrl + Click]`. Drop the selection into the panel dropzone **while holding `[Shift]`**. All component types are treated as filters in this context.
* A single drop-down filter can only contain a single component type. If you include multiple component types in your selection, a separate drop-down filter is created per component type. For example, if you include both metrics and dimension items in your selection, two separate drop-down filters are created. One drop-down filter includes dimension items, and the other includes metrics.

Select one of the options from the drop-down list to change the data in the panel. You can also choose to not filter any in the panel data by selecting **[!UICONTROL No filter]**.

![The Panel window with the Mobile Customer segment field available to drop a static drop-down filter. ](assets/create-dropdown.png)

Right-clicking a drop-down filter provides the following options:

* **[!UICONTROL Add label]**: When you add a drop-down filter to a project, a label is automatically set to the component name. If you delete the label, you can add it again with this option.
* **[!UICONTROL Delete label]**: Remove the text above a drop-down filter.
* **[!UICONTROL Delete drop-down filter]**: Removes the drop-down filter from the panel. 

[Watch the video](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/using-panels/using-panels-to-organize-your-analysis-workspace-projects.html) to learn more about how to add drop-down filters to your project.

### Dynamic drop-down filters

Dynamic drop-down filters allow you to determine available values based on data within the panel's reporting range and values in other drop-down filters. For example, you can create two dynamic drop-downs using a Countries dimension and Cities dimension. When you select a country from the UICONTROL Countries drop-down list, the Cities drop-down list dynamically adjusts to only show cities within that country.

This same concept applies to all dimensions; only dimension items that appear within the panel's date range and selected filters are visible. Dimension items selected in static drop-down filters affect available values in dynamic drop-down filters. However, the inverse is not true; Dimension items selected in dynamic drop-down filters do not affect available values in static drop-down filters.

Manual selection of dimension items is available if you anticipate a certain dimension item to be collected in the future. You can also clear a dynamic drop-down filter so that it does not contain a value, allowing other dynamic drop-down filters to contain more values. Select **[!UICONTROL Reset all]** to clear the selection from all drop-down filters for that panel.

To create a dynamic drop-down filter:

* Drag and drop a single dimension into the panel dropzone **while holding `[Shift]`**.
* Dynamic drop-down filters are not available for metrics, filters, or date ranges.
* Right-click a drop-down filter and select **[!UICONTROL Delete filter]** to delete it.

Right-clicking a dynamic drop-down filter provides the same options as static drop-down filters.

## Right-click menu {#right-click}

Additional functionality for a panel is available by right-clicking on the panel header.

![The right-click options for a panel header.](assets/right-click-menu.png)

The following settings are available:

| Setting | Description |
| --- | --- |
| [!UICONTROL Insert Copied Panel/Visualization] | Lets you paste ("insert") a copied panel or visualization to another place within the project, or into a different project.|
| [!UICONTROL Copy Panel] | Lets you right-click and copy a panel, so that you can insert it to another place within the project, or into a different project.|
| [!UICONTROL Duplicate Panel] | Makes an exact duplicate of the current panel, which you can then modify. |
| [!UICONTROL Collapse/Expand all Panels] | Collapses and expands all project panels. |
| [!UICONTROL Collapse/Expand all Visualizations in Panel] | Collapses and expands all visualizations in the current panel. |
| [!UICONTROL Edit Description] | Add (or edit) a text description for the panel. |
| [!UICONTROL Get Panel Link] | Lets you direct someone to a specific panel within a project. When the link is clicked, the recipient will be required to login before being directed to the exact panel linked to. |
