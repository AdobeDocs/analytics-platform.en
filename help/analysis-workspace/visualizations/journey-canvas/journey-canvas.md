---
description: Journey canvas overview
title: Journey canvas
feature: Visualizations
role: User
---
# Journey canvas overview

The Journey canvas visualization lets you analyze and gain deep insights on the journeys you provide to your users and customers. It allows you to define a journey, then see how users left (fell out) or continued through (fell through) the journey. 

The journeys you define can start from multiple entry points, and they can contain multiple events, conditions, and paths.

## Key features

Key features of the Journey canvas visualization include:

* Deep analysis of fallout and fallthrough that accommodates the most complex user journeys.

* A canvas for mapping and visualizing the various entry points, nodes, and paths of a user journey.

* Drag-and-drop interactions for adding components to the canvas and for repositioning existing nodes.

* The option to build analyses of user journeys within Journey canvas or to automatically create them based on Journey Optimizer journeys.


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

### Choose which visualization to use

If your fallout analysis involves only a linear journey that has a single known beginning and end, consider using a [Fallout visualization](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) as a more simple option for these more straightforward user journeys.

Journey canvas is essential for fallout analysis involving journeys with multiple entry points and paths, or for analyzing journeys that were created in Journey Optimizer.

## Analyze Journey Optimizer journeys

>[!NOTE]
>
>Organization who have purchased Journey Optimizer can use Journey canvas to analyze Journey Optimizer journeys. If your organization doesn't have access to Journey Optimizer, you can still [build analyses in Journey canvas](#build-analyses-in-customer-journey-analytics).

Analyzing Journey Optimizer journeys in Journey canvas provides deep, actionable insights on how users interact with a journey. 

When you analyze a Journey Optimizer journey in Journey canvas, the journey is displayed with the same order, sequence, and structure as it has in Journey Optimizer.

### Benefits of analyzing Journey Optimizer journeys with Journey canvas

Journey canvas provides deep, thorough analysis that isn't possible in Journey Optimizer. Using Journey canvas to analyze journeys that were created in Journey Optimizer provides various benefits:

| Feature | Customer Journey Analytics | 
|---------|----------|
| **Create events** | Create events by using any Customer Journey Analytics dimensions. In Journey Optimizer, a technical user must create an event before it can be added to a journey. |
| **Create audiences** | Create audiences based on a specific node, edge, or fallout within the Journey canvas visualization. (Launches the Customer Journey Analytics audience builder.) In Journey Optimizer, this is not available |
| **Fallthrough and fallout** | B3 | 

### Terminology differences between Journey Optimizer and Customer Journey Analytics

Certain terms that mean one thing in Journey Optimizer mean something else in Customer Journey Analytics. When using Journey canvas, the Customer Journey Analytics terms are used.

|Term | Journey canvas | Journey Optimizer |
|---------|----------|---------|
| **Event** | One of several standard metrics that is available in Customer Journey Analytics. This metric counts things like revenue, subscriptions, or leads generated. | The category of activity that triggers a personalized journey, such as an online purchase.  |
| A2 | B2 | C2 |
| A3 | B3 | C3 |

### Analyze a Journey Optimizer journey in Journey canvas

