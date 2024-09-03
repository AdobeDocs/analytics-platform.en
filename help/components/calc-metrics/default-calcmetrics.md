---
description: Adobe provides various calculated metrics that you can use. This page lists those metrics and their intended uses.
title: Default calculated metrics
feature: Calculated Metrics
exl-id: 08d11cce-170e-42a2-806f-e0a28b70a2dc
role: User
---
# Default calculated metrics

Customer Journey Analytics provides the following default calculated metrics to cover the most common use-cases. These Adobe defined default calculated metrics are identified by a small ![AdobeLogoSmall](/help/assets/icons/AdobeLogoSmall.svg) logo.

| Calculated metric name | Description<br/>Formula |
|---------|----------|
| Session Start Rate | The percent that any dimension item occurred on the first event of a session.<p>This calculated metric is automatically added to Workspace when you include the [!UICONTROL Session Starts] [standard component](/help/data-views/component-reference.md) in your [data view](/help/data-views/create-dataview.md).</p>Summary: **(** ![Event](/help/assets/icons/Event.svg) **Session Starts** ![Divide](/help/assets/icons/Divide.svg) ![Event](/help/assets/icons/Event.svg) **Sessions** **)** | 
| Time Spent Per Person | The average amount of time a person spent on any given dimension item.<p>This calculated metric is automatically added to Workspace when you include the [!UICONTROL Time Spent (seconds)] [standard component](/help/data-views/component-reference.md) in your [data view](/help/data-views/create-dataview.md). The filter Exclude Last Event of Session is applied to the People metric. The filter excludes the last event of each session in a dataset. This exclusion can help you analyze user behavior leading up to an event or action, such as a purchase or form submission, while excluding the final action itself.</p>Summary: **(** ![Event](/help/assets/icons/Event.svg) **Time Spent (seconds)** ![Divide](/help/assets/icons/Divide.svg) ![Segmentation](/help/assets/icons/Segmentation.svg) **Exclude Last Event of Session(** ![Event](/help/assets/icons/Event.svg) **People ) )** |
| Sessions Per Person | The average number of Sessions per Person.<p>Summary: **(** ![Event](/help/assets/icons/Event.svg) **Sessions** ![Divide](/help/assets/icons/Divide.svg) ![Event](/help/assets/icons/Event.svg) **People** **)** |
| Time Spent Per Session | The average amount of time a person spent per Session on any given dimension item.<p>This calculated metric is automatically added to Workspace when you include the [!UICONTROL Time Spent (seconds)] [standard component](/help/data-views/component-reference.md) in your [data view](/help/data-views/create-dataview.md). The filter Exclude Last Event of Session is applied to the Sessions metric. The filter excludes the last event of each session in a dataset. This exclusion can help you analyze user behavior leading up to an event or action, such as a purchase or form submission, while excluding the final action itself.</p>Summary: **(** ![Event](/help/assets/icons/Event.svg) **Time Spent (seconds)** ![Divide](/help/assets/icons/Divide.svg) ![Segmentation](/help/assets/icons/Segmentation.svg) **Exclude Last Event of Session(** ![Event](/help/assets/icons/Event.svg) **Sessions ) )** |
| Session End Rate | The percent that any dimension item occurred on the last event of a session. <p>This calculated metric is automatically added to Workspace when you include the [!UICONTROL Session Ends] [standard component](/help/data-views/component-reference.md) in your [data view](/help/data-views/create-dataview.md).</p>Summary: **(** ![Event](/help/assets/icons/Event.svg) **Session Ends** ![Divide](/help/assets/icons/Divide.svg) ![Event](/help/assets/icons/Event.svg) **Sessions** **)** |

{style="table-layout:auto"}
