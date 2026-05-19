---
description: Understand how to use real-time reporting in Analysis Workspace.
title: Use Real-Time Reporting
feature: Real-time Reporting
role: User
exl-id: 6e7dba80-5fb9-4554-b989-85eb54a4bd6a
autotag-review: '2026-05-19T08:47:15.932Z'
TQID: 'https://experienceleague.adobe.com/t20pdV4qS-FIBGrxOXAD5xAD58f4gtN74uheJ94sK4s'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
    internal-label: Administration
  - id: b3197353-f189-4932-8378-3f3bc40e6071
    internal-label: Data management
subfeature_v2:
  - id: d3c978ee-1ff0-4475-968a-721e2dd99ef1
    internal-label: Freeform tables
  - id: d1779026-aeed-458e-a1c7-839d4acac922
    internal-label: Real-time reporting
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
---
# Use real-time reporting {#use-real-time-reporting}

>[!CONTEXTUALHELP]
>id="workspace_panel_realtime_refresh"
>title="Real-time refresh"
>abstract="Enable to refresh data and visualizations in this panel in real-time."

To use real-time reporting, enable the **[!UICONTROL Real-time refresh]** toggle on any of the following panels in your Workspace project:

* [Blank panel](/help/analysis-workspace/c-panels/blank-panel.md)
* [Freeform](/help/analysis-workspace/c-panels/freeform-panel.md)
* [Attribution](/help/analysis-workspace/c-panels/attribution.md)
* [Next or previous item](/help/analysis-workspace/c-panels/next-previous.md)

You see a message with the timestamp of the most recent refresh of the data. For example: [!UICONTROL  *Last refreshed at 07:55 pm*].

Select the real-time period that you want to report on from the drop-down menu. Available options are:

* [!UICONTROL Last 15 minutes]
* [!UICONTROL Last 30 minutes]
* [!UICONTROL Last hour]
* [!UICONTROL Last 8 hours]
* [!UICONTROL Last 24 hours]

All visualizations in the panel are now updated every minute for a maximum of 30 minutes while the browser tab with the real-time refresh enabled panel is active.

As an example, see below a snapshot of a **[!UICONTROL Real-time reporting panel]** that refreshes the **[!UICONTROL Total Revenue / Hour]** bar visualization and **[!UICONTROL Total Revenue / Hour]** freeform table as time moves from **[!UICONTROL *06:26pm*]** to **[!UICONTROL *06:27 pm*]**.

![Real-time refresh](assets/real-time-refresh.gif)

After 30 minutes, or as soon as the browser tab becomes inactive, the **[!UICONTROL Real-time refresh]** toggle is disabled automatically and real-time updates are stopped.

As soon as the Real-time refresh toggle is disabled, the panel (and all visualizations within) return to [use the standard reporting data and features from Customer Journey Analytics](real-time.md#how-it-works).
