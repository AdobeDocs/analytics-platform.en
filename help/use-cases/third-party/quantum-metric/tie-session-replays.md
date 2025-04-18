---
title: Tie Quantum Metric session replays to data in Customer Journey Analytics
description: Link Quantum Metric session replays with CJA data to better understand "the why" behind "the what".
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: yes
hide: yes
exl-id: fcc36457-4ce9-4c93-93e2-de03becfd5da
---
# Tie Quantum Metric session replays to data in Customer Journey Analytics

By linking Quantum Metric session replays with CJA data, customers can better understand "the why" behind "the what".  Workspace can be used to discover sessions with friction, then you can click hyperlinked session IDs to explore the session replay in Quantum Metric.  This data allows for viewing behavior within a session and better understanding of what drives consumer friction.  Through session replays tied with CJA, you can capture critical context around customer behavior in your experience. 

## Prerequisites

These steps assume that you use tags in Adobe Experience Platform Data Collection. You can adapt these data collection methods towards a manual Web SDK implementation if your organization does not use tags.

See the [Quantum Metric tag extension](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/analytics/quantum-metric) documentation for more information.

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

## Step 4: Configure Workspace to accommodate the session ID dimension

Create a freeform table in Workspace and configure it so that session ID values are links directly to Quantum Metric.

1. Log in to [experience.adobe.com](https://experience.adobe.com).
1. Navigate to Customer Journey Analytics, and select **[!UICONTROL Workspace]** in the top menu.
1. Select an existing project, or create a project.
1. Create a [Freeform table](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md).
1. Drag the session ID dimension to the Workspace canvas.
1. Right-click the dimension column header, then select **[!UICONTROL Create hyperlinks for all dimension items]**.
1. Select **[!UICONTROL Create a custom URL]**.
1. Paste the following URL structure:

    ```
    https://adobe.quantummetric.com/#/replay/cookie:$value
    ```

1. Click **[!UICONTROL Create]**.

Each session ID is now a clickable link. See [Create hyperlinks in a freeform table](/help/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md) for more information on adding hyperlinks to Analysis Workspace dimension items.

## Step 5: View sessions from Customer Journey Analytics

Once you've found an insteresting segment that you want to explore session replays, you can apply it to the panel that includes your session ID links and  segment. The table returns all sessions in that segment, and you can click any one of them to explore further in Quantum Metric. 

See [The enterprise guide to session replay](https://www.quantummetric.com/resources/ebook/the-enterprise-guide-to-session-replay) on Quantum Metric for more information. You can also contact your Quantum Metric customer support representative or submit a request through the [Quantum Metric Customer Request Portal](https://community.quantummetric.com/s/public-support-page).
