---
description: Manage logs for existing exports
keywords: Analysis Workspace
title: Manage export logs
feature: Components
---
# Manage export logs

{{select-package}}

Export logs provide details about each export, and are generated any time Analysis Workspace data is exported to the cloud. (For information about how data can be exported to the cloud, see [Export Customer Journey Analytics data to the cloud](/help/analysis-workspace/export/export-cloud.md).) 

You can view details about each export logs, filter and search for logs, and manage logs. Logs cannot be deleted.

## Retry an export

You can re-run the export associated with the selected log, using the data as it was on the day the log was originally exported. This is useful when selecting a log that show a failed export or when selecting a log that was accidentally deleted.

This option is not available when selecting multiple logs.

1. In Customer Journey Analytics, select [!UICONTROL **Components**] > [!UICONTROL **Exports**].

1. Select the [!UICONTROL **Logs**] tab, then select a log.

   <!-- add screenshot? -->

1. Select [!UICONTROL **Retry**].
   
## Open a project

You can open the project that contains the data associated with specific logs.

This option is not available when selecting multiple logs.

1. In Customer Journey Analytics, select [!UICONTROL **Components**] > [!UICONTROL **Exports**].

1. Select the [!UICONTROL **Logs**] tab, then select a log.

   <!-- add screenshot? -->

1. Select [!UICONTROL **Open project**].

## Log a ticket with Customer Care

You can create a ticket for Adobe Customer Care that includes your feedback along with basic information about specific logs. Adobe Customer Care responds by email to any tickets you create.

1. In Customer Journey Analytics, select [!UICONTROL **Components**] > [!UICONTROL **Exports**].

1. Select the [!UICONTROL **Logs**] tab, then select one or more existing logs.

   <!-- add screenshot? -->

1. Select [!UICONTROL **Create ticket**].

1. Specify the details about any issues you encountered in the selected logs, then select [!UICONTROL **Submit**].

   A ticket is created for Adobe Customer Care that includes your feedback along with basic information about the selected logs. Adobe Customer Care responds by email to any tickets you create.

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
   | Account | The account type that the export is associated with, such as Google Cloud Platform, Azure SAS, or Azure RBAC. | 
   | Status | The status of the export. The following statuses are available: <ul><li>Pending</li><li>Completed</li><li>Failed<p>The following situations can result in a failed export. Hover over the Failed status to see details about the failure. <ul><li>Scheduled export expiration</li><li>Row limit reached for scheduled export </li></ul> </p></li></ul> | 

### Search for logs

1. In Customer Journey Analytics, select [!UICONTROL **Components**] > [!UICONTROL **Exports**].

1. Select the [!UICONTROL **Logs**] tab.

1. In the search tab, begin typing any information associated with the log you're searching for. You can search for data from any column available in the table. 

## Configure columns

You can configure what information is displayed for each export on the Exports page by adding or removing columns.

1. In Customer Journey Analytics, select [!UICONTROL **Components**] > [!UICONTROL **Exports**].

1. Select the [!UICONTROL **Logs**] tab.

1. Select the **Configure columns** icon in the upper-right of the Logs page.

   <!-- add screenshot -->

   The following columns are available:

   |Available column | Description |
   |---------|----------|
   | Export name | B1 | 
   | Export ID | B2 | 
   | Instance ID | B3 |
   | Number of files | B3 |
   | Size | B3 |
   | Number of rows | B3 |
   | Location | B3 |
   | Account | B3 |
   | Status | B3 |
   | Date delivered | B3 |
   | Account type | B3 |

   {style="table-layout:auto"}

1. Ensure that any columns you want to display are selected. Selected columns appear on the Exports page and display the relevant information.

## View audit logs

Full-table exports are also tracked in the [Customer Journey Analytics audit logs](/help/privacy/audit-log.md). <!-- Need to see what the Component Type for full-table export will be and add it here. Also, under "Event type captured by audit logs" there would be a new event type called "Full-table export". 4 actions would be "Create, Delete, Edit, Export" and "API_Request"? Also information about the locations. Probably have a different component for the location credentials.-->