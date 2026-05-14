---
description: Learn how to use components in a project in Analysis Workspace
title: Use Components In A Project
feature: Components
role: User
exl-id: 97bdfb9e-a27e-4a6b-b6cc-21a292398037
TQID: https://experienceleague.adobe.com/kXVC79sHZMIdUELOC6KjtT7tJdh9pVySu-jApef-8lk
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
    internal-label: Metrics
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
    internal-label: Segments, Segments (CJA)
  - id: bcaa1b08-8269-4ff3-a0c2-f599783b6107
    internal-label: Filters
  - id: df28738e-9c71-4aa8-929e-edde22340cc6
    internal-label: Data Dictionary
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
    internal-label: Dimensions
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
    internal-label: Calculated metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
---
# Use components in a project

Components make up the actual data of any project in Analysis Workspace. Components consist of dimensions, metrics, segments, and date ranges. You can add components to a project by dragging them into visualizations or panels.

See the [Components overview](/help/components/overview.md) for more information on the types of components that you can add.

>[!TIP]
>
>For information about each component, use ![InfoOutline](/help/assets/icons/InfoOutline.svg). See [Component info](#component-info) for more information

## Add components to a project

1. [Create a project in Analysis Workspace](/help/analysis-workspace/build-workspace-project/create-projects.md).

1. [Add a panel](/help/analysis-workspace/c-panels/panels.md#create-a-panel) or [add a visualization](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel) to the project in Analysis Workspace. If you add a component to a blank project, a freeform table visualization is already created for you.

1. Select ![Curate](/help/assets/icons/Curate.svg) **[!UICONTROL Components]** from the button panel. You see all available components in the left panel. See [Interface](/help/analysis-workspace/home.md#interface) for more details.

1. Scroll to or search for the component that you want to add, then drag it to a panel or visualization within your project. 

1. You can optionally drag a component to the segment drop zone in a panel header. This drag and drop defines the component as a segment and applies the segment to all the content within the panel.
   For information about how you can use the segment drop zone on a panel to segment your panel, see [Drop zone](/help/analysis-workspace/c-panels/panels.md#drop-zone) in [Panels overview](/help/analysis-workspace/c-panels/panels.md).

1. For more detailed information, see the following sections:

   * [Add dimensions to a project](#add-dimensions-to-a-project)

   * [Add metrics to a project](#add-metrics-to-a-project)

   * [Add segments to a project](#add-segments-to-a-project)

   * [Add date ranges to a project](#add-date-ranges-to-a-project)

### Add dimensions to a project

[Dimensions](/help/components/dimensions/overview.md) are variables in Customer Journey Analytics that typically contain string values. In contrast, [metrics](/help/components/calc-metrics/calc-metr-overview.md) contain numeric values that tie to a dimension. A basic report shows rows of string values (dimension), against a column of numeric values (metric).

1. Start adding a dimension to your project in Analysis Workspace, as described in [Add components to a project](#add-components-to-a-project).

1. Choose one of the following methods to add dimensions and determine the type of data you want to analyze:

   ![Add a dimension](/help/components/assets/add-dimension.gif)

   * Drag a dimension to a visualization (such as a freeform table) in Analysis Workspace.
   
   * Drag one or more dimensions from the left panel onto the segment drop zone to create a quick segment, as described in [Add segments to a project](#add-filters-to-a-project).

1. You can optionally break down dimensions and dimension items in Analysis Workspace with other components. For more information, see [Break down dimensions in Workspace](/help/components/dimensions/t-breakdown-fa.md).

For more information about how to use dimensions in Analysis Workspace, see [Preview dimensions](/help/components/dimensions/view-dimensions.md), [Break down dimensions](/help/components/dimensions/t-breakdown-fa.md), and [Time-parting dimensions](/help/components/dimensions/time-parting-dimensions.md).

### Add metrics to a project

Metrics allow you to quantify data points in Analysis Workspace. They are most commonly used as columns in a visualization and tied to dimensions.

To add a metric to a project in Analysis Workspace:

1. Start adding a metric to your project in Analysis Workspace,as described in [Add components to a project](#add-components-to-a-project).



1. Choose one of the following methods to add a metric in Analysis Workspace:

   ![Adding a metric](/help/components/assets/add-metric.gif)

   * Drag a metric to the metric drop zone in an empty Freeform table to see that metric trended over the project's date period. 

   * Drag a metric when a dimension is present to see that metric for each dimension item. 

   * Drag a metric on top of an existing metric header to replace it.

   * Drag a metric next to the left of right side of an existing metric header to add the new metric.

   * Drag a metric above or below an existing metric header to create a metric overlap.

     
For more information about metrics, see [Metrics](/help/components/apply-create-metrics.md).

### Add segments to a project

[Segments](/help/components/segments/seg-overview.md) allow you to identify subsets of persons, sessions or events based on characteristics or specific interactions.

You can use segments in Analysis Workspace in any of the following ways:

* Add segments to a panel
  When you add segments to a panel, the segments apply to all content within the panel.
  For information about how you can use the segment drop zone on a panel to segment your panel, see [Drop zone](/help/analysis-workspace/c-panels/panels.md#drop-zone) in [Panels overview](/help/analysis-workspace/c-panels/panels.md).

* Add segments to a visualization
  When you add segments to a column in a freeform table, the segments apply to all content within the table column. You can also add segments as part of a fallout visualization.

* Use segments in components
  Whe you define components like [calculated metrics](/help/components/calc-metrics/cm-workflow/metrics-with-segments.md), [annotations](/help/components/annotations/create-annotations.md#annotation-builder), or even [segments](/help/components/segments/seg-builder.md) you can use segments as part of the definition.


### Add date ranges to a project

[Date ranges](/help/components/date-ranges/overview.md) determine the reporting time frame in Analysis Workspace, and can be applied to one or more panels within a project and also to some visualizations (like the Freeform table).

Each panel includes a date range by default. There are multiple ways to update a date range for a panel. One way to update a date range for a panel in Analysis Workspace is to drag a date range component from the left panel:

1. Optionally, add a date range to your project in Analysis Workspace, as described in [Add components to a project](#add-components-to-a-project).

1. Drag and drop a date range from the left panel onto:

   * The current date range, to modify the date range for the panel.

      ![Drop a date range](assets/add-date-range.gif)

   * A metric or dimension in a Freeform table visualization. See [Use date ranges](/help/components/date-ranges/overview.md#use-date-ranges) for more information.

For more information about how to use and manage date ranges in Analysis Workspace, see [Date ranges overview](/help/components/date-ranges/overview.md).

## Component info

You can hover over any component to display ![More info](/help/assets/icons/InfoOutline.svg). When selected, a popup is displayed with additional information on the component. 

![Component info](assets/component-info.png)

Based on your access control, you can:

* Access the ![Bookmark](/help/assets/icons/Bookmark.svg) [!UICONTROL Data dictionary] definition for the component.
* Access the ![Edit](/help/assets/icons/Edit.svg) component builder or data view where the component is defined.
