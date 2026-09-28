---
title: Use Cached Results for Faster Loading in Analysis Workspace
description: Enable a project setting that caches query results for 12 hours, so panels and shared projects load instantly instead of running a new query.
feature: Workspace Basics
hide: true
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

# Use cached results in Workspace projects

>[!CONTEXTUALHELP]
>id="project_cached_results"
>title="Use cached results for faster loading"
>abstract="When enabled, results load faster for 12 hours after a project is first opened or it is first delivered (for scheduled projects). Anyone who opens the project during that time sees the same results, even though data continues to flow in the background. To load the latest results, refresh individual panels or the entire project."

You can configure Analysis Workspace projects to use cached data from an earlier query for a 12-hour window, allowing results to load instantly. When this option is configured, people who use the project don't have to wait for potentially long load times.

>[!NOTE]
>
>Only the query results are cached. Underlying event data continues to flow into Customer Journey Analytics as usual. Data can be refreshed manually by people who access the project during the 12-hour window before cached results expire.

## Enable cached results for a project

When you enable this option for a project:

* The first time the project runs, Analysis Workspace runs the query as usual and caches the results. This happens when someone opens the project or when the project runs for a scheduled delivery.
* Anyone who opens the same project within 12 hours sees the cached results load instantly, without waiting for a new query.
* After 12 hours, the next person to open the project triggers a new query, which starts a new 12-hour window.

For example, if a project is scheduled for delivery at 6:00 AM, the results are cached until 6:00 PM. The first person to open the project that day sees results load instantly.

This setting is stored at the data view level, so the cached results are shared. If you share the project with someone else, they see the same results you saw, as long as they open it within the 12-hour window.

>[!NOTE]
>
>To see the latest results before the 12-hour window ends, refresh individual panels or the entire project, as described below.

In the Workspace project where you want to enabled cached results for faster loading: 

1. Go to **[!UICONTROL Projects]** > **[!UICONTROL Project info and settings]**.
1. Select **[!UICONTROL Use cached results for faster loading]**.
1. Select **[!UICONTROL Save]**.

## View data timestamps on cached projects

When a project is configured to use cached results, a timestamp displays at the top of the project and on each panel, showing when the results were cached:

* **[!UICONTROL Showing data from ] [_date_]**: All panels in the project show cached results from the date and time shown.
* **[!UICONTROL Showing some data from ] [_date_]**: Some panels show cached results from the date and time shown, while others were refreshed more recently.

## Manually refresh results on cached projects

You can manually refresh results any time during the 12-hour window in order to view the latest data.

In the Workspace project where you want to view the latest data, do either of the following:

1. To load the latest results for a single panel only, select **[!UICONTROL Refresh]** next to a panel's timestamp. 

   **Note:** This option is not available during the alpha phase of release.

   Or

   To load the latest results for all panels and start a new 12-hour window, select **[!UICONTROL Refresh]** at the top of the project.

