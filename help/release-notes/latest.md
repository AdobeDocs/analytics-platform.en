---
title: Current Customer Journey Analytics release notes
description: View the latest Customer Journey Analytics release notes
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
---
# Current Customer Journey Analytics release notes (April 2026)

**Last update**: April 8 , 2026

These release notes cover the April 2026 release period. Adobe Customer Journey Analytics releases operate on a [continuous delivery model](releases.md), which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## New or updated features 

| Feature and description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| -----------|-----------|-----------|
| **Italian language support**<br/>The Italian locale (it-IT) is now supported in Analysis Workspace in Customer Journey Analytics. <p>Customer Journey Analytics supports all languages that are supported in the Experience Platform UI, as described in [Browser and language support for the Experience Platform UI](https://experienceleague.adobe.com/en/docs/experience-platform/landing/platform-ui/browser-language-support#language-support).</p><p>You can [change your default language](https://experienceleague.adobe.com/en/docs/experience-platform/landing/platform-ui/browser-language-support#change-default-language) in Experience Platform.</p> | | April 8, 2026 |
| **Data validation in the Adobe Engineering Agent** <br/>New data validation skills are available within the Data Engineering Agent. These skills help teams quickly assess data quality directly in Adobe Experience Platform, before the data is analyzed in Customer Journey Analytics. <p>Data validation skills enable on‑demand, field‑level, and dataset‑level validation, combining statistical summaries with intelligent detection of invalid or anomalous values. </p><p>Using data validation skills reduces manual QA effort and accelerates trusted data onboarding and transformations across data engineering workflows.</p><p>(Documentation link to follow.)<!--For more information, see [Data Engineering Agent]() (will be in this repo: https://experienceleague.adobe.com/en/docs/experience-cloud-ai/experience-cloud-ai/agents/cja-data-insights-agent).--></p> | | End of April, 2026 <p>(Originally planned to release on March 31, 2026)</p> |
| **MCP servers for Customer Journey Analytics** <br/>You can now tie Customer Journey Analytics into your existing agentic workflows using MCP (Model Context Protocol). You can request reports and insights using natural language. | | End of April 2026 |
| **Streaming media services: Support schedule data** <br/>You can now upload schedule data of past live Streaming Media content to more easily and accurately track viewership.<p>The following are examples of live content that are supported with schedule data upload:</p><ul><li>FAST (Free Ad Supported TV) platforms</li><li>Local streams</li><li>Live sports</li></ul><p>Uploading schedule data allows you to track viewership data for individual programs that ran during the time you designate in the upload file. You can even gather viewership data for specific topics or program segments.</p><p>These capabilities are available regardless of how you implemented Streaming Media Collection.</p><p>Previously, it was difficult to accurately tie a given session to specific programs when analyzing live content, and it wasn't possible to tie a given session to individual topics or program segments.</p><p>For more information, see [Upload schedule data to track live content](https://experienceleague.adobe.com/en/docs/media-analytics/using/media-use-cases/track-schedule-data)</p>| October 29, 2025 | First half of 2026<p>(Originally planned to release on October 29, 2025)</p> |
| **Multiple dimension API reporting**<br/>Report multiple dimensions in a single API request and perform dimension-level searches. [Learn more](https://developer.adobe.com/cja-apis/docs/endpoints/reporting/multidim) | | March 2026 |
| **Multi-column API sorting**<br/>Sort multiple dimension and metric objects in an API request. Mix dimensions and metrics in the same sort definition. [Learn more](https://developer.adobe.com/cja-apis/docs/endpoints/reporting/multidim#multi-column-sorting) | | March 2026 |

## Fixes in Customer Journey Analytics

**Analysis Workspace**: AN-440336, AN-440216, AN-438445, AN-438216, AN-437856, AN-437776, AN-437765, AN-437365, AN-432793, AN-432094, AN-431557, AN-431200, AN-429621, AN-429424, AN-427973, AN-426089, AN-425883, AN-424359
**Components**: 
**Content Analytics**:
**Guided analysis**: 
**Exports**: AN-432030
**Data views**: AN-440004, AN-437154, AN-431165
**Implementation**: 
**Report Builder**: AN-437895, AN-437083, AN-434288, AN-434209, AN-433224, AN-430622
**Reporting**: AN-439482, AN-439545, AN-438708, AN-431206, AN-430079, AN-428302, AN-428257, AN-425779, AN-423330
**Segmentation**: 
**Scheduled reports**: 
**Shared metrics and dimensions**: 
**Other**: AN-439795, AN-434783, AN-434233, AN-434005, AN-433368, AN-431322, AN-431165, AN-431012, AN-429983, AN-429067, AN-423285


## Important notices for Customer Journey Analytics Administrators

| Notice | Notice added or updated | Description |
| --- | --- | --- |
| **TLS 1.2 cipher suites removal** | February 11, 2026 | Notice to admins: Adobe plans to remove support for the following TLS 1.2 cipher suites from Adobe data collection servers on May 27, 2026.<ul><li>`TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_256_CBC_SHA`</li></ul><p>No customer action is required for most implementations. This change primarily affects Analytics data sent from legacy native applications that use outdated TLS libraries, and a small number of web visitors on obsolete browsers or operating systems. Removing support for these cipher suites enhances security and aligns Adobe with modern encryption standards. Less than 0.1% of data collection traffic currently relies on these cipher suites.</p> |

## Related resources

* [Previous Customer Journey Analytics release notes for 2025](/help/release-notes/2025.md)
* [Adobe Analytics release notes](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html)
* [Streaming Media Collection release notes](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* [Adobe Experience Cloud release notes](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)
* [Customer Journey Analytics documentation updates](/help/release-notes/doc-changes.md)
