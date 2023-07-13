---
title: Results Truncated dimension item
description: Explains the dimension item "Results Truncated" and why it appears in reporting.
feature: FAQ
exl-id: 262a219a-315a-4c9b-a400-48cff119d45d
---
# Results Truncated dimension item

When using a dimension that contains many unique values, a report can return a dimension item labeled **[!UICONTROL Results Truncated]**. This dimension item means that the requested report contained too many unique values for it to process efficiently. As a result, it removes items deemed least important.

## Customer Journey Analytics processing architecture and unique values

Customer Journey Analytics processes reports at the time that they are run, distributing the combined dataset to several servers. Data per processing server is grouped by Person ID, meaning that a single processing server contains all data for a given person. Once the server finishes processing, it hands its subset of processed data to an aggregator server. All subsets of processed data are combined and returned in the form of a Workspace report.

If any individual server aggregates a result set which is over a size threshold, it truncates the results before sending them back. This optimization keeps the network traffic and aggregation within bounds to allow for fast reporting. Since each processing server truncates results with only the view of its own data, it is possible that the items shown in Analysis Workspace have metric values that are slightly off.

The server chooses which dimension items to discard based on the metric that is used for sorting. If the sorting metric is a calculated metric, the server uses metrics within the calculated metric to determine which dimension items to truncate. Since calculated metrics can contain several metrics of varying importance, results can be less accurate. For example, when calculating "Revenue per person", the total amount of revenue and total number of persons are returned and aggregated before doing the division. As a result, each node chooses which items to remove without knowing how their results affects overall sorting.

## Differences between 'Results Truncated' and 'Low-Traffic'

In previous versions of Adobe Analytics, a different processing architecture was used. Data was processed at the time that it was collected. Dimension items were placed under 'Low-Traffic' after a dimension reached 500,000 unique values, and applied more aggressive filtering at one million unique values. The "Unique value" count was reset at the beginning of each calendar month. Processed data was permanent; there was no way to get existing data out of 'Low-Traffic'.

In Customer Journey Analytics, dimension items are only truncated if the results of a report are too large. Processed data is not permanent, which means that you can reduce or eliminate the truncation by modifying your report.

## Reduce the 'Results Truncated' dimension item

If you want to reduce the number of events in the 'Results Truncated' dimension item, Adobe recommends any of the following:

* Use a [Filter](/help/components/filters/create-filters.md). Filters apply at the time that each server processes a subset of data. Limiting the number of unique values they return reduces the 'Results Truncated' dimension item.
* Use a search. If a search is used, those items not matching the search are removed from the report results, making it more likely that you see the items that you want.
* Use a lookup dataset dimension. Lookup dataset dimensions combine event dataset dimension items, which limit the number of unique values returned.
