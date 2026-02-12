---
title: Summary Data
description: Learn about the details and information on how to use and configure summary data in a data view.
solution: Customer Journey Analytics
feature: Data Views
role: Admin
exl-id: 417443ae-a1ab-483b-a8fd-cff5ee8b6263
---
# Summary data

Summary data is time-series data that is not tied to an individual person ID. Summary data represents aggregated data at a different level of aggregation, for example campaigns. You can use this data in Customer Journey Analytics to support various use cases. For example, data containing a date and a single metric value, or data containing multiple dimensions and metrics.

This summary data can then be used to present high-level performance indicators or perform analysis. Examples of summary data can be advertising impressions, email opens, advertising spend, cost of good sold, S&P indices, and more. You can also use summary data to upload targets or goals on an hourly or daily basis.

>[!NOTE]
>
>Summary data is time-series data from a summary dataset. That summary dataset is based on a schema that uses the XDM Summary Metrics class as its base class.
>Only hourly or daily based time-series data are supported.

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

As explained in [Combined event dataset](/help/connections/combined-dataset.md), when defining a connection, Customer Journey Analytics creates an overall combined event dataset. When you configure your data view for dimensions originating from a summary dataset, options are available to group and hide dimensions as a preparation for reporting in Workspace. Specifically for summary data, the summary data is combined with event data, based on the [summary data group component](component-settings/summary-data-group.md) configuration.

| Tracking Code | Campaign Code | Impressions | Cost | Click-throughs | Revenue |
|---|---|--:|--:|--:|--:|
| abc123 | abc123 | 1,250 | $1,500 | 1,250 | $7,200 |
| def456 | def123 |775 | $650 | 775 | $1,250 |
| ghi789 | ghi789 | 500 | $500 | 500 | $750 |



### Reporting

Combining the summarized event data and on-site clickstream data enables you to report in Workspace on return on ad spend (ROAS).

| Tracking Code | Impressions | Cost | Click-throughs | Revenue | ROAS |
|---|--:|--:|--:|--:|:--|
| abc123 | 1,250 | $1,500 | 1,250 | $7,200 | 4.80 |
| def456 | 775 | $650 | 775 | $1,250 | 1.92 |
| ghi789 | 500 | $500 | 500 | $750 | 1.50 |


### Lookup data

If you want to report using a dimension defined in an additional lookup dataset (for example, campaign name), you have to follow these additional steps:

