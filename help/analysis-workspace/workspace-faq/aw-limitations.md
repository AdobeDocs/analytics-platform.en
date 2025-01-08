---
description: Learn about known limitations in Adobe Analysis Workspace and its related components
title: Known limitations in Analysis Workspace
feature: FAQ
exl-id: 334cfe24-a4b2-43be-94df-5a2df90612f0
role: User
---
# Known limitations in Analysis Workspace 

Here is a list of known limitations in Analysis Workspace and its related components: 

## Tables

* Date comparison columns cannot be added when either date ranges or metrics are used as rows of a table.
* Create metric from selection is disabled when filters are used as rows of a table. Additionally, Create metric from selection should not be applied to date-aligned columns.
* Conditional formatting for breakdown rows cannot use custom ranges.
* Table total rows cannot be trended when Calculate totals by summing the row values setting is applied (typically used with Static row items).

## Visualizations

* Visualizations that leverage filters, such as [!UICONTROL Fallout], [!UICONTROL Flow], [!UICONTROL Cohort], and [!UICONTROL Histogram], cannot accept calculated metrics as inputs.
* [!UICONTROL Flow]: Entry/Exit dimensions, e.g. [!UICONTROL Entry page], cannot be used in Flow.
* [!UICONTROL Cohort]: Non-integers cannot be used as Cohort criteria.

## Filters

* Certain metrics and dimensions cannot be filtered, such as [!UICONTROL Events], [!UICONTROL Persons], etc.
* Ad hoc filters created in the [panel dropzone](/help/analysis-workspace/c-panels/panels.md) are a type of quick filter. They do not appear in the left panel of Workspace or the Filter component manager unless they are made public. For more information, see [Quick filters](/help/components/filters/quick-filters.md).

## Calculated Metrics

* Calculated metrics cannot be used in certain visualizations. See [Visualizations](#visualizations).
* Calculated metrics cannot be used in the [!UICONTROL Attribution] panel, since calculated metrics themselves can include separate attribution models.
* Certain components and operators are unavailable if a calculated metric is created from Workspace (as opposed to being created from [!UICONTROL Components > filters]). For example, [!UICONTROL IP Address].

## Date Ranges

* Custom date ranges do not support [!UICONTROL This day last year], [!UICONTROL This day last month], etc.


## Report Settings

* Some of the settings on the [!UICONTROL Report Settings] page do not apply. Analysis Workspace uses only the [!UICONTROL Language/Currency/Encoding] settings at the bottom: [!UICONTROL Thousands separator], [!UICONTROL Scheduled Report Encoding], and [!UICONTROL CSV Separator Character].

