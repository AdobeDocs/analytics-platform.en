---
title: Customer Journey Analytics Product Comparison
description: Compare Customer attributes of Journey Analytics reporting and export tools, such as Analysis Workspace, Report Builder, Full Table Export, Data Feeds, APIs, and MCP.
keywords: clickstream;data feed;datafeed;product comparison;Analysis Workspace;Report Builder;Full Table Export
feature: Components
hold: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
    internal-label: Exports
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
---

# Analytics product comparison

Use this page to compare Customer Journey Analytics reporting and export tools on key attributes to help you choose the right tool for your analysis or data export needs.

| Product name and help Link | [Analysis Workspace](/help/analysis-workspace/home.md) | [Report Builder](/help/report-builder/rb-overview.md) | [Full Table Export](/help/analysis-workspace/export/export-cloud.md) | [Data Feeds](/help/components/exports/cja-data-feeds/data-feed-overview.md) | [APIs](https://developer.adobe.com/cja-apis/docs/) | MCP | BI extension | Coworker |
|---|---|---|---|---|---|---|---|---|
| **Access method** | Browser | Microsoft Excel | Browser | Setup through browser | RESTful API tools | MCP-compatible tools | BI tools | MCP-compatible tools |
| **Data granularity** | Aggregated | Aggregated | Aggregated | Event | Aggregated | Aggregated | Aggregated | Aggregated |
| **Experience Cloud ID (ECID) available** | No | No | No | Yes | No | No | No | No |
| **Timestamp available** | No | No | No | Yes | No | No | No | No |
| **Level of processing** | Fully-processed | Fully-processed, with seprate real-time report | Fully-processed | Fully-processed| Fully-processed | Fully-processed | Fully-processed | Fully-processed |
| **Where bot filtering is applied** | Within the [Datastream](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/bot-detection) and/or within [CJA](/help/data-views/derived-fields/derived-fields.md#simple-bot-detection) | Within the [Datastream](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/bot-detection) and/or within [CJA](/help/data-views/derived-fields/derived-fields.md#simple-bot-detection) | Within the [Datastream](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/bot-detection) and/or within [CJA](/help/data-views/derived-fields/derived-fields.md#simple-bot-detection) | Within the [Datastream](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/bot-detection) and/or within [CJA](/help/data-views/derived-fields/derived-fields.md#simple-bot-detection) |  |  | Within the [Datastream](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/bot-detection) and/or within [CJA](/help/data-views/derived-fields/derived-fields.md#simple-bot-detection)| |
| **Visible row limit (before pagination)** | 400 | 50,000 | Limit of 3 million, 30 million, 150 million, or 300 million, depending on tier  | Dependent on tier | 50,000 | 50,000 | 50,000 | 50,000 |
| **Multiple data views** | Yes, a project can contain data from multiple data views | Yes, a project can contain data from multiple data views | No, an export can contain data from only one data view | No, an export can contain data from only one data view | No, each query can reference only one data view | No, each query can reference only one data view | No, each query can reference only one data view | Yes, if prompted by the user |
| **Number of dimension columns** | Up to 5 | ? | Up to 10 | Unlimited | Up to 5 | ? | ? | ? |
| **Number of metric columns** | ? | ? | Up to 10 | Unlimited | ? | ? | ? | ? |
| **Segmentation** <br> [Learn more](/help/components/segments/seg-overview.md) | Yes | Yes | Yes | Yes, with [limitations](/help/components/exports/cja-data-feeds/df-segmentation.md) | Yes | Yes | Yes | Yes |
| **Calculated metrics** <br> [Learn more](/help/components/calc-metrics/calc-metr-overview.md) | Yes | Yes | Yes, with [limitations](/help/analysis-workspace/export/export-cloud.md#calculated-metric-functions-support) | No | Yes | Yes | Yes | Yes |
| **Derived fields** <br> [Learn more](/help/data-views/derived-fields/derived-fields.md) | Yes | Yes | Yes | Yes | Yes | Yes | Yes| Yes |
| **Attribution** <br> [Learn more](/help/analysis-workspace/attribution/overview.md) | Yes | Limited | Yes, with [limitations](/help/analysis-workspace/export/export-cloud.md#attribution-behavior) | No | Yes | Yes | Yes | Yes |
| **Scheduled delivery** | Yes | Yes | Yes | Yes | — | — | — | — |
| **Delivery destinations** | Email | Email | Amazon S3, Azure RBAC, Azure SAS, GCP | Amazon S3, Azure RBAC, Azure SAS, GCP | — | — | — | — |

{style="table-layout:auto"}
