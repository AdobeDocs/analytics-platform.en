---
description: Send an Analysis Workspace project to a cloud location.
keywords: Analysis Workspace
title: Export project data to the cloud
feature: Curate and Share
---
# Export project data to the cloud

You can export full table data from Analysis Workspace and send it to designated cloud destinations. 

## Advantages of exporting full table data to the cloud

There are various methods of exporting data, as described in [Export project data overview](/help/analysis-workspace/export/export-project-overview.md). 

Exporting full table data to the cloud allows you to: 

* Export data to a shared location, such as Google Cloud Platform, Microsoft Azure, Amazon S3, Snowflake, or Adobe Experience Platform.

* Store large amounts of historical data.

  This type of data can be used to detect long-term trends in order to gain business intelligence, and ultimately lead to better business decision-making.
  
* Export full tables that contain thousands or millions of rows. Other export methods allow a maximum of 50,000 rows.

* Breakdown a variable by more than Workspace limits (5 breakdowns) <!-- does this apply to the other export methods also? -->

* Supports calculated metrics

* Data output is structured as concatenated values (like Data Warehouse for Adobe Analytics).

* Send exported data ad hoc or on a schedule. (Also available with [other export options](/help/analysis-workspace/export/export-project-overview.md))

* Export files in CSV or PDF format. (Also available with [other export options](/help/analysis-workspace/export/export-project-overview.md))

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
