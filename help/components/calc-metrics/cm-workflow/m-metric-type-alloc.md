---
description: Learn about
title: Metric Type and Attribution
feature: Calculated Metrics
exl-id: da73a9ba-542e-436c-bdb2-b629b5b6f760
---
# Metric Type and Attribution

Selecting the gear icon next to a metric lets you specify the metric type and the attribution model.

## Metric Type

To specify the metric type when building a calculated metric:

1. Select the gear icon next to the metric whose type you want to select.

   ![](assets/cm_type_alloc.png) 

1. Choose from the following options:

   |  Metric Type  | Definition  |
   |---|---|
   |  Standard  | These metrics are the same metrics used in standard [!DNL Analytics] reporting. If a formula consisted of a single standard metric, it displays identical data to its non-calculated-metric counterpart. Standard metrics are useful for creating calculated metrics specific to each individual line item. For example, [Orders] / [Sessions] takes orders for that specific line item and divides it by the number of sessions for that specific line item.  |
   |  Grand total  | Use the Grand total for the reporting period in every line item. If a formula consisted of a single Grand total metric, it displays the same Grand total number on every line item. Grand total metrics are useful for creating calculated metrics that compare against total data. For example, [Orders] / [Total Sessions] shows the proportion of orders against ALL sessions on a channel, not just the sessions to the specific line item.  |

## Attribution

For information about attribution in Customer Journey Analytics, see [Attribution component settings](/help/data-views/component-settings/attribution.md).
