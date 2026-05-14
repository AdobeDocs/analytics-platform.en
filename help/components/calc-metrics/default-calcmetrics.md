---
description: Adobe provides various calculated metrics that you can use. This page lists those metrics and their intended uses.
title: Calculated metrics templates
feature: Calculated Metrics
exl-id: 08d11cce-170e-42a2-806f-e0a28b70a2dc
role: User
TQID: https://experienceleague.adobe.com/-jngIXgXeFZZkfL5jSHLuX8ZmcWU5rIfLqb26ovn6QY
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: ad333ea6-e90d-4c8f-8d61-9f8690784d6f
    internal-label: Templates, Templates (CJA)
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
    internal-label: Metrics
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
    internal-label: Calculated metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
---
# Calculated metrics templates

Customer Journey Analytics provides the following calculated metrics templates to cover the most common use cases. These Adobe-defined calculated metrics are identified by a small ![AdobeLogoSmall](/help/assets/icons/AdobeLogoSmall.svg) logo. To quickly filter these metrics, select ![Label](/help/assets/icons/Label.svg) **[!UICONTROL Adobe Template]** in the [Components filter](/help/components/overview.md#filter).

| Calculated metric name | Description<br/>Formula |
|---------|----------|
| **[!UICONTROL Session start rate]** | The percent that any dimension item occurred on the first event of a session.<p>This calculated metric is automatically added to Workspace when you include the [!UICONTROL Session Starts] [standard component](/help/data-views/component-reference.md) in your [data view](/help/data-views/create-dataview.md).</p>Summary: **(** ![Event](/help/assets/icons/Event.svg) **Session starts** ![Divide](/help/assets/icons/Divide.svg) ![Event](/help/assets/icons/Event.svg) **Sessions** **)** |
| **[!UICONTROL Time spent per person]** | The average amount of time a person spent on any given dimension item.<p>This calculated metric is automatically added to Workspace when you include the [!UICONTROL Time Spent (seconds)] [standard component](/help/data-views/component-reference.md) in your [data view](/help/data-views/create-dataview.md). The segment Exclude Last Event of Session is applied to the People metric. The segment excludes the last event of each session in a dataset. This exclusion can help you analyze user behavior leading up to an event or action, such as a purchase or form submission, while excluding the final action itself.</p>Summary: **(** ![Event](/help/assets/icons/Event.svg) **Time spent (seconds)** ![Divide](/help/assets/icons/Divide.svg) ![Segmentation](/help/assets/icons/Segmentation.svg) **Exclude last event of session(** ![Event](/help/assets/icons/Event.svg) **People ) )** |
| **[!UICONTROL Sessions per person]** | The average number of Sessions per Person.<p>Summary: **(** ![Event](/help/assets/icons/Event.svg) **Sessions** ![Divide](/help/assets/icons/Divide.svg) ![Event](/help/assets/icons/Event.svg) **People** **)** |
| **[!UICONTROL Time spent per session]** | The average amount of time a person spent per Session on any given dimension item.<p>This calculated metric is automatically added to Workspace when you include the [!UICONTROL Time Spent (seconds)] [standard component](/help/data-views/component-reference.md) in your [data view](/help/data-views/create-dataview.md). The segment Exclude Last Event of Session is applied to the Sessions metric. The segment excludes the last event of each session in a dataset. This exclusion can help you analyze user behavior leading up to an event or action, such as a purchase or form submission, while excluding the final action itself.</p>Summary: **(** ![Event](/help/assets/icons/Event.svg) **Time spent (seconds)** ![Divide](/help/assets/icons/Divide.svg) ![Segmentation](/help/assets/icons/Segmentation.svg) **Exclude last event of session(** ![Event](/help/assets/icons/Event.svg) **Sessions ) )** |
| **[!UICONTROL Session end rate]** | The percent that any dimension item occurred on the last event of a session. <p>This calculated metric is automatically added to Workspace when you include the [!UICONTROL Session Ends] [standard component](/help/data-views/component-reference.md) in your [data view](/help/data-views/create-dataview.md).</p>Summary: **(** ![Event](/help/assets/icons/Event.svg) **Session ends** ![Divide](/help/assets/icons/Divide.svg) ![Event](/help/assets/icons/Event.svg) **Sessions** **)** |
| **[!UICONTROL Web sessions]** | The number of sessions that occurred on the website. |
| **[!UICONTROL Survey completion rate]** | The rate at which people completed a survey after starting it.  |
| **[!UICONTROL Multi-channel session rate]** | The ratio of sessions that occurred that included multiple channels (such as web traffic and mobile traffic), compared to those that included only a single channel.  |
| **[!UICONTROL Multi-channel person rate]** | The ratio of people who have particicpated in multiple channels, compared to those who have only participated in a single channel. |
| **[!UICONTROL Mobile app sessions]** | The number of sessions that occurred on the mobile app. |
| **[!UICONTROL Web+app cross-channel sessions]** | The number of sessions that occured that included both web traffic and mobile traffic. |
| **[!UICONTROL Cost of calls]** | The total cost for call center calls. <!-- <p>Summary: Call length</p> -->  |
| **[!UICONTROL Average call duration]** | The average duration of calls made to the call center.  |
| **[!UICONTROL Average cost per call]** | The average cost of calls made to the call center.  |
| **[!UICONTROL Average call survey score]** | The average survey score regarding calls made to the call center. |

{style="table-layout:auto"}
