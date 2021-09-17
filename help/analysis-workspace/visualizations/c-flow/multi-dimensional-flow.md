---
description: An inter-dimensional flow lets you examine user paths across various dimensions.
title: Inter-dimensional flows
uuid: 51d08531-1c56-46c7-b505-bd8d5e6aa6c1
exl-id: 459166b1-a522-45b6-9d2c-69e3409e442e
---
# Inter-dimensional flows

>[!NOTE]
>
>You are viewing the documentation for Analysis Workspace in Customer Journey Analytics. Its feature set differs slightly from [Analysis Workspace in traditional Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). [Learn more...](/help/getting-started/cja-aa.md)

An inter-dimensional flow lets you examine user paths across various dimensions.

A dimension label at the top of each Flow column makes using multiple dimensions in a flow visualization more intuitive:

![](assets/flow.png)

We will look at 2 use cases: an app use case and a web use case.

## Use case one: app

The [!UICONTROL Action Name] dimension was added to the flow, with the top returned item being [!UICONTROL ItemAdded]:

![](assets/multi-dimensional-flow.png)

To explore the interaction between screens/pages and actions in this app, you can then drag the page dimension to multiple places, depending on what you want to explore:

* Drag it to either end of the drop zone (inside the black-rimmed rectangular zone that appears) to **replace** the top results on the ends:

  ![](assets/multi-dimensional-flow2.png) ![](assets/multi-dimensional-flow3.png)

* Drag it to the white space on the end (notice the black bracket) to **add on to** the visualization:

  ![](assets/multi-dimensional-flow4.png)

Here is the result if you decide to replace the ItemScaled item in the right column with the Page dimension. The top result now changes to the top result for the Page dimension:

![](assets/multi-dimensional-flow5.png)

Now you can see how customers are moving through actions and pages. You can further explore the flow by clicking on different nodes:

![](assets/multi-dimensional-flow6.png)

This is what happens if you add another Action Name dimension onto the end of the visualization:

![](assets/multi-dimensional-flow7.png)

This will allow for some deep insights and possible changes to the app you are analyzing.

## Use case two: web

This use case shows how you can analyze which campaigns drive the most entries to a web site.

Drag the Campaign Name dimension into a new flow:

![](assets/multi-dimensional-flow8.png)

Now I want to see to which pages those campaigns are driving traffic, so I drag the Page dimension to the right of the flow results to add on to the visualization:

![](assets/multi-dimensional-flow9.png)
