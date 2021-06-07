---
description: You can create filters from a touchpoint, add filters as touchpoint, and compare key workflows across various filters in Analysis Workspace.
keywords: fallout and filters;filters in fallout analysis;compare filters in fallout
title: Apply filters in fallout analysis
exl-id: 85b1024f-acd2-43b7-b4b1-b10961ba43e8
---
# Apply filters in fallout analysis

>[!NOTE]
>
>You are viewing the documentation for Analysis Workspace in Customer Journey Analytics. Its feature set differs slightly from [Analysis Workspace in traditional Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). [Learn more...](/help/getting-started/cja-aa.md)

You can create filters from a touchpoint, add filters as touchpoint, and compare key workflows across various filters in Analysis Workspace.

>[!IMPORTANT]
>
>Filters used as checkpoints in Fallout must use a container that is at a lower level than the overall context of the Fallout visualization. With a visitor-context Fallout, filters used as checkpoints must be visit or hit-based filters. With a visit-context Fallout, filters used as checkpoint must be hit-based filters. If you use an invalid combination, the fallout will be 100%. We have added a warning to the Fallout visualization that will display when you add an incompatible filter as a touchpoint. Certain invalid filter container combinations will lead to invalid Fallout diagrams, such as:

* Using a visitor-based filter as a touchpoint inside a visitor-context Fallout visualization
* Using a visitor-based filter as a touchpoint inside a visit-context Fallout visualization
* Using a visit-based filter as a touchpoint inside a visit-context Fallout visualization

## Create a filter from a touchpoint {#section_915E8FBF35CD4F34828F860C1CCC2272}

1. Create a filter from a specific touchpoint that you are especially interested in and that might be useful to apply to other reports. You do this by right-clicking the touchpoint and selecting **[!UICONTROL Create filter from touchpoint]**.

   ![](assets/segment-from-touchpoint.png)

   The Filter Builder opens, pre-populated with the pre-built sequential filter that matches the touchpoint you selected:

   ![](assets/segment-builder.png)

1. Give the filter a title and description and save it.

   You can now use this filter in any project you wish.

## Add a filter as a touchpoint {#section_17611C1A07444BE891DC21EE8FC03EFC}

If you want to see, for example, how your US users trend and affect the fallout, just drag the US users filter into the fallout:

![](assets/segment-touchpoint.png)

Or you can create an AND touchpoint by dragging the US users filter onto another checkpoint.

## Compare filters in fallout {#section_E0B761A69B1545908B52E05379277B56}

You can compare an unlimited number of filters in the Fallout visualization.

1. Select the filters you want to compare from the [!UICONTROL Filter] rail on the left. In our example, we have selected 2 filters: US Users and Non-US Users.
1. Drag them into the Filter drop zone at the top.

   ![](assets/segment-drop.png)

1. Optional: You can keep "All Visits" as the default container or delete it.

   ![](assets/seg-compare.png)

1. You can now compare the fallout across the two filters, such as where one filter is outperforming another, or other insights.
