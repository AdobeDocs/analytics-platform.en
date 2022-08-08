---
title: Metric deduplication component settings
description: Count only the first occurence of a metric in reports.
exl-id: ced0c637-5cbe-47a4-897a-eb79961986a3
solution: Customer Journey Analytics
feature: Data Views
---
# Metric deduplication component settings

Metric deduplication lets you configure a metric to only count values non-repetitively.

| Setting | Description |
| --- | --- |
| [!UICONTROL Metric deduplication] | A checkbox that allows you to enable metric deduplication. Disabled by default. |
| [!UICONTROL Deduplication scope] | Lets you determine how far back the unique check goes.<br>**Session**: Only the first metric occurrence of the session is counted.<br>**Person**: Only the first metric occurrence in the reporting window is counted. |
| [!UICONTROL Deduplication ID] | Instead of applying deduplication on the metric itself, allows you to apply metric deduplication based on a dimension instead. Valuable for dimensions like Purchase ID to apply deduplication. |

{style="table-layout:auto"}
