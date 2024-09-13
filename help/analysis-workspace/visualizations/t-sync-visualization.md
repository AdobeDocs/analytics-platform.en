---
description: Synchronizing visualizations lets you control which data table or data source corresponds to a visualization.
keywords: Analysis Workspace;Synchronize visualization with data source
title: Manage data sources
feature: Visualizations
exl-id: f9e89bef-0e78-49c7-8b7b-1fefd709c0cd
role: User
---
# Manage data sources

Synchronizing visualizations lets you control which data table or data source corresponds to a visualization.

>[!TIP]
>
>You can tell which visualizations are related by the color of ![StatusOrange](/help/assets/icons/StatusOrange.svg) next to the title of visualizations. Matching colors mean that visualizations are based on the same data source.
>

You can show or hide the data source. You can also lock the selection to selected positions or selected items. These settings determine how the visualization changes (or doesn't change) when new data comes in.

![The Data Source option dialog showing the options described in the next section.](assets/lock-selection.png)


| Option | Description |
|--- |--- |
| **[!UICONTROL Data source]** | Select the data source on which the visualization is based, from the dropdown menu. | 
| **[!UICONTROL Linked visualizations]** | Lists all linked visualizations. Applies to the data source (freeform table). |
| **[!UICONTROL Show data source]** | Lets you show or hide the data source (freeform table) that corresponds to the visualization. |
| **[!UICONTROL Lock Selection]** | Select this option to lock the visualization ![LockClosed](/help/assets/icons/LockClosed.svg)  to the data currently selected in the corresponding data table. Once enabled, select between:  <ul><li>**Selected Positions**: The visualization is locked on the **positions** that are selected in the corresponding data table. These positions continue to be visualized, even if the specific items in these positions change (for example due to sorting or filtering). For example, select this option if you want to show the top five campaign names listed in the data source in this visualization at all times. No matter which campaign names show up.</li> <li>**Selected Items**: The visualization is locked on the specific **items** currently selected in the corresponding data table. These items continue to be visualized, even if they change their ranking among items in the table. For example, select this option if you want to show the same five specific campaign names listed in the data source in this visualization at all times. No matter how those campaign names rank.</li></ul> |
