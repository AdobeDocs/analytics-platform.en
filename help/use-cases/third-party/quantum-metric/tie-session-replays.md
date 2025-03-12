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

By linking Quantum Metric session replays with CJA data, customers can better understand "the why" behind "the what".  Workspace can be used to discover sessions with friction, then you can click hyperlinked session IDs to explore the session replay in Quantum Metric.  This data allows for viewing behavior within a session and better understanding of what drives consumer friction.

## Prerequisites

This use case requires that you collect Quantum Metric's session ID alongside the rest of your implementation. See [Collect Quantum Metric session IDs in Customer Journey Analytics](collect-session-id.md) to learn how to modify your implementation.

## Step 1: Configure Workspace to accommodate the session ID dimension

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

Each session ID is now a clickable link. These links take you to Quantum Metric in a new tab, allowing you to analyze that particular session in more detail. See [Create hyperlinks in a freeform table](/help/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md) for more information on adding hyperlinks to Analysis Workspace dimension items.

## Step 2 Viewing sessions from Customer Journey Analytics

Once you create the Workspace report with clickable links, you can use Filters in Customer Journey Analytics to identify interesting sessions that you can further analyze in Quantum Metric.
The table will return all the sessions in that segment, and you can click any one of them to explore further in QM.  Learn more about Quantum Metric session replay at https://www.quantummetric.com/platform/session-replay

