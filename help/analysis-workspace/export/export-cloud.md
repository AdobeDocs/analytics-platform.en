---
description: Export an Analysis Workspace project to a cloud location.
keywords: Analysis Workspace
title: Export Customer Journey Analytics data to the cloud
feature: Curate and Share
---
# Export Customer Journey Analytics data to the cloud

{{select-package}}

You can export full tables from Customer Journey Analytics and send it to designated cloud destinations. 

Other methods of exporting Customer Journey Analytics data are also available, as described in [Export overview](/help/analysis-workspace/export/export-project-overview.md).

## Advantages of exporting to the cloud

Exporting Customer Journey Analytics data to the cloud allows you to: 

* Export to a shared location, such as Google Cloud Platform, Microsoft Azure, Amazon S3, Snowflake, or Adobe Experience Platform.

* Store large amounts of historical data.

  This type of data can be used to detect long-term trends in order to gain business intelligence, and ultimately lead to better business decision-making.
  
* Export full tables that contain thousands or millions of rows. Other export methods allow a maximum of 50,000 rows.

* Break down a variable by more than the current Workspace limitations (5 breakdowns). <!-- does this apply to the other export methods also? -->

* Include calculated metrics in the exported Customer Journey Analytics data.

* Structure data output as concatenated values (like Data Warehouse for Adobe Analytics).

* Export ad hoc or on a schedule. (Also available with [other export options](/help/analysis-workspace/export/export-project-overview.md).)

* Export files in CSV or PDF format. (Also available with [other export options](/help/analysis-workspace/export/export-project-overview.md).)

## Export full tables from Analysis Workspace

You can export full tables from Analysis Workspace to designated cloud destinations. 

>[!NOTE]
>
>Consider the following when exporting full tables:
>* Tables must meet the following criteria to be supported with a full-table export:
>   * Include at least one dimension and one metric 
>
>* The following features and components are not supported with a full-table export:
>
>   * Row-based percentages
>   * Search filtering
>   * Static rows
>   * Sorting that is applied 
>   * Totals that are shown 
>   * Date ranges
>   * The following calculated metrics:
>        * <!-- add list of components. I asked for a list in Slack. In Saved for later -->
>* Breakdowns are converted and added as a secondary dimension
>
>* Any components that have been restricted by an administrator from being exported cannot be included in a full-table export. 
>  
>   For more information, see the "Filter on Data Governance policies in data views" section in [Labels and policies](/help/data-views/data-governance.md).

To export full tables from Analysis Workspace:

1. If you haven't already, configure an export account and location, as described in [Configure cloud export accounts](/help/components/exports/cloud-export-accounts.md).

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

## Manage exports

After data is exported from Analysis Workspace, you can edit, re-export, duplicate, tag, or delete existing exports, as described in [Manage exports](/help/components/exports/manage-exports.md). 

You can also retry or log support tickets for failed exports, as described in [Manage export logs](/help/components/exports/manage-export-logs.md).

