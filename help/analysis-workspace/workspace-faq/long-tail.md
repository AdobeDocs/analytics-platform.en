---
title: Long Tail dimension item
description: Explains the dimension item "Long Tail" and why it appears in reporting.
feature: FAQ
exl-id: 262a219a-315a-4c9b-a400-48cff119d45d
---
# Long-tail dimension item

When using a dimension that contains a large number of unique values, sometimes you a warning that says **[!UICONTROL Results Truncated]**.  This means that the reporting architecture CJA uses contained too many unique values for it to process efficiently. As a result. it removed the items that it deemed  least important.

## CJA processing architecture and unique values

CJA processes reports at the time they are run, distributing the combined dataset to a number of servers. Data per processing server is grouped by Person ID, meaning that a single processing server contains all data for a given person. Once the server finishes processing, it hands its subset of processed data to an aggregator server. All subsets of processed data are combined and returned in the form of a Workspace report.

If any individual server aggregates a result set which is over a size threshold, then it will truncate the results before sending them back. This keeps the network traffic and aggregation within bounds to allow for quick reporting.  Because it truncates the results with only the view of its own data, it is possible (though unlikely) that the items shown in Analysis Workspace have incorrect metric values.

The server chooses which items to discard based on the metric used for sorting.  If this is a calculated metric, it may not be obvious how to sort it, and so results may be less accurate.  For example, when calculating "Revenue per person", the total amount of revenue and total number of persons are returned and aggregated before doing the division. As a result, each node much choose which items to remove, without really knowing how their results will affect the overall sorting.

## Differences between 'Long Tail' and 'Low-Traffic'

In previous versions of Adobe Analytics, a different processing architecture was used. Data was processed at the time it was collected. Dimension items were placed under 'Low-Traffic' after a dimension reached 500K unique values, and applied more aggressive filtering at 1M unique values. The "Unique value" count was reset at the beginning of each calendar month. Processed data was permanent; there was no way to get existing data out of 'Low-Traffic'.

In CJA, dimension items are only truncated if the results of a report are too large. Processed data is not permanent, which means that you can reduce or eliminate the truncation by modifying your report.

## Reduce the 'Long Tail' dimension item

If you want to reduce the 'Long Tail' truncation, Adobe recommends any of the following:

* Use a [filter](/help/components/filters/create-filters.md). Filters apply at the time each server processes a subset of data. Limiting the number of unique values they return reduces the 'Long Tail' truncation.
* Use a search. If a search is used, those items not matching the search are truncated first, thus making it more likely that you see the items you want.
* Use a lookup dataset dimension. Lookup dataset dimensions combine event dataset dimension items, which limit the number of unique values returned.

Overall, it is difficult to consume a report that contains too many unique dimension items. If you apply a filter or a lookup dataset dimension, you can reduce the 'Long Tail' truncation while making your report easier to consume.
