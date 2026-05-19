---
title: Metric deduplication component settings
description: Count only the first occurence of a metric in reports.
exl-id: ced0c637-5cbe-47a4-897a-eb79961986a3
solution: Customer Journey Analytics
feature: Data Views
role: Admin
autotag-review: '2026-05-19T09:10:57.728Z'
TQID: 'https://experienceleague.adobe.com/bCgBjD9r0cQ3O73fEip-EQHItMHQSX-2AECydDxR9Ms'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: b3197353-f189-4932-8378-3f3bc40e6071
    internal-label: Data management
subfeature_v2:
  - id: e1471301-a189-438e-8d48-264a8db508a6
    internal-label: Data views
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
---
# Metric deduplication component settings {#metric-deduplication-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_metric_deduplication"
>title="Metric deduplication"
>abstract="Configure a metric to only count values that occur non-repetitively."

<!-- markdownlint-enable MD034 -->


Metric deduplication lets you configure a metric to only count values non-repetitively.

![Metric deduplication](../assets/metric-deduplication.png)

| Setting | Description |
| --- | --- |
| [!UICONTROL Metric deduplication] | A checkbox that allows you to enable metric deduplication. Disabled by default. |
| [!UICONTROL Deduplication scope] | Lets you determine how far back the unique check goes.<br/>**[!UICONTROL Global account]**: Only the first metric occurrence in the reporting window is counted.<br/>**[!UICONTROL Account]**: Only the first metric occurrence in the reporting window is counted.<br/>**[!UICONTROL Opportunity]**: Only the first metric occurrence in the reporting window is counted.<br/>**[!UICONTROL Buying group]**: Only the first metric occurrence in the reporting window is counted.<br/>**[!UICONTROL Person]**: Only the first metric occurrence in the reporting window is counted.<br>**[!UICONTROL Session]**: Only the first metric occurrence of the session is counted.<br> |
| [!UICONTROL Deduplication ID] | Instead of applying deduplication on the metric itself, allows you to apply metric deduplication based on a dimension instead. Valuable for dimensions like Purchase ID to apply deduplication. |
| [!UICONTROL Value to keep]|<ul><li>**Keep first instance**: Use this in situations where the initial instance of the metric is the valid one. The most common one would probably be a purchase confirmation. Even if someone inadvertently reloads the page and we get another instance of a purchase confirmation, the initial event is the valid one.</li><li>**Keep last instance**: Use this in situations where the last instance makes more sense to collect. Example: Someone makes an update to their online profile. We only want to count one of these updates per session. However, they may update their profile multiple times during the session. If we keep the first instance, there could be activities which would not tie to the event. In this case, it makes more sense to keep the last instance.</li></ul> |

{style="table-layout:auto"}

>[!CAUTION]
>
>Deduplication at a _person_ scope is evaluated by complete months in UTC time. A partial-month reporting window may not display all first or last instances, if some occurred within the full month but outside of the reporting dates.
