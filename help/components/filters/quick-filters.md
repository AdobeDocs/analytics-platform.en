---
description: Use quick filters in Analysis Workspace for Customer Journey Analytics
title: Quick filters
feature: CJA Workspace Basics
role: User, Admin
exl-id: 549e5db5-fcdf-43c5-bc43-590144aee309
---
# Quick filters

You can create quick filters within a project to bypass the complexity of the full [Filter Builder](/help/components/filters/create-filters.md). Quick filters

* Apply as [project-only filters](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/quick-filters.html?lang=en#project-only).
* Allow for up to 3 rules
* Do not accommodate nested containers, or sequential rules.

For a comparison of what quick filters can do vs. full-fledged component-list filters, go [here](/help/components/filters/filters-overview.md).

Here is a video on quick filters (note that it uses the term "quick segments" instead.) However, the functionality is the same.

>[!VIDEO](https://video.tv.adobe.com/v/341466/?quality=12&learn=on)

## Prerequisites {#prereqs}

Anyone can create a quick filter. However, you need the Filter Creation permission in the [Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/summary-tables.html?lang=en#analytics-tools) to be able to save a quick filters or to open it in the Filter Builder.

## Create quick filters {#create}

In a Freeform table, click the filter+ icon in the panel header:

![Segment filter](assets/quick-seg1.png)

| Setting | Description |
| --- | --- |
| [!UICONTROL Name] | The default name of a filter is a combination of the rule names in the filter. You can rename the filter to a more friendly name. |
| [!UICONTROL Include/exclude] | You can either include or exclude components in your filter definition, but not both. |
| [!UICONTROL Hit/Visit/Visitor] container | Quick filters include one [filter container](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/filters-overview.html?lang=en#filter-containers) only that lets you include a dimension/metric/date range in (or exclude it from) the filter. [!UICONTROL Visitor] contains overarching data specific for the visitor across visits and page views. A [!UICONTROL Visit] container lets you set rules to break down the visitor’s data based on visits, and a [!UICONTROL Hit] container lets you break down visitor information based on individual page views. The default container is [!UICONTROL Hit]. |
| [!UICONTROL Components] (Dimension/metric/date range) | Define up to 3 rules by adding components (dimensions, metrics, date ranges, or dimension values). There are 3 ways to find the right component:<ul><li>Start typing and the [!UICONTROL Quick Filter] builder automatically finds the appropriate component.</li><li>Use the drop-down list to find the component.</li><li>Drag and drop components from the left rail.</li></ul>  |
| [!UICONTROL Operator] | Use the drop-down menu to find standard operators and [!UICONTROL Distinct Count] operators. See [Filter operators](operators.md). |
| Plus (+) sign | Add another rule |
| AND/OR qualifiers | You can add "AND" or "OR" qualifiers to the rules, but you cannot mix "AND" and "OR" in a single filter definition. |
| [!UICONTROL Apply] | Apply this filter to the panel. If the filter contains no data, you will be asked if you want to continue. |
| [!UICONTROL Open builder] | Opens the Filter Builder. Once you save or apply the filter in the Filter Builder, it is no longer considered a "Quick Filter". It becomes part of the component-list filter library. |
| [!UICONTROL Cancel] | Cancel this quick filter - don't apply it. |
| [!UICONTROL Date range] | The validator uses the panel date range for its data lookup. But any date range applied in a quick filter overrides the panel date range at the top of the panel.  |
| Preview (top right) | Lets you see whether you have a valid filter and how broad the filter is. Represents the breakdown of the data set you can expect to see when you apply this filter. You might get a notice that indicates that this filter has no data. In this case, you can proceed or change the filter definition. |

Here is an example of a filter that combines dimensions and metrics:

![Filter definition example](assets/quick-seg2.png)

The filter appears at the top. Notice its blue-striped sidebar, as opposed to the blue sidebar for component-level filters in the filter library on the left.

![Filter component locations](assets/quick-seg3.png)

## Edit quick filters {#edit}

1. Hover over the quick filter and select the pencil icon.
1. Edit the filter definition or the filter name.
1. Click [!UICONTROL Apply].

## Save quick filters {#save}

You can choose to save quick filters either in the [!UICONTROL Quick Filter Builder] or in the [!UICONTROL Filter Builder].

>[!IMPORTANT]
>Once you save or apply the filter, you can no longer edit it in the Quick Filter Builder, only in the regular Filter Builder.

### Save in Quick Filter builder {#save2}

1. Once you have applied the quick filter, hover over it and select the info ("i") icon.
1. Click **[!UICONTROL Make available to all projects and add to your component list]**.
1. (Optional) Rename the filter.
1. Click **[!UICONTROL Save]**.

Notice how the filter's side bar changes from striped blue to a lighter blue. It now appears in your component list in the left rail.

### Save in Filter Builder {#save3}

1. Hover over the quick filter and select the info ("i") icon.
1. Select **[!UICONTROL Save filter]**
1. Leave the name as is or rename the filter.

   Go back to Workspace and notice how the filter now has a light blue sidebar. This indicates it can no longer be edited/opened in the Quick Filter Builder. And by saving it, it becomes part of the component list.

   ![Filter component list](assets/quick-seg4.png)

After you have applied the filter, you can choose to add it to your filter component list and make it available to all your projects.

1. Hover over the saved filter and select the pencil icon.

1. At the top of the Filter Builder, notice this dialog:

   ![Filter dialog](assets/project-only.png)

1. Select the checkbox next to **[!UICONTROL Make available to all your projects and add to your component list.]**
1. Click **[!UICONTROL Save]**.
1. The filter now appears in your filter component list for all your projects.
1. You can also [share the filter](/help/components/filters/manage-filters.md) with other people in your organization.

## What are project-only filters? {#project-only}

Project-only filters are filters that only apply to the current project they were created in. They are not available in other projects and cannot be shared to other users. They are intended for quick exploration of your data without having to create and save a filter in the left rail. Project-only filters can be created in the panel drop zone either with Quick filters or [ad-hoc filters](/help/components/filters/ad-hoc-filters.md). 

If you open a project-only filter in the [!UICONTROL Filter Builder], a project-only notification appears. If you do not check "Make this filter available.." and click **[!UICONTROL APPLY]**, the segment remains a project-only segment. 

>[!NOTE]
>
>If you apply a Quick filter from the Filter Builder, it can no longer be opened in the [!UICONTROL Quick Filter Builder]. 

![Project only unchecked](assets/project-only-unchecked.png)

If you check "Make this filter available.." and click **[!UICONTROL SAVE]**, the filter becomes available in the left rail component list for use in other projects. It can also be shared with other users from the Filter Manager.

![Project only checked](assets/project-only-checked.png)

