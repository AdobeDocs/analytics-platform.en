---
description: Learn how to export a full table to a cloud location.
keywords: Analysis Workspace
title: Export Full Tables To The Cloud
feature: Curate and Share
exl-id: 072eadcc-43ff-42e3-86ee-82062fa02eba
role: User
---
# Export full tables to the cloud {#full-table-export}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-full-table-export"
>title="Create full table exports similar to Data Warehouse"
>abstract="Full table exports are available as soon as you see data in Analysis Workspace. You can create or schedule full table exports as needed.<br><br>You can create full table exports in only a few minutes if you already know what data to include in the export."

<!-- markdownlint-enable MD034 -->

In Customer Journey Analytics, you can export full tables from Analysis Workspace to designated cloud destinations.

Other methods of exporting Customer Journey Analytics reports are also available, as described in [Export overview](/help/analysis-workspace/export/export-project-overview.md).

## Understand full table export

You can export full tables from Analysis Workspace to cloud providers like Google, Azure, Amazon, and Adobe.

[Advantages of full table export](#advantages-of-full-table-export) include the ability to export millions of rows, include calculated metrics, structure data output in concatenated values, and more. 

When exporting full tables, consider the following:

* Before you export to the cloud, make sure that your tables, your environment, and your permissions meet the [minimum export requirements](#minimum-requirements).

* Some [features](#unsupported-features) and [components](#unsupported-components) are not supported when exporting full tables to the cloud.

Use the following process when exporting full tables to the cloud:

1. [Configure a cloud account](/help/components/exports/cloud-export-accounts.md)

1. [Configure a location on the account](/help/components/exports/cloud-export-locations.md)

1. [Export a full table from Workspace](#export-full-tables)

1. Access data in the cloudin your cloud account and [Manage exports in Adobe](/help/components/exports/manage-exports.md)

![The full table export process described in steps 1 through 4.](assets/export-full-table-process.png)

## Export full tables  {#export-from-workspace}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-export-details"
>title="Details"
>abstract="Specify a name for the export. You can also add a description and any tags. This information helps to identify the export in the exports table and in email notifications."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-export-data-structure"
>title="Data structure"
>abstract="This is the Freeform table that you are exporting. You can modify the data structure by dragging components from the left panel to the table. You can apply a filter by dragging a component into the filter area. The table dynamically updates as you add components to the canvas."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="export-manifest"
>title="Include manifest file"
>abstract="When selected, a manifest file is included with any successful export delivery. The manifest file enables you to confirm that all files were delivered successfully."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-export-schedule"
>title="Schedule"
>abstract="Select how often the export should occur. Choose Send now (one-time) to initiate the export immediately. Scheduled exports are initiated at the date and time you specify."

<!-- markdownlint-enable MD034 -->


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-export-destination"
>title="Destination"
>abstract="Select the cloud account and location where you want the data to be sent. You can choose an existing account and location or select 'Add new' to create them. Specify users and groups to notify about failed or expiring exports."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-export-file-format"
>title="File format"
>abstract="When choosing the Parquet file format, some special characters included in component names are replaced with an underscore (_). See the link below for a complete list of characters that are replaced."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-export-notifications"
>title="Notifications"
>abstract="Add users and groups who you want to receive notifications when this export fails or is about to expire."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
>
>Before you export data as described in this section, learn more about full table export in the [Understand full table export](#understand-full-table-export) section above.

To export full tables from Analysis Workspace:

1. If you haven't already, configure an export account and location, as described in [Configure cloud export accounts](/help/components/exports/cloud-export-accounts.md) and [Configure export locations](/help/components/exports/cloud-export-locations.md).

1. In Analysis Workspace, right-click the heading of a freeform table to reveal the context menu, then select [!UICONTROL **Export full table**].

   ![The Freeform table context menu with Export full table highlighted.](assets/export-full-table.png)

1. In the [!UICONTROL **New full table export**] dialog box, specify the following information:

   |Field name | Function |
   |---------|----------|
   | Name | Specify a name for the export. This name displays in the list of exports. |
   | Tags | You can apply an existing tag to the export or you can create a new tag and apply it. <p>To apply an existing tag to the export, select any tags from the drop-down menu. Any tags in your company are available to apply.</p> <p>To create a new tag, type the name of the new tag, then press Enter.</p><p>Consider the following when applying tags to an export: <ul><li>Tags that you apply can be filtered on or searched for in the exports table.</li> <li>Tags applied to a project are not automatically applied when exporting a full table, as described in "Configure columns on the exports page" in [Manage exports](/help/components/exports/manage-exports.md). (Alternatively, when [scheduling a full project for export](/help/analysis-workspace/export/t-schedule-report.md), any tags applied to the project are automatically applied to the export.) </li></ul> |
   | Description | Add a description to the export. You can choose to view descriptions as a column in the [Exports page](/help/components/exports/manage-exports.md) when viewing exports. |
   | Data view | Select the data view that contains the components that you want to include in the export. The ![Data](/help/assets/icons/Data.svg) Data view drop-down menu is located in the upper-left corner of the dialog.  <p>**Note:** If you select a data view that is missing components that are already included in your data table, then you are prompted to clear and re-create the panel using components that are included in the selected data view. </p> | 
   | Data structure | Displays the Freeform table that you are exporting. You can modify the data structure by dragging components from the left panel to the table. You can apply a filter by dragging a component into the filter area. The table dynamically updates as you add components to the canvas. You can include up to 10 columns.<p>Any segments that were applied to the full table in the project appear above the table. You can apply a segment or group of segments to an export.</p> |
   | Report window | Select the reporting time-frame to include in each export file. Options include [!UICONTROL **Today**], **[!UICONTROL Yesterday]**, **[!UICONTROL Last 7 days]**, **[!UICONTROL Last 30 days]**, **[!UICONTROL This week]**, and **[!UICONTROL This month]**. <p>This option is not displayed when the **[!UICONTROL Export frequency]** is set to **[!UICONTROL Send now (one-time)]**.</p> | 
   | Clear all | Clears the contents of the data table. This allows you to start building a new table directly within the New full table export dialog.  |
   | File format | Choose whether the exported data should be in .csv, .json, or .parquet format. <p>When choosing the Parquet file format, any of the following characters included in component names are replaced with an underscore (_): <ul><li>' ' - ASCII space</li><li>',' - ASCII comma</li><li>';' - ASCII colon</li><li>'{' or '}'  - ASCII open/close brace</li><li>'(' or ')' - ASCII open/close parenthesis</li><li>'\n' - ASCII newline</li><li>'\t' - ASCII tab</li><li>'=' - ASCII equals</li></ul></p> |
   | Include manifest file | When enabled, a manifest file is included with any successful export delivery. <p>The manifest file enables you to confirm that all files were delivered successfully. It includes the following information:</p> <ul><li>A list of all files that were delivered</li><li>The MD5 checksum of each file</li></ul><p>Exported data is available as a compressed file in the cloud destination that you configured, as described in [Configure cloud export accounts](/help/components/exports/cloud-export-accounts.md) and [Configure cloud export locations](/help/components/exports/cloud-export-locations.md).</p><p>The filename of the compressed file is as follows, depending on whether you chose **[!UICONTROL csv]**, **[!UICONTROL json]**, or **[!UICONTROL parquet]** as the file format:</p><ul> <li>`cja-export-{reportInstanceId}-{idx}.csv.gz`</li><li>`cja-export-{reportInstanceId}-{idx}.json.gz`</li><li>`cja-export-<instanceId>-<idx>.snappy.parquet`<p>Each column in the parquet file is compressed.</p></li></ul><p>Choose the file format in the **[!UICONTROL File format]** field above.</p>| 
   | Frequency | Set the schedule for how often the export should occur. <p>You can choose [!UICONTROL **Send now (one-time)**] to send the export only once. When you select this option, the export is initiated immediately.</p><p>Or, you can choose to send the export on a defined schedule. When sending on a schedule, options include **[!UICONTROL Daily]**, **[!UICONTROL Weekly]**, **[!UICONTROL Monthly by day of the week]**, **[!UICONTROL Monthly by day of the month]**, **[!UICONTROL Yearly by day of the month]**, and **[!UICONTROL Yearly by specific date]**. </p> <p>When selecting an export frequency, consider the following:</p><ul><li>The options in the **[!UICONTROL Lookback window]** field change depending on what you select here.</li><li>Additional configuration fields display depending on the option that you choose.</li></ul>  | 
   | Starting on  | The day and time that the scheduled export should begin. <p>This option is available only when choosing a scheduled export frequency.</p> | 
   | Ending on | The day and time that the scheduled export expires. The scheduled export no longer runs after the date and time that you set. <p>This option is available only when choosing a scheduled export frequency.</p> |   
   | View destinations for all users | System administrators can select this option to view all accounts and locations, regardless of who created them. |
   | Account | Select the cloud export account where you want the data to be sent. <p>Or, if you haven't already configured a cloud account that you want to use, you can configure a new account:<ol><li>In the **[!UICONTROL Account]** drop-down menu, select **[!UICONTROL Add account]**, then specify the following information:<ul><li>**[!UICONTROL Location account name]**: Specify a name for the location account. This name appears when creating a location </li><li>**[!UICONTROL Location account description]**: Provide a short description of the account to help differentiate it from other accounts of the same account type.</li><li>**Make account available to all users in your organization**: Select this option if you want to allow other users in your organization to use the account.</li><li>**[!UICONTROL Account type]**: Select the type of cloud account you are exporting to. Available account types are Amazon S3 Role ARN, Google Cloud Platform, Azure SAS, Azure RBAC, Snowflake, and AEP Data Landing Zone.</li></ul><li>To finish configuring your account, continue with the link below that corresponds to the **[!UICONTROL Account type]** you selected:<ul><li>[AEP Data Landing Zone](/help/components/exports/cloud-export-accounts.md#aep-data-landing-zone)</li><li>[Amazon S3 Role ARN](/help/components/exports/cloud-export-accounts.md#amazon-s3-role-arn)</li><li>[Google Cloud Platform](/help/components/exports/cloud-export-accounts.md#google-cloud-platform)</li><li>[Azure SAS](/help/components/exports/cloud-export-accounts.md#azure-sas)</li><li>[Azure RBAC](/help/components/exports/cloud-export-accounts.md#azure-rbac)</li><li>[Snowflake](/help/components/exports/cloud-export-accounts.md#snowflake)</li></ul></ol> |
   | Location | Select the location on the account where you want the export data to be sent.<p>Or, if you haven't already configured a cloud account that you want to use, you can configure a new account:<ol><li>In the **[!UICONTROL Location]** drop-down menu, select **[!UICONTROL Add location]**, then specify the following information:<ul><li>**[!UICONTROL Name]**: The name of the location.</li><li>**[!UICONTROL Description]**: Provide a short description of the location to help differentiate it from other locations on the account.</li><li>**Make location available to all users in your organization**: Select this option if you want to allow other users in your organization to use the location.</li><li>**[!UICONTROL Location account]**: Select the account where you want to create the location.</li></ul><li>To finish configuring your location, continue with the link below that corresponds to the account type that you selected in the **[!UICONTROL Location account]** field:<ul><li>[AEP Data Landing Zone](/help/components/exports/cloud-export-locations.md#aep-data-landing-zone).</li><li>[Amazon S3 Role ARN](/help/components/exports/cloud-export-locations.md#amazon-s3-role-arn)</li><li>[Google Cloud Platform](/help/components/exports/cloud-export-locations.md#google-cloud-platform)</li><li>[Azure SAS](/help/components/exports/cloud-export-locations.md#azure-sas)</li><li>[Azure RBAC](/help/components/exports/cloud-export-locations.md#azure-rbac)</li><li>[Snowflake](/help/components/exports/cloud-export-locations.md#snowflake)</li></ul> |
   | Notifications | Add users and groups who you want to receive notifications when this export fails or is about to expire. Begin typing the name or email address of a user, or begin typing the name of a group, then select it when it appears in the drop-down list. |

   {style="table-layout:auto"}

1. Select [!UICONTROL **Save**] to save the export.

   Data is sent to the cloud account that you specified at the frequency that you specified.

1. (Optional) After you create the export, whether you chose to send it now or on a defined schedule, you can view and manage it on the [Exports page](/help/components/exports/manage-exports.md) and view it in the [Export logs](/help/components/exports/manage-export-logs.md).

## Manage exports

After data is exported from Analysis Workspace, you can edit, re-export, duplicate, tag, or delete existing exports, as described in [Manage exports](/help/components/exports/manage-exports.md). 

## Advantages of full table export {#advantages}

Exporting Customer Journey Analytics data to the cloud allows you to: 

* Export to a shared location, such as Adobe Experience Platform Data Landing Zone, Google Cloud Platform, Microsoft Azure, Amazon S3, or Snowflake.

* Store large amounts of historical data.

  This type of data can be used to detect long-term trends to gain business intelligence, and ultimately lead to better business decision-making.
  
* Export full tables that contain thousands or millions of rows (3 million, 30 million, 150 million, or 300 million rows, depending on license type). Other export methods allow a maximum of 50,000 rows.

* Include calculated metrics in the exported Customer Journey Analytics data.

* Structure data output as concatenated values.

* Export one-time or on a schedule. (Also available with [other export options](/help/analysis-workspace/export/export-project-overview.md).)

* Export files in CSV, JSON, or Parquet format. (Also available with [other export options](/help/analysis-workspace/export/export-project-overview.md).)

* Export tables that include multiple dimensions.

## Minimum requirements

Make sure that your tables, your environment, and your permissions meet the following requirements:

* **Tables:** All tables must include at least one dimension in the row and one metric in each column to be supported with a full-table export. 

* **Environment:** Ensure that the [IP addresses](/help/technotes/ip-addresses.md) and [Domains](/help/technotes/domains.md) used by Customer Journey Analytics are allowed through their organization's firewall.

* **Permissions:** In the Adobe Admin Console, users must be assigned a product profile that has the **[!UICONTROL Full Table Export]** permission assigned to it to export full tables. For information about assigning a permission to a product profile in the Admin Console, see [Customer Journey Analytics permission in Admin Console](/help/technotes/access-control.md).

  >[!NOTE]
  >
  >  Users who are assigned the [Product Admin role](/help/technotes/access-control.md#product-admin-role) always have access to export full tables; these users do not need to be assigned the **[!UICONTROL Full Table Export]** permission.


## Unsupported features

The following features are not supported and are automatically removed from full-table exports:

* Percentages
* Totals
* Search filtering
* Static rows
* Date aligning
* Metrics from summary datasets
* Dynamic dimension items

  Dynamic dimension items are created when you drop a dimension on a column header in a freeform table, resulting in the column being filtered dynamically by the top 5 dimension items. In Analysis Workspace, these top 5 dimension items update each time you load the project. In a full-table export, these dimension items become static. For more information, see [Dynamic vs static dimension items in freeform tables](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md).
* Dimensions in the first breakdown are converted and added as a secondary dimension in the row of the exported table. Any other breakdowns are not included in the table.
* Sorting is not supported for most datasets; data might be sorted for small datasets.

## Unsupported components

The following components are not supported, and Analysis Workspace prompts you to remove them from your table when performing a full-table export:

* Calculated metrics that use unsupported functions in the metric definition (see [Unsupported calculated metric functions](#unsupported-calculated-metric-functions) for more information)
* Components that have been restricted by an administrator from being exported (see the *Segment on Data Governance policies in data views* section in [Labels and policies](/help/data-views/data-governance.md) for more information)
* Any dimension that meets all of the following criteria:
  * Is created from a field that is part of an [array of objects](/help/use-cases/object-arrays.md) (similar to multi-value variables in Adobe Analytics).
  * Has [persistence enabled](/help/data-views/component-settings/persistence.md).
  * Is not using a [binding dimension](/help/use-cases/data-views/binding-dimensions-metrics.md).
* Multiple dimensions that are from fields referencing different [arrays of objects](/help/use-cases/object-arrays.md). (Multiple dimensions referencing the same array of objects are allowed.)
* More than 10 dimensions and 10 metrics per report (up to 10 dimensions and 10 metrics are supported)
* In table columns:
  * Date ranges
  * Dimensions
* In table rows:
  * Calculated metrics
  * Metrics
  * Date ranges
  * Segments

## Calculated metric functions support

The following basic and advanced sections list which calculated metric functions are supported when exporting full tables:

### Basic function support


| Basic function | Support status | 
|---------|----------|
| Absolute Value | ![StatusGreen](/help/assets/icons/StatusGreen.svg) Supported  |
| Column Maximum | ![StatusGreen](/help/assets/icons/StatusGreen.svg) Supported |
| Column Minimum | ![StatusGreen](/help/assets/icons/StatusGreen.svg) Supported | 
| Column Sum | ![StatusGreen](/help/assets/icons/StatusGreen.svg) Supported |
| Count | ![StatusGreen](/help/assets/icons/StatusGreen.svg) Supported |  
| Exponent | ![StatusGreen](/help/assets/icons/StatusGreen.svg) Supported | 
| Mean | ![StatusGreen](/help/assets/icons/StatusGreen.svg) Supported | 
| Median | ![StatusRed](/help/assets/icons/StatusRed.svg) Not supported |
| Modulo | ![StatusGreen](/help/assets/icons/StatusGreen.svg) Supported | 
| Percentile | ![StatusRed](/help/assets/icons/StatusRed.svg) Not supported  |
| Power Operator | ![StatusGreen](/help/assets/icons/StatusGreen.svg) Supported |
| Quartile | ![StatusRed](/help/assets/icons/StatusRed.svg) Not supported  | 
| Row Count | ![StatusGreen](/help/assets/icons/StatusGreen.svg) Supported | 
| Row Max | ![StatusGreen](/help/assets/icons/StatusGreen.svg) Supported | 
| Row Min | ![StatusGreen](/help/assets/icons/StatusGreen.svg) Supported | 
| Row Sum | ![StatusGreen](/help/assets/icons/StatusGreen.svg) Supported | 
| Round | ![StatusGreen](/help/assets/icons/StatusGreen.svg) Supported | 
| Square Root | ![StatusGreen](/help/assets/icons/StatusGreen.svg) Supported | 
| Standard Deviation | ![StatusRed](/help/assets/icons/StatusRed.svg) Not supported | 
| Variance | ![StatusBlue](/help/assets/icons/StatusBlue.svg) Planned |

### Advanced function support

#### Algebra functions

| Advanced function | Support status | 
|---------|----------|
| Log Base 10 (Exponential Algebra) | ![StatusGreen](/help/assets/icons/StatusGreen.svg) Supported  |
| Cube Root (Exponential Algebra) | ![StatusGreen](/help/assets/icons/StatusGreen.svg) Supported    |
| Natural Log (Exponential Algebra) | ![StatusGreen](/help/assets/icons/StatusGreen.svg) Supported  | 
| Floor (Numeric Adjustment Algebra) | ![StatusGreen](/help/assets/icons/StatusGreen.svg) Supported  |

#### Logic functions

| Advanced function | Support status | 
|---------|----------|
| If (Logic) | ![StatusGreen](/help/assets/icons/StatusGreen.svg) Supported  |

#### Boolean functions

| Advanced function | Support status | 
|---------|----------|
| Not (Boolean Operator Logic) | ![StatusGreen](/help/assets/icons/StatusGreen.svg) Supported  |
| Or (Boolean Operator Logic) | ![StatusGreen](/help/assets/icons/StatusGreen.svg) Supported  |
| And (Boolean Operator Logic) | ![StatusGreen](/help/assets/icons/StatusGreen.svg) Supported  |

#### Comparison functions

| Advanced function | Support status | 
|---------|----------|
| Less Than (Comparison Logic) | ![StatusGreen](/help/assets/icons/StatusGreen.svg) Supported  |
| Less Than or Equal (Comparison Logic) | ![StatusGreen](/help/assets/icons/StatusGreen.svg) Supported  |
| Equal (Comparison Logic) | ![StatusGreen](/help/assets/icons/StatusGreen.svg) Supported  |
| Greater Than or Equal (Comparison Logic) | ![StatusGreen](/help/assets/icons/StatusGreen.svg) Supported  |
| Greater Than (Comparison Logic) | ![StatusGreen](/help/assets/icons/StatusGreen.svg) Supported  |
| Not Equal (Comparison Logic) | ![StatusGreen](/help/assets/icons/StatusGreen.svg) Supported  |


#### Trigonometry functions

| Advanced function | Support status | 
|---------|----------|
| Pi | ![StatusGreen](/help/assets/icons/StatusGreen.svg) Supported  |
| Sine (Standard) | ![StatusGreen](/help/assets/icons/StatusGreen.svg) Supported  |
| Cosine (Standard) | ![StatusGreen](/help/assets/icons/StatusGreen.svg) Supported  |
| Tangent (Standard) | ![StatusGreen](/help/assets/icons/StatusGreen.svg) Supported  |
| Arc Sine (Standard) | ![StatusGreen](/help/assets/icons/StatusGreen.svg) Supported  |
| Arc Cosine (Standard) | ![StatusGreen](/help/assets/icons/StatusGreen.svg) Supported  |
| Arc Tangent (Standard) | ![StatusGreen](/help/assets/icons/StatusGreen.svg) Supported  |

#### Hyperbolic functions

| Advanced function | Support status | 
|---------|----------|
| Hyperbolic Cosine | ![StatusGreen](/help/assets/icons/StatusGreen.svg) Supported  |
| Hyperbolic Sine | ![StatusGreen](/help/assets/icons/StatusGreen.svg) Supported  |
| Hyperbolic Tangent | ![StatusGreen](/help/assets/icons/StatusGreen.svg) Supported  |

#### WASKR functions

| Advanced function | Support status | 
|---------|----------|
| Confidence (WASKR) | ![StatusRed](/help/assets/icons/StatusRed.svg) Not supported  |
| Confidence (Lower) (WASKR) | ![StatusRed](/help/assets/icons/StatusRed.svg) Not supported  |
| Confidence (Upper) (WASKR) | ![StatusRed](/help/assets/icons/StatusRed.svg) Not supported  |

#### Distribution functions

| Advanced function | Support status | 
|---------|----------|
| T-Score (Student T-Distribution) | ![StatusRed](/help/assets/icons/StatusRed.svg) Not supported  |
| T-Test (Student T-Distribution) | ![StatusRed](/help/assets/icons/StatusRed.svg) Not supported  |
| CDF-T (Student T-Distribution) | ![StatusRed](/help/assets/icons/StatusRed.svg) Not supported  |
| Z-Score (Normal Distribution) | ![StatusRed](/help/assets/icons/StatusRed.svg) Not supported  |
| Z-Test (Normal Distribution) | ![StatusRed](/help/assets/icons/StatusRed.svg) Not supported  |
| CDF-Z (Normal Distribution) | ![StatusRed](/help/assets/icons/StatusRed.svg) Not supported  |

#### Regression functions

| Advanced function | Support status | 
|---------|----------|
| Correlation Coefficient (Exponential Regression) | ![StatusRed](/help/assets/icons/StatusRed.svg) Not supported  |
| Intercept (Exponential Regression) | ![StatusRed](/help/assets/icons/StatusRed.svg) Not supported  |
| Predicted Y (Exponential Regression) | ![StatusRed](/help/assets/icons/StatusRed.svg) Not supported  |
| Slope (Exponential Regression) | ![StatusRed](/help/assets/icons/StatusRed.svg) Not supported  |
| Correlation Coefficient (Linear Regression) | ![StatusRed](/help/assets/icons/StatusRed.svg) Not supported  |
| Intercept (Linear Regression) | ![StatusRed](/help/assets/icons/StatusRed.svg) Not supported  |
| Predicted Y (Linear Regression) | ![StatusRed](/help/assets/icons/StatusRed.svg) Not supported  |
| Slope (Linear Regression) | ![StatusRed](/help/assets/icons/StatusRed.svg) Not supported  |
| Correlation Coefficient (Log Regression) | ![StatusRed](/help/assets/icons/StatusRed.svg) Not supported  |
| Intercept (Log Regression) | ![StatusRed](/help/assets/icons/StatusRed.svg) Not supported  |
| Predicted Y (Log Regression) | ![StatusRed](/help/assets/icons/StatusRed.svg) Not supported  |
| Slope (Log Regression) | ![StatusRed](/help/assets/icons/StatusRed.svg) Not supported  |
| Correlation Coefficient (Power Regression) | ![StatusRed](/help/assets/icons/StatusRed.svg) Not supported  |
| Intercept (Power Regression) | ![StatusRed](/help/assets/icons/StatusRed.svg) Not supported  |
| Predicted Y (Power Regression) | ![StatusRed](/help/assets/icons/StatusRed.svg) Not supported  |
| Slope (Power Regression) | ![StatusRed](/help/assets/icons/StatusRed.svg) Not supported  |
| Correlation Coefficient (Quadratic Regression) | ![StatusRed](/help/assets/icons/StatusRed.svg) Not supported  |
| Intercept (Quadratic Regression) | ![StatusRed](/help/assets/icons/StatusRed.svg) Not supported  |
| Predicted Y (Quadratic Regression) | ![StatusRed](/help/assets/icons/StatusRed.svg) Not supported  |
| Slope (Quadratic Regression) | ![StatusRed](/help/assets/icons/StatusRed.svg) Not supported  |
| Correlation Coefficient (Reciprocal Regression) | ![StatusRed](/help/assets/icons/StatusRed.svg) Not supported  |
| Intercept (Reciprocal Regression) | ![StatusRed](/help/assets/icons/StatusRed.svg) Not supported  |
| Predicted Y (Reciprocal Regression) | ![StatusRed](/help/assets/icons/StatusRed.svg) Not supported  |
| Slope (Reciprocal Regression) | ![StatusRed](/help/assets/icons/StatusRed.svg) Not supported  |

#### Other advanced functions

| Advanced function | Support status | 
|---------|----------|
| Approximate Count Distinct | ![StatusBlue](/help/assets/icons/StatusBlue.svg) Planned |
| Cumulative | ![StatusBlue](/help/assets/icons/StatusBlue.svg) Planned |
| Cumulative Average | ![StatusBlue](/help/assets/icons/StatusBlue.svg) Planned |
| Lift | ![StatusBlue](/help/assets/icons/StatusBlue.svg) Planned |
| Sample Variance | ![StatusBlue](/help/assets/icons/StatusBlue.svg) Planned |

## Attribution behavior

Full table export supports calculated metrics that use a non-default attribution model (as described in the *Use non-default attribution model* section in [Column settings](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)). 

If a non-default attribution model is being used in a report, the allocation model that is used in the report is either ignored or retained, depending on whether the report has a single dimension or multiple dimensions:

* **For reports that include metric attribution in a single dimension:** [Metric attribution](/help/data-views/component-settings/attribution.md) overrides the [allocation model](/help/data-views/component-settings/persistence.md) as is normally done when using metric attribution.  

  For example, a "first touch" metric attribution overrides a "most recent" dimension allocation.

* **For reports that include metric attribution on multiple dimensions at the same time:** [Metric attribution](/help/data-views/component-settings/attribution.md) is applied in addition to the dimension [allocation model](/help/data-views/component-settings/persistence.md).

  For example, a "first touch" metric attribution is applied in addition to a "most recent" dimension allocation. Additionally, metric attribution is applied to post-allocated dimension item pairs as if they were single dimension items, rather than to each dimension item independently as is normally done in a Freeform table.

   >[!NOTE]
   >
   >Multi-dimensional reports are supported only when exporting data to the cloud, as described in this article.

## Comparison to Data Warehouse

If you previously used Data Warehouse to export Adobe Analytics data, the following table can help you understand the differences between exporting full tables in Customer Journey Analytics versus exporting data with Data Warehouse in Adobe Analytics.

|Feature | Full Table Export in Customer Journey Analytics | Data Warehouse in Adobe Analytics |
|---------|----------|---------|
| Build a custom report | Yes | Yes |
| Calculated metrics | Yes | No |
| Segments | Yes | Limited |
| Dimensions | Limit of 10 | Unlimited |
| Metrics | Limit of 10 | Unlimited |
| Reporting rows | Limit of 3 million, 30 million, 150 million, or 300 million, depending on tier | Unlimited |
| Number of reports | Unlimited | Unlimited |
| Ad hoc (one-time) delivery | Yes | Yes |
| Schedule recurring delivery | Yes | Yes |
| Email delivery | No | Yes |
| FTP / SFTP | No | Legacy support |
| Azure | Yes | Yes |
| Amazon S3 | Yes | Yes |
| Google Cloud Platform | Yes | Yes |
| Snowflake | Yes | No |
| Delivery frequency | Daily | Hourly |
