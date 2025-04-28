---
title: Shared metrics & dimensions overview
description: Use the same dimension or metric reference across multiple data views.
exl-id: 998a9f9b-cfa7-4b97-b32b-d50e35d01b39
---
# Shared metrics & dimensions overview

Shared metrics & dimensions provide a central location to manage dimensions and metrics that can be used across any number of data views. These components are especially valuable to organizations that use multiple data views, especially if those data views share common component settings. Changes made to shared metrics and dimensions instantly apply across every data view that it is shared to. When editing an individual data view, shared dimensions and metrics can be identified by a ![Shared component icon](/help/assets/icons/CCLibrary.svg) icon next to the component name.

While shared dimensions and metrics allow common components to be used across many data views, they cannot be shared across connections.

## Workflow

Most organizations use the following overarching workflow to deduplicate and maintain dimensions and metrics over time:

1. Import components from each data view that might be shared across multiple data views. If the same dimension or metric exists in multiple data views, Adobe recommends importing all instances of that component. While this best practice imports duplicates, they are imported so that they can be deduplicated and retain their respective references to Workspace projects.
1. Review all components that use the same component ID but have different component settings. For each group of duplicate components, select the desired component settings to be applied to all other components that share that component ID.
1. Review all components that use the same component ID and also have the same component settings. These dimensions or metrics can easily and safely be merged.

## [!UICONTROL Shared Metrics & Dimensions] manager

**[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Data views]** > **[!UICONTROL Shared Metrics & Dimensions]**

Navigating to this UI shows all current dimensions and metrics that are available to be shared across multiple data views. The top right contains two buttons to add components to this interface:

* **[!UICONTROL Import]**: Opens a modal window that lets you select a data view, then lets you select components to make available for sharing.
* **[!UICONTROL Create new]**: Opens the [Shared component editor](shared-component-editor.md).

Directly below these two buttons, four overview cards are visible:

![Overview cards preview](assets/overview-cards.png)

* **Metrics**: The total number of metrics available to share across data views for this connection. Each connection can contain up to 10,000 shared metrics.
* **Dimensions**: The total number of dimensions available to share across data views for this connection. Each connection can contain up to 10,000 shared dimensions.
* **Duplicate components to review**: When importing components across multiple data views, some dimensions or metrics might share the same component ID. The number in this overview card shows the total number of components that have the same component ID but different component settings. Selecting **[!UICONTROL Review]** enables a filter that allows you to select the desired component to act as a source of truth for all other components with the same ID.
* **Components available to merge**: If a dimension or metric shares the same component ID and the same component settings, then they are effectively identical and are ready to deduplicate. Selecting **[!UICONTROL Review]** enables a filter that allows you to merge all components with the same component ID into a single shared dimension or metric.

All shared dimensions and metrics are displayed below the four overview cards.

![Available dimensions and metrics preview](assets/shared-metrics-dimensions.png)

* **Filter**: Select the ![Filter icon](../../assets/icons/Filter.svg) icon to show or hide available filters. The following filters are available:
  * **[!UICONTROL Component type]**: View only dimensions or only metrics.
  * **[!UICONTROL Dataset]**: View only components where the dataset is included in the data views that a component is shared to.
  * **[!UICONTROL Data view]**: View only components shared to that data view.
  * **[!UICONTROL Created by]**: View only components created by a given user.
  * **[!UICONTROL Duplicates]**: View only components that have the same component ID as another component. These filters are identical to reviewing components through the overview cards.
