---
title: Current Customer Journey Analytics release notes
description: View the latest Customer Journey Analytics release notes
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
---
# Current Customer Journey Analytics release notes (May 2026)

**Last update**: May 13 , 2026

These release notes cover the May 2026 release period. Adobe Customer Journey Analytics releases operate on a [continuous delivery model](releases.md), which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## New or updated features 

| Feature and description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| -----------|-----------|-----------|
| **CJA API Postman Collections** <br/>A downloadable Postman collection is available for calling CJA API endpoints.<p>For more information, see the [analytics-cja-postman-collections Github repository](https://github.com/AdobeDocs/analytics-cja-postman-collections).  </p> | | May 1, 2026 |
| **MCP servers for Customer Journey Analytics** <br/>The Analytics MCP (Model Context Protocol) servers allow you to connect a supported MCP client to Adobe Customer Journey Analytics. Once connected, your MCP client can invoke product-specific tools to retrieve data, run queries, or perform supported operations as part of an LLM or agentic workflow. For more information, see [Analytics MCP servers](https://developer.adobe.com/analytics-mcp/docs/).<p>If you used these MCP servers during the beta period, please note that there are different URLs between beta and production endpoints. Ensure that any agentic workflows created during the beta period are updated to use the production endpoints before May 31.</p> | | May 5, 2026 |
| **Content Analytics support for native mobile app experiences**<br/>Organizations can extend their content performance analysis to iOS and Android apps, capturing image assets and granular experience elements to understand which in-app content drives user engagement and business outcomes.<p> [Documentation](/help/content-analytics/content-analytics.md) is updated to describe the mobile channel capabilities and configuration. Information about the [Content Analytics Mobile SDK extension](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/) is available on [Adobe Developer](https://developer.adobe.com/).</p><p>Insights are available for all Adobe Content Analytics customers.</p> | | May 6, 2026 |
| **Data validation in the Adobe Engineering Agent** <br/>New data validation skills are available within the Data Engineering Agent. These skills help teams quickly assess data quality directly in Adobe Experience Platform, before the data is analyzed in Customer Journey Analytics. <p>Data validation skills enable on‑demand, field‑level, and dataset‑level validation, combining statistical summaries with intelligent detection of invalid or anomalous values. </p><p>Using data validation skills reduces manual QA effort and accelerates trusted data onboarding and transformations across data engineering workflows.</p><p>(Documentation link to follow.)<!--For more information, see [Data Engineering Agent]() (will be in this repo: https://experienceleague.adobe.com/en/docs/experience-cloud-ai/experience-cloud-ai/agents/cja-data-insights-agent).--></p> | | May 19, 2026 <p>(Originally planned to release on March 31, 2026)</p> |
| **Content Analytics: Line visualization thumbnails and previews** <br/>[Thumbnails and previews](/help/content-analytics/report/report.md) are now available for assets and experiences in line visualizations for Content Analytics. |  | May 20, 2026 |
| **Data Insights Agent on Agent Orchestrator** <br/> In addition to being available in the right rail in Customer Journey Analytics, Data Insights Agent is now available as part of Agent Orchestrator. This means that you can now get insights that rely on Customer Journey Analytics data and capabilities while you're working in other Experience Platform apps, such as within Journey Optimizer.<p>In Customer Journey Analytics, Data Insights Agent includes the following enhancements:</p><ul><li>A more consistent user experience with Agent Orchestrator</li><li>Explanatory summary paragraphs</li><li>Answers to "why" questions through root cause analysis</li><li>In-line tables</li><li>And much more!</l></ul><p>(Documentation link to follow.)</p> | | End of May 2026 |
| **Streaming media services: Support schedule data** <br/>You can now upload schedule data of past live Streaming Media content to more easily and accurately track viewership.<p>The following are examples of live content that are supported with schedule data upload:</p><ul><li>FAST (Free Ad Supported TV) platforms</li><li>Local streams</li><li>Live sports</li></ul><p>Uploading schedule data allows you to track viewership data for individual programs that ran during the time you designate in the upload file. You can even gather viewership data for specific topics or program segments.</p><p>These capabilities are available regardless of how you implemented Streaming Media Collection.</p><p>Previously, it was difficult to accurately tie a given session to specific programs when analyzing live content, and it wasn't possible to tie a given session to individual topics or program segments.</p><p>For more information, see [Upload schedule data to track live content](https://experienceleague.adobe.com/en/docs/media-analytics/using/media-use-cases/track-schedule-data)</p>| October 29, 2025 | First half of 2026<p>(Originally planned to release on October 29, 2025)</p> |

{style="table-layout:auto"}


## Fixes in Customer Journey Analytics

**Analysis Workspace**: AN-446522, AN-445779, AN-445759, AN-444676, AN-442813, AN-441943, AN-441717, AN-441538, AN-441123, AN-440976, AN-440952, AN-440919, AN-439797, AN-434855, AN-429777, AN-429048, AN-428892, AN-428189, AN-425215
**Components**: 
**Connections**: AN-449652, AN-444560, AN-442824, AN-440937, AN-440092, AN-439823, AN-429781
**Content Analytics**:
**Guided analysis**: 
**Exports**: AN-438953, AN-437115
**Data views**: AN-442809
**Implementation**: 
**Report Builder**: AN-448697, AN-447128, AN-441148, AN-441136, AN-438147, AN-425150
**Reporting**: AN-445123, AN-442231, AN-442169, AN-441811, AN-441733, AN-440505, AN-440300, AN-434824, AN-434210, AN-424000, AN-423359, AN-406242
**Segmentation**: 
**Scheduled reports**: 
**Shared metrics and dimensions**: 
**Other**: AN-449159, AN-444661, AN-443900, AN-397985

## Related resources

* [Previous Customer Journey Analytics release notes for 2025](/help/release-notes/2025.md)
* [Adobe Analytics release notes](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html)
* [Streaming Media Collection release notes](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* [Adobe Experience Cloud release notes](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)
* [Customer Journey Analytics documentation updates](/help/release-notes/doc-changes.md)
