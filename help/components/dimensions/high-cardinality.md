---
title: High cardinality dimensions
description: Explains how Customer Journey Analytics handles dimensions with many unique values
feature: Dimensions
solution: Customer Journey Analytics
exl-id: 17b275a5-c2c2-48ee-b663-e7fe76f79456
---
# High cardinality dimensions

When using a dimension that contains many unique values, the resulting report can contain too many unique dimension items to display or calculate. Results are truncated by removing dimension items deemed least important. These optimizations are done to maintain project and product performance.

When you request a report with too many unique values, Analysis Workspace shows an indicator in the dimension header stating that not all dimension items are included. For example, "Rows: 1-50 of more than 22,343,156". The "more than" keyword indicates that some optimization was applied to the report to return the most important dimension items.

![Workspace preview](assets/high-cardinality.png)

## Determining which dimension items to display

Customer Journey Analytics processes reports at the time that they are run, distributing the combined dataset to several servers. Data per processing server is grouped by person ID, meaning that a single processing server contains all data for a given person. Once a server finishes processing, it hands its subset of processed data to an aggregator server. All subsets of processed data are combined and returned in the form of a Workspace report.

If any individual server processes data that exceeds a unique threshold, it truncates the results before returning the processed subset of data. Truncated dimension items are determined based on the metric that is used for sorting.

If the sorting metric is a calculated metric, the server uses the metrics within the calculated metric to determine which dimension items to truncate. Since calculated metrics can contain several metrics of varying importance, results can be less accurate. For example, when calculating "Revenue per person", the total amount of revenue and total number of persons are returned and aggregated before doing the division. As a result, each individual processing server chooses which items to remove without knowing how their results affect overall sorting.

Though some individual dimension items might be missing from high cardinality reports, column totals are accurate and not based on truncated data. The 'Count Distinct' function in calculated metrics is also not affected by truncated dimension items.

## Best practices for high cardinality dimensions

The best way to accommodate high cardinality dimensions is to limit the number of dimension items that a report processes. Since all reports are processed at the time that they are requested, you can adjust report parameters for immediate results. Adobe recommends any of the following optimizations to high cardinality dimensions:

* Use a [Filter](/help/components/filters/create-filters.md). Filters apply at the time that each server processes a subset of data.
* Use a search. Dimension items excluded from the search term are removed from the report results, making it more likely that you see the desired dimension items.
* Use a lookup dataset dimension. Lookup dataset dimensions combine event dataset dimension items, which limit the number of unique values returned.
* Use the [Include/exclude](/help/data-views/component-settings/include-exclude-values.md) component setting in the data view manager.
* Shorten the request's date range. If many unique values accumulate over time, shortening the date range of the Workspace report can limit the number of unique values for servers to process.
