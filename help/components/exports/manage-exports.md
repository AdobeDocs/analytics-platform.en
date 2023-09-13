---
description: Manage existing exports
keywords: Analysis Workspace
title: Manage exports
feature: Components
---
# Manage exports

{{select-package}}

After you export a full table as described in [Export Customer Journey Analytics data to the cloud](/help/analysis-workspace/export/export-cloud.md), the exports are available on the [!UICONTROL Exports] tab on the [!UICONTROL Exports] page. 

You can see only the exports that you create.

## Filter and search for exports

To find information you need, you can either filter the list of exports or search for an export.

### Filter the list of exports 

1. In Customer Journey Analytics, select [!UICONTROL **Components**] > [!UICONTROL **Exports**].

1. Select the [!UICONTROL **Exports**] tab.

1. Select the **Filter** icon.

   <!--add screenshot -->

   You can filter by the following criteria:

   |Filter | Description |
   |---------|----------|
   | [!UICONTROL **Account type**] | The account type that the export is associated with. The following account types are available: <ul><li>[!UICONTROL **Amazon S3 Role ARN**]</li><li>[!UICONTROL **Google Cloud Platform**]</li><li>[!UICONTROL **Azure SAS**]</li><li>[!UICONTROL **Azure RBAC**]</li><li>[!UICONTROL **Snowflake**]</li><li>[!UICONTROL **Adobe Experience Manager**]</li></ul>. | 
   | [!UICONTROL **Status**] | The status of the export. The following statuses are available: <ul><li>[!UICONTROL **Active**]: Indicates that a scheduled export has not yet expired. </li><li>[!UICONTROL **Completed**]: Indicates that an export has successfully exported. For scheduled exports, this indicates that the schedule has expired.</li><li>[!UICONTROL **Failed**]<p>The following situations can result in a failed export. Hover over the Failed status to see details about the failure. <ul><li>Scheduled export expiration</li><li>Row limit reached for scheduled export </li></ul> </p></li></ul> | 
   | [!UICONTROL **Frequency**] | How often the export occurs. The following frequencies are available: <ul><li>[!UICONTROL **One time**]</li><li>[!UICONTROL **Daily**]</li><li>[!UICONTROL **Weekly**]</li><li>[!UICONTROL **Monthly**]</li><li>[!UICONTROL **Yearly**]</li></ul>|

   {style="table-layout:auto"}

### Search for exports

1. In Customer Journey Analytics, select [!UICONTROL **Components**] > [!UICONTROL **Exports**].

1. Select the [!UICONTROL **Exports**] tab.

1. In the search field, begin typing any information associated with the export you're searching for. You can search for data from any column available in the table. 

## Edit an export

You can edit an export's properties, format, scheduling, and location information. 

1. In Customer Journey Analytics, select [!UICONTROL **Components**] > [!UICONTROL **Exports**].

1. On the [!UICONTROL **Exports**] tab, select the export you want to edit.

   This option is not available when selecting multiple exports. 

1. Select [!UICONTROL **Edit**].

## Duplicate an export

You can duplicate an existing export.

1. In Customer Journey Analytics, select [!UICONTROL **Components**] > [!UICONTROL **Exports**].

1. On the [!UICONTROL **Exports**] tab, select the export you want to duplicate.

   This option is not available when selecting multiple exports. 

1. Select [!UICONTROL **Duplicate**].

   A duplicate of the export is created. The name of the new export matches the name of the original export, with _[!UICONTROL - Copy]_ appended to the file name. 

1. (Optional) [Edit the new export](#edit-an-export), including the file name and any other properties you want to change.

## Manually initiate an export

You can manually initiate an export, either for a scheduled export or a one-time export that previously completed. 

1. In Customer Journey Analytics, select [!UICONTROL **Components**] > [!UICONTROL **Exports**].

1. On the [!UICONTROL **Exports**] tab, select the export you want to run.

   This option is not available when selecting multiple exports. 

1. Select [!UICONTROL **Export now**].

## Tag an export

When you apply tags to an export, you can view those tags in the [!UICONTROL Tags] column on the [!UICONTROL Exports] page. See [Configure columns](#configure-columns) for more information.

1. In Customer Journey Analytics, select [!UICONTROL **Components**] > [!UICONTROL **Exports**].

1. On the [!UICONTROL **Exports**] tab, select one or more exports that you want to tag.

1. Select [!UICONTROL **Tag**].

1. In the Tag export dialog, type the name a tag to create a new tag, or choose an existing tag from the drop-down menu.

   Any common tags between the selected exports are shown in the tag dialog. <!-- what happens if one export has a tag and another doesn't? Is the tag removed if you don't select it? I'm guessing not, but maybe check -->

1. Select [!UICONTROL **Apply tags**].

## Delete an export

You can delete exports from the Exports page. Scheduled exports that are deleted will no longer be sent. 

1. In Customer Journey Analytics, select [!UICONTROL **Components**] > [!UICONTROL **Exports**].

1. On the [!UICONTROL **Exports**] tab, select one or more exports that you want to delete.

1. Select [!UICONTROL **Delete**], then select [!UICONTROL **Delete**] when you see the confirmation message.

## Configure columns on the [!UICONTROL Exports] page

You can add or remove columns on the [!UICONTROL Exports] tab to configure what information is displayed.

1. Select the **Customize table** icon ![customize table](assets/customize-table-icon.png) in the upper-right of the [!UICONTROL Exports] page.

   The following columns are available:

   |Available column | Description |
   |---------|----------|
   | Name | The name of the export. Users give exports a name when they create them, as described in [Export Customer Journey Analytics data to the cloud](/help/analysis-workspace/export/export-cloud.md).  | 
   | ID | The ID automatically assigned to the export when it is created. <!-- True? --> | 
   | Status | The status of the export. Available statuses are [!UICONTROL Active], [!UICONTROL Paused], [!UICONTROL Completed], and [!UICONTROL Failed].<p> **Note:** For information about troubleshooting failed exports, see [Troubleshoot failed exports](/help/components/exports/troubleshoot-exports.md).</p> |
   | Data view name | The name of the data view associated with the export. Users can select the data view when they create the export, as described in [Export Customer Journey Analytics data to the cloud](/help/analysis-workspace/export/export-cloud.md). |
   | Status | The status of the export. Available statuses are [!UICONTROL Pending], [!UICONTROL Delivered], and [!UICONTROL Failed]. |
   | Table size (last send) | The size of the export the last time it was sent.  |
   | Created by | The user who created the export. |
   | Created | The date and time the export was created. <!-- true? --> |
   | Location | The location on the account where the data was exported. |
   | Account | The account where the data was exported. |
   | Frequency | The frequency in which the export is sent. Available options are [!UICONTROL One time], [!UICONTROL Daily], [!UICONTROL Weekly], [!UICONTROL Monthly by day of the week], [!UICONTROL Monthly by day of the month], [!UICONTROL Yearly by day of the month], and [!UICONTROL Yearly by specific date]. |
   | Time sent | The time the export was sent. |
   | Last sent | The last time the export was sent. |
   | Account type | The type of cloud account where the data was exported. Available account types are [!UICONTROL Amazon S3 Role ARN], [!UICONTROL Google Cloud Platform], [!UICONTROL Azure SAS], [!UICONTROL Azure RBAC], [!UICONTROL Snowflake], and [!UICONTROL Adobe Experience Platform].  |
   | Tags | Displays any tags that are applied to the export. For information about how to apply tags to an export, see [Tag an export](#tag-an-export). |

   {style="table-layout:auto"}

1. Ensure that any columns you want to display are selected. Selected columns appear on the Exports page and display the relevant information.