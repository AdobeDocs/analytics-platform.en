---
title: Add Quantum Metric friction events to Customer Journey Analytics
description: Add depths to insights in Customer Journey Analytics using friction events collected in Quantum Metric.
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: yes
hide: yes
exl-id: 1b7d5159-39b2-4ba4-be64-f448ae53c70e
---
# Add Quantum Metric friction events to Customer Journey Analytics

Quantum Metric collects friction events such as page load slowness, page load errors, rage clicks, and more. These events can be passed into Customer Journey Analytics as complementary events in the user journey. With this combined data, you can better understand the impact of friction on downstream metrics.

This use case has two requirements:

* You must be entitled to Quantum Metric's **Dev Ops** package.
* You must use tags in Adobe Experience Platform Data Collection.

## Step 1: Capture friction events using the Quantum Metric tag extension

The Quantum Metric CSM team can help you determine the right schema elements to add, and help instruct you to modify your implementation to collect the desired data for use in Customer Journey Analytics. Contact your Quantum Metric customer success manager for more information.

Ultimately, you will want to begin tracking the friction event name in a field.

## Step 2: Confirm included dataset fields

Confirm that the datasets in your connection now have the Quantum Metric session ID in the desired dataset.

## Step 3: Add one or more dimensions and metrics to the data view in Customer Journey Analytics

Edit your existing data view to add the session ID as an available dimension in Customer Journey Analytics.

1. Log in to [experience.adobe.com](https://experience.adobe.com).
1. Navigate to Customer Journey Analytics, and select **[!UICONTROL Data views]** in the top menu.
1. Select the desired existing data view.
1. Locate the Quantum Metric friction event field list on the left, and drag it to the metrics area in the center.
1. In the right pane, set the [Include/Exclude values](/help/data-views/component-settings/include-exclude-values.md) setting to the desired friction events that you want to track. You can add multiple friction events to the same metric to combine them. You can also drag another copy of the friction events field to the metrics area to track other friction events as a separate metric.
1. Once you have created all desired dimensions and metrics, Click **[!UICONTROL Save]**.

## Step 4: Use the dimension and metrics with the rest of your data in Analysis Workspace

With Quantum Metric friction event data collected alongside the rest of your visitor data, you can use them exactly as you would any other dimension or metric in Customer Journey Analytics.

1. Log in to [experience.adobe.com](https://experience.adobe.com).
1. Navigate to Customer Journey Analytics, and select **[!UICONTROL Workspace]** in the top menu.
1. Select an existing project, or create a project.
1. Create a [Freeform table](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md).
1. Drag the desired dimensions and metrics to the Workspace canvas for analysis.

Possible analysis ideas are:

* Trend friction event data over time
* In a fallout or funnel visualization, add Customer Journey Analytics events as some steps and Quantum Metric friction events as others. This report allows you to see where visitors most commonly run into trouble.
* Create and apply a filter for visitors who experience friction events for deeper analysis
