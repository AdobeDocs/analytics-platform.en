---
title: Filters manager
description: lean how to manage filters in Customer Journey Analytics
exl-id: b8869560-0cf1-4e5d-a03c-dfca85d05e66
feature: Filters
role: User
---
# Filters manager

The Filters manager offers many ways of curating filters, such as sharing, tagging, approving, copying, deleting, and marking as favorites.

The Filters manager shows you all the filters you own and that have been shared with you. Admin-level users can see all filters in the organization. This overview presents the user interface and the capabilities of the Filters manager. 

![](assets/filter-manager-ui.png)

## Access the Filters manager

1. In Customer Journey Analytics, select the **[!UICONTROL Components]** tab, then select **[!UICONTROL Filters]**.

## Available actions in the Filters manager

In the Filters manager, you can:

* [Filter the list of filters](/help/components/filters/filters-filter.md)

* [Mark filters as favorites](/help/components/filters/filters-favorite.md)

* [Approve filters](/help/components/filters/filters-approve.md)

* [Tag filters](/help/components/filters/filters-tag.md)

* [Share filters](/help/components/filters/filters-share.md)

* Export a filter to a CSV file.

* [Copy filters](/help/components/filters/filters-copy.md)

* Delete filters

## Configure columns

You can configure the information displayed for each filter in the Filters manager by configuring the columns that are displayed.

To configure the visible columns in the Filters manager:

1. In Customer Journey Analytics, select the **[!UICONTROL Components]** tab, then select **[!UICONTROL Filers]**. 

1. In the Filters manager, select the **Customize columns** icon ![Customize columns icon](assets/customize-columns-icon.png), then select the columns that you want to be displayed in the Filters manager.

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
   | Used in | Shows where filters are currently being used, and how many times they are being used in each area. <p>For example, if the filter is being used in 40 projects and 2 alerts, then the value of this column shows as [!UICONTROL **42 components**].</p> <p>Select the value in this column to see the breakdown of where the filters are being used (for example, [!UICONTROL **Projects (40)**], [!UICONTROL **Mobile Scorecards (2)**]). Furthermore, you can view the list of items where the filters are being used. For example, so see the list of projects where they are being used, select the [!UICONTROL **Projects (40)**] link.</p><p>Each of the following areas shows the number of instances of filters being used in that area:</p>  <ul><li>[!UICONTROL **Projects**]<p>Contains filters that were [created in the filter builder](/help/components/filters/filter-builder.md#) and are available for all projects.</p></li><li>[!UICONTROL **Ad hoc components**]<p>Contains filters that were [created as quick filters](/help/components/filters/quick-filters.md) and are available only within a single project.</p></li><li>[!UICONTROL **Scheduled projects**]</li><li>[!UICONTROL **Mobile Scorecards**]</li><li>[!UICONTROL **Annotations**]</li><li>[!UICONTROL **Calculated metrics**]</li><li>[!UICONTROL **Report Builder**]<p>Selecting this option downloads a CSV file, with the following columns of data:</p><ul><li>Report Builder Name</li><li>Last accessed</li><li>Last accessed IMS User ID</li><li>Last accessed user name</li></ul></li><p>When viewing information for Report Builder, usage information is available starting in September 2024.</p></ul><p>This information can help you determine whether a component is valuable to users in your organization, where it is used, and if it needs to be deleted or modified.</p><p>Consider the following when viewing this column:</p><ul><li>This information is available only to system administrators.</li><li>The [!UICONTROL **Used in**] column does not display by default. [Configure columns](#configure-columns) to display it.</li><li>If a filter includes another filter in its definition, any use of that filter is not shown in the [!UICONTROL **Used in**] column. If a filter is included in the definition of another type of component (such as a calculated metric), then usage is shown in the [!UICONTROL **Used in**] column.</li><li>This information does not include usage from the API or Data Warehouse.</li><li>If there is no data in this column for a given component but it has a [!UICONTROL **Last used**] date, the component might have been used in an analysis without being saved.</li><li>Usage information is available starting in September 2023.</li></ul><p>You can use the [Data Dictionary](/help/components/data-dictionary/data-dictionary-overview.md) along with this information to help you keep track of and better understand how components are being used in your organization.</p>  |
   | Last used | Shows the date when the filter was last used in any of the following component types: <ul><li>Calculated metrics</li><li>Projects</li><li>Scheduled projects</li><li>Filters</li></ul> <p>This information can help you determine whether a component is valuable to users in your organization, or whether it should be deleted.</p><p>Consider the following when viewing this column:</p><ul><li>This information does not include usage from the API, Report Builder, or Data Warehouse.</li><li>For some components, this column might not contain data if the component was last used prior to September 2023.</li><li>This information is available only to system administrators.</li></ul><p>You can use the [Data Dictionary](/help/components/data-dictionary/data-dictionary-overview.md) along with this information to help you keep track of and better understand how components are being used in your organization. |
   
   {style="table-layout:auto"}
