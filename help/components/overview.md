---
title: Components overview
description: Learn what components CJA offers, and how you can use them in reporting.
---

# Components overview

Components are features in Customer Journey Analytics that can be used in reports, or complement reporting features. You can manage these components using the following steps:

1. Log in to [analytics.adobe.com](https://analytics.adobe.com) using your Adobe ID credentials.
2. Navigate to [!UICONTROL Components] > [!UICONTROL Components] in the header menu.

You can manage the following components:

* [**Filters**](filters/filters-overview.md): Exclude parts of your data to focus on common dimension items
* [**Calculated metrics**](calc-metrics/calc-metr-overview.md): Use metrics and formulas as new components for use in reporting
* [**Date ranges**](date-ranges/overview.md): Customize and refine the date ranges Analysis Workspace offers
* [**Projects**](/help/analysis-workspace/home.md): Organize and maintain your projects in Analysis Workspace

## Analysis Workspace components

Components in Analysis Workspace consist of metrics, dimensions, segments, and time granularities that you can drag-and-drop onto a project. Custom components that you create are added to these panels, such as custom date ranges.

To access the Components panel, click the **[!UICONTROL Components]** icon in the left rail. You can switch among Panels (Blank panel, [Freeform panel](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md), [Quick Insights](/help/analysis-workspace/c-panels/quickinsight.md), or [Attribution IQ](/help/analysis-workspace/c-panels/attribution.md) panel), [Visualizations](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md), and Components using the left-rail icons or by using [hotkeys](/help/analysis-workspace/build-workspace-project/fa-shortcut-keys.md).

![](assets/components.png)

See [Create a project](/help/analysis-workspace/home.md) for information about using Components in a project.

## Component actions

You can manage components (individually or by selecting more than one) in a number of ways. Right-click a component or click **[!UICONTROL Actions]** at the top of the component list.

>[!NOTE]
>
>These actions do not apply to Time components.

| Component Action | Description |
|--- |--- |
|Tag|Organize or manage components by applying tags to them. It then shows up in the respective component manager, such as  Analytics >  Components >  Segments, or  Analytics >  Components >  Projects|
|Favorite|Add the component to your list of favorites. It then shows up in the respective component manager, such as  Analytics >  Components >  Segments, or  Analytics >  Components >  Projects.|
|Approve|Approve the component to make it canonical. It then shows up in the respective component manager, such as  Analytics >  Components >  Segments, or  Analytics >  Components >  Projects|
|Share|Applies only to segments.|
|Delete|Applies only to segments.|

Watch the video on Creating Metrics, Segments, and Dates:

>[!VIDEO](https://video.tv.adobe.com/v/23979)

## Component access permissions

Admins can curate (via [Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=en#manage-users-and-products)) which components are exposed to users in reporting. The following table shows how these component access permissions behave:

| Curation type | Admin can see | Non-admin project owner (or edit role) can see | Non-admin duplicate role |
| --- | --- | --- | --- |
| **Components "hidden" from a data view** | All data view components available for reporting (hidden components require clicking "Show all") | Not available for reporting | Not available for reporting |
| **Components added or removed from a data view** | Only components added to the data view (hidden or not hidden). Admins cannot report on fields or components that are not defined by the data view. | Only components added to the data view, or components owned by or shared with the user. Hidden components are not available (like VRS curation). | Only components added to the DV, are not hidden and have been included in the Project curation. | 
| **Curated components in a Project** | All data view components available for reporting (hidden components require clicking "Show all") | All non-hidden data view components (requires clicking "show all") | Only curated components, plus any components owned or shared with the user |
| **Curated Project using a data view with hidden components** | All data components available for reporting (hidden and non-curated components require clicking "Show all")| All non-curated project components, all non-hidden data view components, and any components owned by or shared with the user | Only curated components, plus any components owned by or shared with the user |

