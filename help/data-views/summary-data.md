---
title: Summary data
description: Details and information on how to use summary data in a data view.
solution: Customer Journey Analytics
feature: Data Views
role: Admin
---

# Summary data

Summary data is time-series data that is not tied to an individual person ID. Summary data represents aggregated data at a different level of aggregation, for example campaigns. You can use this data in Customer Journey Analytics to support various use cases. For example, data containing a date and a single metric value, or data containing multiple dimensions and metrics.

This summary data can then be used to present high-level performance indicators or perform analysis. Examples of summary data can be advertising impressions, email opens, advertising spend, cost of good sold, S&P indices, and more. You can also use summary data to upload targets or goals on an hourly or daily basis.

>[!NOTE]
>
>Summary data is time-series data from a summary dataset. That summary dataset is based on a schema that uses the XDM Summary Metrics class as its base class.
>Currently only hourly or daily based time-series data are supported.

>[!TIP]
>
>You can configure a connection, data view and subsequently report on **only** summary data. It is not required to have additional event, profile or lookup data as part of your configuration.


## Example

An example of using summary data is combining summarized advertising campaign data with on-site clickstream data for reporting.

### Summary data

Your summary data contains the following advertising campaign data.

| Campaign Code | Impressions | Cost |
|---|---:|---:|
| abc123 | 1,250 | $1,500 |
| def456 | 775 | $650 |
| ghi789 | 500 | $500 |


### Event data

Your on-site clickstream data contains the following events.

| Tracking Code | Click-throughs | Revenue |
|---|---:|---:|
| abc123 | 1,250 | $7,200 |
| def456 | 775 | $1,250 |
| ghi789 | 500 | $750 |

### Combined data

As explained in [Combined event dataset](/help/connections/combined-dataset.md), when defining a connection, Customer Journey Analytics creates an overall combined event dataset. Summary data is considered an event dataset, and combined with the event data containing the clickstream data, the table below represents the combined dataset.

| Tracking Code | Campaign Code | Impressions | Cost | Click-throughs | Revenue | 
|---|---|--:|--:|--:|--:|
| abc123 | abc123 | 1,250 | $1,500 | 1,250 | $7,200 |
| def456 | def123 |775 | $650 | 775 | $1,250 |
| ghi789 | ghi789 | 500 | $500 | 500 | $750 |

When you configure your data view for dimensions originating from a summary dataset, options are available to group and hide dimensions as a preparation for reporting in Workspace. See [Summary data group component settings](component-settings/summary-data-group.md) for more details.

### Reporting

Combining the summarized event data and on-site clickstream data enables you to report in Workspace on return on ad spend (ROAS).

| Tracking Code | Impressions | Cost | Click-throughs | Revenue | ROAS |
|---|--:|--:|--:|--:|:--|
| abc123 | 1,250 | $1,500 | 1,250 | $7,200 | 4.80 |
| def456 | 775 | $650 | 775 | $1,250 | 1.92 |
| ghi789 | 500 | $500 | 500 | $750 | 1.50 |





