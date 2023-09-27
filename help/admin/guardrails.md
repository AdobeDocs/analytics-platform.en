---
title: Customer Journey Analytics Guardrails
description: Learn about the guardrails, static limits, performance guardrails, scoping parameters and entitlements for Customer Journey Analytics
solution: Customer Journey Analytics
feature: CJA Administration
---

# Customer Journey Analytics Guardrails

This document provides static limits, performance guardrails, scoping parameters and entitlements for various components of Customer Journey Analytics. See for definitions the [Product Description](https://helpx.adobe.com/ie/legal/product-descriptions/customer-journey-analytics.html). 

The document also provides some soft limits. Soft limits can be seen as guardrails, thresholds that provide guidance for data and system usage, performance optimization, and avoidance of errors or unexpected results in Customer Journey Analytics. 

Some of the features and their associated value for static limit, performance guardrail, scoping parameter, soft limit or entitlement are dependent on the Customer Journey Analytics package (Foundation, Select) you are entitled to. 

>[!NOTE]
>
>The values outlined in this document are subject to change based on continuing improvements in the product. Please check back regularly for updates. If you are interested in learning about custom limits, please contact your customer care representative. 

## Ad Hoc SQL Queries

| Name | Type | Value | Description | In Product Description? |
|---|---|--:|---|:---:|
| Try again timeout | Static limit | 90 | Maximum number of seconds before reporting engine responds back that the request takes too long to return results (possibly due to other simultaneous other requests); it is possible to request again. | | 
| Don't try again timeout | Static limit | 600 | Maximum nunber of seconds before Ad Hoc SQL queries will time out. Otherwise stated, maximum number of seconds before reporting engines reports back that the request takes too long to return results and should not be tried again as the request will never return results. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  | 
| Concurrent requests | Performance guardrail | 5 | Maximum number of concurrent requests. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  |
| Metrics | Static limit | 150 | Maximum number of metrics in a request. | | |
| Query users | Scoping parameter | 5 | Maximum number of users to run ad-hoc queries. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  | 
| Validation users | Scoping parameter | 1 | Maximum number of users running Ad Hoc queries for the purpose of data ingestion validation unless increased by your contractual terms for query users. Talk to your Adobe representative for more information. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  |
| Interactive Query Output Rows | Static limit | 50,000 | Default number of rows returned unless specified otherwise. | | 

{style="table-layout:auto"}

## Analysis Workspace projects

| Name | Type | Value | Description | In Product Description? |
|---|---|--:|---|:---:|
| Visible rows per table | Static limit | 400 |  Maximum number of visible rows in any freeform table in your Analysis Workspace project. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) | 
| Exportable rows per table | Static limit | 50,000 |  Maximum number of rows you can export per single dimension. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) | 
| Panels per project | Static limit | 15 | Maximum number of [panels](../analysis-workspace/home.md#panels) per project. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) | 
| Visualizations per panel | Static limit | 25 | Maximum number of [visualizations](../analysis-workspace/home.md#visualizations) per panel. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) | 

{style="table-layout:auto"}

## Attribution AI

| Name | Type | Value | Description | In Product Description? |
|---|---|--:|---|:---:|
| Attribution AI models | Static limit | 35 | Maximum number of Attribution AI Model per year to analyze the impact of up to an average of 60 independent touchpoints on a specified conversion event  | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  | 
| Region based iterations | Static limit | 10 | Maximum number of region-based iterations of each Attribution AI model | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  | 
| Export Insights batches | Static limit | 12 | Maximum number of export batches times the number of authorized Attribution AI Insights per year | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) | 

{style="table-layout:auto"}

## Audiences

| Name | Type | Value | Description | In Product Description? |
|---|---|--:|---|:---:|
| Audience filters | Static limit | 20 | Maximum number of filters per audience. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  | 
| Number of audience identities | Static limit | 20,000,000 | Maximum number of identities per audience. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  | 
| Audience refresh frequency | Static limit | 4 | Maximum frequency in hours an audience may be refreshed. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  | 
| Audience refresh lookback window | Static limit | 90 | Maximum number of days for refresh lookback window. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) | 
| Refreshing audience expiration date | Soft | 13 | Maximum number of months audience will cease to refresh from the date of creation. Customers have the ability to extend this for an additional 13 months (contact your customer care representative). | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  | 
| Number of refreshing audiences | Static limit | 75<br/>100<br/>150 | Maximum number of refreshing audiences for Select / Prime / Ultimate customers. <br/>A refreshing audience is an audience updating itself based on where new profiles qualifying for the filter are added and existing profiles that do not longer qualify for the filter are removed. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) |

{style="table-layout:auto"}

See also Experience Platform [Real-time Customer Data Platform guardrails](https://experienceleague.adobe.com/docs/experience-platform/profile/guardrails.html?lang=en).


## Automated dataset expiration

| Name | Type | Value | Description | In Product Description? |
|---|---|--:|---|:---:|
| Work orders | Static limit | 20 | Maximum number of automated dataset expiration work orders | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) | 

{style="table-layout:auto"}



## Connections, Data views, Projects

