---
title: What are components in Customer Journey Analytics?
description: Learn what components Customer Journey Analytics offers, and how you can use them in reporting.
exl-id: f9b0b3c2-7c88-4bef-af33-0d309cafe799
solution: Customer Journey Analytics
feature: Components
role: User
---
# Components overview

Components are features in Customer Journey Analytics that can be used in visualizations (like Freeform table), or to complement reporting features.

To manage components from the main Customer Journey Analytics interface: 
  
   1. Select **[!UICONTROL Components]** from the top bar.
   1. Select **[!UICONTROL Components]** to see an overview of the components you can manage, or directly select the component you want to manage from the menu.

You can manage the following components:  

* [Segments](filters/filters-overview.md): Build, manage, share, and apply powerful, focused audience segments to your reports. Filters let you identify subsets of persons based on characteristics or interactions.
* [Calculated metrics](calc-metrics/calc-metr-overview.md): Use metrics and formulas as new components for use in reporting
* [Date ranges](date-ranges/create.md): Customize and refine the date ranges Analysis Workspace offers.
* [Annotations](/help/components/annotations/overview.md): Communicate contextual data nuances and insights to your organization.
* [Intelligent alerts](/help/components/c-intelligent-alerts/intelligent-alerts.md): Allow you to be notified based on changed percentages or specific data points. 
* [Scheduled projects](/help/analysis-workspace/export/t-schedule-report.md#scheduled-projects-manager): Manage your scheduled projects.
* [Preferences](/help/analysis-workspace/user-preferences.md): Manage the preferences for Analysis Workspace.
* [Audiences](/help/components/audiences/audiences-overview.md): Create and publish audiences from Customer Journey Analytics to [Real-Time Customer Data Platform](https://experienceleague.adobe.com/en/docs/experience-platform/profile/home) in Experience Platform for targeting and personalization.
* [Exports](/help/components/exports/manage-export-locations.md): Manage your export account and locations.


## Analysis Workspace components

Components in Analysis Workspace consist of metrics, dimensions, segments, and date ranges that you can drag-and-drop onto panels and visualizations in your Workspace project. Custom components that you create are added to these panels, such as a calculated metric, or a custom date range.

To access the Components panel, select ![Curate](/help/assets/icons/Curate.svg) **[!UICONTROL Components]** in the button panel. 

![Workspace panel highlighting the Components icon in the left-rail](assets/components.png)

See [Create a project](/help/analysis-workspace/home.md) for information on how to use components in a project.


## Manage components {#actions}

You can quickly create a new component using the **[!UICONTROL Components]** menu in Analysis Workspace. See the [Analysis Workspace menu](/help/analysis-workspace/home.md#menu) for more details.

You can manage components (individually or by selecting more than one). 

1. Select one or more components.

1. From the context menu, or from the ![MoreVertical](/help/assets/icons/MoreVertical.svg) Component actions button (at the top of Components), select one of the following actions.
   

   >[!TIP]
   >
   >You can select multiple components by holding **[!UICONTROL Shift]**, or by holding **[!UICONTROL Command]** (on macOS) or **[!UICONTROL Ctrl]** (on Windows).


   ![Component Actions list showing Tag, Favorite, approve, Share, and Delete.](assets/component-menu.gif){width=100%}

   | Component action | Description |
   |--- |--- |
   | ![Label](/help/assets/icons/Label.svg) [!UICONTROL **Tag**] | Organize or manage components by applying tags to them. You can then search by tag in the left panel by selecting the ![Filter](/help/assets/icons/Filter.svg) filter or typing `#`. Tags also act as filters in the component managers. |
   | ![Star](/help/assets/icons/Star.svg) [!UICONTROL **Favorite**] | Add the component to your list of favorites. Like tags, you can search by Favorites in the left panel and filter by them in the component managers. |
   | ![StarOutline](/help/assets/icons/StarOutline.svg) **[!UICONTROL Un-favorite]** | Remove the component from your list of favorites. |
   | ![Checkmark](/help/assets/icons/Checkmark.svg) [!UICONTROL **Approve**] | Mark components as Approved to signal to your users that the component is organization-approved. Like tags, you can search and filter by Approved in the left panel. A ![Checkmark](/help/assets/icons/Checkmark.svg) identifies approved components. |
   | ![Share](/help/assets/icons/ShareAlt.svg) [!UICONTROL **Share**] | Share components to users in your organization. This option is available for custom components only, such as segments or calculated metrics. |
   | ![Delete](/help/assets/icons/Delete.svg) [!UICONTROL **Delete**] | Delete components that you no longer need. This option is available for custom components only, such as segments or calculated metrics. |

Custom components can also be managed through their respective Component managers. For example, see [Manage segments](/help/components/filters/manage-filters.md).

## Manage the component list

You can search, filter, and sort the component list in the left panel of Analysis Workspace to locate a particular component. 

### Search

1. Select **Components** ![Components icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) in the left panel.

2. In the search field, begin typing the name of the component you want to use in your project.

   A color and icon identify the type of component. **Dimensions** ![Dimension icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) are orange, **Filters** ![Filter icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) are blue, **Date ranges** ![Date range icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) are purple, and **Metrics** ![Metric icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) are green.<br/>The Adobe icon ![AdobeLogo](/help/assets/icons/AdobeLogoSmall.svg) indicates either a calculated metric template or a segment template. The calculator icon ![Calculator icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg) indicates a calculated metric that an administrator in your organization has created. 

3. Select the component from the drop-down list.

### Filter

1. Select the **Components** icon ![Components icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) in the left panel.

2. Select **Filter** ![Data Dictionary Filter icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg), or enter `#` in the search field.

3. Select any of the following filter options to filter the list of components:

   | Icon | Filter option | Description |
   |---------|---|----------|
   | ![Checkmark](/help/assets/icons/Checkmark.svg) | **[!UICONTROL Approved]** | Show only components that are marked as Approved by an administrator. |
   | ![Star](/help/assets/icons/Star.svg) | **[!UICONTROL Favorites]**| Show only components that are in your list of Favorites. <br/>For information about adding components to your list of favorites, see [Manage components](#manage-components). |
   | ![Dimensions](/help/assets/icons/Dimensions.svg) | **[!UICONTROL Dimensions]** | Show only components that are Dimensions. |
   | ![Event](/help/assets/icons/Event.svg) | **[!UICONTROL Metrics]** | Show only components that are Metrics. |
   | ![Segmentation](/help/assets/icons/Segmentation.svg)| **[!UICONTROL Filters]** | Show only components that are Filters. |
   | ![Calendar](/help/assets/icons/Calendar.svg) | **[!UICONTROL Date ranges]** | Show only components that are Date ranges. |
   | ![Label](/help/assets/icons/Label.svg) | **[!UICONTROL *Tag name*]** | Show only components with the specific selected tags. A dedicated tag is available for Adobe Template which are the [default calculated metrics](/help/components/calc-metrics/default-calcmetrics.md) from Adobe. |

   Select ![CrossSize75](/help/assets/icons/CrossSize75.svg) in a filter to remove the filter.

4. You can optionally sort the component list, as described in [Sort the component list](#sort-the-component-list).

### Sort

<!-- {{release-limited-testing-section}}-->

1. (Optional) Apply any filters to the component list, as described in [Filter the component list](#filter-the-component-list).

2. Select **Components** ![Components icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) in the left panel.

3. Select **Sort** ![Sort components icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg), then select any of the following filter options to sort the list of components.

The following sort options are available:

{{components-sort-options}}

## Access permissions

In Analysis Workspace, administrators can [curate](/help/analysis-workspace/curate-share/curate.md) which components are exposed to users in reporting.
