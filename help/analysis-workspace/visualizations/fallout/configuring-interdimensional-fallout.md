---
description: Learn how the fallout visualization in Analysis Workspace lets you mix and match dimensions and metrics as touchpoints in funnels and workflows. Understand how this provides more flexibility in defining the user steps you want to investigate.
title: Inter-Dimensional Fallout
feature: Visualizations
exl-id: 7975324c-4efc-4c36-bc83-dcde85d2febc
role: User
TQID: https://experienceleague.adobe.com/bfanNzUIgz1FKpupAkdgjvkCNMIz0hyaN-CQm6Jj528
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
    internal-label: Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
---
# Inter-dimensional fallout

Fallout in Analysis Workspace lets you mix and match dimensions and metrics as touchpoints in funnels and workflows. Fallouts gives you more flexibility in defining the user steps you want to investigate.

For example, in addition to a Page dimension, you can add other dimension items (like a specific device name from the Device name dimension) to a Fallout visualization. Combining dimensions lets you visualize how pages and certain actions interplay in customers' paths.

![The All Visits view showing multiple dimensions as touchpoints.](assets/fallout-otherdimension.png)

The fallout gets updated dynamically and lets you see fallout across multiple dimensions.

You can also add metrics. For example, you can add the metric Call to show only paths for users for which calls exist and have contacted the call center:

![The All Visits view showing the added metric: "Shared Photo".](assets/fallout-metrics.png)

You can combine dimensions and metrics. Drag another dimension or metric on top of an existing one. For example, to understand the fallout of people that have an iPhone and have contacted the call center.

![The All Visits view showing the added Action Name: Shared AND Shared Photo metric.](assets/fallout-combined.png)
