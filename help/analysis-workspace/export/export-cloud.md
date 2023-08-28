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

* Export tables that include multiple dimensions.

## Export full tables from Analysis Workspace

>[!NOTE]
>
>Before you export data as described in this section, make sure your table meets the [Export requirements](#export-requirements).

To export full tables from Analysis Workspace:

1. If you haven't already, configure an export account and location, as described in [Configure cloud export accounts](/help/components/exports/cloud-export-accounts.md).

1. In Analysis Workspace, right-click the Freeform table that contains the data that you want to export. 

1. Select [!UICONTROL **Export full table**].

   ![export full table](assets/export-full-table.png)

1. In the [!UICONTROL **New full table export**] dialog box, specify the following information:

   |Field name | Function | 
   |---------|----------|
   | Name | Specify a name for the export. This name displays in the list of exports. | 
   | Tags | Select any tags to apply to the export. You can filter or search by tags in the exports table. <p>Tags applied to a project are not automatically applied when exporting a full table. (Alternatively, when [scheduling a full project for export](/help/analysis-workspace/export/t-schedule-report.md), any tags applied to the project are automatically applied to the export.)  <!-- Right now we don't have a column for them on the exports table, so this isn't true. Jaden is adding the column. --></p>| 
   | Description | Add a description to the export. |
   | Data view | Select the data view that contains the components that you want to include in the export. <p>**Note:** If you choose a data view that doesn't contain any components that are already included in your data table, then you are prompted to clear the data table and re-create it using components that are included in the data view you select. </p> | 
   | Lookback window | Select the time-frame to include in the data table. Options include [!UICONTROL **Today**], [!UICONTROL **Yesterday**], [!UICONTROL **Last 7 days**], [!UICONTROL **Last 30 days**], [!UICONTROL **This week**], and [!UICONTROL **This month**]. | 
   | Clear | Clears the contents of the data table. This allows you to start building a new table directly within the New full table export dialog.  | 
   | Export frequency | Select how often the export should occur. You can choose [!UICONTROL **One time**] to send the export only once. Or, you can choose to send the export on a defined schedule. When sending on a schedule, options include [!UICONTROL **Daily**], [!UICONTROL **Weekly**], [!UICONTROL **Monthly by day of the week**], [!UICONTROL **Monthly by day of the month**], [!UICONTROL **Yearly by day of the month**], and [!UICONTROL **Yearly by specific date**].<p>When selecting an export frequency, consider the following:</p><ul><li>The options in the [!UICONTROL **Lookback window**] field might change depending on what you select here.<!-- if they're doing Daily, then we might not let them look back to the last year... --></li><li>Additional configuration fields display depending on the option you choose.</li> | 
   | Starting on  | The day that the scheduled export should begin (available only when choosing a scheduled export frequency). | 
   | Ending on | The day that the scheduled export should end (available only when choosing a scheduled export frequency). | 
   | Optimize for consistent delivery time | Select this option if you want delivery to always occur 8 hours after the delivery time specified. <p>For example, for a daily file delivery that is set to occur at 3:00am, that would be: 3:00am + 8 hours = 11:00am</p> | 
   | File format | Choose whether the exported data should be in .csv or .json format. | 
   | Include manifest file | <!-- this is not going to be in the UI, and we're just always going to include it. I still need to document that it will be included, what it's for, and where people can find it. --> | 
   | Account | Select the cloud export account where you want the data to be sent. <p>For more information, see [Configure cloud export accounts](/help/components/exports/cloud-export-accounts.md).</p> |
   | Location name | The location on the account where you want the export data to be sent. <p>For more information, see [Configure cloud export locations](/help/components/exports/cloud-export-locations.md).</p><p>You can select the [!UICONTROL **Add new location**] button to create a new location for an existing export account. |
   | Data Preview | Shows the estimated size, estimated number of rows, and number of breakdowns. | 

1. Select [!UICONTROL **Save**] to save the export.

## Export requirements {#export-requirements}

### Minimum requirements

Tables must include at least one dimension in the row and one metric in each column in order to be supported with a full-table export. 

### Unsupported features

The following features are not supported and are automatically removed from full-table exports:

* Percentages
* Totals
* Search filtering
* Static rows
* Date aligning
* Dynamic dimensions

  For more information, see [Dynamic vs static dimension items in freeform tables](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md).
* Dimensions in the first breakdown are converted and added as a secondary dimension in the row of the exported table; any other breakdowns are not included in the table
* Sorting is not supported for most data sets; data might be sorted for small data sets

### Unsupported components

The following components are not supported, and Analysis Workspace prompts you to remove them from your table when performing a full-table export:

* Calculated metrics that use advanced functions in the metric definition (see [Advanced functions](/help/components/calc-metrics/cm-adv-functions.md) for more information)
* Components that have been restricted by an administrator from being exported (see the *Filter on Data Governance policies in data views* section in [Labels and policies](/help/data-views/data-governance.md) for more information)
* More than 5 dimensions and 5 metrics per report (up to 5 dimensions and 5 metrics are supported)
* In table columns:
  * Date ranges
  * Dimensions
* In table rows:
  * Calculated metrics
  * Metrics
  * Date ranges
  * Filters

### Attribution behavior

Full table export supports calculated metrics that use a non-default attribution model (as described in the *Use non-default attribution model* section in [Column settings](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)). 

When metric attribution is applied to a report that contains multiple dimensions, it does not override the allocation models applied to each of the dimensions in the report. In a single-dimensional report, attribution does override the allocation model. Multi-dimensional reports are supported only when exporting data to the cloud, as described in this article.

For more information about allocation and attribution, see [Persistence component settings](/help/data-views/component-settings/persistence.md) and [Attribution component settings](/help/data-views/component-settings/attribution.md). 

## Manage exports

After data is exported from Analysis Workspace, you can edit, re-export, duplicate, tag, or delete existing exports, as described in [Manage exports](/help/components/exports/manage-exports.md). 

You can also retry or log support tickets for failed exports, as described in [Manage export logs](/help/components/exports/manage-export-logs.md).
