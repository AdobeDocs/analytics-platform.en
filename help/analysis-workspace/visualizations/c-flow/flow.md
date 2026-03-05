---
description: Learn how to use the flow visualization in Analysis Workspace.
title: Flow Overview
feature: Visualizations
exl-id: 2ef325d9-1d82-46c9-86e3-6b2332548823
role: User
---
# Flow overview {#flow}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_flow_button"
>title="Flow"
>abstract="Create a visualization to view the flow of people from one checkpoint to the next."

>[!CONTEXTUALHELP]
>id="workspace_flow_panel"
>title="Flow"
>abstract="Analyze the flow of visits or visitors from one touchpoint to the next. Specify a component (metric, dimension, or item) to start with, to end with. Optionally, you can define advanced settings to further configure the visualization."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_This article documents the Flow visualization in_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**._<br/>_See [Flow](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/visualizations/flow/flow) for the_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics** version of this article._

>[!ENDSHADEBOX]


The ![GraphPathing](/help/assets/icons/GraphPathing.svg) **[!UICONTROL Flow]** visualization shows customer paths through your websites and apps.

With the visualization you can: 

* Visualize the customer journey through your website or application.
* Analyze where customers go before and after specified checkpoints, such as entry, a specific dimension, or exit.
* Create segments by designating a specific point in a chosen path.


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Create a flow visualization](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/analyzing-customer-journeys/flow-visualization){target="_blank"} for a demo video.

{{videoaa}}

>[!ENDSHADEBOX]


## Inter-dimensional flows

You can show the [flow between dimensions](/help/analysis-workspace/visualizations/c-flow/multi-dimensional-flow.md). For example, you might combine pages and departments in one diagram. In this case, your flow might go from the home page, to the Men page, then to the Shoes department.

Each column could show a different dimension. Drag a dimension and drop in a drop zone to add that dimension to the diagram.

>[!MORELIKETHIS]
>
>[Configure a flow visualization](/help/analysis-workspace/visualizations/c-flow/create-flow.md).
>

## Choose between Flow, Fallout, or Journey canvas visualizations

The Flow visualization has similarities with the [Fallout visualization](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) and the [Journey canvas visualization](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md), but with important differences. 

### Understand the differences

<!-- Information in this snippet is shared between Journey canvas, Fallout, and Flow visualization docs -->

{{journey-visualization-comparisons}}

### When to use Flow

Flow visualizations are best suited for:

* Exploratory, ad hoc analysis for the immediate next touchpoint on the path. (Use Journey canvas for journeys with a predefined sequence of pages, or those that use an eventual path.)

* Non-linear journeys with multiple entry points and paths. (Use Journey canvas for journeys with a predefined sequence of pages.)

Use [the table above](#understand-the-differences) to understand the differences between Flow, Fallout, and Journey canvas.
