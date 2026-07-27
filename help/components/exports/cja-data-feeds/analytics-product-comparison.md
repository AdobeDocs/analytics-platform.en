---
title: Customer Journey Analytics Product Comparison
description: Compare Customer attributes of Journey Analytics reporting and export tools, such as Analysis Workspace, Report Builder, Full Table Export, Data Feeds, APIs, and MCP.
keywords: clickstream;data feed;datafeed;product comparison;Analysis Workspace;Report Builder;Full Table Export
feature: Components
hide: true
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

{{release-limited-testing}}

Use this page to compare Customer Journey Analytics reporting and export tools on key attributes to help you choose the right tool for your analysis or data export needs.

| Product name and help Link | [Analysis Workspace](/help/analysis-workspace/home.md) | [Report Builder](/help/report-builder/rb-overview.md) | [Full Table Export](/help/analysis-workspace/export/export-cloud.md) | [Data Feeds](/help/components/exports/cja-data-feeds/data-feed-overview.md) | [APIs](https://developer.adobe.com/cja-apis/docs/) | MCP |
|---|---|---|---|---|---|---|
| **Access method** | Browser | Microsoft Excel | Browser | Setup through browser | RESTful API tools | MCP-compatible tools |
| **Data granularity** | Aggregated | Aggregated | Aggregated | Event | Aggregated | Aggregated |
| **Experience Cloud ID (ECID) available** | No | No | Yes | Yes | No | No |
| **Timestamp available** | No | No | No | Yes | No | No |
| **Level of processing** | Fully-processed | Fully-processed | Fully-processed | Fully-processed | Fully-processed | Fully-processed |
| **Bot filter data included** | No | No | No | No | No | No |
| **Low traffic (Uniques exceeded) appears** <br> [Learn more](/help/components/dimensions/high-cardinality.md) | Yes | Yes | No | No | Yes | Yes |
| **Visible row limit (before pagination)** | 400 | 50,000 | Unlimited | Unlimited | 50,000 | 50,000 |
| **Multiple data views** | Yes | Yes | No | Yes | Yes | Yes |
| **Number of breakdowns** | Unlimited | Up to 2 | Unlimited | Unlimited | Unlimited, run across multiple queries | Unlimited |
| **Segmentation** <br> [Learn more](/help/components/segments/seg-overview.md) | Yes | Yes | Yes | Yes, with [limitations](/help/components/exports/cja-data-feeds/df-segmentation.md) | Yes | Yes |
| **Calculated metrics** <br> [Learn more](/help/components/calc-metrics/calc-metr-overview.md) | Yes, with [Attribution](/help/analysis-workspace/attribution/overview.md) | Yes, with Attribution | No | No | Yes, with Attribution | Yes, with Attribution |
| **Derived fields** <br> [Learn more](/help/data-views/derived-fields/derived-fields.md) | Yes | Yes | Yes | Yes | Yes | Yes |
| **Cohort analysis** | [Yes](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | No | No | No | No | No |
| **Attribution** <br> [Learn more](/help/analysis-workspace/attribution/overview.md) | Yes | Limited | No | No | Yes | Yes |
| **Curation** <br> [Learn more](/help/analysis-workspace/curate-share/curate.md) | Yes – Project and Data view | No | No | No | Yes – Data view only | Yes – Data view only |
| **Project sharing** <br> [Learn more](/help/analysis-workspace/curate-share/share-projects.md) | Yes, with project roles | No | No | No | No | No |
| **Scheduled delivery** | Yes | Yes | Yes | Yes | No | No |
| **Delivery destinations** | Email | Email | Amazon S3, Azure RBAC, Azure SAS, GCP | Amazon S3, Azure RBAC, Azure SAS, GCP | — | — |
| **Data view report-time processing** <br> [Learn more](/help/data-views/data-views.md) | Yes | Yes | No | No | Yes | Yes |

{style="table-layout:auto"}
