---
title: Filters manager
description: lean how to manage filters in Customer Journey Analytics
exl-id: b8869560-0cf1-4e5d-a03c-dfca85d05e66
feature: Filters
role: User
---
# Manage filters


You can share, filter, tag, approve, rename, copy, delete, export filters and mark filters as favorite from a central [!UICONTROL Filters] management interface. To manage filters:

* Select **[!UICONTROL Components]** in the main interface, then select **[!UICONTROL Filters]**.


>[!NOTE]
>
>The quick filters that you create within a specific Workspace project do not appear in the [!UICONTROL Filters] manager, unless you have made the filter available to all your projects. 
>

## Filters manager

The Filters manager has the following interface elements:

![Filters interface](assets/filters-manager.png)

### Filters list

The filters list ➊ displays all the filters that you own, the filters that have been scoped to all your projects, and the filters that have been shared with you. The list has the following columns:

| Column | Description |
| --- | --- | 
| ![StarOutline](/help/assets/icons/StarOutline.svg)  | Select to favor ![Star](/help/assets/icons/Star.svg) or un-favor ![StarOutline](/help/assets/icons/StarOutline.svg) a filter. See [Mark filter as favorite](/help/components/filters/filters-favorite.md) |
| **[!UICONTROL Title and description]** | Provided in the [Filter builder](filter-builder.md). To edit the title and description, select the title link. This opens the [Filters builder](filter-builder.md). A shared filter is indicated with ![Share](/help/assets/icons/Share.svg). |
| **[!UICONTROL Data view]** | The data views that this filter applies to.  | 
| **[!UICONTROL Owner]** | Indicates who owns the annotation. As a user, you only see the annotations that you own or the annotations that are shared with you. |
| **[!UICONTROL Tags]** | Lists the tags for this annotation. |
| **[!UICONTROL Shared with]** | Lists how many individuals or groups that you shared the annotation with. Select to open the **[!UICONTROL Share Component]** dialog and modify the tags for the annotation. |
| **[!UICONTROL Date modified]** | Displays the date and time that the annotation was last modified. |
| **[!UICONTROL Used in]** | Displays the components the filter is used in. When you select **[!UICONTROL x Components]**, a new browser tab opens that shows the [Project manager](/help/analysis-workspace/build-workspace-project/freeform-overview.md) filtered to only show projects for the components used.  |
| **[!UICONTROL Last Used]** | Displays when the filter was last used. |

{style="table-layout:auto"}

Use ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) to specify which columns you want to display.

### Action bar

You can action on filters using the action bar ➋. The action bar contains the following actions:

| Action | Description |
|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]** | Add another filters, using the [Filter builder](filter-builder.md). |
| ![Search](/help/assets/icons/Search.svg) [!UICONTROL *Search by title*] | When no filter is selected in the list, search for filters using this search field. |
| ![Label](/help/assets/icons/Label.svg) **[!UICONTROL Tag]** | Tag the selected filters. In the **[!UICONTROL Tag Filter]** dialog, select or de-select the tags for the selected filters. Select **[!UICONTROL Save]** to save the tags for the selected filters. See [Tag filters](/help/components/filters/filters-tag.md) for more information.|
| ![Share](/help/assets/icons/Share.svg) **[!UICONTROL Share]** | Share the selected filters. In the **[!UICONTROL Share Filter]** dialog, you can ![Search](/help/assets/icons/Search.svg) *Search individuals or groups* or you can select **[!UICONTROL Organization]** or **[!UICONTROL Groups]**. Select **[!UICONTROL Save]** to save share details for the selected filters. See [Share filters](filters-share.md) for more details. |
| ![Delete](/help/assets/icons/Delete.svg) **[!UICONTROL Delete]** | Delete the selected filters. You are prompted for a confirmation. |
| ![Edit](/help/assets/icons/Edit.svg) **[!UICONTROL Rename]** | Rename a single selected filter. When selected, you can rename the filter inline. |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Approve]** | Approve the selected filters. | 
| ![Copy](/help/assets/icons/Copy.svg)  **[!UICONTROL Copy]** | Copy the selected filter. New filters are created with the same name and suffix (Copy) | 
| ![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Export to CSV]** | Export the filters to an `Filters List.csv` file. |

### Active filter bar

The filter bar ➌ shows the active filters applied from the filter panel to the list of filters (if any). You can quickly remove a filter using ![CrossSize75](/help/assets/icons/CrossSize75.svg). If more than one filter is specified, you can remove all filters using **[!UICONTROL Remove all]**.

### Filter panel

You can filter the list of filters using the ![Filter](/help/assets/icons/Filter.svg) **[!UICONTROL Filter]** left panel ➍. The filter panel displays the type of filter and the number of filters that honor the specific filter. Select ![Filter](/help/assets/icons/Filter.svg) to toggle the display of the filter panel. 

See [Filter the list of filters](filters-filter.md) for more information.
