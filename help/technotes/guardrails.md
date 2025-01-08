---
title: Customer Journey Analytics Guardrails
description: Learn about the Guardrails for Customer Journey Analytics
solution: Customer Journey Analytics
feature: Administration
role: Admin
exl-id: f093ac54-7d31-449b-a441-a65856a1d535
---
# Customer Journey Analytics Guardrails

This document provides limits for various components of Customer Journey Analytics. For Guardrails, Scoping Parameters, and Entitlements, see the [Product Description for Customer Journey Analytics](https://helpx.adobe.com/legal/product-descriptions/customer-journey-analytics.html) or the [Product Description for Adobe Analytics Add-on: Customer Journey Analytics](https://helpx.adobe.com/legal/product-descriptions/adobe-analytics-addon-customer-journey-analytics.html).

## Limit types

There are two types of default limits within this document: 

| Guardrail type | Description|
|----------|---------|
| **Performance Guardrails (soft limit)** | Performance Guardrails are usage limits that relate to the scoping of your use cases. When exceeding performance Guardrails, you may experience performance degradation and latency. Adobe is not responsible for such performance degradation. Customers who consistently exceed a performance Guardrail  may elect to license additional capacity to avoid performance degradation.|
| **System-enforced Guardrails (hard limit)** | System-enforced Guardrails are enforced by the Customer Journey Analytics UI or API. These are limits that you cannot exceed as the UI and API block you from doing so or return an error.|

{style="table-layout:auto"}

Some of the features and their associated value for the limit depend on the Customer Journey Analytics Package you are entitled to. 

>[!NOTE]
>
>The values outlined in this document are subject to change based on continuing improvements in the product. Check back regularly for updates. If you are interested in learning about custom limits, contact your customer care representative. 

## Ad-hoc SQL queries

| Name | Value | Limit Type | Description |
|---|--:|---|---|
| Try Again Timeout | 90 | System-enforced Guardrail  | Maximum number of seconds before reporting engine responds back that the request takes too long to return results (possibly due to other simultaneous other requests); it is possible to request again. |
| Don't Try Again Timeout | 600 | System-enforced Guardrail  | Maximum number of seconds before Ad Hoc SQL queries time-out. Otherwise stated, the maximum number of seconds before reporting engines reports back that the request has taken too long to return results, and should not be tried again. The request most likely never returns results due to issues in the background process. |
| Metrics | 150 |System-enforced Guardrail  |  Maximum number of metrics in a request. |
| Interactive Query Output Rows | 50,000 | System-enforced Guardrail  | Default number of rows returned unless specified otherwise. | 

{style="table-layout:auto"}

## Analysis Workspace projects

| Name | Value | Limit Type | Description | 
|---|--:|---|---|
| Visible Rows per Table | 400 | System-enforced Guardrail  |  Maximum number of visible rows in any freeform table in an Analysis Workspace project. | 
| Exportable Rows per Table | 50,000 | System-enforced Guardrail  |  Maximum number of rows that can be exported per single dimension. |
| Panels per Project | 15 | System-enforced Guardrail  | Maximum number of [panels](../analysis-workspace/home.md#panels) per project. |
| Visualizations per Panel | 25 | System-enforced Guardrail  |  Maximum number of [visualizations](../analysis-workspace/home.md#visualizations) per panel. |
| Derived Fields per Freeform Table | 5 | System-enforced Guardrail | Maximum number of different derived fields in a single freeform table. |

{style="table-layout:auto"}

<!--
## Attribution AI

| Name |  Value | Description | PD? |
|---|--:|---|:---:|
| Attribution AI models | 35 | Maximum number of Attribution AI Model per year to analyze the impact of up to an average of 60 independent touchpoints on a specified conversion event.  | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  | 
| Region based iterations | 10 | Maximum number of region-based iterations of each Attribution AI model. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  | 
| Export Insights batches | 12 | Maximum number of export batches times the number of authorized Attribution AI Insights per year. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) | 

{style="table-layout:auto"}
-->

## Audiences

| Name | Value | Limit Type | Description | 
|---|--:|---|---|
| Audience Filters | 20 | System-enforced Guardrail  | Maximum number of [filters](../components/filters/filters-overview.md) per audience. | 
| Number of Audience Identities | 20 million | System-enforced Guardrail  | Maximum number of identities per audience. | 
| Audience Refresh Frequency | 4 | System-enforced Guardrail  | Maximum frequency in hours an [audience](../components/audiences/audiences-overview.md) may be refreshed. |
| Audience Refresh Lookback Window | 90 | System-enforced Guardrail  | Maximum number of days for refresh lookback window. | 
| Refreshing Audience Expiration Date | 13 | System-enforced Guardrail  | Maximum number of months audience ceases to refresh from the date of creation. Customers can extend this for an additional 13 months. | 
| Number of Refreshing Audiences | 75, 150 | System-enforced Guardrail  | Maximum number of refreshing audiences. Value varies depending on the Customer Journey Analytics package (see Product Description). | 

{style="table-layout:auto"}

See also Experience Platform [Real-time Customer Data Platform Guardrails](https://experienceleague.adobe.com/docs/experience-platform/profile/guardrails.html).


## Automated dataset expiration

| Name |  Value | Limit Type | Description | 
|---|--:|---|:---:|
| Work Orders | 20 | System-enforced Guardrail  | Maximum number of automated dataset expiration work orders per month. | 

{style="table-layout:auto"}



## Connections, Data views, Projects

| Name |  Value | Limit Type | Description | 
|---|--:|---|---|
| Projects | 50,000 | System-enforced Guardrail  | Maximum number of projects for an organization. |
| Data Views | 2,000 |System-enforced Guardrail  |  Maximum number of [data views](../data-views/data-views.md) for an organization. |
| Data Views | 500-1000 | System-enforced Guardrail  | Maximum number of data views for a connection. Value varies depending on the Customer Journey Analytics package (see Product Description). |
| Datasets | 100 | System-enforced Guardrail  | Maximum number of [datasets](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/overview.html) per connection. |
| Connections | 1000 | System-enforced Guardrail  | Maximum number of [connections](../connections/overview.md) for an organization. |
| Connection Title | 500 | System-enforced Guardrail |Maximum number of characters for a connection title. |
| Metrics | 5,000 | System-enforced Guardrail  | Maximum number of metrics in a data view. |
| Dimensions | 5,000 | System-enforced Guardrail  | Maximum number of dimensions in a data view. | 
| Annotation Title | 100 | System-enforced Guardrail  | Maximum number of characters for an annotation title. |
| Annotation Description | 250 | System-enforced Guardrail  | Maximum number of characters for an annotation description. |
| Schema Fields | 10 | System-enforced Guardrail  | Maximum number of schema fields (not including standard fields) when defining rules for a [derived field](../data-views/derived-fields/derived-fields.md). |
| Lookup / Profile Fields | 3 | System-enforced Guardrail  |  Maximum number of lookup or profile schema fields within the maximum number of schema fields (not including standard fields) when defining rules for a derived field. |
| Derived Fields | 100 - 500 | System-enforced Guardrail  | Maximum number of derived fields per connection. Value varies depending on the Customer Journey Analytics package (see Product Description). |

{style="table-layout:auto"}


## Data transfer limits

| Name |  Value | Limit Type | Description | 
|---|--:|---|---|
| Fields | 10,000 | System-enforced Guardrail  | Maximum number of properties or fields per row in a dataset. | 
| Unique Strings | 10 million | System-enforced Guardrail  | Maximum number of unique keys per lookup dataset. | 
| Rows | 1 million | System-enforced Guardrail  | Maximum number of rows per unique person ID in a given month within a connection. | 
| Row Size | 2 | Performance Guardrail / System-enforced Guardrail | Average size in kilobytes per row of data ingested into Customer Journey Analytics (soft limit). A static limit for row size is determined by Guardrails for data ingestion in Experience Platform. | 

{style="table-layout:auto"}

See also Experience Platform [Guardrails for Data Ingestion](https://experienceleague.adobe.com/docs/experience-platform/ingestion/guardrails.html).


## Destinations Data Export

| Name | Value | Limit Type | Description |
|---|--:|---|---|
| Data Export | Total Authorized Data Lake Storage | Performance Guardrail | Customer may use Destination Dataset Export to export Customer Data in the Data Lake up to the Total Authorized Data Lake Storage.|
| Available Datasets | Profile and Event | System Enforced Guardrail | Event, Profile or Lookup datasets created in the Experience Platform UI after ingesting or collecting data through Sources, Web SDK, Mobile SDK, Analytics Data Connector, and Audience Manager. |

{style="table-layout:auto"}

See also Experience Platform [Dataset Export Guardrails](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/guardrails#dataset-exports)


## Data landing zone

| Name | Value | Limit Type | Description |
|---|--:|---|---|
| Data Landing Zone per Sandbox | 1 | System-enforced Guardrail  | Maximum number of data landing zones per sandbox. |
| Data Storage| 7| System-enforced Guardrail  |  Maximum number of days data is stored at data landing zone before being deleted. | 

{style="table-layout:auto"}


## Field-based stitching

| Name |  Value | Limit Type | Description |
|---|--:|---|---|
| Stitched Datasets | 5 - 50 | System-enforced Guardrail  | Maximum number of stitched datasets per customer. Value varies depending on the Customer Journey Analytics package (see Product Description). | 
| Backfill Length | 6 - 25 | System-enforced Guardrail  | Maximum number of months of backfill data. Value varies depending on the Customer Journey Analytics package (see Product Description). |
| Lookback Window / Replay Frequency | 1/1 - 30/7 | System-enforced Guardrail | Maximum lookback window in days / Replay frequency. Value varies depending on the Customer Journey Analytics package (see Product Description). |

{style="table-layout:auto"}


## Graph-based stitching 

| Name |  Value | Limit Type | Description |
|---|--:|---|---|
| Stitched Datasets | 10 - 50 | System-enforced Guardrail  | Maximum number of stitched datasets per customer. Value varies depending on the Customer Journey Analytics package (see Product Description). | 
| Backfill Length | 13 - 25 | System-enforced Guardrail  | Maximum number of months of backfill data. Value varies depending on the Customer Journey Analytics package (see Product Description). |
| Lookback Window / Replay Frequency | 1/1 - 30/7 | System-enforced Guardrail | Maximum lookback window in days / Replay frequency. Value varies depending on the Customer Journey Analytics package (see Product Description). |


## Filters and calculated metrics 

| Name |  Value | Limit Type | Description | 
|---|--:|---|---|
| Containers per Filter | 50 | System-enforced Guardrail  | Maximum number of containers per filter. | 
| Metrics per Calculated Metric | 25 | System-enforced Guardrail  | Maximum number of metrics per calculated metric. |
| Metrics and Dimensions per Filter | 25 |System-enforced Guardrail  |  Maximum number of unique metrics and dimensions per filter. | 
| Nested Containers per Filter | 10 | System-enforced Guardrail  | Maximum number of nested containers per filter. |
| Rules per filter| 100 | System-enforced Guardrail  | Maximum number of rules per filter. |
| String Compares per Dimension per Filter | 100 |  System-enforced Guardrail  | Maximum number of strings comparisons per dimension per filter. | 
| Calculated Metrics | 6,000 | System-enforced Guardrail  |  Maximum number of calculated metrics for an organization. |
| Filters | 50,000 | System-enforced Guardrail | Maximum number of filters you can define for an organization. |
| API Calls | 120 | System-enforced Guardrail | API requests per minute (12 requests every 6 seconds). |

{style="table-layout:auto"}


## Mobile application

| Name |  Value | Limit Type | Description |
|---|--:|---|---|
| Tiles | 16 | System-enforced Guardrail  | Maximum number of tiles per scorecard. |
| Filters | 10 | System-enforced Guardrail  | Maximum number of filters per scorecard. | 
| Dimensions | 10 | System-enforced Guardrail  | Maximum number of dimensions per scorecard. |

{style="table-layout:auto"}

## Report Builder

| Name | Value | Limit Type | Description |
|---|--:|---|---|
| Workbook File Size | 5 | System-enforced Guardrail  | Maximum file size in MB of a scheduled workbook. |
| Data Blocks | 1000 | System-enforced Guardrail  | Maximum number of [data blocks](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/manage-reportbuilder.html) per workbook. | 
| Metrics | 20 | System-enforced Guardrail  | Maximum number of metrics per data block. | 
| Date Range Span | 13 | System-enforced Guardrail  | Maximum number of months a date range can span per data block. | 
| Rows | 50,000 | System-enforced Guardrail  | Maximum number of rows per data block. | 

{style="table-layout:auto"}


## Full table export

| Name |  Value | Limit Type | Description | 
|---|--:|---|---|
| Rows per Report |  3 million - 300 million | System-enforced Guardrail  | Maximum number of reporting rows per report. Value varies depending on the Customer Journey Analytics package (see Product Description). |
| Breakdowns per Table |  5 | System-enforced Guardrail  | Maximum number of breakdowns per table. |
| Metrics per Table |  5 | System-enforced Guardrail  | Maximum number of metrics per table. |
| Schedule Frequency |  1 | System-enforced Guardrail  | Exports can be scheduled once (1) a day or on a longer schedule (for example: once every 2 days, or weekly). |

{style="table-layout:auto"}

## Latencies

>[!NOTE]
>
>Processing times below are Guardrails, not contractual service level agreements (SLAs). Latency varies depending on customer configuration, data volumes, and consumer applications. Real processing times are often faster. Refer to your Customer Journey Analytics contract for your specific contractual terms and SLAs. See Experience Platform [Guardrails for Data Ingestion](https://experienceleague.adobe.com/docs/experience-platform/ingestion/guardrails.html) for more information.

| Data flow | Expected latency |
|---|---|
| Adobe Analytics to Adobe Analytics Source Connector (A4T enabled) | < 30 minutes |
| Adobe Analytics Source Connector to Real-time Customer Profile (A4T not enabled) | < 2 minutes |
| Adobe Analytics Source Connector to Real-time Customer Profile (A4T enabled) | < 30 minutes |
| Data Ingestion into Data Lake from Edge Network or Streaming Ingestion | < 60 minutes |
| Data Ingestion into Data Lake from Adobe Analytics Source Connector | < 2.25 hours |
| Data Ingestion into Customer Journey Analytics from Data Lake | < 90 minutes |
| Stitching (optional feature; see [Stitching overview](../stitching/overview.md) for more information) | < 3.25 hours | 
| Adobe Analytics Source Connector Backfill of less than 10 billion events (maximum of 13 months of historical data) | < 4 weeks |
| Audience Publishing to Real-time Customer Profile, including automatic creation of the streaming segment, and allowing the segment to be ready to receive the data. | ≈ 60 minutes |
| Refresh Frequency for Audiences | One-time refresh: latency of less than 5 minutes.<br/>Refresh every 4 hours, daily, weekly, monthly (latency goes hand in hand with the refresh rate). |

{style="table-layout:auto"}
