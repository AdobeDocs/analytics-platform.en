---
title: Include Exclude values component settings
description: Conditionally include or exclude a dimension item depending on its value.
exl-id: 1a3f8ab5-bd82-415a-989a-f93e6714df4b
solution: Customer Journey Analytics
feature: Data Views
role: Admin
---
# Include Exclude values component settings {#include-exclude-values-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_dataview_component_metric_includeexcludevalues"
>title="Include exclude values"
>abstract="Filter a metric to only count values matching specific criteria."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_dataview_component_dimension_includeexcludevalues"
>title="Include exclude values"
>abstract="Narrow a dimension to only include values matching specific criteria. Inclusions and exclusions happen before allocation and filters in reports.<br/><br/>**Parameters**<br/>**Case sensitive**: Determine if the filter logic below is case-sensitive."

<!-- markdownlint-enable MD034 -->

Include Exclude values lets you create rules that depend on the value of a dimension item. Values that don't meet the criteria that you set are treated in Analysis Workspace as if they never existed, though the data still exists in the underlying dataset.

![Data views window highlighting the Include exclude values](../assets/include-exclude.png)

| Setting | Description/Use case |
| --- | --- |
| [!UICONTROL Set include/exclude values] | A checkbox that lets you enable conditions where data is included in a data view. |
| [!UICONTROL Case sensitive] | Visible on String schema data types. Defaults to on. This setting applies only to the [!UICONTROL Include/Exclude Values] logic, not to the resulting value. It allows you to specify if the rule is case sensitive. |
| [!UICONTROL Match] | Lets you specify which values you would like to consider for reporting prior to attribution and filters (e.g., only use values containing the phrase "error"). You can specify **[!UICONTROL If all criteria are met]** or **[!UICONTROL If any criteria are met]**. Separate each value using a space. |
| [!UICONTROL Criteria] | Lets you specify the match logic that should be applied to a specific filter rule.<ul><li>**String**: [!UICONNTROL Contains the phrase], [!UICONTROL Contains any term], [!UICONTROL Contains all terms], [!UICONTROL Does not contain any term], [!UICONTROL Does not contain the phrase], [!UICONTROL Equals], [!UICONTROL Does not equal], [!UICONTROL Starts with], [!UICONTROL Ends with]</li><li>**Double/Integer**: [!UICONTROL Equals], [!UICONTROL Does not equal], [!UICONTROL Is greater than], [!UICONTROL Is less than], [!UICONTROL Is greater than or equal to], [!UICONTROL Is less than or equal to]</li><li>**Date**: [!UICONTROL Equals], [!UICONTROL Does not equal], [!UICONTROL Is later than], [!UICONTROL Is before], [!UICONTROL Occurs within]</li></ul> |
| [!UICONTROL Match operand] | Lets you specify the match operand that the match operator should be applied to.<ul><li>**String**: Text field</li><li>**Double/Integer**: Text Field with up/down arrows for numeric values</li><li>**Date**: Day granularity selector (calendar)</li><li>**Date Time**: Date and time granularity selector</li></ul> |
| [!UICONTROL Add rule] | Lets you specify an additional match operator and operand. |

{style="table-layout:auto"}
