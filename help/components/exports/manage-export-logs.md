---
description: Manage logs for existing exports
keywords: Analysis Workspace
title: Manage export logs
feature: Components
---
# Manage export logs

{{select-package}}

Export logs provide details about each export, and are generated any time Analysis Workspace data is exported to the cloud. (For information about how data can be exported to the cloud, see [Export Customer Journey Analytics data to the cloud](/help/analysis-workspace/export/export-cloud.md).) 

You can view details about each export logs, filter and search for logs, and manage logs.

## Manage logs

There are various options available for managing export logs.

1. In Customer Journey Analytics, select [!UICONTROL **Components**] > [!UICONTROL **Exports**].

1. Select the [!UICONTROL **Logs**] tab, then select one or more existing logs.

   <!-- add screenshot? -->

1. Select one of the following options:

   |Option | Function | 
   |---------|----------|
   | [!UICONTROL **Retry**] | Re-runs the export associated with the selected log, using the data as it was on the day the log was originally exported. This is useful when selecting a log that show a failed export or when selecting a log that was accidentally deleted. </br>This option is not available when selecting multiple logs. | 
   | [!UICONTROL **Create ticket**] | Opens a dialog that allows you to specify details about any issues you encountered in the selected logs. Selecting [!UICONTROL **Submit**] in the dialog creates a ticket for Adobe Customer Care that includes your feedback along with basic information about the selected logs. Adobe Customer Care responds by email to any tickets you create. | 
   | [!UICONTROL **Open project**] | Opens the project that contains the data associated with the selected log. </br>This option is not available when selecting multiple logs. | 
   | [!UICONTROL **Delete**] | Deletes the selected logs. This does not delete the export associated with the selected logs. | 

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
   | Status | The status of the export. The following statuses are available: <ul><li>Pending</li><li>Completed</li><li>Failed</li></ul> | 

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

1. Ensure that any columns you want to display are selected. Selected columns appear on the Exports page and display the relevant information.