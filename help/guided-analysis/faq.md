---
title: Guided analysis FAQ
description: Frequently asked questions around Guided analysis.
exl-id: b6f92d47-6c09-4338-9dc5-b30bbfbe9f7f
feature: Guided Analysis
keywords: product analytics
---
# Guided analysis FAQ

Frequently asked questions around Guided analysis.

+++**How can my organization be provisioned for Guided analysis?**

Guided analysis is a paid add-on to Customer Journey Analytics. If you would like to start using this add-on, contact your Adobe Account Team.

+++

+++**What implementation changes are required to use Guided analysis?**

If you are already using Customer Journey Analytics today, no additional implementation changes are needed. Guided analysis uses the same [Data views](../data-views/data-views.md) and [Connections](../connections/overview.md) as other CJA interfaces like [Analysis Workspace](../analysis-workspace/home.md). 

To enable your end users to be most successful with Guided analysis, it is recommended you have a strong event schema and managment strategy in place in Adobe Experience Platform and [Data views](../data-views/data-views.md).

+++

+++**When should you use Guided analysis or Analysis Workspace?**

**Guided analysis** can help users get high quality insights quickly. It's useful for product teams, users looking to work more confidently with data, and even analysts as a head start to deeper analysis.

**[Analysis Workspace](../analysis-workspace/home.md)** is a more freeform space that lets you dive further into the data to uncover more insights. It's useful for analysts and power users who understand the data well and want to dive deeply into it.

+++

+++**How does terminology compare between Guided analysis and Analysis Workspace?**

Guided analysis uses terms that are more frequently used among product teams. You can reference this table when switching between Guided analysis and [Analysis Workspace](../analysis-workspace/home.md).

| Guided analysis term | Analysis Workspace term |
| --- | --- |
| Event | Metric |
| Users | People |
| Property | Dimension |
| Value | Dimension item |
| Segment | Filter |

{style="table-layout:auto"}

+++

+++**What are some differences around how Guided analysis and Analysis Workspace approach reporting?**

While [Analysis Workspace](../analysis-workspace/home.md) and Guided analysis use the same underlying data, the way that each tool enables you to form queries of that data is different.

* **Analysis Workspace is a dimension-centered experience.** Tables typically consist of dimensional rows, while columns are typically metrics. Filters can be applied in both rows and columns to obtain the desired data.

* **Guided analysis is an event-centered experience.** Each analysis starts by selecting events, then dimensions and filters can be added to refine that event data.

![Structure](assets/structure.png)

Consider the following example where you focus on data around your website's home page. Teams ask similar questions, but the analysis approach can be different.

* A typical dimension-centered Analysis Workspace approach would be, "Let's look at the home page and see how many page views it received."

   ![Dimension centered](assets/dimension-centered.png)

* A typical event-centered Guided analysis approach would be, "How many users have viewed the home page?"

   ![Event centered](assets/event-centered.png)

+++
