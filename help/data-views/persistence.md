---
title: What is dimension persistence in Customer Journey Analytics?
description: Dimension persistence is a combination of allocation and expiration. Together, they determine what dimension values persist.
---

# Persistence

Dimension persistence is a combination of allocation and expiration. Together, they determine what dimension values persist. Adobe highly recommends that you discuss within your organization how multiple values for each dimension are handled (allocation) and when dimension values stop persisting data (expiration).

* By default, a dimension value uses [WHAT?] allocation. 
* By default, a dimension value uses an expiration of [!UICONTROL Session].

## Allocation

Allocation applies a transformation to the underlying value you are using. Supported allocation models include:

* Most recent
* Original
* All
* First known
* Last known

### [!UICONTROL Most recent] allocation

Here is a before-and-after example of [!UICONTROL Most recent] allocation:

| Dimension | Hit 1 | Hit 2 | Hit 3 | Hit 4 | Hit 5 |
| --- | --- | --- | --- | --- | --- |
| timestamp (min) | 1 | 2 | 3 | 6 | 7 |
| original values |  | C | B |  | A |
| Most recent allocation |  | C | B | B | A |

### [!UICONTROL Original] allocation

Here is a before-and-after example of [!UICONTROL Original] allocation:

| Dimension | Hit 1 | Hit 2 | Hit 3 | Hit 4 | Hit 5 |
| --- | --- | --- | --- | --- | --- |
| timestamp (min) | 1 | 2 | 3 | 6 | 7 |
| original values |  | C | B |  | A |
| Original allocation |  | C | C | C | C |

### [!UICONTROL All] allocation

This new dimension allocation can be applied to both array-based dimensions or single-value dimensions. It acts similarly to the [!UICONTROL Participation] attribution model for metrics. The difference is that individual values within the field can expire at different points. For example, let's say we have 5 events in a string field, with allocation set to "All" and expiration set to 5 mins. We would expect the following behavior:

| Dimension | Hit 1 | Hit 2 | Hit 3 | Hit 4 | Hit 5 |
| --- | --- | --- | --- | --- | --- |
| timestamp (min) | 1 | 2 | 3 | 6 | 7 |
| original values | A | B | C |  | A |
| after-persistence | A | A,B | A,B,C | B,C | A,C |

Notice that the value of A persists until it reaches the 5-min mark, while B and C continue persisting into Hit 4 because 5 mins have not yet passed for those values. Note that this allocation will create a multi-valued dimension from a single-valued field. This model should also be supported on array-based dimensions:

| Dimension | Hit 1 | Hit 2 | Hit 3 | Hit 4 | Hit 5 |
| --- | --- | --- | --- | --- | --- |
| timestamp (min) | 1 | 2 | 3 | 6 | 7 |
| original values | A,B | C | B,C |  | A |
| after-persistence | A,B | A,B,C | A,B,C | B,C | A,B,C |

### "First Known" and "Last Known" allocations

These two new allocation models take the first or last observed value for a dimension within a specified persistence scope (session, person, or custom time period with lookback) and apply it to all events within the specified scope. Example:

| Dimension | Hit 1 | Hit 2 | Hit 3 | Hit 4 | Hit 5 |
| --- | --- | --- | --- | --- | --- |
| timestamp (min) | 1 | 2 | 3 | 6 | 7 |
| original values |  | C | B |  | A |
| first known | C | C | C | C | C |
| last known | A | A | A | A | A |

The first or last known values could be applied to just a session or at the person (reporting window) scope or at a custom, or time-based scope (essentially a person scope with a lookback window added).

## Expiration

[!UICONTROL Expiration] lets you specify the persistence window for a dimension.

There are four ways to expire a dimension value:

* Session (default): Expires after a given session.
* Person: ?
* Time: You can set the dimension value to expire after a specified time period or event.
* Metric: You can specify any of the defined metrics as the expiration end for this dimension (e.g. a "Purchase" metric).
* Custom: 

### What's the difference between Allocation and Attribution?

**Allocation**: Think of allocation as "data transformation" of the dimension. Allocation happens before filtering. If you create a filter, it will key off of the transformed dimension.

**Attribution**: How am I distributing the credit of a metric to the dimension that it is applied to? Attribution happens after filtering.

