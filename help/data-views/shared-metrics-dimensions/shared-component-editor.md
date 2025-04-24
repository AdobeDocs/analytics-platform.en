---
title: Shared component editor
description: Create or edit shared dimensions and metrics.
---
# Shared component editor

The shared component editor allows you to create or edit shared dimensions and metrics. It shares many UI elements when [creating a data view](/help/data-views/create-dataview.md), but these interfaces are distinct in purpose:

* The data view component editor allows you to create and edit components specific to that data view. You cannot edit shared dimensions or metrics in the data view component editor. Shared dimensions and metrics can be identified by a ![Shared component icon](/help/assets/icons/CCLibrary.svg) icon next to the component name.
* The shared component editor allows you to create and edit shared dimensions and metrics. You cannot edit components that belong to a single data view in the shared component editor.

![Component editor screenshot](assets/component-editor.png)

The top right includes three buttons:

* **[!UICONTROL Close]** or **[!UICONTROL Cancel]**: If all changes are saved, the **[!UICONTROL Close]** button closes the editor. If there are any unsaved changes, the **[!UICONTROL Cancel] button closes the editor without saving those changes.
* **[!UICONTROL Save]**: Saves all components

The interface includes three main columns/sections:

* **Schema field selector**: Locate the desired schema field(s) and drag them to the included components area.
* **Included components**: The components that you configure to be shared. When creating shared components, you can drag more than one schema field to this area to create multiple components simultaneously. When editing shared components, you can select multiple components to edit, which lists all selected components in this area.
* **Component settings**: When selecting a component, all available settings can be configured in this column. See [Component settings](/help/data-views/component-settings/overview.md) for all available options for dimensions and metrics.