---
description: Learn how to build a simple calculated metric.
title: Build A Simple Calculated Metric
feature: Calculated Metrics
exl-id: 2d1c4677-b07c-4eca-97b7-e5e4594daee1
TQID: https://experienceleague.adobe.com/hbiAmMoSUMm2Ggf5Vkxm484SzYETtgRRZAuaWvlS884
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
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
    internal-label: Calculated metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: bcc5edb5-84c3-4940-9f84-ed88b6c16274
    internal-label: Experimentation
---
# Build a simple calculated metric

The following information explains how to create a simple *Page Views per Visits* metric.

1. Start to build a metric, as described in [Build metrics](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).
1. Name the metric `Page Views per Session` or something similar.
1. Give the metric a user-friendly **[!UICONTROL Description]** to show what the metric is used for.
1. Select the right **[!UICONTROL Format]**. For this example, choose **[!UICONTROL Decimal]**.
1. Decide how many decimal places you want the report to show.
1. In the **[!UICONTROL Show updward trend as]** drop-down menu, select ▲ **[!UICONTROL Good (Green)]**.
1. Add a **[!UICONTROL Tag]** to organize your metrics.
1. For this calculated metric, first drag **[!UICONTROL Page Views]** from the **[!UICONTROL Metrics]** components into the **[!UICONTROL Definition]** section of the canvas.
1. Then drag **[!UICONTROL Sessions]** from the **[!UICONTROL Metrics]** components and drop the metric underneath **[!UICONTROL Page Views]** (wait until the blue line appears before you drop the metric).
1. Select the divide ![Divide](/help/assets/icons/Divide.svg) operator. (Divide is the default operator.) 
1. You can see a **[!UICONTROL Preview]** of the metric while you are building the metric.
1. **[!UICONTROL Product compatibility]** shows if the calculated metric is compatible everywhere in Customer Journey Analytics (excluding experimentation).

   ![Simple calculated metric](assets/simple-calculated-metric.png)
1. Select **[!UICONTROL Save]**.
  
   Notice that the **[!UICONTROL Summary]** formula updates anytime you make a change to the metric definition.

1. (Optional) To share, approve, (re-)tag, rename, or delete a metric, you can go to the [Calculated metrics manager](/help/components/calc-metrics/cm-workflow/cm-manager.md).

