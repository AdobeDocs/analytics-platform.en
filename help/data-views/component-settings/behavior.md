---
title: Behavior component settings
description: Specify how a dimension or metric behaves in reporting.
exl-id: 170f445f-1eac-4b70-8956-1afb0cb2d611
solution: Customer Journey Analytics
feature: Data Views
---
# Behavior component settings

Behavior settings are available on both dimensions and metrics. The available settings depend on the component type and schema data type.

![Behavior settings](../assets/behavior-settings.png)

## Dimension behavior settings

| Setting | Description|
| --- | --- |
| [!UICONTROL Lower case] | De-duplicates rows that have the same value but different case. If enabled, all instances of a dimension with the same value are reported as lower case. For example, your data contains the values `"liverpool"`, `"Liverpool"`, and `"LIVERPOOL"` in a string dimension. If [!UICONTROL Lower case] is enabled, all three values are combined into `"liverpool"`. If disabled, all three values are treated as distinct. |

{style="table-layout:auto"}

![Case-sensitive dimension](../assets/case-sens-workspace.png)

>[!NOTE]
>
>If you enable [!UICONTROL Lower case] on a lookup dataset dimension, multiple lookup values can exist for the same identifier. If this conflict happens, Customer Journey Analytics uses the first ASCII collated value (Uppercase values precede lowercase values). Adobe advises against using lookup datasets that contain the same value when [!UICONTROL Lower case] is enabled.

## Metric behavior settings

| Setting | Description/Use case |
| --- | --- |
| [!UICONTROL Count values] | Visible on Integer and Double schema data types. Increase the metric by the specified amount. For example, increases a metric by 50 if the value of the column is `50`. |
| [!UICONTROL Count instances] | Visible on Integer and Double schema data types. Increase the metric by one, regardless of the value. The presence of any value increases the metric. For example, increases a metric by 1 if the value of the column is `50`. |
| [!UICONTROL Values to count] | Visible on Boolean schema data types. Lets you determine if the metric increases by counting `true`, `false`, or both. |

{style="table-layout:auto"}

You can generate both an 'Orders' and 'Revenue' metric in Analysis Workspace using the same event dataset column with different behaviors. Drag the 'Revenue' dataset column into the data view twice and set one to 'Count values' and the other to 'Count instances'. The 'Orders' metric counts instances, while the 'Revenue' metric counts values.
