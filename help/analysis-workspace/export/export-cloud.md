---
description: Send an Analysis Workspace project to a cloud location.
keywords: Analysis Workspace
title: Export project data to the cloud
feature: Curate and Share
---
# Export project data to the cloud

You can export full-table data from Analysis Workspace and send it to designated cloud destinations. 

## Advantages of exporting full-table data to the cloud

There are various methods of exporting data, as described in [Export project data overview](/help/analysis-workspace/export/export-project-overview.md). 

Exporting full-table data to the cloud allows you to: 

* Export data to a shared location, such as Google Cloud Platform, Microsoft Azure, Amazon S3, Snowflake, or Adobe Experience Platform.

* Store large amounts of historical data.

  This type of data can be used to detect long-term trends in order to gain business intelligence, and ultimately lead to better business decision-making.
  
* Export full tables that contain thousands or millions of rows. Other export methods allow a maximum of 50,000 rows.

* Break down a variable by more than the current Workspace limitations (5 breakdowns). <!-- does this apply to the other export methods also? -->

* Include calculated metrics in the exported data.

* Structure data output as concatenated values (like Data Warehouse for Adobe Analytics).

* Send exported data ad hoc or on a schedule. (Also available with [other export options](/help/analysis-workspace/export/export-project-overview.md).)

* Export files in CSV or PDF format. (Also available with [other export options](/help/analysis-workspace/export/export-project-overview.md).)

## Export full tables from Analysis Workspace

Before you can export full tables from Analysis Workspace, you first need to configure an export account and location, as described in [Configure cloud export locations](/help/analysis-workspace/export/cloud-export-accounts.md).

To export a full table from Analysis Workspace:

1. In Analysis Workspace, right-click the Freeform table that contains the data that you want to export. 

1. Select [!UICONTROL **Export full table**].

1. On the [!UICONTROL **New export**] dialog box, specify the following information:

   |Field name | Function | 
   |---------|----------|
   | Name | B1 | 
   | Tags | B2 | 
   | Data view | B3 | 
   | Reporting window | B3 | 
   | Preview | B3 | 
   | Clear | B3 | 
   | File format | B3 | 
   | Include manifest file | B3 | 
   | Export frequency | B3 | 
   |  | B3 | 
   |  | B3 | 
   |  | B3 | 

1. Select ...

## Manage existing exports

After you export a full table as described in the sections above, the exports are available on the [!UICONTROL Exports] page. 

You can edit, re-export, duplicate, tag, pause, or delete existing exports:

1. In Customer Journey Analytics, select [!UICONTROL **Components**] > [!UICONTROL **Exports**].

1. On the [!UICONTROL **Exports**] tab, select one or more existing exports.

   <!-- add screenshot? -->

1. Select one of the following options:

   |Option | Function | 
   |---------|----------|
   | [!UICONTROL **Edit**] | Allows you to edit the selected export, including the properties, format, scheduling, and location information. </br>This option is not available when selecting multiple exports. | 
   | [!UICONTROL **Export now**] | Runs the selected export using the most recent data. This is useful if you want to re-export data that you previously exported ad hoc, or if you set up an export to run on a schedule and you want to run the export before the next scheduled export. </br>This option is not available when selecting multiple exports. | 
   | [!UICONTROL **Duplicate**] | Duplicates the selected export. </br>This option is not available when selecting multiple exports. | 
   | [!UICONTROL **Tag**] |  |  
   | [!UICONTROL **Delete**] | Deletes the selected exports. | 

## Manage export logs

Export logs provide details about each export. There are various options available for managing export logs.

1. In Customer Journey Analytics, select [!UICONTROL **Components**] > [!UICONTROL **Exports**].

1. Select the [!UICONTROL **Logs**] tab, then select one or more existing logs.

   <!-- add screenshot? -->

1. Select one of the following options:

   |Option | Function | 
   |---------|----------|
   | [!UICONTROL **Retry**] | Re-runs the export associated with the selected log, using the data as it was on the day the log was originally exported. This is useful when selecting a log that show a failed export or when selecting a log that was accidentally deleted. </br>This option is not available when selecting multiple exports. | 
   | [!UICONTROL **Create ticket**] | Opens a dialog that allows you to specify details about any issues you encountered in the selected logs. Selecting [!UICONTROL **Submit**] in the dialog creates a ticket for Adobe Customer Care that includes your feedback along with basic information about the selected logs. Adobe Customer Care responds by email to any tickets you create. | 
   | [!UICONTROL **Open project**] | Opens the project that contains the data associated with the selected log. </br>This option is not available when selecting multiple exports. | 
   | [!UICONTROL **Delete**] | Deletes the selected logs. This does not delete the export associated with the selected logs. | 



