---
title: Customer Journey Analytics Guardrails
description: Learn about the guardrails, static limits, performance guardrails, scoping parameters and entitlements for Customer Journey Analytics
solution: Customer Journey Analytics
feature: CJA Administration
---

# Customer Journey Analytics Guardrails

This document provides static and soft limits for various components of Customer Journey Analytics. For performance guardrails, scoping parameters and entitlements, see the [Product Description for Customer Journey Analytics](https://helpx.adobe.com/legal/product-descriptions/customer-journey-analytics.html) or the [Product Description for Adobe Analytics Add-on: Customer Journey Analytics](https://helpx.adobe.com/legal/product-descriptions/adobe-analytics-addon-customer-journey-analytics.html).

Static and soft limits can be seen as guardrails, thresholds that provide guidance for data and system usage, performance optimization, and avoidance of errors or unexpected results in Customer Journey Analytics. 

Some of the features and their associated value for the static and soft limits are dependent on the Customer Journey Analytics package you are entitled to. 

>[!NOTE]
>
>The values outlined in this document are subject to change based on continuing improvements in the product. Please check back regularly for updates. If you are interested in learning about custom limits, please contact your customer care representative. 

## Ad Hoc SQL Queries

| Name | Value | Description | PD? |
|---|--:|---|:---:|
| Try again timeout | 90 | Maximum number of seconds before reporting engine responds back that the request takes too long to return results (possibly due to other simultaneous other requests); it is possible to request again. | | 
| Don't try again timeout | 600 | Maximum nunber of seconds before Ad Hoc SQL queries will time out. Otherwise stated, maximum number of seconds before reporting engines reports back that the request takes too long to return results and should not be tried again as the request will never return results. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  | 
| Metrics | 150 | Maximum number of metrics in a request. | | |
| Interactive Query Output Rows | 50,000 | Default number of rows returned unless specified otherwise. | | 

{style="table-layout:auto"}

## Analysis Workspace projects

| Name | Value | Description | PD? |
|---|--:|---|:---:|
| Visible rows per table | 400 |  Maximum number of visible rows in any freeform table in your Analysis Workspace project. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) | 
| Exportable rows per table | 50,000 |  Maximum number of rows you can export per single dimension. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) | 
| Panels per project | 15 | Maximum number of [panels](../analysis-workspace/home.md#panels) per project. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) | 
| Visualizations per panel | 25 | Maximum number of [visualizations](../analysis-workspace/home.md#visualizations) per panel. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) | 

{style="table-layout:auto"}

## Attribution AI

| Name |  Value | Description | PD? |
|---|--:|---|:---:|
| Attribution AI models | 35 | Maximum number of Attribution AI Model per year to analyze the impact of up to an average of 60 independent touchpoints on a specified conversion event.  | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  | 
| Region based iterations | 10 | Maximum number of region-based iterations of each Attribution AI model. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  | 
| Export Insights batches | 12 | Maximum number of export batches times the number of authorized Attribution AI Insights per year. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) | 

{style="table-layout:auto"}

## Audiences

| Name | Value | Description | PD? |
|---|--:|---|:---:|
| Audience filters | 20 | Maximum number of filters per audience. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  | 
| Number of audience identities | 20,000,000 | Maximum number of identities per audience. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  | 
| Audience refresh frequency | 4 | Maximum frequency in hours an audience may be refreshed. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  | 
| Audience refresh lookback window | 90 | Maximum number of days for refresh lookback window. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) | 
| Refreshing audience expiration date | 13 | Maximum number of months audience will cease to refresh from the date of creation. Customers have the ability to extend this for an additional 13 months (contact your customer care representative). | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  | 
| Number of refreshing audiences | 75, 100, 150 | Maximum number of refreshing audiences, depending on the package. <br/>A refreshing audience is an audience updating itself based on where new profiles qualifying for the filter are added and existing profiles that do not longer qualify for the filter are removed. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) |

{style="table-layout:auto"}

See also Experience Platform [Real-time Customer Data Platform guardrails](https://experienceleague.adobe.com/docs/experience-platform/profile/guardrails.html?lang=en).


## Automated dataset expiration

| Name |  Value | Description | PD? |
|---|--:|---|:---:|
| Work orders | 20 | Maximum number of automated dataset expiration work orders. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) | 

{style="table-layout:auto"}



## Connections, Data views, Projects

| Name |  Value | Description | PD? |
|---|--:|---|:---:|
| Projects | 2,000 | Maximum number of projects for an organization. | |
| Data views | 2,000 | Maximum number of [data views](../data-views/data-views.md) for an organization. | |
| Data views | 50 | Maximum number of data views for a connection | |
| Datasets | 100 | Maximum number of [datasets](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/overview.html?lang=en) per connection. | |
| Connections | 1000 | Maximum number of [connections](../connections/overview.md) for an organization. | |
| Connection Title | 500 | Maximum number of characters for a connection title. | | 
| Annotation Title | 100 | Maximum number of characters for an annotation title. | |
| Annotation Description | 250 | Maximum number of characters for an annotation description. | | 
| Schema fields | 10 | Maximum number of schema fields (not including standard fields) when defining rules for a [derived field](../data-views/derived-fields/derived-fields.md). | | 
| Lookup / Profile fields | 3 | Maximum number of lookup or profile schema fields within the maximum number of schema fields (not including standard fields) when defining rules for a derived field. |
| Derived Fields | 100 | Maximum number of derived fields per connection. | |

