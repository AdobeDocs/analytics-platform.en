---
title: Use Quantum Metric heatmaps with Customer Journey Analytics
description: Better understand page-level engagement and optimize pages based on consumer behavior using Quantum Metric heatmap data.
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
exl-id: d861135f-42a4-45ac-8b11-41f151bfce92
autotag-review: '2026-05-19T09:50:41.180Z'
TQID: 'https://experienceleague.adobe.com/EvPGghY3E7eoiJb6TcWnaOhneS6oQJj4bcwU3K2v3Ng'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
    internal-label: Integrations
subfeature_v2:
  - id: e1bd5a34-b16e-477b-84cc-247fa0793f4b
    internal-label: Analytics integration
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
---
# Use Quantum Metric heatmaps with Customer Journey Analytics

Linking Quantum Metric heatmapping to CJA data lets you better understand page-level engagement and optimize pages based on consumer behavior. Workspace can be used to understand consumer user flows and see what paths consumers follow from one page to the next. Then, you can click hyperlinked Page URLs to visually heatmap how users engage with the content. By linking Quantum Metric Heatmapping to CJA, you can now associate page-level interactions with business outcomes, taking your analysis to the next level.

The table will return all the sessions in that segment, and you can click any one of them to explore further in QM.  Learn more about Quantum Metric session replay at https://www.quantummetric.com/platform/session-replay 

## Prerequisites

You must be entitled to Quantum Metric's **UX Ops** package in order to access Quantum Metric's heatmap capabilities.

## Step 1: Configure links in Analysis Workspace

1. Log in to [experience.adobe.com](https://experience.adobe.com).
1. Navigate to Customer Journey Analytics, and select **[!UICONTROL Workspace]** in the top menu.
1. Select an existing project, or create a project.
1. Create a [Freeform table](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md).
1. Drag the page URL dimension to the Workspace canvas.
1. Right-click the dimension column header, then select **[!UICONTROL Create hyperlinks for all dimension items]**.
1. Select **[!UICONTROL Create a custom URL]**.
1. Paste the following URL structure:

    ```
    $value?qm-visible=true
    ```

1. Click **[!UICONTROL Create]**.
1. Test one of the links to see if it opens in the URL with the Quantum Metric extension visible. These links open in a new tab so your Workspace project remains open.

![Heatmap](assets/heatmap.png)

## Step 2: View heatmaps by clicking links within Customer Journey Analytics

Once you've found a page that you want to explore heatmapping, you can apply it to the desired panel. The table returns a URL that lets you explore heatmaps, scroll depth, and key zones for interaction using Quantum Metric. See [Quantum Metric heatmap product overview](https://www.quantummetric.com/platform/interaction-heatmaps) for more information. You can also contact your Quantum Metric customer support representative or submit a request through the [Quantum Metric Customer Request Portal](https://community.quantummetric.com/s/public-support-page).
