---
description: Learn how to create calculated metrics.
title: Create Calculated Metrics
feature: Calculated Metrics
exl-id: 55ed36c1-99ca-400a-bc2b-661994cbf720
TQID: https://experienceleague.adobe.com/8xHrnqI8ZUf3qwy4Im3Qa-ESAokGMs3XPOYmpFF6Dx0
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
    internal-label: Metrics
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
    internal-label: Segments, Segments (CJA)
  - id: bcaa1b08-8269-4ff3-a0c2-f599783b6107
    internal-label: Filters
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
    internal-label: Calculated metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
---
# Create calculated metrics

By default, only administrators can create calculated metrics. Users have rights to view calculated metrics, similar to how users view other components (such as segments, annotations, and more).

However, administrators can give the **[!UICONTROL Calculated Metric Creation]** permission for **[!UICONTROL Reporting Tools]** in **[!UICONTROL Edit permissions for CJA Workspace Access]** to users via the [Admin Console](/help/technotes/access-control.md#user-level-access).


You can create a calculated metric in the following ways:

![Ways to create a metric](assets/create-metric.png)

* **A**. In the main interface, select **[!UICONTROL Components]** and select **[!UICONTROL Calculated metrics]**. Select ![AddCircle](/help/assets/icons/AddCircle.svg) [!UICONTROL **[!UICONTROL Add]**] from the [[!UICONTROL Calculated metrics] manager](/help/components/calc-metrics/cm-workflow/cm-manager.md). 
* **B**. In a Workspace project, from the Components left panel, select ![Add](/help/assets/icons/Add.svg) at ![Event](/help/assets/icons/Event.svg) **Metrics**.
* **C**. In a Workspace project, from the context menu in metrics column header, select **[!UICONTROL Create metric from selection]**. From the submenu, you can select a function, or select **[!UICONTROL Open in calculated metric builder]**. <br/>If you select a function, the calculated metric is defined as a project-only metric. When you later edit this metric, through the [Component info](/help/components/use-components-in-workspace.md#component-info) popup, you see a notification in the [Calculated metric builder](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).
* **D**. In a Workspace project, select **[!UICONTROL Components]** from the menu, and select **[!UICONTROL Create metric]**. 
* **E**. In a Workspace project, use the shortcut **[!UICONTROL shift+cmd+c]** (macOS) or **[!UICONTROL shift+ctrl+c]** (Windows).

To define the new calculated metric, you use the [Calculated metric builder](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).


## Workflow 

Before you create calculated metrics, carefully consider the following workflow:

| Workflow Task | Description |
| --- | --- |
| Plan calculated metrics | Especially for metrics that are going to be officially approved, planning makes sense to outline which calculated metrics will be widely used and how they will be defined. |
| [Build](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md) calculated metrics | Build and edit calculated and advanced calculated metrics for use in [!DNL Customer Journey Analytics] components. |
| [Tag](cm-tagging.md) calculated metrics | Tag calculated metrics for ease of organization and sharing. See how to plan and assign tags for simple and advanced searches and organization. |
| [Approve](cm-approving.md) calculated metrics | Approve calculated metrics to make them canonical. |
| Use calculated metrics | Use the calculated metrics in your projects. |
| [Share](cm-sharing.md) calculated metrics | Share your calculated metrics with other individuals, groups, or organizations. |
| [Filter](cm-filter.md) calculated metrics | Filter calculated metrics by tags, owners, and other filters (Show All, Mine, Shared With me, Favorites, and Approved.) |
| Mark calculated metrics as [favorites](cm-finding.md) | Marking metrics as favorites is another way to organize them for ease of use.|

