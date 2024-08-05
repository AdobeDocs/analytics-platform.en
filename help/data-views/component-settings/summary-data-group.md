---
title: Summary data group component settings
description: Combine numeric values in a dimension.
solution: Customer Journey Analytics
feature: Data Views
role: Admin
---
# [!UICONTROL Summary data group] component settings

A summary data group creates an association between all dimensions in the grouping and is used to combine dimensions from summary datasets with other dimensions for reporting.

![Summary data group component settings](/help/data-views/assets/summary-data-group.png)

To create a grouping of dimensions:

1. Select a dimension.
1. Select ![ChevronDown](/help/assets/icons/ChevronDown.svg) **[!UICONTROL Summary data group]**.
1. Enable **[!UICONTROL Create grouping]**.
1. Select a dimension from the **[!UICONTROL Dimension]** dropdown that you want to group with the selected dimension from the first step. 
1. Optionally, enable **[!UICONTROL Hide in reporting]** to hide the grouped dimension from reporting. Enabling this option is similar as configuring **[!UICONTROL Hide in reporting]** on the grouped dimension separately. See [Component settings](overview.md) for more information.
1. Optionally, to add additional dimensions to the grouping, select ![Add](/help/assets/icons/Add.svg) **[!UICONTROL Add dimension to group]**.<br/>You can add up to nine dimensions, as a summary data group has a limit of ten dimensions.

## Same component settings

When grouping dimensions, you must ensure the settings for [!UICONTROL Substring], [!UICONTROL Behavior (Lower case)], and [!UICONTROL Include exclude values] for each of the dimensions part of the group are the same. Otherwise, each dimension of the group can potentially return different results prior to the grouping.
For example:

1. You have created a summary data group for [!UICONTROL campaign_code] (part of summary data) and [!UICONTROL tracking_code] (part of your event data).
1. You have applied [!UICONTROL Behaviour (Lower case)] to the [!UICONTROL campaign_code] but not to the tracking_code dimension.
   
Values in [!UICONTROL tracking_code] potentially can show up as different from [!UICONTROL campaign_code].

>[!IMPORTANT]
>
>Ensure you do the grouping of dimensions from one dimension only, and not apply grouping from multiple dimensions. For example, if you create a grouping by adding the `campaign_name` dimension to the `tracking_code` dimension, do not also create a grouping for the `campaign_name` dimension.
>


