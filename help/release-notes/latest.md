---
title: Current Customer Journey Analytics release notes
description: View the latest Customer Journey Analytics release notes
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
TQID: https://experienceleague.adobe.com/EQKhna8E33DddZQGWe3ASBKMY9r-UsfuUcJg7DMwH0w
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: ad333ea6-e90d-4c8f-8d61-9f8690784d6f
    internal-label: Templates, Templates (CJA)
  - id: ad5685a0-8296-4a0c-814c-658c10b4af12
    internal-label: Content Analytics
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
    internal-label: Metrics
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
    internal-label: Segments, Segments (CJA)
  - id: bcaa1b08-8269-4ff3-a0c2-f599783b6107
    internal-label: Filters
  - id: cc092ab1-90ba-4bbc-b4c6-6249d87daf5c
    internal-label: Audiences
  - id: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7
    internal-label: Connections
  - id: d3c978ee-1ff0-4475-968a-721e2dd99ef1
    internal-label: Freeform tables
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
    internal-label: Dimensions
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
    internal-label: Exports
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
---
# Current Customer Journey Analytics release notes (April 2026)

**Last update**: May 7, 2026

These release notes cover the April 2026 release period. Adobe Customer Journey Analytics releases operate on a [continuous delivery model](releases.md), which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## New or updated features 

| Feature and description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| -----------|-----------|-----------|
| **Italian language support**<br/>The Italian locale (it-IT) is now supported in Analysis Workspace in Customer Journey Analytics. <p>Customer Journey Analytics supports all languages that are supported in the Experience Platform UI, as described in [Browser and language support for the Experience Platform UI](https://experienceleague.adobe.com/en/docs/experience-platform/landing/platform-ui/browser-language-support#language-support).</p><p>You can [change your default language](https://experienceleague.adobe.com/en/docs/experience-platform/landing/platform-ui/browser-language-support#change-default-language) in Experience Platform.</p> | | April 8, 2026 |
| **Data validation in the Adobe Engineering Agent** <br/>New data validation skills are available within the Data Engineering Agent. These skills help teams quickly assess data quality directly in Adobe Experience Platform, before the data is analyzed in Customer Journey Analytics. <p>Data validation skills enable on‑demand, field‑level, and dataset‑level validation, combining statistical summaries with intelligent detection of invalid or anomalous values. </p><p>Using data validation skills reduces manual QA effort and accelerates trusted data onboarding and transformations across data engineering workflows.</p><p>(Documentation link to follow.)<!--For more information, see [Data Engineering Agent]() (will be in this repo: https://experienceleague.adobe.com/en/docs/experience-cloud-ai/experience-cloud-ai/agents/cja-data-insights-agent).--></p> | | May 2026 <p>(Originally planned to release on March 31, 2026)</p> |
| **MCP servers for Customer Journey Analytics** <br/>The Analytics MCP (Model Context Protocol) servers allow you to connect a supported MCP client to Adobe Customer Journey Analytics. Once connected, your MCP client can invoke product-specific tools to retrieve data, run queries, or perform supported operations as part of an LLM or agentic workflow. For more information, see [Analytics MCP servers](https://developer.adobe.com/analytics-mcp/docs/).<p>If you used these MCP servers during the beta period, please note that there are different URLs between beta and production endpoints. Ensure that any agentic workflows created during the beta period are updated to use the production endpoints before May 31.</p> | | May 5, 2026 |
| **Content Analytics support for native mobile app experiences**<br/>Organizations can extend their content performance analysis to iOS and Android apps, capturing image assets and granular experience elements to understand which in-app content drives user engagement and business outcomes. [Documentation](/help/content-analytics/content-analytics.md) is updated to describe the mobile channel capabilities and configuration. Information about the [Content Analytics Mobile SDK extension](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/) is available from [Adobe Developer](https://developer.adobe.com).<p>Insights are available for all Adobe Content Analytics customers.</p> | May 6, 2026 | May 6, 2026 |
| **Streaming media services: Support schedule data** <br/>You can now upload schedule data of past live Streaming Media content to more easily and accurately track viewership.<p>The following are examples of live content that are supported with schedule data upload:</p><ul><li>FAST (Free Ad Supported TV) platforms</li><li>Local streams</li><li>Live sports</li></ul><p>Uploading schedule data allows you to track viewership data for individual programs that ran during the time you designate in the upload file. You can even gather viewership data for specific topics or program segments.</p><p>These capabilities are available regardless of how you implemented Streaming Media Collection.</p><p>Previously, it was difficult to accurately tie a given session to specific programs when analyzing live content, and it wasn't possible to tie a given session to individual topics or program segments.</p><p>For more information, see [Upload schedule data to track live content](https://experienceleague.adobe.com/en/docs/media-analytics/using/media-use-cases/track-schedule-data)</p>| October 29, 2025 | First half of 2026<p>(Originally planned to release on October 29, 2025)</p> |
| **Multiple dimension API reporting**<br/>Report multiple dimensions in a single API request and perform dimension-level searches. [Learn more](https://developer.adobe.com/cja-apis/docs/endpoints/reporting/multidim) | | March 2026 |
| **Multi-column API sorting**<br/>Sort multiple dimension and metric objects in an API request. Mix dimensions and metrics in the same sort definition. [Learn more](https://developer.adobe.com/cja-apis/docs/endpoints/reporting/multidim#multi-column-sorting) | | March 2026 |

## Fixes in Customer Journey Analytics

**Analysis Workspace**: AN-442813, AN-442410, AN-442231, AN-441943, AN-441717, AN-434855, AN-429777, AN-429048, AN-428892, AN-428189, AN-425215
**Components**: 
**Connections**: AN-442824, AN-440937, AN-440092, AN-429781
**Content Analytics**:
**Guided analysis**: 
**Exports**: 
**Data views**: AN-442809, AN-434824, AN-434210, AN-424000
**Implementation**: 
**Report Builder**: AN-441136, AN-438147, AN-425150
**Reporting**: AN-443900, AN-441811, AN-441506, AN-440919, AN-440545, AN-440505, AN-440300
**Segmentation**: 
**Scheduled reports**: 
**Shared metrics and dimensions**: 
**Other**: AN-423359, AN-406242, AN-397985

## Related resources

* [Previous Customer Journey Analytics release notes for 2025](/help/release-notes/2025.md)
* [Adobe Analytics release notes](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html)
* [Streaming Media Collection release notes](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* [CX Enterprise release notes](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)
* [Customer Journey Analytics documentation updates](/help/release-notes/doc-changes.md)
