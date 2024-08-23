---
description: Journey canvas overview
title: Journey canvas
feature: Visualizations
role: User
---
# Journey canvas overview

The Journey canvas visualization allows you to analyze and gain deep insights on the journeys that you provide to your users and customers. It allows you to define a journey, then see how people left (fell out) or continued through (fell through) the journey. 

Journey canvas allows you to build analyses of user journeys by creating a flexible graph of nodes and arrows representing any combination of events, dimension items, and filters. Drag nodes on the canvas to rearrange the events and conditions of the journey. As you do, data updates accordingly.

## Key features

Key features of the Journey canvas visualization include:

* Deep analysis of fallout and fallthrough that accommodates the most complex user journeys.

* A canvas for mapping and visualizing the various entry points, nodes, and paths of a user journey.

* Drag-and-drop interactions for adding components to the canvas and for repositioning existing nodes.

* The option to build analyses of user journeys within Journey canvas or to automatically create them based on Journey Optimizer journeys.

## Potential insights

Following are a few examples of the types of insights Journey canvas can help provide. You can choose whether these insights are based off all people in the data view or all people who started the journey.

**Fallthrough** 

* The number and percentage of people who completed the journey (arrived at the ending node)

* The number and percentage of people who arrived at a given point (node) of the journey

* The most common previous or next steps from a given point (node) of the journey

**Fallout**

* The points (nodes) of the journey where people most commonly fell out of the journey

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

When you analyze a Journey Optimizer journey in Journey canvas, the journey displays with the same order, sequence, and structure as it has in Journey Optimizer. If you can make changes to it within Journey canvas, [changes are no longer synchronized from Journey Optimizer](#synchronization-between-journey-optimizer-and-journey-canvas).

### Benefits of analyzing Journey Optimizer journeys with Journey canvas

Journey canvas provides deep, thorough analysis that isn't possible in Journey Optimizer. 

Using Journey canvas to analyze journeys that were created in Journey Optimizer provides various benefits:

| Feature | Benefit | 
|---------|----------|
| **Create events** | Easily create events by using any Customer Journey Analytics dimensions, metrics, or filters. <p>In Journey Optimizer, a technical user must create an event before it can be added to a journey.</p> |
| **Create audiences from custom nodes** | Create audiences based on a custom node that you create in the journey within the Journey canvas visualization. (Launches the Customer Journey Analytics audience builder.) <p>In Journey Optimizer, you can create audiences only for pre-defined activities.</p> |
| **Fallthrough and fallout** | B3 | 
| **Break down events** | B3 | 

### Synchronization between Journey Optimizer and Journey canvas

After you create an analysis of a Journey Optimizer journey in Journey canvas, data syncs in only one direction, from Journey Optimizer to Journey canvas. This means that changes made to a journey in Journey canvas are never reflected in Journey Optimizer.

Furthermore, changes made to a journey in Journey Optimizer sync to Journey canvas only if the journey remains unmodified in Journey canvas. After you modify a journey in Journey canvas, any changes you make to the journey in Journey Optimizer are not reflected in Journey canvas. To see the changes reflected in Journey canvas, you can delete and [re-create the journey in Journey canvas](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

### Terminology differences between Journey Optimizer and Customer Journey Analytics

Certain terms that mean one thing in Journey Optimizer mean something else in Customer Journey Analytics. When using Journey canvas, the Customer Journey Analytics terms are used.

|Term | Journey canvas | Journey Optimizer |
|---------|----------|---------|
| **Event** | One of several standard metrics that is available in Customer Journey Analytics. This metric counts things like revenue, subscriptions, or leads generated. | The category of activity that triggers a personalized journey, such as an online purchase.  |
| A2 | B2 | C2 |
| A3 | B3 | C3 |

### Analyze a Journey Optimizer journey in Journey canvas

For information about analyzing a Journey Optimizer journey in Journey canvas, see [Configure a Journey canvas visualization](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

## Build analyses in Journey canvas

You can build analyses in Journey canvas that are based on any dimensions or metrics that are available in Analysis Workspace. Or, you can analyze journeys that were created in Journey Optimizer. For more information, see [Configure a Journey canvas visualization](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).


