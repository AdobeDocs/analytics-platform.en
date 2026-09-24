---
title: Reuse Recent Data for Faster Loading in Analysis Workspace
description: Enable a project setting that reuses data from an earlier load for 12 hours, so panels and shared projects load instantly instead of running a new query.
feature: Workspace Basics
exl-id: 6d7b9d34-ec7e-45ec-98cc-0fd4cbfd43d3
role: User
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
subfeature_v2:
  - id: a8b1c240-f315-46e3-b813-f545c4279dd1
    internal-label: Workspace basics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
---

# Reuse recent data

>[!CONTEXTUALHELP]
>id="project_reuse_data"
>title="Reuse recent data for faster loading"
>abstract="When enabled, data loads faster for 12 hours after someone first loads the project. Anyone who opens the project during that window sees the same data. To load the latest data, refresh individual panels or the entire project."

Enabling **[!UICONTROL Reuse recent data for faster loading]** lets a project load instantly by reusing data from an earlier load instead of running a new query every time someone opens it.

## How it works

When you enable **[!UICONTROL Reuse recent data for faster loading]** for a project:

* The first time anyone opens the project, Analysis Workspace runs the query as usual.
* Anyone who opens the same project again within 12 hours sees that same data load instantly, without waiting for a new query.
* After 12 hours, the next person to open the project triggers a new query, which starts a new 12-hour window.

This setting is stored at the data view level, so the data is shared. If you share the project with someone else, they see the same data you saw, as long as they open it within the 12-hour window.

>[!NOTE]
>
>To see the latest data before the 12-hour window ends, refresh individual panels or the entire project, as described below.

## Data-freshness timestamp

When this setting is enabled, a timestamp appears at the top of the project and on each panel, showing the status of the data:

* **[!UICONTROL Showing data from ]***[date]* — All panels in the project are showing data from the date and time shown.
* **[!UICONTROL Showing some data from ]***[date]* — Some panels are showing data from the date and time shown, while others have been refreshed more recently.

## Refresh data

Select **[!UICONTROL Refresh]** next to a panel's timestamp to load the latest data for that panel only. Select **[!UICONTROL Refresh]** at the top of the project to load the latest data for all panels and start a new 12-hour window.

## Enable Reuse recent data for faster loading

1. In Workspace, navigate to **[!UICONTROL Projects]** > **[!UICONTROL Project info and settings]**.
1. Select **[!UICONTROL Reuse recent data for faster loading]**.
1. Select **[!UICONTROL Save]**.
