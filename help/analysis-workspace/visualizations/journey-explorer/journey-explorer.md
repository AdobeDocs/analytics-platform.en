---
description: Learn about Journey explorer reports and visualizations.
title: Journey explorer overview
feature: Visualizations
---
# Journey explorer overview

>[!CONTEXTUALHELP]
>id="cja_viz_journeyexplorer_long_description"
>title="Journey explorer"
>abstract="Explore the journeys your users are taking to learn how to better optimize and improve their experiences. <br>Define the journey with a starting touchpoint and ending touchpoint. Then, select the pathing dimension to auto-populate the important milestones in between the two touchpoints. You can manually include midpoints for any milestones that weren't automatically included.<br><b>Parameters</b><br><b>Starting touchpoint:</b> Create a starting milestone to anchor your journey. All paths in the journey will stem from this starting touchpoint. The starting touchpoint can include up to 10 dimension items, metrics, or segments.<br><b>Midpoint:</b> Keep track of any critical milestones between your starting and ending touchpoints. Unlike pathpoints (which are automatically sourced based on users' most common actions), you can manually define midpoints to capture data that specifically interests you. You can add up to 18 midpoints, and each midpoint can include up to 10 dimension items, metrics, or segments.<br><b>Ending touchpoint:</b> Create an ending milestone to mark the successful completion of the journey. Paths that reach this ending touchpoint positively affect the total conversion rate of the journey, while paths that drop off and never reach the ending touchpoint have a negative impact. The ending touchpoint can include up to 10 dimension items, metrics, or segments.<br><b>Pathing dimension:</b> Select the dimension to use to populate the pathpoints that appear between the starting touchpoint and the ending touchpoint. Pathpoints are automatically sourced based on the dimension you choose. For example, if you want pathponits to be based on users' most common actions, you would create a dimension called 'Action' and then choose it as the pathing dimension.<br><b>Segments (optional):</b> You can apply up to 3 segments to your journey. If you apply multiple segments, a separate visualization is created for each segment, allowing for easy comparison.<br>
>additional-url="https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/visualizations/journey-explorer/journey-explorer-create.html" text="Learn more about Journey explorer"

The Journey explorer visualization allows you to define user journeys and explore user behavior throughout those journeys. Because Customer Journey Analytics focuses on multi-channel analyses, Journey explorer encompasses journeys across all of your various channels: from apps and websites, to CRM systems, and more. 

Understanding the most successful paths users take to complete a journey—or the paths that commonly lead to users dropping off of a journey—can provide valuable insights to help you better optimize and improve the experiences you provide to your users.

<!--
Other ideas for the opening paragraph:
The Journey explorer visualization provides insight into user behavior across journeys that you define.  helps you define journeys shows the journeys that your users take in order to learn how to better optimize and improve their experiences.

The Journey explorer visualization allows you to explore the journeys that your users take in order to learn how to better optimize and improve their experiences.
-->

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

1. Customers who make a purchase on the site after receiving the promotional email are considered successfully retained. Those who do not make a purchase are still considered at risk . 

The company takes this business objective and [creates a journey in Journey explorer](#the-company-creates-a-journey-in-journey-explorer).

### The company creates a journey in Journey explorer

In Analysis Workspace, the company creates a Journey explorer visualization (based on their [business objective](#business-objective)) in order to analyze the retention plan's effectiveness. The only information they need to provide is:

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

1. Drop-off point (Customer leaves site or session times out, etc.)

Path #2

1. **Starting touchpoint:** Contacted Customer Support with a complaint

1. **Pathpoint:** Received the promotional email with 10% discount code

1. **Pathpoint:** Logged in to the online site

1. **Pathpoint:** Viewed Product D

1. **Pathpoint:** Added Product D to the cart

1. **Pathpoint:** Viewed Product E

1. **Pathpoint:** Removed Product D from the cart

1. Drop-off point (Customer leaves site or session times out, etc.)

Path #3

1. **Starting touchpoint:** Contacted Customer Support with a complaint

1. **Pathpoint:** Received the promotional email with 10% discount code

1. **Pathpoint:** Logged in to the online site

1. **Pathpoint:** Viewed Product E

1. **Pathpoint:** Viewed Product D

1. Drop-off point (Customer leaves site or session times out, etc.)

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