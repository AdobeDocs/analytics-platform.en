---
title: Long Tail dimension item
description: Explains the dimension item "Long Tail" and why it appears in reporting.
---

# Long Tail dimension item

If you use a dimension that contains a large number of unique values, sometimes you can see a value in reporting labeled "Long Tail". This dimension item means that the reporting architecture CJA uses contained too many unique values for it to process.

## CJA processing architecture and unique values

CJA processes reports at the time they are run, distributing the combined dataset to a number of servers. Data per processing server is grouped by Person ID, meaning that a single processing server contains all data for a given person. Once it finishes processing, it hands its subset of processed data to an aggregator server. All subsets of processed data are combined and returned in the form of a Workspace report.

If any individual server processing a subset of data encounters more than 500,000 unique dimension items, it returns the top 500,000 dimension items of its own subset then returns the rest under 'Long Tail'. The 'Long Tail' dimension item seen in a Workspace report is the aggregated total of each individual processing server's values that exceeded 500K unique values.

## Differences between 'Long Tail' and 'Low-Traffic'

In previous versions of Adobe Analytics, a different processing architecture was used. Data was processed at the time it was collected. Dimension items were placed under 'Low-Traffic' after a dimension reached 500K unique values, and applied more aggressive filtering at 1M unique values. Unique value count was reset at the beginning of each calendar month. Processed data was permanent; there was no way to get existing data out of 'Low-Traffic'.

In CJA, dimension items are only put in 'Long Tail' if an individual processing server contains more than 500K unique values. Processed data is not permanent, which means that you can reduce the 'Long Tail' dimension item by modifying your report.

## Reduce the 'Long Tail' dimension item

If you want to reduce the 'Long Tail' dimension item, Adobe recommends any of the following:

* Use a segment. Segments apply at the time each server processes a subset of data. Limiting the number of unique values they return reduces the 'Long Tail' dimension item.
* Use a lookup dataset dimension. Lookup dataset dimensions combine event dataset dimension items, which limit the number of unique values returned.

Overall, it is difficult to consume a report that contains more than 500K unique dimension items. If you apply a segment or a lookup dataset dimension, you can reduce the presence of 'Long Tail' while making your report easier to consume. Adobe plans to improve this experience as CJA is developed further.
