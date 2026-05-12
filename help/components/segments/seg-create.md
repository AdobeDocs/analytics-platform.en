---
title: Create Segments
description: Understand the segment creation user interface.
exl-id: b6a921d5-7dd3-4230-88b8-5f1cd313b791
feature: Filters, Segments
role: User
TQID: https://experienceleague.adobe.com/mzu9V8ETlAV0gREJQQhRIDFUwZNlKUR-8P1dtwJTCIA
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
    internal-label: Segments, Segments (CJA)
  - id: bcaa1b08-8269-4ff3-a0c2-f599783b6107
    internal-label: Filters
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
    internal-label: Calculated metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
---
# Create segments

You can create different types of segments in Customer Journey Analytics.  The type you select depends on how complex the segments need to be and whether the segments should apply to the current Workspace project only or apply to all projects. You can create segments directly in the main interface of Customer Journey Analytics or when working in a Workspace project. 

By default, only administrators can create segments. Users have rights to view segments, similar to how users view other components (such as annotations, calculated metrics, etc.).

However, administrators can give the **[!UICONTROL Segment Creation]** permission for **[!UICONTROL Reporting Tools]** in **[!UICONTROL Edit permissions for CJA Workspace Access]** to users via the [Admin Console](/help/technotes/access-control.md#user-level-access).

You can create a segment in the following ways:

![Ways to create a segment](assets/create-filter.png)

* **A**. In the main interface, select **[!UICONTROL Components]** and select **[!UICONTROL Segments]**. Select ![AddCircle](/help/assets/icons/AddCircle.svg) [!UICONTROL **[!UICONTROL Add]**] from the [[!UICONTROL Segment] manager](/help/components/segments/seg-manage.md). 
* **B**. In a Workspace project, from the Components left panel, select ![Add](/help/assets/icons/Add.svg) at ![Segment](/help/assets/icons/Segmentation.svg) **Segments**.
* **C**. In a Workspace project, from the context menu in a visualization, select **[!UICONTROL Create segment from selection]**.
* **D**. In a Workspace project, select **[!UICONTROL Components]** from the menu, and select **[!UICONTROL Create segment]**. 
* **E**. In a Workspace project, use the shortcut **[!UICONTROL shift+cmd+e]** (macOS) or **[!UICONTROL shift+ctrl+e]** (Windows).
* **F**. Select ![Add](/help/assets/icons/Add.svg) in ***Drop a segment here (or any other component)*** drop zone. This action creates a Project-only segment.

To define the new segment, you use the [Segment builder](/help/components/segments/seg-builder.md).

When you are in a Workspace project, you can also create a segment quickly using [Quick segment](/help/components/segments/seg-quick.md).
