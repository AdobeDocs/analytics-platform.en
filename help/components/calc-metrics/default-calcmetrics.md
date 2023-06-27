---
description: Adobe provides various calculated metrics that you can use. This page lists those metrics and their intended uses.
title: Default calculated metrics
feature: Calculated Metrics
exl-id: 08d11cce-170e-42a2-806f-e0a28b70a2dc
---
# Default calculated metrics

Customer Journey Analytics provides the following calculated metrics to cover the most common use-cases: 

| Calculated metric name | Description | Formula |
|---------|----------|---------|
| Session Start Rate | The percent that any dimension item occurred on the first event of a session.<p>This calculated metric is automatically added to Workspace when you include the `[Session Starts]` [standard component](/help/data-views/component-reference.md) in your [data view](/help/data-views/create-dataview.md).</p> | `[Session Starts] / [Sessions]` |
| Time Spent Per Person | The average amount of time a person spent on any given dimension item.<p>This calculated metric is automatically added to Workspace when you include the `[Time Spent (seconds)]` [standard component](/help/data-views/component-reference.md) in your [data view](/help/data-views/create-dataview.md).</p> | `[Time Spent (seconds)] / [Users]` |
| Sessions Per Person | The average number of Sessions per Person. | `[Sessions] / [Users]` |
| Time Spent Per Session | The average amount of time a person spent per Session on any given dimension item.<p>This calculated metric is automatically added to Workspace when you include the `[Time Spent (seconds)]` [standard component](/help/data-views/component-reference.md) in your [data view](/help/data-views/create-dataview.md).</p> | `[Time Spent (seconds)] / [Sessions]` |
| Session End Rate | The percent that any dimension item occurred on the last event of a session. <p>This calculated metric is automatically added to Workspace when you include the `[Session Ends]` [standard component](/help/data-views/component-reference.md) in your [data view](/help/data-views/create-dataview.md).</p> | `[Session Ends] / [Sessions]` |

{style="table-layout:auto"}
