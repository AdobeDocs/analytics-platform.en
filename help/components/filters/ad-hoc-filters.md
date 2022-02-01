---
description: Use ad-hoc filters in Analysis Workspace.
title: Ad-hoc project filters
feature: CJA Workspace Basics
role: User, Admin
exl-id: 79513ad9-3c9d-441e-a5c5-c2b1e5cacc2e
---
# Ad-hoc project filters

Here is a video on creating ad-hoc project filters:

>[!VIDEO](https://video.tv.adobe.com/v/23978/?quality=12)

You can create ad-hoc project filters if you want to quickly explore how a filter might affect your project, without going to the Segment Builder. Think of these filters as temporary, project-level filters. They will typically not be part of your filter "library" like component filters in the left rail. However, you can save them, as shown below.

For a comparison of what ad-hoc project filters can do vs. full-fledged component-level filters, go [here](/help/components/filters/filters-overview.md).

1. Drop any component type (dimension, dimension item, event, metric, filter, filter template, date range) into the filter drop zone at the top of a panel. Component types are auto-converted into filters. 
   Here is an example of how to create a filter for the Twitter referring domain:

   ![](assets/ad-hoc1.png)

   Your panel automatically gets this filter applied and you can instantly see the results. 

1. You can add an unlimited number of components to a panel.
1. If you decide that you want to save this filter, refer to the section below.

Keep in mind:

* You **cannot** drop the following component types into the filter zone: calculated metrics and dimensions/metrics from which you cannot build filters.
* For full dimensions and events, Analysis Workspace creates "exists" hit filters. Examples: `Hit where eVar1 exists` or `Hit where event1 exists`.
* If "unspecified" or "none" is dropped in the filter drop zone, it is automatically converted to a "does not exist" filter so that it is treated correctly in filtering.

>[!NOTE]
>
>Segments created this way are internal to the project.

## Save ad-hoc project filters {#ad-hoc-save}

You can choose to save these filters by following these steps:

1. Hover over the filter in the drop zone and click the "i" icon.
1. In the information panel that displays, click **[!UICONTROL Save]**.

   ![](assets/segment-info.png)

## What are project-only filters?

Project-only filters are either quick filters or ad-hoc Workspace project filters. When editing/opening them in the filter builder then the project-only box will show up. If they APPLY a quick filter in the builder but don’t check the make available box, then it is still a project-only filter but it can no longer be opened in the QS builder. If they check the box and SAVE it is now a component-list filter.