1. Create a new derived field that uses the [Lookup](/help/data-views/derived-fields/derived-fields.md#lookup) function to lookup the campaign name from the lookup dataset. In the definition of the [Lookup](/help/data-views/derived-fields/derived-fields.md#lookup) function you use the match between campaign code and tracking code to lookup the campaign name.
1. Add the newly created derived field as a dimension component to your data view.
1. Configure the campaign name dimension component (from the lookup dataset) to have a summary data grouping with the newly created derived field.

See the [Ingest and report on summary data](/help/use-cases/data-views/summary-data.md) use case for a detailed article on how to make use of, report on, and analyze summary data in Customer Journey Analytics.


## Prerequisites

To use summary data properly in your reports and analysis, a number of prerequisites apply. The following sections detail these prerequisites.

### Granularity and timezone

When configuring the dataset containing the summary data in Customer Journey Analytics, you notice that the granularity is automatically derived from the data. The selections for **[!UICONTROL Timestamp]** and **[!UICONTROL Timezone]** drop-down menu are disabled as both are derived from the schema definition. 

#### Granularity

You cannot mix and match the hourly and daily granularity of your summary data in one dataset (or with different datasets), using one summary data schema. For example, if you do have daily and hourly granular summary data for advertising campaign data, you need two schemas: one for the daily and one for the hourly summary data. And then upload the relevant granular data into datasets associated with the proper schema (for example, upload hourly data into a dataset associated with the hourly summary data schema).

#### Timezone

The timezone of your summary data is defined at the summary schema level in Experience Platform. The timezone applies to hourly granular data only.

- For daily granularity, Experience Platform assumes UTC, unless a timezone offset is included in the timestamp. When adding the summary dataset containing the daily summary data, Customer Journey Analytics ignores the timezone definition set on the schema and respects the day associated with the timestamp from the data in the dataset.
- For hourly granularity, Customer Journey Analytics respects the timezone configured on the summary data schema in Experience Platform when interpreting the timestamp. The table below provides some examples of this interpretation.
  
  | Timestamp <br/>source data | Timezone<br/>schema |  Timestamp<br/>Experience<br/>Platform | Timezone<br/> data<br/>view | Timestamp<br/>Customer<br/>Journey<br>Analytics |
  |---|---|---|:---|---|
  | 2024-07-29T01:00:00 | *default GMT* | 2024-07-29T01:00:00 | GMT | 2024-07-29T01:00:00 |
  | 2024-07-29T01:00:00 | *default GMT* | 2024-07-29T01:00:00 | PST | 2024-07-28T18:00:00 |
  | 2024-07-30T01:00:00-05:00 | *default GMT* | 2024-07-30T06:00:00 | GMT | 2024-07-30T06:00:00 |
  | 2024-07-30T01:00:00-05:00 | *default GMT* |2024-07-30T06:00:00 | PST | 2024-07-29T23:00:00 |
  | 2024-08-02 | *default GMT* | 2024-08-02T00:00:00 | IST | 2024-08-02T05:00:00 |
  | 2024-07-29T01:00:00 | `America/`<br/>`Los_Angeles`| 2024-07-28T18:00:00 | PST | 2024-07-28T18:00:00 |
  | 2024-07-30T01:00:00-05:00 | `Australia/`<br/>`Sydney` |2024-07-30T17:00:00 | CET | 2024-07-30T08:00:00 |

  For timezones with a 30 minutes offset (for example IST, India Standard Time), the 30 minute offset is dropped when reporting on summary data. For example: 12:30 is reported as 12:00.


To ensure, the proper timezone is used for your hourly granular summary data, you must ensure the schema used for summary data has the proper timezone configured. 

To configure the granularity and timezone for your summary data schema, you have to use the following API call as there is no equivalent user interface available.

```shell
curl -X POST \
https://platform.adobe.io/data/foundation/schemaregistry/tenant/descriptors \
 -H "Authorization: Bearer {$ACCESS_TOKEN}" \
 -H 'Content-Type: application/json' \
 -H 'x-api-key: {$API_KEY}' \
 -H 'x-gw-ims-org-id: {$ORG_ID}' \
 -H 'x-sandbox-name: {$SANDBOX_NAME}' \
 -d '{  
    "@type": "xdm:descriptorTimeSeriesGranularity",
    "xdm:sourceSchema": "{$SCHEMA_ID}",
    "xdm:sourceVersion": 1,
    "xdm:granularity": "{$GRANULARITY}",
    "xdm:ianaTimezone": "{$TIMEZONE}" 
 }'
```

| Variable | Value |
|---|---|
|`$ACCESS_TOKEN`<br/>`$API_KEY`<br/>`$ORG_ID`<br/>`$SANDBOX_NAME` | See [Authenticate and access Experience Platform APIs](https://experienceleague.adobe.com/en/docs/experience-platform/landing/platform-apis/api-authentication) for more information on how to specify values for these variables. |
| `$SCHEMA_ID` | You can find the id of your schema in the Experience Platform UI. Select your summary schema from the list of schemas, and find the **[!UICONTROL API Usage]** > **[!UICONTROL Schema ID]** in the right panel. Use that id as the value. |
| `$GRANULARITY` | Specify `hour` or `day` as the value. |
| `$TIMEZONE` | Specify the proper timezone identifier value from the TZ identifier column in the [List of tz database time zones](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones). For example: `America/Los_Angeles`. |

## Component settings

Ensure the component settings for a summary data group are the same. See [Summary data group component settings](component-settings/summary-data-group.md#same-component-settings) for more details.

>[!MORELIKETHIS]
>
>- See the [Use summary data](/help/use-cases/data-views/summary-data.md) article for a detailed use case example on how to use and report on summary data.
>- Blog: [How Summary Data Enhances Adobe Customer Journey Analytics Datasets](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/how-summary-data-enhances-adobe-customer-journey-analytics/ba-p/704635)

