---
title: Context-aware sessions
description: Settings in a Data view you can use to define context-aware sessions.
solution: Customer Journey Analytics
feature: Data Views
---

# Context-aware sessions

Context-aware sessions in Data views change how Customer Journey Analytics calculates sessions from the data in your connection.

Within the [!UICONTROL Settings] tab of Data views, you can define a session in any way to match how persons interact with your digital experiences. Context-aware session definitions are non-destructive and do not alter the underlying data. You can set up multiple data views each with their specific context-aware session definition as a foundation for your workspace projects.

To define the context of a session for a data view:

1. Select **[!UICONTROL Data views]** in the Customer Journey Analytics UI.

1. Create a new or edit an existing data view. See [Create or edit a data view](create-dataview.md) for more information.

1. Select the **[!UICONTROL Settings]** tab. Underneath [!UICONTROL Session settings]:

   1. Enter a value for **[!UICONTROL Session timeout]** in [!UICONTROL minute(s)], [!UICONTROL hour(s)], [!UICONTROL day(s)], or [!UICONTROL week(s)]. The session timeout determines how long a session can be idle (no events occur) before starting a new session.

   2. Select a metric from the **[!UICONTROL Drop a metric here]** list underneath [!UICONTROL Start new session with a metric]. Alternatively you can drag and drop a metric from the left pane on the **[!UICONTROL Drop a metric field]**. The selected metric defines the start of a new session. You can define more than one metric.

1. Select **[!UICONTROL Save]** or **[!UICONTROL Save and finish]** to save the context-aware session definition.

