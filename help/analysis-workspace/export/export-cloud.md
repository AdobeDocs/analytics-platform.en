---
description: Export an Analysis Workspace project to a cloud location.
keywords: Analysis Workspace
title: Export Customer Journey Analytics data to the cloud
feature: Curate and Share
---
# Export Customer Journey Analytics data to the cloud

{{select-package}}

You can export full tables from Customer Journey Analytics and send data to designated cloud destinations. 

Other methods of exporting Customer Journey Analytics data are also available, as described in [Export overview](/help/analysis-workspace/export/export-project-overview.md).

## Advantages of exporting to the cloud

Exporting Customer Journey Analytics data to the cloud allows you to: 

* Export to a shared location, such as Google Cloud Platform, Microsoft Azure, Amazon S3, Snowflake, or Adobe Experience Platform.

* Store large amounts of historical data.

  This type of data can be used to detect long-term trends in order to gain business intelligence, and ultimately lead to better business decision-making.
  
* Export full tables that contain thousands or millions of rows. Other export methods allow a maximum of 50,000 rows.

* Include calculated metrics in the exported Customer Journey Analytics data.

* Structure data output as concatenated values (like Data Warehouse for Adobe Analytics).

* Export ad hoc or on a schedule. (Also available with [other export options](/help/analysis-workspace/export/export-project-overview.md).)

* Export files in CSV or PDF format. (Also available with [other export options](/help/analysis-workspace/export/export-project-overview.md).)

## Export full tables from Analysis Workspace

>[!NOTE]
>
>Tables must include at least one dimension and one metric to be supported with a full-table export. 
>
>For information about other restrictions associated with full-table exports, see [Features and components not supported with full-table exports](#features-and-components-not-supported-with-full-table-exports).

To export full tables from Analysis Workspace:

1. If you haven't already, configure an export account and location, as described in [Configure cloud export accounts](/help/components/exports/cloud-export-accounts.md).

1. In Analysis Workspace, right-click the Freeform table that contains the data that you want to export. 

1. Select [!UICONTROL **Export full table**].

1. In the [!UICONTROL **New export**] dialog box, specify the following information:

   |Field name | Function | 
   |---------|----------|
   | Name | B1 | 
   | Tags | B2 | 
   | Data view | B3 | 
   | Reporting window | B3 | 
   | Preview | B3 | 
   | Clear | B3 | 
   | File format | B3 | 
   | Data view | Change the data view that components are being taken from <!-- re-word. A data view drop-down will be updated. Also adding a Data view column in the export. (I also might need to write a warning dialog that comes up if there are components that don't exist in the new data view they're picking -->
   | Include manifest file | B3 | 
   | Export frequency | <!-- We'll add One Time, and then the below will go away... It's either a drop-down or a range picker. Both in the Data table section above. Lookback window changes depending on what is selected (if they're doing Daily, then we might not let them look back to the last year)... --> | 
   | Starting on  | B3 | 
   | Ending on | B3 | 
   | Daily frequency | B3 | 
   | Optimize for consistent delivery time | B3 | 
   |  | B3 |
   |  | B3 |
   |  | B3 |
   |  | B3 |

1. Select ...

## Features and components not supported with full-table exports

### Unsupported features

The following features are not supported and are automatically removed from full-table exports:

* Percentages
* Totals
* Search filtering
* Static rows
* Date aligning
* Dynamic dimensions
* Dimensions in the first breakdown are converted and added as a secondary dimension in the row of the exported table; any other breakdowns are not included in the table
* Sorting is not supported for most data sets; data might be sorted for small data sets
* Attribution models (in calculated metrics and on metric columns)

### Unsupported components

The following components are not supported, and Analysis Workspace prompts you to remove them from your table when performing a full-table export:

* Calculated metrics that use advanced functions in the metric definition (see [Advanced functions](/help/components/calc-metrics/cm-adv-functions.md) for more information)
* Calculated metrics that use a non-default attribution model (see the *Use non-default attribution model* section in [Column settings](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md) for more information)
* Components that have been restricted by an administrator from being exported (see the *Filter on Data Governance policies in data views* section in [Labels and policies](/help/data-views/data-governance.md) for more information)
* In table columns:
  * Date ranges
  * Dimensions
* In table rows:
  * Calculated metrics
  * Metrics
  * Date ranges
  * Filters

 ## Manage exports

After data is exported from Analysis Workspace, you can edit, re-export, duplicate, tag, or delete existing exports, as described in [Manage exports](/help/components/exports/manage-exports.md). 

You can also retry or log support tickets for failed exports, as described in [Manage export logs](/help/components/exports/manage-export-logs.md).
