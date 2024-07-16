---
title: Guided analysis FAQ
description: Frequently asked questions for Guided analysis.
exl-id: b6f92d47-6c09-4338-9dc5-b30bbfbe9f7f
feature: Guided Analysis
keywords: product analytics
role: User
---
# Guided analysis FAQ

Frequently asked questions for guided analysis.

+++**Does my organization have access to guided analysis?**

Guided analysis views are included in all Customer Journey Analytics packages. See the [provisioning](overview.md#provisioning) section on the overview page to learn more about the views that your CJA package unlocks.

+++

+++**What implementation changes are required to use guided analysis?**

If you are already using Customer Journey Analytics today, no additional implementation changes are needed. Guided analysis uses the same [Data views](../data-views/data-views.md) and [Connections](../connections/overview.md) as other CJA interfaces like [Analysis Workspace](../analysis-workspace/home.md). 

To enable your end users to be most successful with guided analysis, it is recommended you have a strong event schema and management strategy in place in Adobe Experience Platform and [Data views](../data-views/data-views.md).

+++

+++**When should you use guided analysis or Analysis Workspace?**

**Guided analysis** can help users get high quality insights quickly. It's useful for product teams, users looking to work more confidently with data, and even analysts as a head start to deeper analysis.

**[Analysis Workspace](../analysis-workspace/home.md)** is a more freeform space that lets you dive further into the data to uncover more insights. It's useful for analysts and power users who understand the data well and want to dive deeply into it.

+++

+++**How does the terminology compare between guided analysis and Analysis Workspace?**

Guided analysis uses terms that are more frequently used among product teams. You can reference this table when switching between guided analysis and [Analysis Workspace](../analysis-workspace/home.md).

| Guided analysis term | Analysis Workspace term |
| --- | --- |
| Event | Metric |
| Users | People |
| Property | Dimension |
| Value | Dimension item |
| Segment | Filter |

{style="table-layout:auto"}

+++

+++**What are some differences in how guided analysis and Analysis Workspace approach reporting?**

While [Analysis Workspace](../analysis-workspace/home.md) and guided analysis use the same underlying data, the way that each tool enables you to form queries of that data is different.

* **Analysis Workspace is a dimension-centered experience.** Tables typically consist of dimensional rows, while columns are typically metrics. Filters can be applied in both rows and columns to obtain the desired data.

* **Guided analysis is an event and user-centered experience.** Each analysis starts by selecting events, then dimensions and filters can be added to refine that event data.

![Analysis Workspace and guided analysis views](assets/structure.png){style="border:1px solid gray"}

Consider the following example where you focus on data around your website's home page. Teams ask similar questions, but the analysis approach can be different.

* A typical dimension-centered Analysis Workspace approach would be, "Let's look at the home page and see how many page views it received."

   ![Dimension centered](assets/dimension-centered.png){style="border:1px solid gray"}

* A typical event and user-centered guided analysis approach would be, "How many users have visited the home page?"

   ![Event centered](assets/event-centered.png){style="border:1px solid gray"}

+++
