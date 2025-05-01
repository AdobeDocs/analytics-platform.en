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

By linking Quantum Metric session replays with CJA data, customers can better understand "the why" behind "the what".  Workspace can be used to discover sessions with friction, then you can click hyperlinked session IDs to explore the session replay in Quantum Metric.  This data allows for viewing behavior within a session and a better understanding of what drives consumer friction.  Through session replays tied with CJA, you can capture critical context around customer behavior in your experience. 

## Prerequisites

These steps assume that you use tags in Adobe Experience Platform Data Collection. You can adapt these data collection methods towards a manual Web SDK implementation if your organization does not use tags.

See the [Quantum Metric tag extension](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/analytics/quantum-metric) documentation for more information.

## Step 1: Create a schema field to accommodate Quantum Metric session ID

This use case requires a dedicated schema field to send data to. You can create this field in any desired location in your schema and name it whatever you'd like. Example values are provided if your organization does not have a preference on name or location.

1. Log in to [experience.adobe.com](https://experience.adobe.com).
1. Navigate to **[!UICONTROL Data Collection]** > **[!UICONTROL Schemas]**.
1. Select the desired schema from the list.
1. Select the ![Add field icon](/help/assets/icons/AddCircle.svg) icon next to the desired object. For example, next to `Implementation Details`.
1. On the right, enter the desired [!UICONTROL Name]. For example, `qmSessionId`.
1. Enter the desired [!UICONTROL Display name]. For example, `Quantum Metric session ID`.
1. Select the [!UICONTROL Type] as **[!UICONTROL String]**.
1. Select **[!UICONTROL Save]**.

## Step 2: Capture the Quantum Metric session ID using the Quantum Metric tag extension

Follow these steps to append the Quantum Metric session ID to the data that you send to Adobe Experience Platform.

1. Log in to [experience.adobe.com](https://experience.adobe.com).
1. Navigate to **[!UICONTROL Data Collection]** > **[!UICONTROL Tags]**.
1. Select the desired tag property.
1. Select **[!UICONTROL Data Elements]**, then select **[!UICONTROL Add Data Element]**.
1. Set the following settings:
   * **[!UICONTROL Name]**: `Quantum Metric session ID`
   * **[!UICONTROL Extension]**: [!UICONTROL Core]
   * **[!UICONTROL Data Element Type]**: [!UICONTROL Custom Code]
1. Select the **[!UICONTROL Open Editor]** button and paste in the following code:

    ```js
    // Check for the presence of the Quantum Metric session ID cookie
    const qmCookie = _satellite.cookie.get("QuantumMetricSessionID");
    if(qmCookie != null) return qmCookie;
    // If a cookie is not set, check local storage
    const qmLocalStorage = JSON.parse(localStorage.getItem("QM_S") || "{}");
    if (qmLocalStorage?.s != null) return qmLocalStorage.s;
    ```

1. Select **[!UICONTROL Save]**.

## Step 3: Map the data element to the desired XDM schema field

Now that the data element has logic to obtain the desired value, map the data element to the XDM object.

1. Within the tag property, select **[!UICONTROL Data Elements]**, then select the data element that houses your XDM object.
1. In the right column of this data element, navigate to the path established when creating the schema field.
1. Set the value to the name of the data element surrounded by percent signs. For example, `%Quantum Metric session ID%`.
1. Select **[!UICONTROL Save]**.
1. Add a library, then publish your changes to production.

If your XDM object is already included in a send event action configuration, then you'll start seeing data when the changes are published.

>[!NOTE]
>
>Sometimes the Web SDK runs faster than the Quantum Metric code. In these cases, the session ID is sent on the subsequent hit. If a visitor bounces, then the session ID is not collected in these instances.

## Step 3: Add Quantum Metric session ID as an available dimension

Once your implementation has the above changes published, edit your existing data view to add the session ID as an available dimension in Customer Journey Analytics.

1. Log in to [experience.adobe.com](https://experience.adobe.com).
1. Navigate to Customer Journey Analytics, and select **[!UICONTROL Data views]** in the top menu.
1. Select the desired existing data view.
1. Locate the Quantum Metric session ID field on the left, and drag it to the dimensions area in the center.
1. In the right pane, set the [persistence](/help/data-views/component-settings/persistence.md) setting to `Session`.
1. Select **[!UICONTROL Save]**.

## Step 4: Configure Analysis Workspace to accommodate the session ID dimension

Create a freeform table in Workspace and configure it so that session ID values link directly to Quantum Metric.

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

Once you've found an interesting segment that you want to explore session replays, you can apply it to the panel that includes your session ID links. The table returns all sessions in that segment, and you can click any one of them to explore further in Quantum Metric. 

See [The enterprise guide to session replay](https://www.quantummetric.com/resources/ebook/the-enterprise-guide-to-session-replay) on Quantum Metric for more information. You can also contact your Quantum Metric customer support representative or submit a request through the [Quantum Metric Customer Request Portal](https://community.quantummetric.com/s/public-support-page).