For information about analyzing a Journey Optimizer journey in Journey canvas, see [Configure a Journey canvas visualization](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

### Enhance Journey Optimizer journeys in Journey canvas for deeper analysis

After you open a Journey Optimizer journey in Journey canvas, you can make changes to it for a deeper or more thorough analysis.

Any changes you make to the journey in Customer Journey Analytics are reflected in Journey Optimizer. <!-- true? -->

For information, see [Configure a Journey canvas visualization](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

## Build analyses in Journey canvas

You can build analyses in Journey canvas that are based on any dimensions or metrics that are available in Analysis Workspace. Or, you can analyze journeys that were created in Journey Optimizer. For more information, see [Configure a Journey canvas visualization](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

## Basic workflow

When creating a Journey explorer visualization, you need to define the starting touchpoint, ending touchpoint, and pathing dimension. 

Based on the information that you provide, Analysis Workspace analyzes the most common paths users took between the two touchpoints, then auto-populates the important milestones (pathpoints) along each path. You can manually include midpoints for any milestones that weren't automatically included.

**Elements of a journey that require your input:**

* Starting touchpoint

* Ending touchpoint

* Midpoints (optional)

**Elements of a journey that are auto-populated by Adobe:**

* Paths

* Pathpoints (based on the pathing dimension that you specify)

The following diagram represents a basic journey. It illustrates the information that you need to provide and the information that is auto-populated. 

>[!NOTE]
>
>For simplicity, the diagram shows only a few paths, pathpoints, and midpoints. However, a journey can contain a combined total of up to 18 pathpoints and midpoints, and it can contain an unlimited number of paths.

![Journey explorer workflow](assets/journey-explorer-workflow.png)

<!-- insert some sort of graphic that illustrates the flow? -->

## Example scenario

To illustrate the types of insights Journey explorer can help provide, consider the following example of a customer journey:

### Business objective

An online retail company wants to retain customers who complained about a purchase within the past 6 months. The company makes the following plan to retain these at-risk customers: 

1. All at-risk customers receive a promotional email with a 10% discount code.

1. Customers who make a purchase on the site after receiving the promotional email are considered successfully retained. Those who do not make a purchase are still considered at risk. 

The company takes action on this business objective and [creates a journey in Journey explorer](#the-company-creates-a-journey-in-journey-explorer).

### The company creates a journey in Journey explorer

In Analysis Workspace, the company creates a Journey explorer visualization (based on their [business objective](#business-objective)) in order to analyze the retention plan's effectiveness. The only information they need to enter in Analysis Workspace is:

1. **Starting touchpoint:** Contacted Customer Support with a complaint

1. **Ending touchpoint:** Made a purchase (checked out)

1. **Pathing dimension:** Event 

With this information, Journey explorer can [fill in the journey](#journey-explorer-analyzes-user-behavior-and-fills-in-the-journey).

### Journey explorer analyzes user behavior and fills in the journey

With the limited amount of information [provided by the company](#the-company-creates-a-journey-in-journey-explorer), Journey explorer analyzes the behavior of all customers who contacted Customer Support with a complaint (the event that matches the starting touchpoint), and then Journey explorer populates the most common events as pathpoints.  

Journey explorer identifies the [top conversion paths](#top-conversion-paths) and [top drop-off paths](#top-drop-off-paths), allowing [the company to glean meaningful insights](#potential-insights).

#### Top conversion paths

The top 3 paths in the journey that led to user conversion (those that resulted with users reaching the ending touchpoint) might look something like this:

Path #1

1. **Starting touchpoint:** Contacted Customer Support with a complaint

1. **Pathpoint:** Received the promotional email with 10% discount code

1. **Pathpoint:** Logged in to the online site

1. **Pathpoint:** Viewed Product A

1. **Pathpoint:** Added an item to the cart

1. **Ending touchpoint:** Made a purchase (checked out)

Path #2

1. **Starting touchpoint:** Contacted Customer Support with a complaint

1. **Pathpoint:** Received the promotional email with 10% discount code

1. **Pathpoint:** Logged in to the online site

1. **Pathpoint:** Viewed Product A

1. **Pathpoint:** Added Product A to the cart

1. **Pathpoint:** Viewed Product B

1. **Pathpoint:** Viewed Product C

1. **Pathpoint:** Added Product C to the cart

1. **Ending touchpoint:** Made a purchase (checked out)

Path #3

1. **Starting touchpoint:** Contacted Customer Support with a complaint

1. **Pathpoint:** Received the promotional email with 10% discount code

1. **Pathpoint:** Logged in to the online site

1. **Pathpoint:** Viewed Product A

1. **Pathpoint:** Added Product A to the cart

1. **Pathpoint:** Viewed Product B

1. **Pathpoint:** Added Product B to the Cart

1. **Pathpoint:** Removed Product A from the cart

1. **Ending touchpoint:** Made a purchase (checked out)

<!-- insert graphic -->

#### Top drop-off paths

The top 3 paths in the journey that led to users dropping off the journey (never reached the ending touchpoint) might look something like this:

Path #1

1. **Starting touchpoint:** Contacted Customer Support with a complaint

1. **Pathpoint:** Received the promotional email with 10% discount code

1. **Pathpoint:** Logged in to the online site

1. **Pathpoint:** Viewed Product C

Path #2

1. **Starting touchpoint:** Contacted Customer Support with a complaint

1. **Pathpoint:** Received the promotional email with 10% discount code

1. **Pathpoint:** Logged in to the online site

1. **Pathpoint:** Viewed Product D

1. **Pathpoint:** Added Product D to the cart

1. **Pathpoint:** Viewed Product E

1. **Pathpoint:** Remobed Product D from the cart

Path #3

1. **Starting touchpoint:** Contacted Customer Support with a complaint

1. **Pathpoint:** Received the promotional email with 10% discount code

1. **Pathpoint:** Logged in to the online site

1. **Pathpoint:** Viewed Product E

1. **Pathpoint:** Viewed Product D

### Potential insights

Following are a few examples of the types of insights Journey explorer can help provide:

>[!NOTE]
>
>**Conversion** refers to a person, session, or path occurrence moving from the journey's starting touchpoint to the ending touchpoint, while **drop-off** refers to a person, session, or path occurrence starting the journey at the starting touchpoint but dropping off before reaching the ending touchpoint.

**Conversion** 

* The paths on the journey that lead to the highest conversion rates

* The number or percentage of people, sessions, or paths that converted (arrived at the ending touchpoint)

* How the conversion rates of a given journey compare to the conversion rates of all other journeys

* The average amount of time it took users on the journey to convert, in total or by individual path

**Drop-offs**

* The paths on the journey that lead to the highest drop-off rates

* The number or percentage of people, sessions, or paths that dropped off (started at the starting touchpoint but never arrived at the ending touchpoint)

* How the drop-off rates of a given journey compare to the drop-off rates of all other journeys

* The average amount of time before users dropped off of a path or dropped off of the journey

**Other**

* The number of people, sessions, or path occurrences on the journey compared to all other journeys

## Create a Journey explorer visualization

>[!CONTEXTUALHELP]
>id="cja_viz_journeyexplorer_short_description"
>title="Journey explorer"
>abstract="Explore the journeys your users are taking to learn how to better optimize and improve their experiences."
>additional-url="https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/visualizations/journey-explorer/journey-explorer.html" text="Learn more"

To create a journey, you define the starting and ending touchpoints, and then allow Analysis Workspace to populate the important pathpoints in between, based on users' most common actions. You can manually include actions by adding them as midpoints.

For more information, see 

<!-- Link to article that explains it -->

## Understand the Journey explorer visualization

<!-- Show a screenshot of the viz and have callouts that define all of the different areas -->

For more information about analyzing a Journey explorer visualization, see [View and configure a Journey explorer visualization](/help/analysis-workspace/visualizations/journey-explorer/journey-explorer-view.md).

