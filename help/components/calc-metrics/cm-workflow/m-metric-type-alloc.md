---
description: Learn about
title: Metric Type and Attribution
feature: Calculated Metrics
exl-id: da73a9ba-542e-436c-bdb2-b629b5b6f760
---
# Metric Type and Attribution

Selecting the gear icon next to a metric lets you specify the metric type and the attribution model.

## Metric Type

![](assets/cm_type_alloc.png) 

|  Metric Type  | Definition  |
|---|---|
|  Standard  | These metrics are the same metrics used in standard [!DNL Analytics] reporting. If a formula consisted of a single standard metric, it displays identical data to its non-calculated-metric counterpart. Standard metrics are useful for creating calculated metrics specific to each individual line item. For example, [Orders] / [Visits] takes orders for that specific line item and divides it by the number of visits for that specific line item.  |
|  Total  | Use the total for the reporting period in every line item. If a formula consisted of a single total metric, it displays the same total number on every line item. Total metrics are useful for creating calculated metrics that compare against site total data. For example, [Orders] / [Total Visits] shows the proportion of orders against ALL visits to your site, not just the visits to the specific line item.  |

## Attribution

>[!IMPORTANT]
>For a full list of non-default attribution models and lookback windows supported, see [Attribution models and lookback windows](/help/analysis-workspace/attribution/models.md).
