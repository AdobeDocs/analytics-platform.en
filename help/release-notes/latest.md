---
title: Current Customer Journey Analytics release notes
description: View the latest Customer Journey Analytics release notes
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
---
# Current Customer Journey Analytics release notes (April 2026)

**Last update**: April 22 , 2026

These release notes cover the April 2026 release period. Adobe Customer Journey Analytics releases operate on a [continuous delivery model](releases.md), which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## New or updated features 

| Feature and description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| -----------|-----------|-----------|
| **MCP servers for Customer Journey Analytics** <br/>The Analytics MCP (Model Context Protocol) servers allow you to connect a supported MCP client to Adobe Customer Journey Analytics. Once connected, your MCP client can invoke product-specific tools to retrieve data, run queries, or perform supported operations as part of an LLM or agentic workflow. For more information, see [Analytics MCP servers](https://developer.adobe.com/analytics-mcp/docs/).<p>If you used these MCP servers during the beta period, please note that there are different URLs between beta and production endpoints. Ensure that any agentic workflows created during the beta period are updated to use the production endpoints before May 31.</p> | | May 5, 2026 |
| **Data Validation Agent** <br/>The Data Validation Agent uses agentic flows to answer simple prompts related to data validation and summarization, such as validating data in a dataset and summarizing dataset content. For complete documentation, see the data validation documentation in Adobe Experience Platform.<p>(Documentation link to follow.)</p> | | May 19, 2026 |
| **Data validation in the Adobe Engineering Agent** <br/>New data validation skills are available within the Data Engineering Agent. These skills help teams quickly assess data quality directly in Adobe Experience Platform, before the data is analyzed in Customer Journey Analytics. <p>Data validation skills enable on‑demand, field‑level, and dataset‑level validation, combining statistical summaries with intelligent detection of invalid or anomalous values. </p><p>Using data validation skills reduces manual QA effort and accelerates trusted data onboarding and transformations across data engineering workflows.</p><p>(Documentation link to follow.)<!--For more information, see [Data Engineering Agent]() (will be in this repo: https://experienceleague.adobe.com/en/docs/experience-cloud-ai/experience-cloud-ai/agents/cja-data-insights-agent).--></p> | | May 2026 <p>(Originally planned to release on March 31, 2026)</p> |
| **Attribution model API reporting guide** <br/>A new Adobe Analytics 2.0 API Attribution Model Report Guide is available. The guide covers how to include attribution model object data in Dimension API reports.<p>(Documentation link to follow.)</p> | | May 2026 |
| **Consolidate duplicate components in the Data Dictionary** <br/>The data dictionary now provides a streamlined process for identifying and consolidating duplicate components. Administrators can easily view which components have duplicate names or definitions, then consolidate those components into a single component. Any assets that reference a replaced duplicate are updated to reference the single consolidated component.<p>Previously, the data dictionary identified duplicate components, but the process of consolidating duplicates was manual.</p> | | May 2026 (at the earliest) |
| **Journey canvas in Adobe Analytics** <br/>Journey canvas is a visualization in Analysis Workspace that allows you to gain deep insights on a defined user journey by analyzing how people proceed through or fall out of the journey. It allows you to create a flexible graph of nodes and arrows representing any combination of events, dimension items, and segments included in the journey. Data updates as you drag nodes onto the canvas or rearrange the events and conditions of the journey.<p>Journey canvas was previously available only for Customer Journey Analytics.</p><p>To learn more about Journey canvas in Adobe Analytics, see Journey canvas overview.</p><p>To learn how to build a Journey canvas visualization in Adobe Analytics, see Configure Journey canvas.</p> | | End of May 2026 |
| **Content Analytics support for native mobile app experiences**<br/>Organizations can extend their content performance analysis to iOS and Android apps, capturing image assets and granular experience elements to understand which in-app content drives user engagement and business outcomes.<p>Insights are available for all Adobe Content Analytics customers.</p> | May 6, 2026 | TBD |
| **Streaming media services: Support schedule data** <br/>You can now upload schedule data of past live Streaming Media content to more easily and accurately track viewership.<p>The following are examples of live content that are supported with schedule data upload:</p><ul><li>FAST (Free Ad Supported TV) platforms</li><li>Local streams</li><li>Live sports</li></ul><p>Uploading schedule data allows you to track viewership data for individual programs that ran during the time you designate in the upload file. You can even gather viewership data for specific topics or program segments.</p><p>These capabilities are available regardless of how you implemented Streaming Media Collection.</p><p>Previously, it was difficult to accurately tie a given session to specific programs when analyzing live content, and it wasn't possible to tie a given session to individual topics or program segments.</p><p>For more information, see [Upload schedule data to track live content](https://experienceleague.adobe.com/en/docs/media-analytics/using/media-use-cases/track-schedule-data)</p>| October 29, 2025 | First half of 2026<p>(Originally planned to release on October 29, 2025)</p> |
| **CJA API Postman Collections** <br/>A downloadable Postman collection is available for calling CJA API endpoints.<p>For more information, see the [analytics-cja-postman-collections Github repository](https://github.com/AdobeDocs/analytics-cja-postman-collections).  </p> | | May 1, 2026 |
| **API Search and Sort** <br/>New search and sort capabilities are available for the Adobe Analytics 2.0 API. <p>For more information, see the Search and Sort guide. (Documentation link to follow.)</p> | | TBD |

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
* [Adobe Experience Cloud release notes](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)
* [Customer Journey Analytics documentation updates](/help/release-notes/doc-changes.md)
