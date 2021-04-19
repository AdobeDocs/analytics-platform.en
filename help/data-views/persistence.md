---
title: What is dimension persistence in Customer Journey Analytics?
description: Dimension persistence is a combination of allocation and expiration. Together, they determine how or whether dimension values persist from one event to the next.
exl-id: b8b234c6-a7d9-40e9-8380-1db09610b941
---
# Persistence

Dimension persistence is a combination of allocation and expiration. Together, they determine how or whether dimension values persist from one event to the next. Dimension persistence is configured on a dimension within Data Views and is retroactive and non-destructive to the data it is applied to. Dimension persistence is an immediate data transformation applied to a dimension that occurs before filtering or other analysis operations are done in reporting.

* By default, a dimension value does not have any persistence enabled. 
* By default, when any allocation model is enabled fir a dimension, an expiration of [!UICONTROL Session] is used.

## Allocation

Allocation applies a transformation to the underlying value you are using. Supported allocation models include:

* Most recent
* Original
* All

### [!UICONTROL Most recent] allocation

Most recent allocation will persist the most recent (by timestamp) value present in the dimension. Any subsequent values that occur within the same Session will replace the previously persisting value. Note that if "Treat 'No Value' as a value" has been selected on this dimenion, the empty values will be replaced with 'No Value' prior to persistence being applied. Here is a before-and-after example of [!UICONTROL Most recent] allocation assuming a [!UICONTROL Session] is used for expiration and all events occur within a [!UICONTROL Session]:

| Dimension | Hit 1 | Hit 2 | Hit 3 | Hit 4 | Hit 5 |
| --- | --- | --- | --- | --- | --- |
| dataset values |  | C | B |  | A |
| Most recent allocation |  | C | B | B | A |

### [!UICONTROL Original] allocation

Original allocation will persist the original value (by timestamp) present within the dimension for an expiration period. Here is a before-and-after example of [!UICONTROL Original] allocation:

| Dimension | Hit 1 | Hit 2 | Hit 3 | Hit 4 | Hit 5 |
| --- | --- | --- | --- | --- | --- |
| dataset values |  | C | B |  | A |
| Original allocation |  | C | C | C | C |

### [!UICONTROL All] allocation

This dimension allocation can be applied to both array-based dimensions or single-value dimensions. It acts similarly to the [!UICONTROL Participation] attribution model for metrics. A key difference is that dimensions with All allocation can be used in Filter definitions. For example, let's say we have 5 events in a string field, with allocation set to "All" and expiration set to 5 mins:

| Dimension | Hit 1 | Hit 2 | Hit 3 | Hit 4 | Hit 5 |
| --- | --- | --- | --- | --- | --- |
| dataset values | A | B | C |  | A |
| after-persistence | A | A,B | A,B,C | A,B,C | A,B,C |

## Expiration

[!UICONTROL Expiration] lets you specify the persistence window for a dimension.

There are four ways to expire a dimension value:

* Session (default): Expires after a given session.
* Person: Expires at the end of your reporting window.
* Time: You can set the dimension value to expire after a specified time period (up to 90 days). This expiration option is only available for Original and Most Recent allocation models. When using time based expiration, values previous to the start of your reporting window (up to 90 days) are considered.
* Metric: You can specify any of the defined metrics as the expiration end for this dimension (e.g. a "Purchase" metric). This expiration is only available for Original and Most Recent allocation models.

### What's the difference between Allocation and Attribution?

**Allocation**: Think of allocation as a data transformation to the dimension. Allocation happens before filtering. If you create a filter, it will key off of the transformed dimension.

**Attribution**: How am I distributing the credit of a metric to the dimension that it is applied to? Attribution is not a data transformation, applies during data aggregation, and does not impact which data is included using a Filter.
