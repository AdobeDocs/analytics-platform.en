---
description: Journey canvas overview
title: Journey canvas
feature: Visualizations
role: User
---
# Journey canvas overview

The Journey canvas visualization allows you to analyze and gain deep insights on the journeys that you provide to your users and customers. It shows how users flow through and fall out of the various events, conditions, and paths of the user journey, which can start from any number of entry points.

Journeys can be created either in Adobe Journey Optimizer or within Journey canvas itself. 

## Journey canvas and Fallout visualizations

Journey canvas visualizations are similar to Fallout visualizations, but with important differences. 

Both visualizations show where persons left (fell out) and continued through (fell through) a predefined sequence of pages. 

**Fallout visualizations:** Provide analysis only for linear journeys that have a single known beginning and end. Consider using a [Fallout visualization](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) as a more simple option for these more straightforward user journeys.

**Journey canvas visualizations:** Supports not only linear journeys, but any number of entry points and paths. Furthermore, journeys can be created in Adobe Journey Optimizer and then analyzed in Journey canvas.

## Analyze Journey Optimizer journeys

>[!NOTE]
>
>Journey Optimizer journeys can be analyzed with Journey canvas only if your organization has purchased Journey Optimizer. If your organization doesn't have access to Journey Optimizer, you can still [build analyses in Journey canvas](#build-analyses-in-customer-journey-analytics).

Organizations who create journeys in Journey Optimizer can analyze those journeys in Journey canvas to gain deep, actionable insights on user behavior. 

When you analyze a Journey Optimizer journey in Journey canvas, the journey is displayed with the same order, sequence, and structure as it has in Journey Optimizer.

### Terminology differences between Journey Optimizer and Customer Journey Analytics

Certain terms that mean one thing in Journey Optimizer mean something else in Customer Journey Analytics. When using Journey canvas, the Customer Journey Analytics terms are used.

|Term | Journey canvas | Journey Optimizer |
|---------|----------|---------|
| **Event** | One of several standard metrics that is available in Customer Journey Analytics. Counts things like revenue, subscriptions, or leads generated. | The category of activity that triggers a personalized journey, such as an online purchase.  |
| A2 | B2 | C2 |
| A3 | B3 | C3 |

### Analyze a Journey Optimizer journey in Journey canvas

To open a Journey Optimizer journey in Journey canvas:

1. In Journey Optimizer, open the journey that you want to analyze in Journey canvas.

1. Select [!UICONTROL **Analyze in CJA**]. <!-- ?? -->

### Enhance Journey Optimizer journeys in Journey canvas for deeper analysis

After you open a Journey Optimizer journey in Journey canvas, you can make changes to it for a deeper or more thorough analysis.

Any changes you make to the journey in Customer Journey Analytics are reflected in Journey Optimizer. <!-- true? -->

## Build analyses in Journey canvas

You can build analyses in Journey canvas that are based on any dimensions or metrics that are available in Analysis Workspace. 

## Create or update a journey in Customer Journey Analytics and Journey Optimizer - Feature comparison

Both Journey Optimizer and Customer Journey Analytics allow you to create or update a journey. Depending on what you want to do, , but not all functionality is available in a single product. Use the following information to determine the best product for a given task:

| Feature | Customer Journey Analytics | Journey Optimizer |
|---------|----------|---------|
| **Create events** | Create events by using any Customer Journey Analytics dimensions. | A technical user must create an event before it can be added to a journey. |
| **Create audiences** | Create audiences based on a specific node, edge, or fallout within the Journey canvas visualization. (Launches the Customer Journey Analytics audience builder.) | Not available |
| **Fallthrough and fallout** | B3 | C3 |

