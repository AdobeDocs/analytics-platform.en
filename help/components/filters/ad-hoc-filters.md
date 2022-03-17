---
description: Use ad-hoc filters in Analysis Workspace.
title: Ad-hoc project filters
feature: CJA Workspace Basics
role: User, Admin
exl-id: 79513ad9-3c9d-441e-a5c5-c2b1e5cacc2e
---
# Ad-hoc project filters

Ad-hoc project filters allow you to drag and drop any component directly into the panel drop zone to create a filter. The filter becomes a [project-level filter](https://experienceleague.adobe.com/docs/analytics-platform/analysis-workspace/components/filters/quick-filters.html?#what-are-project-only-segments) local to the current project. 

Here is a video on creating ad-hoc project filters:

>[!VIDEO](https://video.tv.adobe.com/v/23978/?quality=12)


1. 1. Drop any component type (dimension, dimension item, event, metric, segment, segment template, date range) into the filter drop zone at the top of a panel. Component types are auto-converted into ad-hoc filters or [Quick filters](/help/components/filters/quick-filters.md) if compatible.

   Here is an example of how to create a filter for the Twitter referring domain:

   ![](assets/ad-hoc1.png)

   Your panel automatically gets this filter applied and you can instantly see the results. 

1. You can add an unlimited number of filters to a panel.
1. If you decide that you want to save this filter, refer to the section below.

Keep in mind:

* You **cannot** drop the following component types into the filter zone: calculated metrics and dimensions/metrics from which you cannot build filters.
* For full dimensions and events, Analysis Workspace creates "exists" hit filters. Examples: `Hit where eVar1 exists` or `Hit where event1 exists`.
* If "unspecified" or "none" is dropped in the filter drop zone, it is automatically converted to a "does not exist" filter so that it is treated correctly in filtering.

## Save ad-hoc project filters {#ad-hoc-save}

You can choose to save these filters by following these steps:

1. Hover over the filter in the drop zone and click the "i" icon.
1. Click the edit pencil to go to the Filter Builder. 
1. Check **[!UICONTROL Make available to all projects and add to your component list]**. 
1. Click **[!UICONTROL SAVE]**. 

Once saved, the filter is available in your left rail component list and can be shared with other users from the Filter Manager.

