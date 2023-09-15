---
title: Manage filters
description: lean how to manage filters in Customer Journey Analytics
exl-id: b8869560-0cf1-4e5d-a03c-dfca85d05e66
feature: Filters
---
# Manage filters

The Filter Manager offers many ways of curating filters, such as sharing, tagging, approving, copying, deleting, and marking as favorites.

The Filter Manager shows you all the filters you own and that have been shared with you. Admin-level users can see all filters in the organization. This overview presents the user interface and the capabilities of the Filter Manager. 

![](assets/filter-manager-ui.png)

## Access the Filter manager

1. In Customer Journey Analytics, select the **[!UICONTROL Components]** tab, then select **[!UICONTROL Filters]**.

## Available actions in the Filter manager

In the Filter manager, you can:

* [Filter the list of filters](/help/components/filters/filters-filter.md)

* [Mark filters as favorites](/help/components/filters/filters-favorite.md)

* [Approve filters](/help/components/filters/filters-approve.md)

* [Tag filters](/help/components/filters/filters-tag.md)

* [Share filters](/help/components/filters/filters-share.md)

* Export a filter to a CSV file.

* [Copy filters](/help/components/filters/filters-copy.md)

* Delete filters

## Configure columns

You can configure the information displayed for each filter in the Filter manager by configuring the columns that are displayed.

To configure the visible columns in the Filter manager:

1. In Customer Journey Analytics, select the **[!UICONTROL Components]** tab, then select **[!UICONTROL Filers]**. 

1. In the Filter manager, select the **Customize columns** icon ![Customize columns icon](assets/customize-columns-icon.png), then select the columns that you want to be displayed in the Filter manager.

   The following columns are available:

   | Column title | Description  |
   |---|---|
   | Title and description | These values are provided in the Filter builder. To edit the title and description, select the title link to open the Filter builder.  |
   | Favorites  | Displays star icons next to each filter, allowing you to mark filters as favorites. For more information, see [Mark filters as favorites](/help/components/filters/filters-favorite.md). |
   | Data view  | This column indicates in which data view the filter was last saved.  |
   | Owner  | Indicates who owns the filter. As a non-Admin, you can see only filters you own or those that were shared with you.  |
   | Tags (not checked in column selector, hence column not appearing)  | Tags that were applied to the filter, either by you or by people who shared the filter with you.  |
   | Shared with  | Lists individuals or groups (Admin only) or All (Admin only) that you shared the filter with. <p>When a filter is being shared by you or with you, a share icon displays next to the filter name.</p>|
   | Date modified  | Shows the date that the filter was last modified.  |
   | Used in | Shows in which of the following component types the filter is currently being used: <ul><li>Calculated metrics</li><li>Projects</li><li>Scheduled projects</li><li>Filters</li></ul> For example, if the filter is being used in 40 projects and 2 calculated metrics, this column shows [!UICONTROL **Calculated metrics (2), Projects (40)**]. <p>This information can help you determine whether a filter is valuable to users in your organization, or whether it should be deleted.</p><p>You can use the [Data Dictionary](/help/components/data-dictionary/data-dictionary-overview.md) along with this information to help you keep track of and better understand how components are being used in your organization. |
   | Last used | Shows the date when the filter was last used in any of the following component types: <ul><li>Calculated metrics</li><li>Projects</li><li>Scheduled projects</li><li>Filters</li></ul> <p>This information can help you determine whether a component is valuable to users in your organization, or whether it should be deleted.</p><p>You can use the [Data Dictionary](/help/components/data-dictionary/data-dictionary-overview.md) along with this information to help you keep track of and better understand how components are being used in your organization. |
   
   {style="table-layout:auto"}
