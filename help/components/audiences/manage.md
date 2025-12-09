---
title: Learn how to manage audiences created in Customer Journey Analytics
description: Learn how to manage audiences in Customer Journey Analytics
exl-id: 0cc50f64-40b5-4245-a9bb-a60fc90f507a
feature: Audiences
role: User
---
# Manage published audiences

Audiences can be managed in Customer Journey Analytics using **[!UICONTROL Components]** > **[!UICONTROL Audiences]**.

## Understand audience management tasks

Managing previously created audiences lets you:

* **Schedule or de-schedule** automatic audience refresh/update. The maximum expiration on the schedule is 1 year. 
* **Renew an audience refresh schedule** when it is about to expire. Expiring audiences are treated similarly to expiring scheduled reports - the admin gets an email a month before the schedule expires.
* View the **refresh interval** and the **last time that an audience was updated**
* Gain insight into the **amount of time it took to produce an audience** from Customer Journey Analytics. And the amount of time it took to have the audience appear in Real-time Customer Platform for activation purposes.
* See whether the audiences in Customer Journey Analytics are **being actively used by Real-time Customer Platform**. Or (ideally) any Experience Platform applications that consume the audiences created by Customer Journey Analytics.

If you do have [Audience View](/help/technotes/access-control.md#user-level-access) access, you can view audiences. If you do have [Audience Create](/help/technotes/access-control.md#user-level-access) access, you can edit and delete audiences.

## View audiences in the Audiences list

The Audiences list ➊ shows the existing audiences. 

![Audiences manager](assets/audiences-manager.png)

To view the Audience list:

1. In Customer Journey Analytics, select **[!UICONTROL Components]** > **[!UICONTROL Published audiences]**.

1. (Optional) Use ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) to configure which columns to display. 

1. (Optional) Search for an audience using ![Search](/help/assets/icons/Search.svg). 

   The following columns are available with information about each audience:

   | Column | Description |
   | --- | --- |
   | ![SelectBox](/help/assets/icons/SelectBox.svg) | When one or more audiences are selected, a blue action bar appears at the bottom of the Audiences interface. See [Actions](#actions) for more details. |
   | **[!UICONTROL Title & Description]** | The title and description you entered when you created the audience. |
   | **[!UICONTROL Data view]** | The data view in which this audience was created. |
   | **[!UICONTROL Audience size]** | The total number of people in this audience. |
   | **[!UICONTROL Owner]** | The owner of the audience - the person who created the audience. |
   | **[!UICONTROL Refresh frequency]** | The refresh interval configured when the audience was created. |
   | **[!UICONTROL Tags]** | Any tags that are applied to this audience. |
   | **[!UICONTROL Publishing status]** | Can show ![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL Ready]**, ![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL In progress]**, or ![StatusRed](/help/assets/icons/StatusRed.svg) **[!UICONTROL Error]**. |
   | **[!UICONTROL Last refreshed]** | Timestamp when the audience was last refreshed. |
   | **[!UICONTROL Last modified]** | Timestamp when the audience was last edited or modified. |

## Edit audiences

You can edit the settings of an audience at any time. When you edit an audience (either a one-time audience or a recurring audience), a republish is required. 

To edit an audience:

1. In Customer Journey Analytics, select **[!UICONTROL Components]** > **[!UICONTROL Published audiences]**.

   The Audiences page is displayed.

1. Select the title of the audience that you want to edit.  

   The **[!UICONTROL Edit audience]** dialog displays.

1. You can update any of the available fields for the audience. For information about the fields you can update, see [Audience builder](/help/components/audiences/publish.md#audience-builder) in the article, [Create and publish audiences](/help/components/audiences/publish.md).
   
1. Select **[!UICONTROL Republish]**.

## Actions

The following are common actions in the Scheduled Projects manager. You can select actions from the context menu:

| Icon | Action | Description |
|:---:|---|---|
| ![Labels](/help/assets/icons/Labels.svg)| **[!UICONTROL Tag]** | Tag the selected audiences. In the **[!UICONTROL Update tags: *audience name*]** dialog, select tags from the drop-down menu or type one or more new tags. Select **[!UICONTROL Save]** to save. |
| ![Delete](/help/assets/icons/Delete.svg) | **[!UICONTROL Delete]** | Delete the selected audiences.|
| ![Edit](/help/assets/icons/Edit.svg) | **[!UICONTROL Rename]** | Rename the selected audience. Use the **[!UICONTROL Rename: *audience name*]** dialog to rename the audience and select **[!UICONTROL Save]** to save. |

The following actions are available from the blue action bar when selecting one or more scheduled projects.

| Icon | Action | Description |
|:---:|---|---|
| ![Close](/help/assets/icons/Close.svg) | **[!UICONTROL *x* selected]** | Select to unselect your selected audiences. |
| ![Delete](/help/assets/icons/Delete.svg) | **[!UICONTROL Delete]** | Delete the selected audiences.|
| ![FileCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL Export to CSV]** | Export the selected audiences to a file named `audiences.csv`. |

## Filter the audience list

You can filter the [Audiences list](#audiences-list) using the filter panel ➋. To show or hide the filter panel use ![Filter](/help/assets/icons/Filter.svg).

![Audiences manager](assets/audiences-manager.png)

The filter panel consists of the following sections.

### Data view

| Data view | Description |
|---|---|
| ![Owners](/help/components/audiences/assets/audiences-filter-dataviews.png){width="300"} | The **[!UICONTROL Data view]** section lets you filter on data views. <ul><li>You use ![Search](/help/assets/icons/Search.svg) to search for data views you want to use to filter.</li><li>You can select more than one data view.</li></ul> |

### Owners

| Owner | Description |
|---|---|
| ![Owners](/help/components/audiences/assets/audiences-filter-owner.png){width="300"} | The **[!UICONTROL Owner]** section lets you filter on owners. <ul><li>You use ![Search](/help/assets/icons/Search.svg) to search for owners you want to use to filter.</li><li>You can select more than one owner. </li></ul> |

## Refresh frequency

| Refresh frequency   | Description |
|---|---|
| ![Refresh frequency](/help/components/audiences/assets/audiences-filter-refreshfrequency.png){width="300"} | The **[!UICONTROL Refresh frequency]** section lets you filter on refresh frequency. <ul><li>You use ![Search](/help/assets/icons/Search.svg) to search for refresh frequency you want to use to filter.</li><li>Only the refresh frequencies defined for the audiences<br/> in the [Audiences list](#audiences-list) are shown as available options.</li></ul>|


### Tags

| Tags   | Description |
|---|---|
| ![Tags](/help/components/audiences/assets/audiences-filter-tags.png){width="300"} | The **[!UICONTROL Tags]** section lets you filter on tags. <ul><li>You use ![Search](/help/assets/icons/Search.svg) to search for tags you want to use to filter.  |