{style="table-layout:auto"}


## Data transfer limits

| Name |  Value | Description | PD? |
|---|--:|---|:---:|
| Fields | 10,000 | Maximum number of properties or fields per row in a dataset. | | | 
| Unique strings | 10,000,000 | Maximum number of unique keys per lookup dataset. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  | 
| Rows | 1,000,000 | Maximum number of rows per unique person ID within a connection. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  | 
| Row size | 2 | Average size in kilobytes per row of data ingested into Customer Journey Analytics (soft limit). A static limit is determined by guardrails for data ingestion in Experience Platform. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) |

{style="table-layout:auto"}

See also Experience Platform [Guardrails for Data Ingestion](https://experienceleague.adobe.com/docs/experience-platform/ingestion/guardrails.html?lang=en).


## Data landing zone

| Name | Value | Description | PD? |
|---|--:|---|:---:|
| Data landing zone per sandbox | 1 | Maximum number of data landing zones per sandbox. |  ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) |
| Data storage| 7| Maximum number of days data will be stored at data landing zone before being deleted. |  ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) |

{style="table-layout:auto"}


## Field based stitching

| Name |  Value | Description | PD? |
|---|--:|---|:---:|
| Stitched datasets | 10 | Maximum number of stitched datasets per customer, dependent on the package. |  ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) |
| Backfill data | 60 | Maximum number of days of backfill data, dependend on the package. | |

{style="table-layout:auto"}


## Filters and calculated metrics 

| Name |  Value | Description | PD? |
|---|--:|---|:---:|
| Containers per filter | 50 | Maximum number of containers in a filter. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  | 
| Metrics per calculated metric | 25 | Maximum number of metrics in a calculated metric. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  | 
| Metrics and dimensions per filter | 25 | Maximum number of unque metrics and dimensions in a filter. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  |
| Nested containers per filter | 10 | Maximum number of nested containers in a filter. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  |
| Rules per filter| 100 | Maximum nunber of rules per filter. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)   |
| String compares per dimension per filter | 100 |  Maximum number of strings comparisons per dimension per filter. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  |
| Calculated metrics | 6,000 | Maximum number of calculated metrics for an organization. | |
| Filters | 50,000 | Maximum number of filters you can define for an organization. | |

{style="table-layout:auto"}


## Mobile application

| Name |  Value | Description | PD? |
|---|--:|---|:---:|
| Tiles | 16 | Maximum number of tiles per scorecard. | |
| Filters | 10 | Maximum number of filters per scorecard. | | 
| Dimensions | 10 | Maximum number of dimensions per scorecard. | |

{style="table-layout:auto"}

## Report Builder

| Name | Value | Description | PD? |
|---|--:|---|:---:|
| Workbook file size | 5 | Maximum file size in MB of a scheduled workbook. ||
| Data blocks | 1000 | Maximum number of [data blocks](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/manage-reportbuilder.html?lang=en) per workbook. | | 
| Metrics | 20 | Maximum number of metrics per data block. |   | 
| Date range span | 13 | Maximum number of months a date range can span per data block. |  |
| Rows | 50,000 | Maximum number of rows per data block. |  | 

{style="table-layout:auto"}


## Full table export

| Name |  Value | Description | PD? |
|---|--:|---|:---:|
| Rows per report |  3,000,0000 - 150,000,000 | Maximum number of reporting rows per report, dependent on the package. | |
| Breakdowns per table |  5 | Maximum number of breakdowns per table. | |
| Metrics per table |  5 | Maximum number of metrics per table. | |
| Schedule frequency |  1 | Exports can be scheduled once (1) a day or on a longer schedule (for example: once every 2 days, or weekly). | | 

{style="table-layout:auto"}

## Latencies

>[!NOTE]
>
>Processing times below are guardrails, not contractual service level agreements (SLAs).  Latency will vary depending on customer configuration, data volumes, and consumer applications. Real processing times will often be faster. Refer to your Customer Journey Analytics contract for your specific contractual terms and SLAs. See Experience Platform [Guardrails for Data Ingestion](https://experienceleague.adobe.com/docs/experience-platform/ingestion/guardrails.html?lang=en) for more information.

| Data flow | Expected latency |
|---|---|
| Adobe Analytics to Adobe Analytics source connector (A4T enabled) | < 30 minutes |
| Adobe Analytics source connector to Real-time Customer Profile (A4T not enabled) | < 2 minutes |
| Adobe Analytics source connector to Real-time Customer Profile (A4T enabled) | < 30 minutes |
| Data ingestion into Data Lake from Edge Network or streaming ingestion | < 60 minutes |
| Data ingestion into Data Lake from Adobe Analytics source connector | < 90 minutes |
| Data ingestion into Customer Journey Analytics from Data Lake | < 90 minutes |
| Adobe Analytics source connector backfill of less than 10 billion event (maximum of 13 months of historical data) | < 4 weeks |
| Audience publishing to Real-time Customer Profile, including automatic creation of the streaming segment, and allowing the segment to be ready to receive the data. | ≈ 60 minutes |
| Refresh frequency for audiences | One-time refresh: latency of less than 5 minutes.<br/>Refresh every 4 hours, daily, weekly, monthly (latency goes hand in hand with the refresh rate) |

{style="table-layout:auto"}

