---
description: Manage logs for existing exports
keywords: Analysis Workspace
title: Manage export logs
feature: Components
hide: yes
hidefromtoc: yes
---
# Manage export logs

Export logs provide details about each export, and are generated any time Analysis Workspace data is exported to the cloud. (For information about how data can be exported to the cloud, see [Export Customer Journey Analytics reports to the cloud](/help/analysis-workspace/export/export-cloud.md).) 

For scheduled exports, logs reflect the export settings as they were when the log was sent. Logs cannot be deleted.

## Filter and search for logs

To find information you need, you can either filter the list of logs or search for a log.

### Filter the list of logs

1. In Customer Journey Analytics, select [!UICONTROL **Components**] > [!UICONTROL **Exports**].

1. Select the [!UICONTROL **Logs**] tab.

1. Select the **Filter** icon.

   ![Filter information](assets/export-log-filters.png)

   You can filter by the following criteria:

   |Filter | Description |
   |---------|----------|
   | [!UICONTROL **Account type**] | The account type that the log is associated with. The following account types are available: <ul><li>[!UICONTROL **Adobe Experience Platform Data Landing Zone**]</li><li>[!UICONTROL **Amazon S3 Role ARN**]</li><li>[!UICONTROL **Google Cloud Platform**]</li><li>[!UICONTROL **Azure SAS**]</li><li>[!UICONTROL **Azure RBAC**]</li><li>[!UICONTROL **Snowflake**]</li></ul>. | 
   | [!UICONTROL **Status**] | The status of the export. The following statuses are available: <ul><li>[!UICONTROL **Pending**]: A specific instance of an export has been started but is not yet complete.<p>Re-running an export that has a status of Pending will delay the export process.</p></li><li>[!UICONTROL **Completed**]: A specific instance of an export has finished processing and is available in the export account.</li><li>[!UICONTROL **Failed**]<p>The following situations can result in a failed export. Hover over the Failed status to see details about the failure. <ul><li>Scheduled export expiration</li><li>Row limit reached for scheduled export </li></ul> </p></li></ul> | 

   {style="table-layout:auto"}

### Search for logs

1. In Customer Journey Analytics, select [!UICONTROL **Components**] > [!UICONTROL **Exports**].

1. Select the [!UICONTROL **Logs**] tab.

1. In the search tab, begin typing any information associated with the log you're searching for. You can search for data from any column available in the table. 

<!-- removed for MVP: Retry an export You can re-run the export associated with the selected log, using the data as it was on the day the log was originally exported. This is useful when selecting a log that show a failed export or when selecting a log that was accidentally deleted. 

Retrying an export that has a status of Pending will delay the export process.

This option is not available when selecting multiple logs. -->

<!-- 1. In Customer Journey Analytics, select [!UICONTROL **Components**] > [!UICONTROL **Exports**].

1. Select the [!UICONTROL **Logs**] tab, then select a log.

1. Select [!UICONTROL **Retry**]. -->
   
## Edit an export

You can edit the export associated with a specific log.

This option is not available when selecting multiple logs.

1. In Customer Journey Analytics, select [!UICONTROL **Components**] > [!UICONTROL **Exports**].

1. Select the [!UICONTROL **Logs**] tab.

1. Locate the log that is associated with the export you want to edit.

1. Select the **Edit export** icon ![export log icon](assets/export-icon.png) next to the log.

   Or

   Select the log, then select [!UICONTROL **Edit export**].

## Configure columns

You can add or remove columns on the [!UICONTROL Logs] tab to configure what information is displayed.

Select a column header to sort the logs by that column. By default, logs are sorted by the date and time the export started.

To configure columns on the [!UICONTROL Logs] tab:

1. In Customer Journey Analytics, select [!UICONTROL **Components**] > [!UICONTROL **Exports**].

1. Select the [!UICONTROL **Logs**] tab.

1. Select the **Customize table** icon ![customize table](assets/customize-table-icon.png) in the upper-right of the [!UICONTROL Logs] page.

   The following columns are available:

   |Available column | Description |
   |---------|----------|
   | Export name | The name of the export. Users give exports a name when they create them, as described in [Export Customer Journey Analytics reports to the cloud](/help/analysis-workspace/export/export-cloud.md). | 
   | Export ID | The ID automatically assigned to the export when it is created. <!-- True? --> | 
   | Instance ID | The ID of the Customer Journey Analytics instance. <!-- True? --> |
   | Data view name | The name of the data view associated with the export. Users can select the data view when they create the export, as described in [Export Customer Journey Analytics reports to the cloud](/help/analysis-workspace/export/export-cloud.md). |
   | Number of files | The number of files included in the export. |
   | Size | The size of the export.<p>The file size is calculated with a base of 1024, which is sometimes represented as KIB and MIB. If your cloud provider calculates size with a base of 1000, this may result in the size displayed in your cloud provider being slightly different from the size displayed here.</p> |
   | Location | The location on the account where the data was exported. |
   | Account | The account where the data was exported. |
   | Status | The status of the export. Available statuses are [!UICONTROL Pending], [!UICONTROL Delivered], and [!UICONTROL Failed]. |
   | Date delivered | The date when the export took place. |
   | Account type | The type of cloud account where the data was exported. Available account types are [!UICONTROL Amazon S3 Role ARN], [!UICONTROL Google Cloud Platform], [!UICONTROL Azure SAS], [!UICONTROL Azure RBAC], [!UICONTROL Snowflake], and [!UICONTROL Adobe Experience Platform]. |
   | Number of rows | The number of rows included in the exported table. |

   {style="table-layout:auto"}

1. Ensure that any columns you want to display are selected. Selected columns appear on the [!UICONTROL Logs] page and display the relevant information.

## View audit logs

Full-table exports are also tracked in the [Customer Journey Analytics audit logs](/help/privacy/audit-log.md). <!-- Need to see what the Component Type for full-table export will be and add it here. Also, under "Event type captured by audit logs" there would be a new event type called "Full-table export". 4 actions would be "Create, Delete, Edit, Export" and "API_Request"? Also information about the locations. Probably have a different component for the location credentials.-->