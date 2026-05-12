---
description: Learn how to use quick segments in Analysis Workspace.
title: Quick Segments
feature: Workspace Basics, Filters, Segments
role: User
exl-id: 549e5db5-fcdf-43c5-bc43-590144aee309
TQID: https://experienceleague.adobe.com/DvRdeldUVvvaUfzWVV-vTflR1iZvMUH68pZQTL1d8D8
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: a8b1c240-f315-46e3-b813-f545c4279dd1
    internal-label: Workspace basics
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
    internal-label: Metrics
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
    internal-label: Segments, Segments (CJA)
  - id: bcaa1b08-8269-4ff3-a0c2-f599783b6107
    internal-label: Filters
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
    internal-label: Dimensions
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
    internal-label: Calculated metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
---
# Quick segments

Quick segments allow you to explore data within a Workspace project quickly, without the need to create a segment in the [Segment Builder](/help/components/segments/seg-create.md). 



>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Quick segments in Analysis Workspace](https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/components/filters/create-a-quick-filter){target="_blank"} for a demo video.

>[!ENDSHADEBOX]


When you want to use quick segments, please note that:

* Quick segments are created directly in a Workspace project. As a result, a quick segment applies only to the Workspace project in which you create the quick segment. The quick segments in your Workspace project are not available in other projects and cannot be shared to other users. 
* You can only specify three conditions as part of a quick segment.
* Quick segments do not support nested containers or sequential conditions.
* You can edit quick segments within a shared Workspace project. So, other users can edit the quick segments in a Workspace project you have shared with these users.

## Create

Quick segments apply to panels. You can create one or more quick segments for every panel in your Workspace project. Any user in Analysis Workspace can create quick segments. 

To create a quick segment:

