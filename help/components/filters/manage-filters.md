---
title: Manage segments
description: Learn how to manage segments in Customer Journey Analytics
exl-id: b8869560-0cf1-4e5d-a03c-dfca85d05e66
feature: Filters
role: User
---
# Manage segments


You can [share](filters-share.md), [segment](filters-filter.md), [tag](filters-tag.md), [approve](filters-approve.md), rename, [copy](filters-copy.md), delete, export segments and mark segments as [favorite](filters-favorite.md) from a central [!UICONTROL Segment] management interface. To manage segments:

* Select **[!UICONTROL Components]** in the main interface, then select **[!UICONTROL Segments]**.


>[!NOTE]
>
>The quick segments that you create within a specific Workspace project do not appear in the [!UICONTROL Filters] manager, unless you have made the segment available to all your projects. 
>

## Segment manager

The Segment manager has the following interface elements:

![Segment interface](assets/filters-manager.png)

### Segment list

The segments list ➊ displays all the segments that you own, the segments that have been scoped to all your projects, and the segments that have been shared with you. The list has the following columns:

| Column | Description |
| --- | --- | 
| ![StarOutline](/help/assets/icons/StarOutline.svg)  | Select to favor ![Star](/help/assets/icons/Star.svg) or un-favor ![StarOutline](/help/assets/icons/StarOutline.svg) a segment. See [Mark segment as favorite](/help/components/filters/filters-favorite.md) |
| **[!UICONTROL Title and description]** | To edit the segment, select the title link, which opens the [Filters builder](filter-builder.md). A shared segment is indicated with ![Share](/help/assets/icons/ShareAlt.svg). |
| **[!UICONTROL Data view]** | The data views that this segment applies to.  | 
| **[!UICONTROL Owner]** | The owner of the segment. As a user, you only see the segments that you own or the annotations that are shared with you. |
| **[!UICONTROL Tags]** | The tags for this segment. |
| **[!UICONTROL Shared with]** | How many individuals or groups that you shared the segment with. Select to open the **[!UICONTROL Share Component]** dialog. See [Share segments](filters-share.md) for more information. |
| **[!UICONTROL Date modified]** | The date and time that the segment was last modified. |
| **[!UICONTROL Used in]** | Show where segments are currently being used, and how many times they are being used in each area. <p>For example, if the segment is being used in 40 projects and 2 alerts, then the value of this column shows as [!UICONTROL **42 components**].</p> <p>Select the value in this column to see the breakdown of where the segments are being used (for example, [!UICONTROL **Projects (40)**], [!UICONTROL **Mobile Scorecards (2)**]). Furthermore, you can view the list of items where the segments are being used. For example, so see the list of projects where they are being used, select the [!UICONTROL **Projects (40)**] link.</p><p>Each of the following areas shows the number of instances of segments being used in that area:</p>  <ul><li>[!UICONTROL **Projects**]<p>Contains segments that were [created in the segment builder](/help/components/filters/filter-builder.md#) and are available for all projects.</p></li><li>[!UICONTROL **Ad hoc components**]<p>Contains segments that were [created as quick segments](/help/components/filters/quick-filters.md) and are available only within a single project.</p></li><li>[!UICONTROL **Scheduled projects**]</li><li>[!UICONTROL **Mobile Scorecards**]</li><li>[!UICONTROL **Annotations**]</li><li>[!UICONTROL **Calculated metrics**]</li><li>[!UICONTROL **Report Builder**]<p>Selecting this option downloads a CSV file with the following columns of data:</p><ul><li>Report Builder Name</li><li>Last accessed</li><li>Last accessed IMS User ID</li><li>Last accessed user name</li></ul></li></ul><p>This information helps you to determine whether a component is valuable to users in your organization, where the component is used, and if the component needs to be deleted or modified.</p><p>Consider the following when viewing this column:</p><ul><li>This information is available only to system administrators.</li><li>The [!UICONTROL **Used in**] column does not display by default. Use ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) to configure the display of this column.</li><li>This information does not include usage from the API or Data Warehouse.</li><li>If there is no data in this column for a given component but the component has a [!UICONTROL **Last used**] date, the component might have been used in an analysis without being saved.</li><li>Usage information is available starting in September 2023.</li></ul><p>You can use the [Data Dictionary](/help/components/data-dictionary/data-dictionary-overview.md) along with this information to help you keep track of and better understand how components are being used in your organization.</p>  |
| **[!UICONTROL Last Used]** | When the segment was last used. |

Use ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) to specify which columns you want to display.

### Action bar

You can action on segments using the action bar ➋. The action bar contains the following actions:

| Action | Description |
|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]** | Add another segment, using the [Filter builder](filter-builder.md). |
| ![Search](/help/assets/icons/Search.svg) [!UICONTROL *Search by title*] | When no segment is selected in the list, search for segments using this search field. |
| ![Label](/help/assets/icons/Label.svg) **[!UICONTROL Tag]** | Tag the selected segments. In the **[!UICONTROL Tag Segment]** dialog, select or de-select the tags for the selected segments. Select **[!UICONTROL Save]** to save the tags for the selected segments. See [Tag segments](/help/components/filters/filters-tag.md) for more information.|
| ![Share](/help/assets/icons/ShareAlt.svg) **[!UICONTROL Share]** | Share the selected segments. In the **[!UICONTROL Share Segment]** dialog, you can ![Search](/help/assets/icons/Search.svg) *Search individuals or groups* or you can select **[!UICONTROL Organization]** or **[!UICONTROL Groups]**. Select **[!UICONTROL Save]** to save share details for the selected segments. See [Share segments](filters-share.md) for more information. |
| ![Delete](/help/assets/icons/Delete.svg) **[!UICONTROL Delete]** | Delete the selected segments. You are prompted for a confirmation. |
| ![Edit](/help/assets/icons/Edit.svg) **[!UICONTROL Rename]** | Rename a single selected segment. When selected, you can rename the segment inline. |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Approve]** | Approve the selected segments. See [Approve segments](filters-approve.md) for more information. | 
| ![Copy](/help/assets/icons/Copy.svg)  **[!UICONTROL Copy]** | Copy the selected segment. New segments are created with the same name and suffix `(Copy)`. | 
| ![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Export to CSV]** | Export the segments to a `Filters List.csv` file. |

### Active segment bar

The segment bar ➌ shows the active segments applied from the segment panel to the list of segments (if any). You can quickly remove a segment using ![CrossSize75](/help/assets/icons/CrossSize75.svg). If more than one segment is specified, you can remove all segments using **[!UICONTROL Remove all]**.

### Segment panel

You can segment the list of segments using the ![Segment](/help/assets/icons/Filter.svg) **[!UICONTROL Filter]** left panel ➍. The segment panel displays the type of segment and the number of segments that honor the specific segment. Select ![Segment](/help/assets/icons/Filter.svg) to toggle the display of the segment panel. 

See [Filter the list of segments](filters-filter.md) for more information.
