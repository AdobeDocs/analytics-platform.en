---
title: What are components in Customer Journey Analytics?
description: Learn what components CJA offers, and how you can use them in reporting.
exl-id: f9b0b3c2-7c88-4bef-af33-0d309cafe799
solution: Customer Journey Analytics
feature: Components
---
# Components overview

Components are features in Customer Journey Analytics that can be used in reports, or to complement reporting features. You can manage these components using the following steps:

1. Log in to [analytics.adobe.com](https://analytics.adobe.com) using your Adobe ID credentials.
2. Navigate to [!UICONTROL Components] > [!UICONTROL Components] in the header menu.

You can manage the following components:

* [**Annotations**](/help/components/annotations/overview.md): Communicate contextual data nuances and insights to your organization.
* [**Filters**](filters/filters-overview.md): Exclude parts of your data to focus on common dimension items
* [**Calculated metrics**](calc-metrics/calc-metr-overview.md): Use metrics and formulas as new components for use in reporting
* [**Date ranges**](date-ranges/overview.md): Customize and refine the date ranges Analysis Workspace offers
* [**Projects**](/help/analysis-workspace/home.md): Organize and maintain your projects in Analysis Workspace

## Analysis Workspace components

Components in Analysis Workspace consist of metrics, dimensions, filters, and time granularities that you can drag-and-drop onto a project. Custom components that you create are added to these panels, such as custom date ranges.

To access the Components panel, click the **[!UICONTROL Components]** icon in the left rail. You can switch among Panels (Blank panel, [Freeform panel](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md), [Quick Insights](/help/analysis-workspace/c-panels/quickinsight.md), or [Attribution IQ](/help/analysis-workspace/c-panels/attribution.md) panel), [Visualizations](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md), and Components using the left-rail icons or by using [hotkeys](/help/analysis-workspace/build-workspace-project/fa-shortcut-keys.md).

![](assets/components.png)

See [Create a project](/help/analysis-workspace/home.md) for information about using Components in a project.

## Component actions

You can manage components (individually or by selecting more than one) in a number of ways. Right-click a component or click **[!UICONTROL Actions]** at the top of the component list.

>[!NOTE]
>
>These actions do not apply to Time components.

| Component Action | Description |
| --- | --- |
| Tag | Organize or manage components by applying tags to them. It then shows up in the respective component manager, such as [!UICONTROL Analytics] > [!UICONTROL Components] > [!UICONTROL Filters], or [!UICONTROL Analytics] > [!UICONTROL Components] > [!UICONTROL Projects] |
| Favorite | Add the component to your list of favorites. It then shows up in the respective component manager, such as [!UICONTROL Analytics] > [!UICONTROL Components] > [!UICONTROL filters], or [!UICONTROL Analytics] > [!UICONTROL Components] > [!UICONTROL Projects]. |
| Approve | Approve the component to make it canonical. It then shows up in the respective component manager, such as [!UICONTROL Analytics] > [!UICONTROL Components] > [!UICONTROL Filters], or  [!UICONTROL Analytics] > [!UICONTROL Components] > [!UICONTROL Projects]|
| Share | Applies only to filters. |
| Delete | Applies only to filters. |

Watch the video on Creating Metrics, Filters, and Dates:

>[!VIDEO](https://video.tv.adobe.com/v/23979)

## Manage components {#actions}

You can manage components directly in the left rail. 

1. Right-click a component.

   Or
   
   Select a component, then select the **Action** (3-dot) icon at the top of the component list.

   >[!TIP]
   >
   >   You can select multiple components by holding Shift, or by holding Command (on Mac) or Ctrl (on Windows).


   ![](assets/component-actions.png)

   | Component action | Description |
   |--- |--- |
   | [!UICONTROL **Tag**] | Organize or manage components by applying tags to them. You can then search by tag in the left rail by clicking the filter or typing #. Tags also act as filters in the component managers. |
   | [!UICONTROL **Favorite**] | Add the component to your list of favorites. Like tags, you can search by Favorites in the left rail and filter by them in the component managers. |
   | [!UICONTROL **Approve**] | Mark components as Approved to signal to your users that the component is organization-approved. Like tags, you can search by Approved in the left rail and filter by them in the component managers. |
   | [!UICONTROL **Share**] | Share components to users in your organization. This option is available for custom components only, such as filters or calculated metrics. |
   | [!UICONTROL **Delete**] | Delete components that you no longer need. This option is available for custom components only, such as filters or calculated metrics. |

Custom components can also be managed through their respective Component managers. For example, the [Manage filters](/help/components/filters/manage-filters.md).

## Search, filter, and sort the component list

You can search, filter, and sort the component list in the left rail of Analysis Workspace to quickly locate a particular component. 

### Search the component list

1. Select the **Components** icon ![Components icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) in the left rail.

2. In the search field, begin typing the name of the component you want to use in your project.

   The type of component can be identified by both color and icon. **Dimensions** ![Dimension icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) are orange, **Filters** ![Filter icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) are blue, **Date ranges** ![Date range icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) are purple, and **Metrics** ![Metric icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) are green. The Adobe icon ![Adobe icon](assets/default-calc-metric-icon.png) indicates either a calculated metric template or a filter template, and the calculator icon ![Calculator icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg) indicated a calculated metric that was created by an Analytics administrator in your organization. 

3. Select the component when it appears in the drop-down list.

### Filter the component list

1. Select the **Components** icon ![Components icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) in the left rail.

2. Select the **Filter** icon ![Data Dictionary Filter icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg)).

   Or

   Type the pound sign (#) in the search field.

3. Select any of the following filter options to filter the list of components:

   |Option | Function |
   |---------|----------|
   | [!UICONTROL **Approved**] | Show only components that are marked as Approved by an administrator. |
   | [!UICONTROL **Favorites**] | Show only components that are in your list of Favorites. For information about adding components to your list of favorites, see [Manage components](#manage-components). |
   | [!UICONTROL **Dimensions**] | Show only components that are Dimensions. |
   | [!UICONTROL **Metrics**] | Show only components that are Metrics. |
   | [!UICONTROL **Filters**] | Show only components that are Filters. |
   | [!UICONTROL **Date ranges**] | Show only components that are Date Ranges. |
   | [!UICONTROL **Show all**] | Show all components. This option is available only for administrators. |
   | [!UICONTROL **Unapproved**] | Show only components that are not yet marked as Approved by an administrator. As an administrator, this is helpful when identifying components that require your review and approval. This option is available only for administrators. |

4. (Optional) To further hone the list, you can sort the component list, as described in [Sort the component list](#sort-the-component-list).

### Sort the component list

1. (Optional) Apply any filters to the component list, as described in [Filter the component list](#filter-the-component-list).

2. Select the **Components** icon ![Components icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) in the left rail.

3. Select the **Sort** icon ![Sort components icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg), then select any of the following filter options to sort the list of components:

   {{components-sort-options}}

## Component access permissions

In Analysis Workspace, Admins can [curate](/help/analysis-workspace/curate-share/curate.md) which components are exposed to users in reporting.
