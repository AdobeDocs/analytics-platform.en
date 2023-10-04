---
description: Export an Analysis Workspace project to a cloud location.
keywords: Analysis Workspace
title: Export Customer Journey Analytics reports to the cloud
feature: Curate and Share
exl-id: 072eadcc-43ff-42e3-86ee-82062fa02eba
---
# Export Customer Journey Analytics reports to the cloud

{{release-limited-testing}}

You can export Workspace full tables from Customer Journey Analytics and send exports to designated cloud destinations. 

Other methods of exporting Customer Journey Analytics reports are also available, as described in [Export overview](/help/analysis-workspace/export/export-project-overview.md).

## Understand full table export

You can export full tables from Analysis Workspace to cloud providers like Google, Azure, Amazon, and Adobe.

[Advantages of exporting full tables to the cloud](#advantages-of-exporting-to-the-cloud) include the ability to export millions of rows, include calculated metrics, structure data output in concatenated values, and more. 

When exporting full tables, consider the following:

* Before you export to the cloud, make sure that your tables, your environment, and your permissions meet the [export requirements](#export-requirements).

* Some [features](#unsupported-features) and [components](#unsupported-components) are not supported when exporting full tables to the cloud.

Use the following process when exporting full tables to the cloud:

1. [Configure a cloud account](/help/components/exports/cloud-export-accounts.md)

1. [Configure a location on the account](/help/components/exports/cloud-export-locations.md)

1. [Export a full table from Workspace](#export-full-tables-from-analysis-workspace)

1. [Access data in the cloud](#view-exported-data-and-manifest-file) and [Manage exports in Adobe](/help/components/exports/manage-exports.md)

![Full table export process](assets/export-full-table-process.png)

## Export full tables from Analysis Workspace

>[!NOTE]
>
>Before you export data as described in this section, learn more about full table export in the [Understand full table export](#understand-full-table-export) section above.

To export full tables from Analysis Workspace:

1. If you haven't already, configure an export account and location, as described in [Configure cloud export accounts](/help/components/exports/cloud-export-accounts.md).

1. In Analysis Workspace, right-click the Freeform table that contains the data that you want to export. 

1. Select [!UICONTROL **Export full table**].

   ![export full table](assets/export-full-table.png)

1. In the [!UICONTROL **New full table export**] dialog box, specify the following information:

   |Field name | Function | 
   |---------|----------|
   | Name | Specify a name for the export. This name displays in the list of exports. | 
   | Tags | You can apply an existing tag to the export or you can create a new tag and apply it. <p>To apply an existing tag to the export, select any tags from the drop-down menu. Any tags in your company are available to apply<!-- double-check this -->.</p> <p>To create a new tag, type the name of the new tag, then press Enter.</p><p>Consider the following when applying tags to an export: <ul><li>Tags that you apply can be filtered on or searched for in the exports table.</li> <li>Tags applied to a project are not automatically applied when exporting a full table, as described in "Configure columns on the exports page" in [Manage exports](/help/components/exports/manage-exports.md). (Alternatively, when [scheduling a full project for export](/help/analysis-workspace/export/t-schedule-report.md), any tags applied to the project are automatically applied to the export.)  <!-- Right now we don't have a column for them on the exports table, so this isn't true. Jaden is adding the column. --></li></ul> | 
   | Description | Add a description to the export. You can choose to view descriptions as a column in the [Exports page](/help/components/exports/manage-exports.md) when viewing exports. |
   | Data view | Select the data view that contains the components that you want to include in the export. The Data view drop-down menu is located in the upper-left corner of the dialog and can be identified by the data view icon![data view icon](assets/data-view-icon.png).  <p>**Note:** If you choose a data view that is missing components that are already included in your data table, then you are prompted to clear the data table and re-create it using components that are included in the selected data view. </p> | 
   | Lookback window | Select the reporting time-frame to include in each export file. Options include [!UICONTROL **Today**], [!UICONTROL **Yesterday**], [!UICONTROL **Last 7 days**], [!UICONTROL **Last 30 days**], [!UICONTROL **This week**], and [!UICONTROL **This month**]. <p>This option is not displayed when the [!UICONTROL **Export frequency**] is set to [!UICONTROL **Send now (one-time)**]. | 
   | Data table | Displays the Freeform table that you are exporting. You can modify the data table by dragging components from the left rail to the table. The table dynamically updates as you add components to the canvas.  <p>Any segments that were applied to the full table in the project appear at the top of each individual column in the table.</p> |
   | Clear | Clears the contents of the data table. This allows you to start building a new table directly within the New full table export dialog.  | 
   | Export frequency | Set the schedule for how often the export should occur. <p>You can choose [!UICONTROL **Send now (one time)**] to send the export only once. When you select this option, the export is initiated immediately.<p>Or, you can choose to send the export on a defined schedule. When sending on a schedule, options include [!UICONTROL **Daily**], [!UICONTROL **Weekly**], [!UICONTROL **Monthly by day of the week**], [!UICONTROL **Monthly by day of the month**], [!UICONTROL **Yearly by day of the month**], and [!UICONTROL **Yearly by specific date**]. </p><p>When selecting an export frequency, consider the following:</p><ul><li>The options in the [!UICONTROL **Lookback window**] field change depending on what you select here.<!-- if they're doing Daily, then we might not let them look back to the last year... --></li><li>Additional configuration fields display depending on the option you choose.</li></ul>  | 
   | Starting on  | The day and time that the scheduled export should begin. <p>This option is available only when choosing a scheduled export frequency.</p> | 
   | Ending on | The day and time that the scheduled export expires. The scheduled export no longer runs after the date and time that you set. <p>This option is available only when choosing a scheduled export frequency.</p> |  
   | File format | Choose whether the exported data should be in .csv or .json format. |  
   | Account | Select the cloud export account where you want the data to be sent. <p>For more information, see [Configure cloud export accounts](/help/components/exports/cloud-export-accounts.md).</p> |
   | Location name | Select the location on the account where you want the export data to be sent. <p>For more information, see [Configure cloud export locations](/help/components/exports/cloud-export-locations.md).</p><p>You can select the [!UICONTROL **Add new location**] button to create a new location for an existing export account. |

   {style="table-layout:auto"}

1. Select [!UICONTROL **Save**] to save the export.

   Data is sent to the cloud account that you specified at the frequency that you specified.

1. (Optional) After you create the export, whether you chose to send it now or on a defined schedule, you can view and manage it on the [Exports page](/help/components/exports/manage-exports.md) and view it in the [Export logs](/help/components/exports/manage-export-logs.md).</p>

## Manage exports

After data is exported from Analysis Workspace, you can edit, re-export, duplicate, tag, or delete existing exports, as described in [Manage exports](/help/components/exports/manage-exports.md). 

## View exported data and manifest file

### Exported data

Exported data is available as a compressed file in the cloud destination that you configured, as described in [Configure cloud export accounts](/help/components/exports/cloud-export-accounts.md) and [Configure cloud export locations](/help/components/exports/cloud-export-locations.md). 

The filename of the compressed file is as follows, depending on whether you chose CSV or JSON as the file format:

* `cja-export-{reportInstanceId}-{idx}.csv.gz`

* `cja-export-{reportInstanceId}-{idx}.json.gz`

>[!NOTE]
>
>You choose the file format in the [!UICONTROL **File format**] field when exporting the table, as described in [Export full tables from Analysis Workspace](#export-full-tables-from-analysis-workspace).

### Manifest file

A manifest file with a filename of `cja-export-{reportInstanceId}-{idx}.json.gz` is included with any successful export delivery that contains at least one file. The manifest file enables you to confirm that all files were delivered successfully. It includes the following information: 

* A list of all files that were delivered

* The MD5 checksum of each file

<!-- add in  what the file name, structure, and file format will be -->

## Advantages of exporting to the cloud

Exporting Customer Journey Analytics data to the cloud allows you to: 

* Export to a shared location, such as Adobe Experience Platform Data Landing Zone, Google Cloud Platform, Microsoft Azure, Amazon S3, or Snowflake.

* Store large amounts of historical data.

  This type of data can be used to detect long-term trends in order to gain business intelligence, and ultimately lead to better business decision-making.
  
* Export full tables that contain thousands or millions of rows (3 million, 30 million, 150 million, or 300 million rows, depending on license type). Other export methods allow a maximum of 50,000 rows.

* Include calculated metrics in the exported Customer Journey Analytics data.

* Structure data output as concatenated values.

* Export ad hoc or on a schedule. (Also available with [other export options](/help/analysis-workspace/export/export-project-overview.md).)

* Export files in CSV or JSON format. (Also available with [other export options](/help/analysis-workspace/export/export-project-overview.md).)

* Export tables that include multiple dimensions.

## Export requirements {#export-requirements}

### Minimum requirements

Make sure that your tables, your environment, and your permissions meet the following requirements:

* **Tables:** All tables must include at least one dimension in the row and one metric in each column in order to be supported with a full-table export. 

* **Environment:** Administrators should ensure that the IP addresses listed in [IP addresses used by Customer Journey Analytics](/help/admin/ip-addresses.md) are included in the firewall allowlist.

* **Permissions:** In the Adobe Admin Console, users must be assigned a product profile that has the [!UICONTROL **Full Table Export**] permission assigned to it in order to export full tables. For information about assigning a permission to a product profile in the Admin Console, see [Customer Journey Analytics permission in Admin Console](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-admin/cja-access-control.html?lang=en#customer-journey-analytics-permissions-in-admin-console) in [Customer Journey Analytics Access Control](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-admin/cja-access-control.html).

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

* Calculated metrics that use basic or advanced functions in the metric definition (see [Basic functions](/help/components/calc-metrics/cm-functions.md) and [Advanced functions](/help/components/calc-metrics/cm-adv-functions.md) for more information)
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

If a non-default attribution model is being used in a report, the allocation model being used in the report is either ignored or retained, depending on whether the report has a single dimension or multiple dimensions:

* **For reports that include metric attribution in a single dimension:** [Metric attribution](/help/data-views/component-settings/attribution.md) overrides the [allocation model](/help/data-views/component-settings/persistence.md) as is normally done when using metric attribution.  

  For example, a "first touch" metric attribution overrides a "most recent" dimension allocation.

* **For reports that include metric attribution on multiple dimensions at the same time:** [Metric attribution](/help/data-views/component-settings/attribution.md) is applied in addition to the dimension [allocation model](/help/data-views/component-settings/persistence.md).

  For example, a "first touch" metric attribution is applied in addition to a "most recent" dimension allocation. Additionally, metric attribution will be applied to post-allocated dimension item pairs as if they were single dimension items, rather than to each dimension item independently as is normally done in a Freeform table.

   >[!NOTE]
   >
   >Multi-dimensional reports are supported only when exporting data to the cloud, as described in this article.

## Comparison of Full Table Export (in Customer Journey Analytics) to Data Warehouse (in Adobe Analytics)

If you previously used Data Warehouse to export Adobe Analytics data, the following table can help you understand the differences between exporting full tables in Customer Journey Analytics versus exporting data with Data Warehouse in Adobe Analytics.


|Feature | Full Table Export in Customer Journey Analytics | Data Warehouse in Adobe Analytics |
|---------|----------|---------|
| Build a custom report | Yes | Yes |
| Calculated metrics | Yes | No |
| Segments | Yes | Limited |
| Dimensions | Limit of 5 | Unlimited |
| Metrics | Limit of 5 | Unlimited |
| Reporting rows | Limit of 3 million, 30 million, 150 million, or 300 million, depending on tier | Unlimited |
| Number of reports | Unlimited | Unlimited |
| Ad hoc delivery | Yes | Yes |
| Schedule recurring delivery | Yes | Yes |
| Email delivery | No | Yes |
| FTP / SFTP | No | Legacy support |
| Azure | Yes | Yes |
| Amazon S3 | Yes | Yes |
| Google Cloud Platform | Yes | Yes |
| Snowflake | Yes | No |
| Delivery frequency | Daily | Hourly |