* **Search**: Use the ![Search icon](../../assets/icons/Search.svg) icon to search for a component by name.
* **[!UICONTROL Connection]**: A dropdown that changes the [connection](/help/connections/overview.md). Shared dimensions and metrics are always specific to a single connection.
* **[!UICONTROL Customize table]**: Select the ![Customize table icon](/help/assets/icons/ColumnSetting.svg) icon to show or hide columns in the table. Available options include:
  * **[!UICONTROL Field name]**: The name of the shared dimension or metric. This field is always visible.
  * **[!UICONTROL Type]**: Indicates if the component is a dimension or a metric. This field is always visible.
  * **[!UICONTROL Dataset type]**: The type of dataset. Most datasets are event datasets.
  * **[!UICONTROL Shared to data view]**: All data views that this component is shared to. This field is always visible. Select the link to open a modal that lists all data views that this component is available in.
  * **[!UICONTROL Datasets]**: All datasets that are included in each data view that this component is shared to. Select the link to open a modal that lists all datasets for the component.
  * **[!UICONTROL Created by]**: The name of the individual who created or imported the component into the shared metrics & dimensions interface.
  * **[!UICONTROL Schema type]**: The format that data is stored in. Examples include `string`, `double`, or `boolean`.
  * **[!UICONTROL Component ID]**: The component ID of the dimension or metric. Any components that share the same component ID in this interface must be reviewed and deduplicated.
  * **[!UICONTROL Schema]**: The schema path for the dimension or metric. For example, `web.webPageDetails.URL`.
  * **[!UICONTROL Description]**: The [description](/help/data-views/component-settings/overview.md) of the component.
  * **[!UICONTROL Context labels]**: The [context labels](/help/data-views/component-settings/overview.md) for the component.
  * **[!UICONTROL Include/Exclude values]**: Lists the number of rules as specified under [Include/exclude values](/help/data-views/component-settings/include-exclude-values.md).
  * **[!UICONTROL Data usage labels]**: The [data usage labels](https://experienceleague.adobe.com/en/docs/experience-platform/data-governance/labels/overview) for the schema field.
  * **[!UICONTROL Deprecated]**: Indicates if the deprecated flag is set.
  * **[!UICONTROL Format]**: The format that values appear in. Booleans typically appear as `True | False`, metrics typically appear as `Decimal`, etc.
  * **[!UICONTROL Metric deduplication]**: The component's [Metric deduplication](/help/data-views/component-settings/metric-deduplication.md) settings.
  * **[!UICONTROL Behavior]**: The component's [Behavior](/help/data-views/component-settings/behavior.md) settings.
  * **[!UICONTROL Attribution]**: The component's [Attribution](/help/data-views/component-settings/attribution.md) settings.
  * **[!UICONTROL No value option]**: The component's [No value options](/help/data-views/component-settings/no-value-options.md).
  * **[!UICONTROL Value bucketing]**: The component's [Value bucketing](/help/data-views/component-settings/value-bucketing.md) settings.
  * **[!UICONTROL Persistence]**: The component's [Persistence](/help/data-views/component-settings/persistence.md) settings.
  * **[!UICONTROL Lowercase]**: Indicates if the component is lowercase enabled based on the component's [Behavior](/help/data-views/component-settings/behavior.md) settings.
  * **[!UICONTROL Substring]**: The component's [Substring](/help/data-views/component-settings/substring.md) settings.
  * **[!UICONTROL Summary data group]**: The component's [Summary data group](/help/data-views/component-settings/summary-data-group.md) settings.
  * **[!UICONTROL Date created]**: The date that the component was created or imported.
  * **[!UICONTROL Last modified]**: If the component has been modified after it was created, the date that it was last modified.
* **[!UICONTROL Job history]**: Select the ![History icon](/help/assets/icons/History.svg) icon to open a modal window that shows all instances of importing dimensions and metrics from individual data views.

## Edit components or share components to data views

Use the check box next to a component to reveal all available actions that you can take. Multiple selections are supported.

![Preview of available actions](assets/smd-actions.png)

* ![Pencil icon](/help/assets/icons/Edit.svg) **[!UICONTROL Edit]**: Open the selected dimensions and metrics in the [shared component editor](shared-component-editor.md), which lets you adjust their [component settings](/help/data-views/component-settings/overview.md). When you select multiple components to edit, they are all opened in the component editor. You can shift + click components in the component editor to edit the same field for multiple components.
* ![Share icon](/help/assets/icons/ShareAlt.svg) **[!UICONTROL Share to data view(s)]**: Opens a window that shows all data views available within the selected connection. Select the check box for each data view that you want to make this component available in, then select **[!UICONTROL Share]**.
* ![Unshare icon](/help/assets/icons/SaveTo.svg) **[!UICONTROL Unshare from data view(s)]**: Opens a window that shows all data views that this component is currently shared with. Select the check box for each data view that you want to remove this component's availability from, then select **[!UICONTROL Unshare]**.
* ![Duplicate icon](/help/assets/icons/Copy.svg) **[!UICONTROL Duplicate]**: Creates a copy of the selected component(s). A new component ID is generated for duplicated components.
* ![Delete icon](/help/assets/icons/Delete.svg) **[!UICONTROL Delete]**: Removes the selected components from the interface. If the selected components are shared with any data views, they are unshared.
