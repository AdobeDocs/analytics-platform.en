---
title: Shared metrics & dimensions overview
description: Use the same dimension or metric across multiple data views.
---
# Shared metrics & dimensions overview

Shared metrics & dimensions provide a central location to manage dimensions and metrics that can be used across many data views. These components are especially valuable to organizations that use many data views, especially if those data views share common component settings. If you need to make a change to a given dimension or metric, you can do so using shared metrics & dimensions, instead of having to update a component one-by-one across every data view it is in.

While shared dimensions and metrics allow common components to be used across many data views, they cannot be shared across connections.

## Workflow

Most organizations use the following overarching workflow to deduplicate and maintain dimensions and metrics over time:

1. Import components from each data view that might be shared across multiple data views. If the same dimension or metric exists in multiple data views, Adobe recommends importing all instances of that component. Shared metrics & dimensions provide a workflow to deduplicate these components so that reporting is not impacted from the deduplication.
1. Review all components that use the same IDs

## [!UICONTROL Shared Metrics & Dimensions] manager

**[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Data views]** > **[!UICONTROL Shared Metrics & Dimensions]**

Navigating to this UI shows all current dimensions and metrics that are available to be shared across multiple data views. Four boxes are visible at the top of the page:

![Overview cards preview](assets/overview-cards.png)

* **Metrics**: The total number of metrics available to share across data views for this connection. Each connection can contain up to 10,000 shared metrics.
* **Dimensions**: The total number of dimensions available to share across data views for this connection. Each connection can contain up to 10,000 shared dimensions.
* **Duplicate components to review**: When importing components across multiple data views, some dimensions or metrics might share the same component ID. The number in this overview card shows the total number of components that have the same component ID but different component settings. Selecting **[!UICONTROL Review]** enables a filter that allows you to select the desired component to act as a source of truth for all other components with the same ID.
* **Components available to merge**: If a dimension or metric shares the same component ID and component settings, then they are effectively identical and are ready to deduplicate. Selecting **[!UICONTROL Review]** enables a filter that allows you to merge all components with the same component ID into a single shared dimension or metric.

Below the four overview cards displays all shared dimensions and metrics.

![Available dimensions and metrics preview](assets/shared-metrics-dimensions.png)

* **Filter**: Select the ![Filter icon](../../assets/icons/Filter.svg) icon to show or hide available filters. The following filters are available:
  * **[!UICONTROL Component type]**: View only dimensions or only metrics.
  * **[!UICONTROL Dataset]**: View only components where the dataset is included in the data views that a component is shared to.
  * **[!UICONTROL Data view]**: View only components shared to that data view.
  * **[!UICONTROL Created by]**: View only components created by a given user.
  * **[!UICONTROL Duplicates]**: View only components that have the same component ID as another component. These filters are identical to reviewing components through the overview cards.
* **Search**: Use the ![Search icon](../../assets/icons/Search.svg) icon to search for a component by name.
* **[!UICONTROL Connection]**: