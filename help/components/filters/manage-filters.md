---
title: Filters manager
description: Learn how to manage filters in Customer Journey Analytics
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
| **[!UICONTROL Title and description]** | To edit the filter, select the title link, which opens the [Filters builder](filter-builder.md). A shared filter is indicated with ![Share](/help/assets/icons/Share.svg). |
| **[!UICONTROL Data view]** | The data views that this filter applies to.  | 
| **[!UICONTROL Owner]** | The owner of the filter. As a user, you only see the filters that you own or the annotations that are shared with you. |
| **[!UICONTROL Tags]** | The tags for this filter. |
| **[!UICONTROL Shared with]** | How many individuals or groups that you shared the filter with. Select to open the **[!UICONTROL Share Component]** dialog. See [Share filters](filters-share.md) for more information. |
| **[!UICONTROL Date modified]** | The date and time that the filter was last modified. |
| **[!UICONTROL Used in]** | Show where filters are currently being used, and how many times they are being used in each area. <p>For example, if the filter is being used in 40 projects and 2 alerts, then the value of this column shows as [!UICONTROL **42 components**].</p> <p>Select the value in this column to see the breakdown of where the filters are being used (for example, [!UICONTROL **Projects (40)**], [!UICONTROL **Mobile Scorecards (2)**]). Furthermore, you can view the list of items where the filters are being used. For example, so see the list of projects where they are being used, select the [!UICONTROL **Projects (40)**] link.</p><p>Each of the following areas shows the number of instances of filters being used in that area:</p>  <ul><li>[!UICONTROL **Projects**]<p>Contains filters that were [created in the filter builder](/help/components/filters/filter-builder.md#) and are available for all projects.</p></li><li>[!UICONTROL **Ad hoc components**]<p>Contains filters that were [created as quick filters](/help/components/filters/quick-filters.md) and are available only within a single project.</p></li><li>[!UICONTROL **Scheduled projects**]</li><li>[!UICONTROL **Mobile Scorecards**]</li><li>[!UICONTROL **Annotations**]</li><li>[!UICONTROL **Calculated metrics**]</li><li>[!UICONTROL **Report Builder**]<p>Selecting this option downloads a CSV file with the following columns of data:</p><ul><li>Report Builder Name</li><li>Last accessed</li><li>Last accessed IMS User ID</li><li>Last accessed user name</li></ul></li></ul><p>This information helps you to determine whether a component is valuable to users in your organization, where the component is used, and if the component needs to be deleted or modified.</p><p>Consider the following when viewing this column:</p><ul><li>This information is available only to system administrators.</li><li>The [!UICONTROL **Used in**] column does not display by default. Use ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) to display it.</li><li>This information does not include usage from the API or Data Warehouse.</li><li>If there is no data in this column for a given component but the component has a [!UICONTROL **Last used**] date, the component might have been used in an analysis without being saved.</li><li>Usage information is available starting in September 2023.</li></ul><p>You can use the [Data Dictionary](/help/components/data-dictionary/data-dictionary-overview.md) along with this information to help you keep track of and better understand how components are being used in your organization.</p>  |
| **[!UICONTROL Last Used]** | When the filter was last used. |

{style="table-layout:auto"}

Use ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) to specify which columns you want to display.

### Action bar

You can action on filters using the action bar ➋. The action bar contains the following actions:

| Action | Description |
|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]** | Add another filters, using the [Filter builder](filter-builder.md). |
| ![Search](/help/assets/icons/Search.svg) [!UICONTROL *Search by title*] | When no filter is selected in the list, search for filters using this search field. |
| ![Label](/help/assets/icons/Label.svg) **[!UICONTROL Tag]** | Tag the selected filters. In the **[!UICONTROL Tag Filter]** dialog, select or de-select the tags for the selected filters. Select **[!UICONTROL Save]** to save the tags for the selected filters. See [Tag filters](/help/components/filters/filters-tag.md) for more information.|
| ![Share](/help/assets/icons/Share.svg) **[!UICONTROL Share]** | Share the selected filters. In the **[!UICONTROL Share Filter]** dialog, you can ![Search](/help/assets/icons/Search.svg) *Search individuals or groups* or you can select **[!UICONTROL Organization]** or **[!UICONTROL Groups]**. Select **[!UICONTROL Save]** to save share details for the selected filters. See [Share filters](filters-share.md) for more information. |
| ![Delete](/help/assets/icons/Delete.svg) **[!UICONTROL Delete]** | Delete the selected filters. You are prompted for a confirmation. |
| ![Edit](/help/assets/icons/Edit.svg) **[!UICONTROL Rename]** | Rename a single selected filter. When selected, you can rename the filter inline. |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Approve]** | Approve the selected filters. See [Approve filters](filters-approve.md) for more information. | 
| ![Copy](/help/assets/icons/Copy.svg)  **[!UICONTROL Copy]** | Copy the selected filter. New filters are created with the same name and suffix `(Copy)`. | 
| ![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Export to CSV]** | Export the filters to a `Filters List.csv` file. |

### Active filter bar

The filter bar ➌ shows the active filters applied from the filter panel to the list of filters (if any). You can quickly remove a filter using ![CrossSize75](/help/assets/icons/CrossSize75.svg). If more than one filter is specified, you can remove all filters using **[!UICONTROL Remove all]**.

### Filter panel

You can filter the list of filters using the ![Filter](/help/assets/icons/Filter.svg) **[!UICONTROL Filter]** left panel ➍. The filter panel displays the type of filter and the number of filters that honor the specific filter. Select ![Filter](/help/assets/icons/Filter.svg) to toggle the display of the filter panel. 

See [Filter the list of filters](filters-filter.md) for more information.
