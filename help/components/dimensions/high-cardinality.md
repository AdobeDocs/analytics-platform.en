---
title: Dimensions with very high cardinality in Customer Journey Analytics
description: Describes best practices in dealing with high-cardinality dimensions in Customer Journey Analytics
---

# Dimensions with very high cardinality

Customer Journey Analytics (CJA) does not place limits on the number of unique values or dimension items that can be reported on within a single dimension. However, in some circumstances, dimensions with an extremely large number of unique items - also known as high-cardinality dimensions - may impact what can be reported on. 

## Limitations

Depending on the number of events in a specific CJA Connection, the following two limitations may occur in conjunction with high-cardinality dimensions: 

### 1. Row counts may not be precisely reportable

Row counts on high-cardinality dimensions may not be precisely reportable. When this happens, Freeform tables will provide an indication, as shown below:

   ![](assets/high-cardinality.png)

### 2. Calculated Metrics may use estimates for some functions and for sort order

When used with highly-cardinal dimensions, some Calculated Metric functions may return estimates, including: Column Maximum, Column Minimum, Row Count, Mean, Median, Percentile, Quartile, Standard Deviation, Variance, Regression Functions, and T and Z Functions. 

In addition, sorting a table column using a calculated metric may be based on an estimate and may not always reflect the exact sort order. A warning message will appear to alert you that estimates may have been used.

Be aware that even though calculated metrics may sometimes return estimates, the column totals are always accurate and are never based on estimates. Likewise, when using standard metrics, estimates are never used and always reflect exact sort orders.

### Where all dimension values are considered

Even though there are limitations to some calculated metrics and dimension row counts, be aware that the following capabilities always consider all unique values in any dimension regardless of whether a dimension is highly cardinal or not:

* Metric attribution and dimension allocation
* Line-item searches applied to a Freeform table
* Filters using dimensions or dimension items
* The approximate count distinct function within Calculated Metrics
* Include/Exclude logic applied to any metric or dimension within a Data View
* Lookup datasets added to a Connection

## Best practices for working with high-cardinal dimensions

In order to eliminate the warnings or estimates that may occur when using dimensions with high cardinality, we recommended that you narrow down the number of rows considered in your report, using one of the following methods:

* Add a filter to the column or panel impacted.
* Apply a search to your Freeform table.
* Apply a breakdown to the rows of interest, or use the highly-cardinal dimension as a breakdown dimension
* Add include/exclude criteria to the dimension’s Data View configuration to narrow down the number of unique values present in the dimension.

Using these techniques can often eliminate any undesirable estimations or warnings you experience when using high-cardinal dimensions.
