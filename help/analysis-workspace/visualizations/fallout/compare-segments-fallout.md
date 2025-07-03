---
description: Learn how you can create segments from a touchpoint, add segments as touchpoint, and compare key workflows across various segments in a fallout analysis in Analysis Workspace.
keywords: fallout and segmentation;segments in fallout analysis;compare segments in fallout
title: Apply Segments In Fallout Analysis
feature: Visualizations
exl-id: 85b1024f-acd2-43b7-b4b1-b10961ba43e8
role: User
---
# Apply segments in fallout analysis

You can create segments from a touchpoint, add segments as touchpoint, and compare key workflows across various segments in Analysis Workspace.

>[!IMPORTANT]
>
>Segments used as checkpoints in Fallout must use a container that is at a lower level than the overall context of the Fallout visualization. With a person-context Fallout, segments used as checkpoints must be session or event-based segments. With a session-context Fallout, segments used as checkpoint must be event-based segments. If you use an invalid combination, the fallout is 100%. You see a warning in the Fallout visualization when you add an incompatible segment as a touchpoint. Certain invalid segment container combinations lead to invalid Fallout diagrams, such as:
>
>* Using a person-based segment as a touchpoint inside a person-context Fallout visualization.
>* Using a person-based segment as a touchpoint inside a session-context Fallout visualization.
>* Using a session-based segment as a touchpoint inside a session-context Fallout visualization.
<!-- Should we add B2B context here?
* [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} Usimg a B2B container based segment as a touchpoint inside a non-container based context Fallout visualization.
* -->

## Create a segment from a touchpoint

1. Create a segment from a specific touchpoint that you are especially interested in and that might be useful to apply to other reports. Right-click the touchpoint and select **[!UICONTROL Create segment from touchpoint]**.

   ![The Touchpoint drop-down menu with Create segment from touchpoint highlighted.](assets/fallout-createfilter.png)

   The [!UICONTROL Segment builder] opens, pre-populated with the pre-built sequential segment that matches the touchpoint you selected:

   ![The Segment Builder displays the pre-populated and pre-built sequential segment.](assets/fallout-definefilter.png)

1. Give the segment a title and description and save it.

   You can now use this segment in any project you wish.

## Add a segment as a touchpoint

If you want to see, for example, how your US users trend and affect the fallout, just drag the US users segment into the fallout:

![The US Users segment selected and  highlighted to drag into the fallout.](assets/fallout-addfilter.png)

Or you can create an AND touchpoint by dragging the US users segment onto another checkpoint.

## Compare segments in fallout

You can compare an unlimited number of segments in the Fallout visualization.

1. Select the segments that you want to compare from the [!UICONTROL Segment] panel on the left. In the example, three segments are selected: *Flight Details: Page Version A*, *Flight Details: Page Version B*, and *Flight Details: Page Version C*.
1. You drag the three segments onto the Segment drop zone at the top of the visualization.


1. Optional: You can keep *All Visits* as the default container or delete the container.

   ![The Fallout showing All Visits along with the two segments dragged in the previous step.](assets/fallout-multiplefilters.png)

1. You can now compare the fallout across the three segments, such as where one segment is outperforming another, or other insights.
