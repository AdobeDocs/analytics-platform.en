---
title: Use Cached Results for Faster Loading in Analysis Workspace
description: Enable a project setting in Analysis Workspace that caches query results for 12 hours so projects load instantly. Refresh anytime to see the latest data.
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
>abstract="When enabled, results load faster for 12 hours after a project is first opened by a user or delivered by a schedule. Anyone who opens the project during that time sees the same results, even though data continues to flow in the background. To load the latest results, refresh individual panels or the entire project."

You can configure Analysis Workspace projects to show cached results for a 12-hour window, allowing results to load instantly for anyone who opens the project after it is initially loaded.

Projects can be initially loaded by a user who opens the project or by a scheduled project delivery.

>[!NOTE]
>
>Only the query results are cached. Underlying event data continues to flow into Customer Journey Analytics as usual.
>
>To see the latest data before cached results expire, you can [manually refresh the results](#manually-refresh-results-on-cached-projects).

## Understand cached results in a project

### When results are cached

The first time the project runs, Analysis Workspace runs the query as usual and caches the results for a 12-hour window. This happens when someone opens the project or when the project runs for a scheduled delivery. For example, if a project is scheduled for delivery at 6:00 AM, the results are cached until 6:00 PM. Everyone who opens the project between 6:00 AM and 6:00 PM sees results load instantly, including the first person to open it.

After 12 hours, the cached results expire. The next query on the project, whether a user opens it or a scheduled delivery runs, loads at normal speed and starts a new 12-hour window.

### Who can see cached results

Cached results are shared with everyone who has access to the project and the data views used in the project.

### What results are cached

Analysis Workspace caches each query that runs, not every possible version of a project. When someone changes the query, such as by selecting an item from a panel drop-down menu or applying a segment, Analysis Workspace runs a new query. The new query loads at normal speed the first time. After that, its results are also cached.

Caching a new query doesn't overwrite or invalidate results that are already cached. The original project view is cached along with other variations that people have run.

>[!BEGINSHADEBOX]

**Example scenario**

Suppose a Global Campaign Performance project includes segments for different regions and is scheduled for delivery at 6:00 AM:

| Time | Action | Load speed |
|---|---|---|
| 6:00 AM | Scheduled project delivery | Normal (results are cached for future use) |
| 7:06 AM | User A opens the project | Fast |
| 7:06 AM | User A applies the Americas segment | Normal (results are cached for future use) |
| 8:01 AM | User B opens the project | Fast |
| 8:01 AM | User B applies the Americas segment | Fast |
| 8:01 AM | User B applies the EMEA segment | Normal (results are cached for future use) |

>[!ENDSHADEBOX]

## Enable cached results for a project

Anyone who can update project settings can enable cached results. This includes the project owner and anyone with the **[!UICONTROL Edit original]** role for the project. For more information about project roles, see [Share a specific project role](/help/analysis-workspace/curate-share/share-projects.md#share-a-specific-project-role).

In the Workspace project where you want to enable cached results for faster loading:

1. Go to **[!UICONTROL Projects]** > **[!UICONTROL Project info and settings]**.
1. Select **[!UICONTROL Use cached results for faster loading]**.
1. Select **[!UICONTROL Save]**.

## View data timestamps on cached projects

When a project is configured to use cached results, a timestamp displays at the top of the project, showing when the results were cached:

* **[!UICONTROL Showing data from ] [_date and time_]**: All panels in the project show cached results from the date and time shown.
* **[!UICONTROL Showing some data from ] [_date and time_]**: Some panels show cached results from the date and time shown, while others were refreshed more recently.

Panels also display a timestamp, showing when the results were cached:

* **[!UICONTROL Showing data from ] [_date and time_]**: The panel shows cached results from the date and time shown.

## Manually refresh results on cached projects

You can manually refresh results on a project any time during the 12-hour window in order to view the latest data. When you refresh the entire project, a new 12-hour window begins, and everyone who opens the project during that window sees the refreshed results.

In the Workspace project where you want to view the latest data, you can refresh results for the entire project or for a single panel.

### Refresh results for the entire project

To load the latest results for all panels and start a new 12-hour window:

1. Select **[!UICONTROL Refresh]** at the top of the project next to the project's timestamp.

### Refresh results for a single panel

>[!NOTE]
>
>This option is not available during the alpha phase of release.

To load the latest results for a single panel only:

1. Select **[!UICONTROL Refresh]** next to a panel's timestamp.

