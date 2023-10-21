---
description: An inter-dimensional flow lets you examine user paths across various dimensions.
title: Inter-dimensional flows
feature: Visualizations
exl-id: 459166b1-a522-45b6-9d2c-69e3409e442e
---
# Inter-dimensional flows

An inter-dimensional flow lets you examine user paths across various dimensions.

A dimension label at the top of each Flow column makes using multiple dimensions in a flow visualization more intuitive:

![An intero-dimensional flow highlighting multiple dimensions including Product, Page, OS version, and Time Spent.](assets/flow.png)

We will look at 2 use cases: an app use case and a web use case.

## Use case one: app

The [!UICONTROL Action Name] dimension was added to the flow, with the top returned item being [!UICONTROL ItemAdded]:

![A flow showing the Item Added.](assets/multi-dimensional-flow.png)

To explore the interaction between screens/pages and actions in this app, you can then drag the page dimension to multiple places, depending on what you want to explore:

* Drag it to either end of the drop zone (inside the black-rimmed rectangular zone that appears) to **replace** the top results on the ends:

  ![A flow showing the Page dimension dragged dragged to the multiple areas.](assets/multi-dimensional-flow2.png) ![Flow diagram showing the items dragged.](assets/multi-dimensional-flow3.png)

* Drag it to the white space on the end (notice the black bracket) to **add on to** the visualization:

  ![A flow showing the Page dimension dragged to the white space at the end.](assets/multi-dimensional-flow4.png)

Here is the result if you decide to replace the ItemScaled item in the right column with the Page dimension. The top result now changes to the top result for the Page dimension:

![A fLow showing the Page dimension results at the top of the list.](assets/multi-dimensional-flow5.png)

Now you can see how customers are moving through actions and pages. You can further explore the flow by clicking on different nodes:

![A flow showing Items Added, Items Dragged, and Main View.](assets/multi-dimensional-flow6.png)

This is what happens if you add another Action Name dimension onto the end of the visualization:

![A flow showing the Action Name added.](assets/multi-dimensional-flow7.png)

This will allow for some deep insights and possible changes to the app you are analyzing.

## Use case two: web

This use case shows how you can analyze which campaigns drive the most entries to a web site.

Drag the Campaign Name dimension into a new flow:

![A flow showing the Campaign Name dimension dragged to a new flow.](assets/multi-dimensional-flow8.png)

Now I want to see to which pages those campaigns are driving traffic, so I drag the Page dimension to the right of the flow results to add on to the visualization:

![A flow showing the Page dimension dragged to the right of the flow results.](assets/multi-dimensional-flow9.png)
