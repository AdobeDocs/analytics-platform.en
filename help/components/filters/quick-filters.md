---
description: Use quick filters in Analysis Workspace.
title: Quick filters
feature: Workspace Basics
role: User, Admin
exl-id: 549e5db5-fcdf-43c5-bc43-590144aee309
---
# Quick filters

You can create quick filters within a project to bypass the complexity of the full [Filter Builder](/help/components/filters/create-filters.md). Quick filters

* Apply to specific projects only (you can change this). 
* Allow for up to 3 rules
* Do not accommodate nested containers, or sequential rules.
* Do work in panels with multiple report suites

For a comparison of what quick filters can do vs. full-fledged component-list filters, go [here](/help/components/filters/filters-overview.md). 

>[!IMPORTANT]
> Quick filters are currently in limited testing and are not generally available yet.

## Prerequisites

Users need the [!UICONTROL Segment Creation] permission in the [Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/summary-tables.html?lang=en#analytics-tools) to be able to create quick filters.

## Create quick filters

In a Freeform table, click the filter+ icon in the panel header: 

![](assets/quick-seg1.png)

| Setting | Description |
| --- | --- |
| Name | The default name of a filter is a combination of the rule names in the filter. You can rename the filter. |
| Include/exclude | You can either include or exclude components in your filter definition, but not both. |
| Hit/Visit/Visitor container | Quick filters include one [filter container](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/filters-overview.html?lang=en#filter-containers) only that lets you include a dimension/metric/date range in (or exclude it from) the filter. [!UICONTROL Visitor] contains overarching data specific for the visitor across visits and page views. A [!UICONTROL Visit] container lets you set rules to break down the visitor’s data based on visits, and a [!UICONTROL Hit] container lets you break down visitor information based on individual page views. The default container is [!UICONTROL Hit]. |
| Components (Dimension/metric/date range) | Define up to 3 rules by adding components dimensions and/or metrics and/or date ranges and their values. There are 3 ways to find the right component:<ul><li>Start typing and the [!UICONTROL Quick Filter] builder automatically finds the appropriate component.</li><li>Use the drop-down list to find the component.</li><li>Drag and drop components from the left rail.</li></ul>  |
| Operator | Use the drop-down menu to find standard operators and [!UICONTROL Distinct Count] operators. [Learn more](https://experienceleague.adobe.com/docs/analytics/components/filteration/segment-reference/seg-operators.html?lang=en) |
| Plus (+) sign | Add another rule |
| AND/OR qualifiers | You can add "AND" or "OR" qualifiers to the rules, but you cannot mix "AND" and "OR" in a single filter definition. |
| Apply | Apply this filter to the panel. If the filter contains no data, you will be asked if you want to continue. |
| Open builder | Opens the Filter Builder. Once you save the filter in the Filter Builder, it is no longer considered a "Quick Filter". It becomes part of the component-list filter library. |
| Cancel | Cancel this quick filter - don't apply it. |
| Date range | The validator uses the panel date range for its data lookup. But any date range applied in a quick filter overrides the panel date range at the top of the panel.  |
| Preview (top right) | Lets you see whether you have a valid filter and how broad the filter is. Represents the breakdown of the data set you can expect to see when you apply this filter. you might get a notice that indicates that this filter has no data. You can proceed or change the filter definition. |

Here is an example of a filter that combines dimensions and metrics:

![](assets/quick-seg2.png)

The filter appears at the top. Notice its blue-striped sidebar, as opposed to the blue sidebar for component-level filters in the filter library on the left.

![](assets/quick-seg3.png)

## Edit quick filters

1. Hover over the quick filter and select the pencil icon.
1. Edit the filter definition or the filter name.

## Save quick filters

You can choose to save quick filters either in the [!UICONTROL Quick Filter Builder] or in the [!UICONTROL Filter Builder].

>[!IMPORTANT]
>Once you save or apply the filter, you can no longer edit it in the Quick Filter Builder, only in the regular Filter Builder.

### Save in Quick Filter builder

1. Once you have applied the quick filter, hover over it and select the info ("i") icon.
1. Click **[!UICONTROL Make available to all projects and add to your component list]**.
1. (Optional) Rename the filter.
1. Click **[!UICONTROL Save]**.

Notice how the filter's side bar changes from striped blue to blue. It now appears in your component list in the left rail.

### Save in Filter Builder

1. Hover over the quick filter and select the info ("i") icon.
1. Select **[!UICONTROL Save filter]**
1. Leave the name as is or rename the filter.

   Go back to Workspace and notice how the filter now has a blue sidebar. This indicates it can no longer be edited/opened in the Quick Filter Builder. And by saving it, it becomes part of the component list.

   ![](assets/quick-seg4.png)

After you have applied the filter, you can choose to add it to your filter component list and make it available to all your projects. 

1. Hover over the saved filter and select the pencil icon.

1. At the top of the Filter Builder, notice this dialog:

   ![](assets/project-only.png)

1. Select the checkbox next to **[!UICONTROL Make available to all your projects and add to your component list.]**
1. Click **[!UICONTROL Save]**.
1. The filter now appears in your filter component list for all your projects.
1. You can also [share the filter](/help/components/filters/manage-filters.md) with other people in your organization.

## What are project-only filters?

Project-only filters are either quick filters or ad-hoc Workspace project filters. When editing/opening them in the [!UICONTROL Filter Builder], the project-only box will show up. If you APPLY a quick filter in the builder but don’t check the make available box, then it is still a project-only filter but it can no longer be opened in the [!UICONTROL Quick Filter Builder]. If you check the box and click **[!UICONTROL SAVE]**, it is now a component-list filter.
