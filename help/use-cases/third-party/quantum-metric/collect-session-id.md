---
title: Collect Quantum Metric session IDs in Customer Journey Analytics
description: Modify your implementation to include session IDs so you can analyze them in Customer Journey Analytics.
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: yes
hide: yes
exl-id: cfe4bafd-afe6-4738-94f1-30882893b3b6
---
# Collect Quantum Metric session IDs in Customer Journey Analytics

Some use cases, such as [tying Quantum Metric session replays](tie-session-replays.md) or [using Quantum Metric heatmaps](heatmap.md) require that you modify your implementation to collect the Quantum Metric session ID. This page outlines that process to successfully bring that data into your existing implementation.

## Prerequisites 
These steps assume that you use tags in Adobe Experience Platform Data Collection. You can adapt these data collection methods towards a manual Web SDK implementation if your organization does not use tags.

## Step 1: Capture the Quantum Metric session ID using the Quantum Metric tags extension

Follow these steps to append the Quantum Metric session ID to the data that you send to Adobe Experience Platform.

1. Use the Quantum Metric extension in the tags UI to send data to Quantum Metric.
1. Create four data elements:
   1. One that captures the Quantum Metric session ID from Quantum Metric's cookie named `QuantumMetricSessionID`
   1. One that extracts the Quantum Metric session ID from `localStorage`. Sometimes this data element loads faster than the cookie set in the other data element.
   1. Use the data element assistant or custom JavaScript to extract the `s` node from the `localStorage` data element.
   1. One that uses logic to first look for the cookie data element and return it to an XDM object path if found. If undefined, try looking in the extracted `localStorage` object data element.
1. Send the final Quantum Metric session ID data element to the XDM object sent in every event.

>[!NOTE]
>Sometimes the Web SDK runs faster than the Quantum Metric code. In these cases, the session ID is sent on the subsequent hit. If a visitor bounces, then the session ID is not collected in these instances.

See the [Quantum Metric tag extension](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/analytics/quantum-metric) documentation for more information.

## Step 2: Confirm included dataset fields

Confirm that the datasets in your connection now have the Quantum Metric session ID in the desired dataset.

## Step 3: Add Quantum Metric session ID as an available dimension

Edit your existing data view to add the session ID as an available dimension in Customer Journey Analytics.

1. Log in to [experience.adobe.com](https://experience.adobe.com).
1. Navigate to Customer Journey Analytics, and select **[!UICONTROL Data views]** in the top menu.
1. Select the desired existing data view.
1. Locate the Quantum Metric session ID field list on the left, and drag it to the dimensions area in the center.
1. In the right pane, set the [persistence](/help/data-views/component-settings/persistence.md) setting to 'Session'.
1. Click **[!UICONTROL Save]**.