* Select ![SegmentAdd](/help/assets/icons/FilterAdd.svg) at the top of the panel. <br/>Then, directly edit the segment in the [Quick segment builder](#quick-segment-builder).
* Drag a component from the component panel to the segment drop zone in the panel header. Once dropped, hover over the segment and select ![Edit](/help/assets/icons/Edit.svg) to edit the segment in the [Quick segment builder](#quick-segment-builder).

When you create a quick segment using drag and drop, note that:

* Not all component types are supported. Calculated metrics are not supported, and only dimensions and metrics from which you can build segments are supported.
* For dimensions and metrics components, the [Quick segment builder](#quick-segment-builder) creates automatically an `exists` conditions. For example, if you drag and drop **[!UICONTROL City]**, the condition **[!UICONTROL City]** **[!UICONTROL exists]** is created.
* For dimension values, the [Quick segment builder](#quick-segment-builder) automatically creates an **[!UICONTROL equals]** condition. For example, if you drag and drop **[!UICONTROL Amsterdam]** from the **[!UICONTROL City]** dimension list, the condition **[!UICONTROL City]** **[!UICONTROL equals]** `Amsterdam` is created.
* If you drag and drop **[!UICONTROL unspecified]** or **[!UICONTROL none]**, the [Quick segment builder](#quick-segment-builder) automatically creates a **[!UICONTROL does not exist]** condition.

Quick segments you create appear at the top of the panel. Quick segments do have a light blue thin left bar. When a quick segment is in edit mode using the [Quick segment builder](#quick-segment-builder), the background of the Quick segment is light blue.

The results of the quick segments you create in a panel are applied (using AND logic) to all the visualizations that are part of the panel.


## Manage

To manage a quick segment, hover over the specific **[!UICONTROL Quick segment]**.

* Select ![Edit](/help/assets/icons/Edit.svg) to open the [Quick segment builder](#quick-segment-builder) and edit the quick segment.
* Select ![InfoOutline](/help/assets/icons/InfoOutline.svg) to open a popup. The popup displays information about the segment. You can select **[!UICONTROL Make available to all projects and add to your component list]** To add the segment to the ![Segment](/help/assets/icons/Segmentation.svg) **[!UICONTROL Segments]** component list in the component panel. You see a **[!UICONTROL Save quick segment]** dialog, prompting you to specify a name for the segment. Select **[!UICONTROL Save]** to continue. Your [!UICONTROL Quick segment] turns into a **[!UICONTROL Segment]**. You cannot edit the segment any more using the [Quick segment builder](#quick-segment-builder). Instead, you have to edit the segment as a regular segment, using the [Segment builder](seg-builder.md).

## Quick segment builder

See below for an example of the Quick segment builder. In the example, the builder is opened for a quick segment titled `Call Reason = Order Change AND Online Orders is greater than or equal 1`. Both quick segments at the top do apply to the **[!UICONTROL Average Order Value Dashboard]** panel and all visualizations within, such as the [!UICONTROL Average Order Value Per Country] freeform table.

![Quick segment builder](assets/quick-filter-builder.png)

The quick segment builder consists of the following areas and buttons.

### Header area 

The header area determines the name, type and scope of the quick segment. It also displays a visual for the results of the quick segment.

| Element | Description |
|---|---|
| **[!UICONTROL Name]** | The name is automatically derived from the quick segment definition. |
| **[!UICONTROL People]** <br/>![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) ![Alert](/help/assets/icons/Alert.svg) | Preview visual of the data resulting from the quick segment. A bar and percentage provide insight in how much of the overall data is part of the result of the quick segment. A ![Alert](/help/assets/icons/AlertRed.svg) signals that the quick segment does not return data. |
| **[!UICONTROL Include]**<br/>**[!UICONTROL Exclude]** | Select from the drop-down ![ChevronDown](/help/assets/icons/ChevronDown.svg) whether you want to include or exclude the results of the quick segment from the data in the panel. |
| **[!UICONTROL Event]**<br/>**[!UICONTROL Session]**<br/>**[!UICONTROL Person]** | Select from the drop-down menu ![ChevronDown](/help/assets/icons/ChevronDown.svg) the scope of the quick segment. |

### Condition area 

The condition area specifies the conditions (up to a maximum of three). For each condition you can specify the following:

| Element | Description |
|---|---|
| **[!UICONTROL Dimension]**<br/>**[!UICONTROL Metric]**<br/>**[!UICONTROL Date&nbsp;range]** | Select from the drop-down menu ![ChevronDown](/help/assets/icons/ChevronDown.svg) whether you want to specify a condition for a dimension, metric or date range. |
| **[!UICONTROL *component*]** | The component field for the condition. You can [!UICONTROL *Type to add*] a component, select a component from the list, or you can drag and drop a component from the component panel. You can only drop similar components on the component field of the condition. For example, you can only drop a dimension component from the component panel on a dimension condition. <br/>You can also drag and drop to replace an existing component.<br/>Select ![CrossSize75](/help/assets/icons/CrossSize75.svg) to delete the component from the component field. |
| **[!UICONTROL *operator*]** | The operator for the component. See [Operators](seg-operators.md) for more information. Only available for dimensions and metrics. |
| **[!UICONTROL *value*]** | The value for the condition. Depending on the operator selected, the value can be selected from a list or you enter a value. |
| ![CrossSize75](/help/assets/icons/CrossSize75.svg) | Select to delete a condition from the quick segment. |

### Buttons

| Button | Description |
|---|---|
| **[!UICONTROL AND]**<br/>**[!UICONTROL OR]** | Only available when you define more than one condition. Select from the drop-down menu ![ChevronDown](/help/assets/icons/ChevronDown.svg) between the conditions. The selection determines the boolean logic for the quick segment. You cannot mix logic when having three conditions. The boolean logic is either **[!UICONTROL AND]** or **[!UICONTROL OR]**. |
| ![AddCircle](/help/assets/icons/AddCircle.svg) | Adds another condition to your quick segment. This button is only available when you have defined one or two conditions for the quick segment. |
| **[!UICONTROL Apply]** | Apply the changes to the quick segment. |
| **[!UICONTROL Open builder]** | You are prompted for confirmation with an **[!UICONTROL Are your sure?]** dialog. If you select **[!UICONTROL OK]**, you can no longer modify your segment in the [Quick segment builder](#quick-segment-builder) Your quick segment is renamed to **[!UICONTROL Segment]** and now has a darker blue thin left bar.<br/>The regular [Segment builder](seg-builder.md) opens with the option to **[!UICONTROL Make this segment available to all your projects and add it to your component list]**. <ul><li>If you select this option and select **[!UICONTROL Apply]**, the segment is added to the ![Segment](/help/assets/icons/Segmentation.svg) **[!UICONTROL Segment]** component list in the component panel.</li><li>If you do not select this option and select **[!UICONTROL Apply]**, the segment remains a Workspace project-only segment.</li></ul> |
| **[!UICONTROL Cancel]** | Select to cancel the creation or edit of a quick segment. |

## Quick segments versus segments

Quick segments are exactly what they are named. You can create and edit quick segments quickly inline and see the effects immediately in your panel. 

Segments do have the following advantages compared to quick segments.

* Segments can be made available across all your Workspace projects
* Segments support more complexity using nested and hierarchical [containers](seg-builder.md#containers), and sequences (using [sequential segments](seg-sequential-build.md)).


