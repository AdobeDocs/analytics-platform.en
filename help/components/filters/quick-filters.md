---
description: Use quick filters in Analysis Workspace for Customer Journey Analytics
title: Quick filters
feature: Workspace Basics
role: User
exl-id: 549e5db5-fcdf-43c5-bc43-590144aee309
---
# Quick filters

Quick filters allow you to explore data within a Workspace project quickly, without the need to create a filter in the [Filter Builder](/help/components/filters/create-filters.md). 


+++ The following video demonstrates how to use quick filters.

>[!VIDEO](https://video.tv.adobe.com/v/341466/?quality=12&learn=on)


+++

When you want to use quick filters, please note that:

* Quick filters are created directly in a Workspace project. As a result, a quick filter applies only to the Workspace project in which you create the quick filter. The quick filters in your Workspace project are not available in other projects and cannot be shared to other users. 
* You can only specify three conditions as part of a quick filter.
* Quick filters do not support nested containers or sequential conditions.
* You can edit quick filters within a shared Workspace project. So, other users can edit the quick filters in a Workspace project you have shared with these users.

## Create

Quick filters apply to panels. You can create one ore more quick filters for every panel in your Workspace project. Any user in Analysis Workspace can create quick filters. 

To create a quick filter:

* Select ![FilterAdd](/help/assets/icons/FilterAdd.svg) at the top of the panel. <br/>Then, directly edit the filter in the [Quick filter builder](#quick-filter-builder).
* Drag a component from the component panel to the filter drop zone in the panel header. Once dropped, hover over the filter and select ![Edit](/help/assets/icons/Edit.svg) to edit the filter in the [Quick filter builder](#quick-filter-builder).

When you create a quick filter using drag and drop, note that:

* Not all component types are supported. Calculated metrics are not supported, and only dimensions and metrics from which you can build filters are supported.
* For dimensions and metrics components, the [Quick filter builder](#quick-filter-builder) creates automatically an `exists` conditions. For example, if you drag and drop `City`, the condition `City exists` is created.
* For dimension values, the [Quick filter builder](#quick-filter-builder) automatically creates an `equals` condition. For example, if you drag and drop `amsterdam` from the `City` dimension, the condition `City equals amsterdam` is created.
* If you drag and drop `unspecified` or `none`, the [Quick filter builder](#quick-filter-builder) creates automatically a `does not exist` condition.

Quick filters you create appear at the top of the panel. Quick filters do have a light blue thin left bar. When a quick filter is in edit mode using the [Quick filter builder](#quick-filter-builder), the background of the Quick filter is light blue.

The results of the quick filters you create in a panel are applied (using AND logic) to all the visualizations that are part of the panel.


## Manage

To manage a quick filter, hover over the specific **[!UICONTROL Quick filter]**.

* Select ![Edit](/help/assets/icons/Edit.svg) to open the [Quick filter builder](#quick-filter-builder) and edit the quick filter.
* Select ![InfoOutline](/help/assets/icons/InfoOutline.svg) to open a popup. The popup displays information about the filter. You can select **[!UICONTROL Make available to all projects and add to your component list]** To add the filter to the ![Filter](/help/assets/icons/Segmentation.svg) **[!UICONTROL Filters]** component list in the component panel. You see a **[!UICONTROL Save quick filter]** dialog, prompting you to specify a name for the filter. Select **[!UICONTROL Save]** to continue. Your [!UICONTROL Quick filter] turns into a **[!UICONTROL Filter]**. You cannot edit the Filter anymore using the [Quick filter builder](#quick-filter-builder). Instead, you have to edit the filter as a regular filter, using the [Filter builder](filter-builder.md).

## Quick filter builder

See below for an example of the quick filter builder. In the example, the builder is opened for the quick filter titled `Call Reason = Order Change AND Online Orders is greater than or equal 1`. Both quick filters at the top do apply to the [!UICONTROL Average Order Value Dashboard] panel and all visualizations within, such as the [!UICONTROL Average Order Value Per Country] freeform table.

![Quick filter builder](assets/quick-filter-builder.png)

The quick filter builder consists of the following areas and buttons.

### Header area 

The header area determines the name, type and scope of the quick filter. It also displays a visual for the results of the quick filter.

| Element | Description | 
|---|---|
| **[!UICONTROL Name]** | The name is automatically derived from the quick filter definition. |
| **[!UICONTROL People]** <br/>![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) ![Alert](/help/assets/icons/Alert.svg) | Preview visual of the data resulting from the quick filter. A bar and percentage provide insight in how much of the overall data is part of the result of the quick filter. A red ![Alert](/help/assets/icons/Alert.svg) signals that the quick filter does not return data. |
| **[!UICONTROL Include]**<br/>**[!UICONTROL Exclude]** | Select from the dropdown ![ChevronDown](/help/assets/icons/ChevronDown.svg) whether you want to include or exclude the results of the quick filter from the data in the panel. |
| **[!UICONTROL Event]**<br/>**[!UICONTROL Session]**<br/>**[!UICONTROL Person]** | Select from the dropdown ![ChevronDown](/help/assets/icons/ChevronDown.svg) the scope of the quick filter. |

### Condition area 

The condition area specifies the conditions (up to a maximum of three). For each condition you can specify the following:

| Element | Description | 
|---|---|
| **[!UICONTROL Dimension]**<br/>**[!UICONTROL Metric]**<br/>**[!UICONTROL Date&nbsp;range]** | Select from the dropdown ![ChevronDown](/help/assets/icons/ChevronDown.svg) whether you want to specify a condition for a dimension, metric or date range. |
| **[!UICONTROL *component*]** | The component field for the condition. You can [!UICONTROL *Type to add*] a component, select a component from the list, or you can drag and drop a component from the component panel. You can only drop similar components on the component field of the condition. For example, you can only drop a dimension component from the component panel on a dimension condition. <br/>You can also drag and drop to replace an existing component.<br/>Select ![CrossSize75](/help/assets/icons/CrossSize75.svg) to delete the component from the component field. | 
| **[!UICONTROL *operator*]** | The operator for the component. See [Operators](operators.md) for more information. Only available for dimensions and metrics. |
| **[!UICONTROL *value*]** | The value for the condition. Depending on the operator selected, the value can be selected from a list or you enter a value. |
| ![CrossSize75](/help/assets/icons/CrossSize75.svg) | Select to delete a condition from the quick filter. |

### Buttons

| Button | Description |
|---|---|
| **[!UICONTROL AND]**<br/>**[!UICONTROL OR]** | Only available when you define more than one condition. Select from the dropdown ![ChevronDown](/help/assets/icons/ChevronDown.svg) between the conditions. The selection determines the boolean logic for the quick filter. You cannot mix logic when having three conditions. The boolean logic is either **[!UICONTROL AND]** or **[!UICONTROL OR]**. |
| ![AddCircle](/help/assets/icons/AddCircle.svg) | Adds another condition to your quick filter. This button is only available when you have defined one or two conditions for the quick filter. |
| **[!UICONTROL Apply]** | Apply the changes to the quick filter. |
| **[!UICONTROL Open builder]** | You are prompted for confirmation with an **[!UICONTROL Are your sure?]** dialog. If you select **[!UICONTROL OK]**, you can no longer modify your filter in the [Quick filter builder](#quick-filter-builder) Your quick filter is renamed to **[!UICONTROL Filter]** and now has a darker blue thin left bar.<br/>The regular [Filter builder](filter-builder.md) opens with the option to **[!UICONTROL Make this filter available to all your projects and add it to your component list]**. <ul><li>If you select this option and select **[!UICONTROL Apply]**, the filter is added to the ![Filter](/help/assets/icons/Segmentation.svg) **[!UICONTROL Filters]** component list in the component panel.</li><li>If you do not select this option and select **[!UICONTROL Apply]**, the filter remains a Workspace project-only filter.</li></ul> | 
| **[!UICONTROL Cancel]** | Select to cancel the creation or edit of a quick filter. |

## Quick filters versus Filters

Quick filters are exactly what they are named. You can create and edit quick filters quickly inline and see the effects immediately in your panel. 

Filters do have the following advantages compared to quick filters.

* Filters can be made available across all your Workspace projects
* Filters support more complexity using nested and hierarchical containers, sequences (using qequence filters).


