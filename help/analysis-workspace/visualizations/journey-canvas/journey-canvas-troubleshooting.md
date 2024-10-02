---
description: Examples when configuring a Journey canvas visualization
title: Journey canvas examples
feature: Visualizations
role: User
hide: yes
hidefromtoc: yes
---
# Journey canvas troubleshooting

{{release-limited-testing}}

The Journey canvas visualization allows you to analyze and gain deep insights on the journeys that you provide to your users and customers. 

To learn more about Journey canvas, see [Journey canvas overview](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md) and [Configure a Journey canvas visualization](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).


## Compatibility between the container metric and the primary metric

You can configure the Journey canvas container to be Person (which uses the People metric) or Session (which uses the Sessions metric).

When choosing a primary or secondary metric, make sure you choose a metric that is compatible with the container metric that is currently selected. Most metrics are compatible with the container metrics that are available. However, some combinations of container metrics and primary or secondary metrics should be avoided.

For example, if you use Person as the container with Session as the primary or secondary metric


| Container | Primary or secondary metric | Outcome |
|---------|----------|---------|
| People | Session | This combination can result in unintended outcomes. Specifically, e outcome of this combination can re |
| A2 | B2 | C2 |
| A3 | B3 | C3 |


## Percentages that exceed 100%

The following configurations can result in nodes that show percentages that exceed 100%:

* When the **[!UICONTROL Percentage value]** field is set to **[!UICONTROL Percent of total]**, and a primary metric is selected that results in less data for the start node than on subsequent nodes.

  For example, if Revenue is selected as the primary metric, and no revenue is being realized on the primary metric, then on any node where revenue is being realized will show as exceeding 100%. 


## A journey that is not funnel-shaped

It is possible in Journey canvas for nodes that come later in the journey to show a higher percentage or number count than nodes that come earlier in the journey. 

In other words, unlike in Fallout visualizations, which are always funnel-shaped (with participation decreasing with each step), Journey canvas visualizations can have higher participation in later steps of the journey. 

Consider a journey with the following characteristics:

* The journey contains 3 nodes: Node A ---> Node B ---> Node C

* The **[!UICONTROL Percentage value]** field is set to **[!UICONTROL Percent of total]**

* **[!UICONTROL Person]** is set as the container

* **[!UICONTROL Event]** is set as the primary metric

In this scenario, suppose a visitor visited Node A, Node B, and then Node C. Each of these visits counts as a single event on each node, because they were visited in the order defined by the journey. 

On a subsequent visit to the site, the visitor visits only Node C, resulting in an additional event on Node C. 

In this case, Nodes A and B would each show 1 event and 100%, while Node C would show 2 events and 200%.

On the other hand, if Session were set as the container, then Nodes A, B, and C would each show 1 event and 100%, because the subsequent visit to the site where the visitor visited only Node C would not have met the journey requirements, because Node A and Node B were not visited prior to visiting Node C. 
