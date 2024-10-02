---
description: Journey canvas overview
title: Journey canvas
feature: Visualizations
role: User
exl-id: be03c3b2-8faf-47b8-b3ab-e953202bf488
---
# Journey canvas overview

{{release-limited-testing}}

The Journey canvas visualization allows you to analyze and gain deep insights on the journeys that you provide to your users and customers. It allows you to define a journey from scratch or view one from Journey Optimizer, then see how people left (fell out) or continued through (fell through) the journey. 

You can [build analyses of user journeys](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md) by using any combination of events, dimension items, filters, and date ranges to create journey nodes. Connect the nodes to create the journey's flow, and include multiple paths and decision points. Drag nodes on the canvas to rearrange the events and conditions of the journey. Data updates in realtime as you make changes.

[Nodes are connected](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#logic-when-connecting-nodes) as an "eventual path," which means that visitors are counted as long as they eventually move from one node to the other, regardless of any events occurring between the 2 nodes. The time allotted for users to move along the path is determined by the container setting. 

![Journey canvas](assets/journey-canvas.png)

## Key features

Key features of the Journey canvas visualization include:

* Deep analysis of fallout and fallthrough that accommodates the most complex user journeys.

* A canvas for mapping and visualizing the various entry points, nodes, and paths of a user journey.

* Drag-and-drop interactions for adding components to the canvas and for repositioning existing nodes.

* The option to build analyses of user journeys within Journey canvas or to automatically create them based on Journey Optimizer journeys.

## Potential insights

Following are a few examples of the types of insights Journey canvas can help provide. You can choose whether these insights are based on all people in the data view, all people who started the journey, or all people from the previous node of the journey.

**Fallthrough** 

* The number and percentage of people who completed the journey (arrived at the ending node)

* The number and percentage of people who arrived at a given node of the journey

* The most common step that came after or before a given node of the journey

**Fallout**

* The nodes of the journey where people most commonly fell out of the journey (never arrived at any of the immediate next nodes)

**Other**

* Additional data for any node in the journey (by adding a breakdown dimension for the node)


## Choose between Journey canvas and Fallout visualizations

Journey canvas visualizations are similar to [Fallout visualizations](/help/analysis-workspace/visualizations/fallout/fallout-flow.md), in that both visualizations show where persons left (fell out) and continued through (fell through) a predefined sequence of pages.

However, there are important differences.

### Understand the differences

The following table shows the types of analyses supported in the Journey canvas visualization and the Fallout visualization:

| Function | Journey canvas visualization | Fallout visualization |
|---------|----------|---------|
| Linear journeys | Yes | Yes |
| Non-linear journeys with multiple entry points and paths | Yes | No |
| Adobe Journey Optimizer journeys | Yes | No | 
| Primary metric | Any metric, including calculated metrics | Can use only the Session or User metrics | 
| Secondary metric | Yes<p>Any metric, including calculated metrics</p> | No | 
| Compare filters | No | Yes<p>Compare an [unlimited number of filters](/help/analysis-workspace/visualizations/fallout/compare-segments-fallout.md#compare-filters-in-fallout)</p> |

### Choose which visualization to use

Before you choose between using Journey canvas or Fallout, make sure you [understand the differences between the two](#understand-the-differences).

If your fallout analysis involves only a linear journey that has a single known beginning and end, consider using a [Fallout visualization](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) as a more simple option for these more straightforward user journeys.

Journey canvas is essential for fallout analysis involving journeys with multiple entry points and paths, or for analyzing journeys that were created in Journey Optimizer.

## Analyze Journey Optimizer journeys

>[!NOTE]
>
>If your organization doesn't have access to Journey Optimizer, you can still [build analyses in Journey canvas](#build-analyses-in-customer-journey-analytics).

Analyzing Journey Optimizer journeys in Journey canvas provides deep, actionable insights on how people interact with a journey. 

When you analyze a Journey Optimizer journey in Journey canvas, the journey displays with the same order, sequence, and structure as it has in Journey Optimizer. If you can make changes to a journey within Journey canvas, [changes are no longer synchronized from Journey Optimizer](#synchronization-between-journey-optimizer-and-journey-canvas).

### Benefits of analyzing Journey Optimizer journeys with Journey canvas

Journey canvas provides deep, thorough analysis that isn't possible in Journey Optimizer. 

Using Journey canvas to analyze journeys that were created in Journey Optimizer provides various benefits:

* Create events by using any Customer Journey Analytics dimensions, metrics, filters, or date ranges. 
  
  In Journey Optimizer, a technical user must create an event before it can be added to a journey.

* Create audiences based on a custom node that you create (launches the Customer Journey Analytics audience builder).
  
  In Journey Optimizer, you can create audiences only for pre-defined activities.

* Analyze fallthrough and fallout

* Break down events with any dimension

* Combine events

* Connect events

* Rename and delete events

* Much more

### Synchronization between Journey Optimizer and Journey canvas

After you create an analysis of a Journey Optimizer journey in Journey canvas, data syncs in only one direction, from Journey Optimizer to Journey canvas. This means that changes made to a journey in Journey canvas are never reflected in Journey Optimizer.

Furthermore, changes made to a journey in Journey Optimizer sync to Journey canvas only if the journey remains unmodified in Journey canvas. After you modify a journey in Journey canvas, any changes you make to the journey in Journey Optimizer are not reflected in Journey canvas. To see the changes reflected in Journey canvas, you can delete and [re-create the journey in Journey canvas](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

### Differences after modifying a journey in Journey canvas {#differences-after-modifying}

After you modify a Journey Optimizer journey in Journey canvas, changes can occur in data processing, available features, and synchronization behavior.

If you make a significant modification to a Journey Optimizer journey in Journey canvas, changes can occur in data processing, available features, and synchronization behavior. A significant modification includes any of the following:

* Adding or removing a node

* Adding or removing an arrow between nodes

* Changing the components on a node

If you make other changes to a Journey Optimizer journey in Journey canvas, such as dragging a node or adding a breakdown, the differences described in the following sections do not apply.

>[!NOTE]
>
>To return the journey to its original state, you can press Ctrl+z after making your first change in Journey canvas. Or, you can delete and [re-create the journey in Journey canvas](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)

#### Data processing differences

After you modify a Journey Optimizer journey in Journey canvas, you might notice changes to your data if your journey contains metrics that have non-default attribution models. 

This is because, unlike Journey Optimizer, Journey canvas allows you to apply multiple dimensions within a single journey. This capability means that [metric attribution](/help/data-views/component-settings/attribution.md) is not supported.  

#### Feature differences

After you modify a Journey Optimizer journey in Journey canvas, the functionality might change for the following features, depending on your modifications:

* The values shown in the [!UICONTROL **Node type**] field change. 

* The options that are available in the [!UICONTROL **Arrow settings**] drop-down field change.

For more information about these fields, see [Configure settings](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

#### Synchronization differences

Changes made to a journey in Journey Optimizer sync to Journey canvas only if the journey remains unmodified in Journey canvas. 

After you modify a Journey Optimizer journey in Journey canvas, any changes you make to the journey in Journey Optimizer are not reflected in Journey canvas. To see the changes reflected in Journey canvas, you can delete and [re-create the journey in Journey canvas](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

### Terminology differences between Journey Optimizer and Customer Journey Analytics

Certain terms that mean one thing in Journey Optimizer mean something else in Customer Journey Analytics. When using Journey canvas, the Customer Journey Analytics terms are used.

|Term | Journey canvas | Journey Optimizer |
|---------|----------|---------|
| **Event** | One of several standard metrics that is available in Customer Journey Analytics. This metric counts things like revenue, subscriptions, or leads generated. | The category of activity that triggers a personalized journey, such as an online purchase.  |

### Analyze a Journey Optimizer journey in Journey canvas

For information about analyzing a Journey Optimizer journey in Journey canvas, see [Configure a Journey canvas visualization](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

## Build analyses in Journey canvas

You can build analyses in Journey canvas that are based on any dimensions or metrics that are available in Analysis Workspace. Or, you can analyze journeys that were created in Journey Optimizer. For more information, see [Configure a Journey canvas visualization](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).
