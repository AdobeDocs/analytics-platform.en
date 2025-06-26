---
description: There are two ways to use metrics in Analysis Workspace.
title: Metrics
feature: Components
exl-id: fa7c5a0f-4983-40ee-b9c1-3e10aab3fc28
role: User
---
# Scheduled projects

Scheduled Analysis Workspace projects can be managed in Customer Journey Analytics using **[!UICONTROL Components]** > **[!UICONTROL Scheduled projects]**.

In **[!UICONTROL Scheduled Projects]**, you can edit and delete recurring project schedules.  The [Scheduled project list](#scheduled-project-list) shows the items that a specific user has created. If the user account is disabled in the application, all scheduled deliveries will stop.

![Scheduled projects interface](assets/scheduled-projects.png)

## Scheduled project list

The Scheduled projects list ➊ displays columns for:

| Column | Description |
| --- | --- |
| ![SelectBox](/help/assets/icons/SelectBox.svg) | When one or more scheduled projects are selected, a blue action bar appears at the bottom of the Scheduled Projects interface. See [Actions](#actions) for more details. |
| ![Star](/help/assets/icons/Star.svg) | Select to favor ![Star](/help/assets/icons/Star.svg) or un-favor ![StarOutline](/help/assets/icons/StarOutline.svg) a scheduled project. |
| **[!UICONTROL Schedule ID]** | An ID that is used mainly for debugging purposes. |
| **[!UICONTROL Name]** | Name of this project.<br/>Select ![InfoOutline](/help/assets/icons/InfoOutline.svg) to see more details for the scheduled project.<br/>Select ![More](/help/assets/icons/More.svg) to open a context menu. From this menu you can:<ul><li>![Delete](/help/assets/icons/Delete.svg) **[!UICONTROL Delete]** a scheduled project.</li><li>![Labels](/help/assets/icons/Labels.svg) **[!UICONTROL Tag]** a scheduled project.</li><li>![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Approve]** a scheduled project.</li><li>![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Export CSV]**: Export a scheduled project to a CSV file.</li></ul>|
| **[!UICONTROL Owner]** | The person who created and owns the project. |
| **[!UICONTROL Tags]** | (optional) Tagging is a good way to organize projects. All users can create tags and apply one or more tags to a project. However, you can see tags only for those projects that you own or that have been shared with you.  |
| **[!UICONTROL Delivered to]** | The recipients of this scheduled project. |
| **[!UICONTROL Expiration date]** | You can set the expiration date to up to one year, regardless of schedule frequency. |
| **[!UICONTROL Frequency]** | How often you want to have this schedule project sent to one or more recipients. |
| **[!UICONTROL Execution Time]** | At what time of day this scheduled project gets sent. |
| **[!UICONTROL Number of Queries]** | The number of queries against this project. | 
| **[!UICONTROL Longest Date Range]** | The longest date range defined for the scheduled project. This value might be relevant to investigate performance issues. See [Reporting Activity Manager](/help/reporting-activity-manager/reporting-activity-overview.md) for more information. |
| **[!UICONTROL Number of queries]** | The number of queries executed for the scheduled project. This value might be relevant to investigate performance issues. See [Reporting Activity Manager](/help/reporting-activity-manager/reporting-activity-overview.md) for more information.| 


You can use ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) to configure which columns to display.

Search for a scheduled project using ![Search](/help/assets/icons/Search.svg). You can also see if any filters are applied from the Filters panel. To remove a filter, select ![CrossSize75](/help/assets/icons/CrossSize75.svg) for a filter. To remove all filters, select **[!UICONTROL Clear all]**.

To edit a scheduled project, select the title of the scheduled project. Use the **[!UICONTROL Edit scheduled project]** dialog to update the schedule details. See [Send files to other](../analysis-workspace/export/t-schedule-report.md) for more details.

![Edit scheduled project](assets/edit-scheduled-project.png)

Select **[!UICONTROL Update]** to update the schedule.




## Actions

The following are common actions in the Scheduled Projects manager. You can select actions from the context menu  or from the blue action bar when selecting one or more scheduled projects.

| Icon | Action | Description |
|:---:|---|---|
| ![Close](/help/assets/icons/Close.svg) | **[!UICONTROL *x* selected]** | Select to unselect your selected scheduled projects. |
| ![Delete](/help/assets/icons/Delete.svg) | **[!UICONTROL Delete]** | Delete the selected scheduled projects for the project; the projects are not deleted.|
| ![Labels](/help/assets/icons/Labels.svg)| **[!UICONTROL Tag]** | Tag the selected scheduled projects. In the **[!UICONTROL Tag Scheduled projects]** select tags and select **[!UICONTROL Save]** to save. |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | **[!UICONTROL Approve]** | Approve the selected scheduled projects. |
| ![FileCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL Export to CSV]** | Export the selected scheduled projects to a file named `Export Scheduled Projects List.csv`. |


## Filter

You can filter the scheduled projects [Scheduled Project list](#scheduled-project-list) using the filter panel ➌. To show or hide the filter panel use ![Filter](/help/assets/icons/Filter.svg).

The filter panel consists of the following sections.

### Tags

| Tags   | Description |
|---|---|
| ![Tags](/help/components/assets/scheduledprojects-filter-tags.png){width="300"} | The **[!UICONTROL Tags]** section lets you filter on tags. <ul><li>You use ![Search](/help/assets/icons/Search.svg) **[!UICONTROL Search Tags]** to search for tags you want to use to filter.</li><li>You can select more than one tag. The tags available depend on selections made in other sections in the filter panel.</li><li>The numbers indicate:<ul><li>7︎⃣: The number of scheduled projects associated with the specific tag.</li></ul></li></ul> |


### Owners

| Owner | Description |
|---|---|
| ![Owners](/help/components/assets/scheduledprojects-filter-owners.png){width="300"} | The **[!UICONTROL Owner]** section lets you filter on owners. <ul><li>You use ![Search](/help/assets/icons/Search.svg) *Search Owners* to search for owners you want to use to filter.</li><li>You can select more than one owner. The owners available depend on selections made in other sections in the filter panel.</li><li>The numbers indicate:<ul><li>4︎⃣: The number of scheduled projects associated with the specific owner.</li></ul></li></ul> |


### Other filters 

| Other filters | Description |
|---|---|
| ![Other filters](/help/components/assets/scheduledprojects-filter-otherfilters.png){width="300"} | The **[!UICONTROL Other filters]** section lets you filter on other predefined filter.<ul><li>You can select one or more of the following options:<ul><li> **[!UICONTROL Expired]**: Filter on expired scheduled projects.</li><li>**[!UICONTROL Failed]**: Filter on  scheduled projects for which the schedule has failed.</li></ul>What you can select depends on your role and permissions.</li><li>You can select more than one other filter. The other filters available depend on selections made in other sections in the filter panel.</li><li>The numbers indicate:<ul><li>4︎⃣: The number of scheduled projects associated with the specific other filter.</li></ul></li></ul> |