| Name | Type | Value | Description | In Product Description? |
|---|---|--:|---|:---:|
| Projects | Static limit | 2,000 | Maximum number of projects for an organization. | |
| Data views | Static limit | 2,000 | Maximum number of [data views](../data-views/data-views.md) for an organization. | |
| Data views | Static limit | 50 | Maximum number of data views for a connection | |
| Datasets | Static limit | 100 | Maximum number of [datasets](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/overview.html?lang=en) per connection. | |
| Connections | Static limit | 1000 | Maximum number of [connections](../connections/overview.md) for an organization. | |
| Connection Title | Static limit | 500 | Maximum number of characters for a connection title. | | 
| Annotation Title | Static limit | 100 | Maximum number of characters for an annotation title. | |
| Annotation Description | Static limit | 250 | Maximum number of characters for an annotation description. | | 
| Schema fields | Static limit | 10 | Maximum number of schema fields (not including standard fields) when defining rules for a [derived field](../data-views/derived-fields/derived-fields.md). | | 
| Lookup / Profile fields | Static limit | 3 | Maximum number of lookup or profile schema fields within the maximum number of schema fields (not including standard fields) when defining rules for a derived field. |
| Derived Fields | Static limit | 100 | Maximum number of derived fields per connection. | |

{style="table-layout:auto"}


## Data transfer limits

| Name | Type | Value | Description | In Product Description? |
|---|---|--:|---|:---:|
| Fields | Static limit | 10,000 | Maximum number of properties or fields per row in a dataset. | | | 
| Unique strings | Static limit | 10,000,000 | Maximum number of unique keys per lookup dataset. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  | 
| Rows | Static limit | 1,000,000 | Maximum number of rows per person ID within a connection. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  | 
| Adobe Analytics backfill | Entitlement | 13 | Maximum number of months of backfill data imported via the Adobe Analytics Source Connector to a production sandbox (three months for a non-production sandbox). | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) |
| Row size | Entitlement<br/>Soft Limit | 2 | Average size in kilobytes per row of data ingested into Customer Journey Analytics (soft limit). A hard limit is determined by guardrails for data ingestion in Experience Platform. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) |

{style="table-layout:auto"}

See also Experience Platform [Guardrails for Data Ingestion](https://experienceleague.adobe.com/docs/experience-platform/ingestion/guardrails.html?lang=en).


## Data landing zone

| Name | Type | Value | Description | In Product Description? |
|---|---|--:|---|:---:|
| Data landing zone per sandbox | Static limit | 1 | Maximum number of data landing zones per sandbox |  ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) |
| Data storage| Static limit | 7| Maximum number of days data will be stored at data landing zone before being deleted |  ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) |

{style="table-layout:auto"}


## Field based stitching

| Name | Type | Value | Description | In Product Description? |
|---|---|--:|---|:---:|
| Stitched datasets | Static limit | 10 | Maximum number of stitched datasets per customer |  ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) |

{style="table-layout:auto"}


## Filters and calculated metrics 

| Name | Type | Value | Description | In Product Description? |
|---|---|--:|---|:---:|
| Containers per filter | Static limit | 50 | Maximum number of containers in a filter. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  | 
| Metrics per calculated metric | Static limit | 25 | Maximum number of metrics in a calculated metric. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  | 
| Metrics and dimensions per filter | Static limit | 25 | Maximum number of unque metrics and dimensions in a filter. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  |
| Nested containers per filter | Static limit | 10 | Maximum number of nested containers in a filter. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  |
| Rules per filter| Static limit | 100 | Maximum nunber of rules per filter. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)   |
| String compares per dimension per filter | Static limit | 100 |  Maximum number of strings comparisons per dimension per filter. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  |
| Calculated metrics | Static limit | 6,000 | Maximum number of calculated metrics for an organization. | |
| Filters | Static limit | 50,000 | Maximum number of filters you can define for an organization. | |

{style="table-layout:auto"}


## Mobile application

| Name | Type | Value | Description | In Product Description? |
|---|---|--:|---|:---:|
| Tiles | Static limit | 16 | Maximum number of tiles per scorecard. | |
| Filters | Static limit | 10 | Maximum number of filters per scorecard. | | 
| Dimensions | Static limit | 10 | Maximum number of dimensions per scorecard. | |

{style="table-layout:auto"}

## Report Builder

| Name | Type | Value | Description | In Product Description? |
|---|---|--:|---|:---:|
| Workbook file size | Static limit | 5 | Maximum file size in MB of a scheduled workbook. ||
| Data blocks | Static| 1000 | Maximum number of [data blocks](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/manage-reportbuilder.html?lang=en) per workbook. | | 
| Metrics | Static limit | 20 | Maximum number of metrics per data block. |   | 
| Date range span | Static limit | 13 | Maximum number of months a date range can span per data block. |  |
| Rows | Static limit | 50,000 | Maximum number of rows per data block. |  | 

{style="table-layout:auto"}


## Full table export

| Name | Type | Value | Description | In Product Description? |
|---|---|--:|---|:---:|
| Rows per report | Static | 3,000,000<br/>30,000,000<br/>150,000,000 | Maximum number of reporting rows per report delivered by Full Table Export. | |
| Breakdowns per table | Static | 5 | Maximum number of breakdowns per table | |
| Metrics per table | Static | 5 | Maximum number of metrics per table | |
| Schedule frequency | Static | 1 | Exports can be scheduled once (1) a day or on a longer schedule (for example: once every 2 days, or weekly) | | 

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

