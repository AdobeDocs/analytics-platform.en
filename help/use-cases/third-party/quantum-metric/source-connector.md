---
title: Add Quantum Metric data to Customer Journey Analytics
description: Use Quantum Metric for data collection of user journeys and behaviors, then power CJA from that collected data to draw out richer insights.
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hide: true
exl-id: ea8795fe-f5aa-458f-9e01-53ff1ffe6372
TQID: https://experienceleague.adobe.com/LLrYpPlbagFAIeuD9TMgA3E8lrcUrMxMSWLC-8SiiIY
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
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
    internal-label: Data management
---
# Add Quantum Metric data to Customer Journey Analytics

>[!IMPORTANT]
>
>The Quantum Metric source connector is not yet available at this time.

CJA unlocks report-time control off the QM data, sequential data analysis, rich attribution, and other advanced reporting.  QM can be sent to AEP by using either the QM source connector or the Quantum Metrics Tags extension.

## Step 1: Create a Quantum Metric source connector

1. Log in to [experience.adobe.com](https://experience.adobe.com).
1. Navigate to [!UICONTROL Experience Platform] > [!UICONTROL Connections] > [!UICONTROL Sources].
1. Add the Quantum Metric source connector, and follow the prompts to completion.

See [Adobe Experience Platform source connectors](https://experienceleague.adobe.com/en/docs/experience-platform/sources/home) for more information.

## Step 2: Create a connection in Customer Journey Analytics

Creating a source connector for Quantum Metric data automatically creates a dataset in Adobe Experience Platform. Add this dataset to a new or existing [connection](/help/connections/overview.md) in Customer Journey Analytics.

1. Log in to [experience.adobe.com](https://experience.adobe.com).
1. Navigate to Customer Journey Analytics, and select **[!UICONTROL Connections]**, optionally from **[!UICONTROL Data management]**, in the top menu.
1. Give the connection a name, and add the Quantum Metric dataset to the connection.
1. Click **[!UICONTROL Save]**.

>[!NOTE]
>While you can add Quantum Metric data to the same connection as the rest of your Customer Journey Analytics data, that data cannot be stitched together without a common person ID between the two datasets. If this behavior is desired, Adobe recommends using the [Tag extension](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/analytics/quantum-metric) instead of the source connector.

## Step 3: Create a data view in Customer Journey Analytics

Create a [data view](/help/data-views/data-views.md) to configure dimension and metric settings.

1. Log in to [experience.adobe.com](https://experience.adobe.com).
1. Navigate to Customer Journey Analytics, and select **[!UICONTROL Data views]**, optionally from **[!UICONTROL Data management]**, in the top menu.
1. Select the desired data view, or create a data view.
1. Locate the desired Quantum Metric dimensions and metrics in the schema fields list on the right, and drag them to the dimensions and metrics area in the center.
1. Use the right pane to configure each desired dimension and metric.

## Step 4: Start reporting and analyzing in Customer Journey Analytics

Now that the data is available in Customer Journey Analytics, you can start reporting on data.

1. Log in to [experience.adobe.com](https://experience.adobe.com).
1. Navigate to Customer Journey Analytics, and select **[!UICONTROL Workspace]** in the top menu.
1. Select an existing project, or create a project.
1. Drag any desired Quantum Metric dimension or metric to the Workspace canvas to analyze the data.
