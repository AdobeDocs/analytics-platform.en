---
title: Manage annotations
description: How to manage annotations in Workspace.
feature: Components
exl-id: 12f2cc2f-477c-4f16-afdd-b0db84725b32
role: User
---
# Manage annotations

You can share, filter, tag, approve, copy, delete annotations and mark annotations as favorite from a central [!UICONTROL Annotations] management interface. To manage annotations:

* Select **[!UICONTROL Components]** in the main interface, then select **[!UICONTROL Annotations]**.


>[!NOTE]
>
>The annotations that you create within a specific Workspace project do not appear in the [!UICONTROL Annotations] manager, unless you have made the annotation available to all your projects. 
>

## Annotations manager

The Annotations manager has the following interface elements:

![Annotations interface](assets/annotations-manager.png)

### Annotations list

The annotations list ➊ displays all the annotations that you own, the annotations that have been scoped to all your projects, and the annotations that have been shared with you. The list has the following columns:

| Column | Description |
| --- | --- | 
| ![StarOutline](/help/assets/icons/StarOutline.svg)  | Select to favor ![Star](/help/assets/icons/Star.svg) or un-favor ![StarOutline](/help/assets/icons/StarOutline.svg) an annotation. |
| **[!UICONTROL Title and description]** | Provided in the Annotations Builder. To edit the title and description, select the title link - opens the [Annotations builder](/help/components/annotations/create-annotations.md#annotation-builder). A shared annotation is indicated with ![Share](/help/assets/icons/Share.svg).   |
| **[!UICONTROL Data view]** | The data views that this annotation applies to.  | 
| **[!UICONTROL Owner]** | Indicates who owns the annotation. As a user, you only see the annotations that you own or the annotations that are shared with you. |
| **[!UICONTROL Applied date range]** | The date or date range that this annotation applies to. |
| **[!UICONTROL Tags]** | Lists the tags for this annotation. |
| **[!UICONTROL Shared with]** | Lists how many individuals or groups that you shared the annotation with. Select to open the **[!UICONTROL Share Component]** dialog and modify the tags for the annotation. |
| **[!UICONTROL Date modified]** | Displays the date and time that the annotation was last modified. |

{style="table-layout:auto"}

Use ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) to specify which column you want to display.

### Action bar

You can action on annotations using the action bar ➋. The action bar contains the following actions:

| Action | Description |
|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]** | Add another annotation, using the Annotation builder. |
| ![Search](/help/assets/icons/Search.svg) [!UICONTROL *Search by title*] | When no annotation is selected in the list, search for annotations using this search field. |
| ![Label](/help/assets/icons/Label.svg) **[!UICONTROL Tag]** | Tag the selected annotations. In the **[!UICONTROL Tag Component]** dialog, select or de-select the tags for the selected annotations. Select **[!UICONTROL Save]** to save the tags for the selected annotations. |
| ![Share](/help/assets/icons/Share.svg) **[!UICONTROL Share]** | Share the selected annotations. In the **[!UICONTROL Share Component]** dialog, you can ![Search](/help/assets/icons/Search.svg) *Search individuals or groups* or you can select **[!UICONTROL Organization]** or **[!UICONTROL Groups]**. Select **[!UICONTROL Save]** to save share details for the selected annotations. See [Share annotations](#share-annotations) for more details. |
| ![Delete](/help/assets/icons/Delete.svg) **[!UICONTROL Delete]** | Delete the selected annotations. You are prompted for a confirmation. |
| ![Edit](/help/assets/icons/Edit.svg) **[!UICONTROL Rename]** | Rename a single selected annotation. When selected, you can rename the annotation inline. |
| ![Copy](/help/assets/icons/Copy.svg)  **[!UICONTROL Copy]** | Copy the selected annotations. New annotations are created with the same name and suffix (Copy) | 
| ![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Export to CSV]** | Export the annotations to an `Annotations List.csv` file. |

### Active filter bar

The filter bar ➌ shows the active filters (if any). You can quickly remove a filter using ![CrossSize75](/help/assets/icons/CrossSize75.svg). If more than one filter is specified, you can remove all filters using **[!UICONTROL Remove all]**.

### Filter panel

You can filter annotations using the ![Filter](/help/assets/icons/Filter.svg) **[!UICONTROL Filter]** left panel ➍. The filter panel displays the type of filter and the number of annotations that honor the filter. Select ![Filter](/help/assets/icons/Filter.svg) to toggle the display of the filter panel. 

You can filter on:

| Filter | Description |
|---|---|
| **[!UICONTROL Tags]** | Unfold to see all tags defined and filter on individual tags. You can use ![Search](/help/assets/icons/Search.svg) *Search Tags* to search for tags. |
| **[!UICONTROL Data view]** | Unfold to see the individual data views you can filter on. You can use ![Search](/help/assets/icons/Search.svg) *Search Data views* to search for data views. |
| **[!UICONTROL Owners]** | Unfold to see the individual owners you can filter on. ou can use ![Search](/help/assets/icons/Search.svg) *Search Owners* to search for owners. |
| **[!UICONTROL Applied date range]** | You can filter on the applied date range. Select the data range to display a calendar popup to specify the data range, or simply type the date range. |
| **[!UICONTROL Other filters]** | You can filter on other filters like Show all, Mine, Favorites, Approved and Shared with me. |


## Edit annotations

You can edit an annotation in two ways:

* In a visualization, hover over the annotation and click the pencil icon within the popover.

* In the [[!UICONTROL Annotations] list](#annotations-list), select the title of the annotation.

You use the [Annotation builder](/help/components/annotations/create-annotations.md#annotation-builder) to edit the annotation.

## Share annotations

The following applies when sharing annotations or working with annotations that are shared with you:

* Project-only annotations in a project you share with other users are displayed for those users. The users cannot edit or delete these project-only annotations.
* If you save an annotation and share the annotation directly with a user, that user can edit and delete the annotation only if that user has admin rights.

* If a project is shared with you, annotations created in that project show up only in that project. If an annotation is shared directly with you, the annotation shows up in all projects where that annotation can be displayed. 

## Annotations and time zones

All annotations are created with a timestamp, but no hour or timezone information. At report time, the timezone of the data view configured for the panel is used.
