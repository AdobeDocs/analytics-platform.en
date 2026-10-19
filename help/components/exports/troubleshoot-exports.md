---
description: Manage logs for existing exports
keywords: Analysis Workspace
title: Troubleshoot failed exports
feature: Components
exl-id: fbc25150-4390-40a2-9f17-aadf254258ad
role: User
TQID: https://experienceleague.adobe.com/pKXaX-DMxsFn9Y39AjqL1VGaSM--WFda9fuD7zJLgoI
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
  - id: eb00932f-4d46-46bc-b1d8-10de7588db8d
    internal-label: Data governance
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
    internal-label: Metrics
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
    internal-label: Dimensions
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
    internal-label: Exports
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
    internal-label: Governance
---
# Troubleshoot failed exports

When you [export full tables from Analysis Workspace to cloud destinations](/help/analysis-workspace/export/export-cloud.md), you can view the status of those exports both from the [Exports tab](/help/components/exports/manage-exports.md) and from the [Logs tab](/help/components/exports/manage-export-logs.md). Failed exports show a status of [!UICONTROL **Failed**].

## Common failures and actions

Exports can fail for various reasons. The following table describes some of the most common reasons, with actions you can take to address the failures:

|Reason for failure | Suggested action | More information |
|---------|----------|---------|
| Invalid location or account information | Make sure your credentials and other information is correct for the cloud account and location you are exporting to. | [Configure cloud export accounts](/help/components/exports/cloud-export-accounts.md) and [Configure cloud export locations](/help/components/exports/cloud-export-locations.md). |
| A dimension or metric in the report was removed from the data view | Contact your system administrator to see which components were removed from the data view. You might need to use a different data view in your export, or remove components from your table that are no longer available.  | [Export Customer Journey Analytics reports to the cloud](/help/analysis-workspace/export/export-cloud.md) |
| Row limit exceeded | Depending on your license type, you can export a maximum of 3 million, 30 million, 150 million, or 300 million rows. Update the table you are exporting to reduce the number of total rows. | [Export Customer Journey Analytics reports to the cloud](/help/analysis-workspace/export/export-cloud.md) |
| Scheduled export expiration | The scheduled export that you configured has expired. Update the export's expiration. | [Manage exports](/help/components/exports/manage-exports.md) |
| Dimension not supported | <p>Any dimension that meets all of the following criteria is not supported in Full Table Export:</p> <ul><li>Was created from a field that is part of an array of objects</li><li>Has persistence enabled<li>Is not using a binding dimension</li> | <ul><li>[Use arrays of objects](/help/use-cases/object-arrays.md)</li><li>[Persistence component settings](/help/data-views/component-settings/persistence.md)<li>[Use binding dimensions and metrics in Customer Journey Analytics](/help/use-cases/data-views/binding-dimensions-metrics.md)</li> |
| A data governance policy that is enforced by your organization restricts components in your table from being exported | Contact your system administrator to see which components are restricted from being exported. Remove the restricted components prior to exporting. | *Filter on Data Governance policies in data views* section in [Labels and policies](/help/data-views/data-governance.md) |

## Contact Adobe Customer Care

If you continue to experience issues, contact Adobe Customer Care. When contacting customer care regarding a failed export, make sure you have the following information available:

* Export name

* Export ID

* Instance ID

* Data view name

* Location

* Account

* Connection

* Company name
