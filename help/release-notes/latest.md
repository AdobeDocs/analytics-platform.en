---
title: Current Customer Journey Analytics Release Notes
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
# Current Customer Journey Analytics release notes (September 2026)

**Last update**: September 9, 2026

These release notes cover the September 2026 release period. Adobe Customer Journey Analytics releases operate on a [continuous delivery model](releases.md), which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## New or updated features

| Feature and description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| -----------|-----------|-----------|
| **Customer Journey Analytics MCP server plugin**<br/>Use new Customer Journey Analytics MCP server plugins for ChatGPT and Claude to quickly access your data. <p>For more information, see the [ChatGPT plugin guide](https://developer.adobe.com/analytics-mcp/docs/guides/chatgpt) and the [Claude connector guide](https://developer.adobe.com/analytics-mcp/docs/guides/claude).</p> | September 1, 2026 | September 1, 2026 |
| **Support for additional data usage labels**<br>Customer Journey Analytics now supports the following additional data usage labels for elements within a dataset:<ul><li>C2 – Restrict third-party data export (available now)</li><li>C3 – Restrict directly identifiable data combination (available now)</li><li>C9 – Restrict data science (planned to release in August or September)</li></ul><p>For more information, see [Labels, policies, and marketing actions](/help/data-views/data-governance.md).</p> | | September 3, 2026|
| **Consent policy filtering and reporting**<br>You can now report on which visitors match your Adobe Experience Platform consent policies. (Consent policy dimensions and metrics are added to the data views in your connection.)<p>Additionally, you can exclude non-consenting visitors before their data is ingested into Customer Journey Analytics.</p><p>For more information, see [Consent reporting and filtering overview](/help/connections/consent-reporting-filtering/consent-overview.md).</p> | | September 2026 |
| **Limit segments to the reporting date range**<br/>Data in a Workspace report can extend beyond the reporting date range when a segment includes date range components.<p>A new option is now available that allows you to limit results to the reporting date range regardless of any date components included in the segment.</p><p>This option is available when creating or modifying a segment whose top-level container is Person.</p><p>For more information, see [Build segments](/help/components/segments/seg-builder.md#components).</p> | August 26, 2026 | September 9, 2026 |
| **Analyze LLM customer experiences in Analysis Workspace with Conversation Insights**<br/>Customer Journey Analytics now brings unstructured chat data into Analysis Workspace, allowing you to report on LLM-powered browsing and buying experiences that occur across your properties.<p>With this capability, you can:</p><ul><li>Collect prompts, responses, and agent metadata from conversational agents (either your organization's custom agents or Adobe Brand Concierge) via Web SDK.</li><li>Analyze intent, tone, and sentiment so you can understand what customers are asking, how your agent responds, and how your customers feel about their interactions.</li><li>Analyze at scale using your existing schema, datasets, and data views, then surface insights in Analysis Workspace.</li><li>Connect conversations to outcomes by tying agent interactions to your broader customer journeys, so you can measure real impact on conversion, engagement, and more.</li></ul><p>Previously, LLM-powered experiences were difficult to measure and nearly impossible to connect to your existing customer journeys.</p><p>(Documentation link to follow.)</p> | | September 22, 2026 |
| **Total population reporting**<br/>You can now analyze and report on entities defined in profile and lookup datasets that exist in a Customer Journey Analytics connection. That analysis and reporting go beyond time-based series of events from event datasets. <p>This ability enables new classes of queries, metrics, and audience definitions that reflect the full scope of a business's customer base.</p><p>(Documentation link to follow.)</p> | | September 22, 2026 |
| **Hourly alerts**<br/>You can now set an alert's time granularity to Hourly.<p>Hourly alerts are intended for data that arrives within a given hour. If data has a latency longer than an hour, a longer granularity ensures that the alert evaluates complete data. Check with a data engineer if you're unsure how long data takes to arrive.</p>p>(Documentation link to follow.)</p> | | September 2026 |
| **Alert delivery strictly adheres to the configured delay**<br/>Alerts are now delivered at the end of the delay window that you set, regardless of whether data is complete or still being received for the specified event range. Any data that arrives after the delay window is not included in the alert.<p>Previously, alerts included a background processing check that waited for late-arriving data, even if that meant alerts were delivered after the configured delay window.</p>p>(Documentation link to follow.)</p> | | September 2026 |
| **Adobe Brand Visibility integration**<br/>Connect Adobe Brand Visibility with your organization's Customer Journey Analytics data so you can measure how AI-driven discovery translates into real website engagement and business outcomes.<p>(Documentation link to follow.)</p> | | September 2026 |
| **Additional skills in CX Enterprise Coworker**<br>New skills are coming to Coworker, including:<ul><li><strong>Implementation Guides</strong>: Turn a short discovery conversation into a personalized, dependency-aware implementation plan, with ready-to-use exports to CSV, Jira, Workfront, and Markdown.</li><li><strong>Intelligent Implementation Checklist</strong>: Turn your discovery conversation into a governed, trackable implementation project in Coworker Projects: an ordered checklist of steps you can assign, monitor, and validate.</li><li><strong>Data Validation</strong>: Check your data fields and datasets directly in Coworker to confirm you're working from trusted, accurate data (upgraded from Adobe Agent Orchestrator v1).</li><li><strong>Streaming Media Validation</strong>: Validate your Streaming Media data in Coworker to confirm it's accurate and ready for reporting.</li></ul><p>(Documentation links to follow.)</p> | | September 30, 2026 |

### Fixes in Customer Journey Analytics

**Analysis Workspace**: AN-487374, AN-487119, AN-468907, AN-468810, AN-468363, AN-468096, AN-467414, AN-466986, AN-466982, AN-465073, AN-463571, AN-462373, AN-492801, AN-488821, AN-488452, AN-486517, AN-478930, AN-468325
**Components**: 
**Connections**: AN-451458, AN-365942
**Content Analytics**: 
**Guided analysis**: AN-485600
**Exports**: AN-489161, AN-467131, AN-464746, AN-469034, AN-447252, AN-437803, AN-394444
**Data views**: AN-478732, AN-468836, AN-467851, AN-487651, AN-423592
**Data ingestion**: AN-489829, AN-489722, AN-469451, AN-467436, AN-467049, AN-466087, AN-465049, AN-463524, AN-457433, AN-490288, AN-487500, AN-390916, AN-342311
**Implementation**: 
**Report Builder**: AN-487486, AN-478944, AN-470036, AN-468589, AN-468436, AN-456747, AN-456700, AN-442695, AN-492330, AN-490564, AN-468293, AN-460921
**Reporting**: AN-479145, AN-469095, AN-468070, AN-467786, AN-456684, AN-465257, AN-422685, AN-406114, AN-356706, AN-322733
**Segmentation**: AN-486561, AN-278260
**Scheduled reports**: AN-479157
**Shared metrics and dimensions**: 
**Audience Analysis**: AN-468237, AN-462553
**Other**: AN-469601, AN-462817, AN-362308, AN-349757, AN-326432, AN-326345, AN-324341, AN-309317

## Postponed features

| Feature and description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| -----------|-----------|-----------|
| **Streaming media services: Support schedule data** <br/>You can now upload schedule data of past live Streaming Media content to more easily and accurately track viewership.<p>The following are examples of live content that is supported with schedule data upload:</p><ul><li>FAST (Free Ad Supported TV) platforms</li><li>Local streams</li><li>Live sports</li></ul><p>Uploading schedule data allows you to track viewership data for individual programs that ran during the time you designate in the upload file. You can even gather viewership data for specific topics or program segments.</p><p>These capabilities are available regardless of how you implemented Streaming Media Collection.</p><p>Previously, it was difficult to accurately tie a given session to specific programs when analyzing live content, and it wasn't possible to tie a given session to individual topics or program segments.</p><p>For more information, see [Upload schedule data to track live content](https://experienceleague.adobe.com/en/docs/media-analytics/using/media-use-cases/track-schedule-data).</p> | October 29, 2025 | TBD<p>(Originally planned for October 29, 2025)</p> |

>[!MORELIKETHIS]
>
>* [Previous Customer Journey Analytics release notes for 2026](/help/release-notes/2026.md)
>* [Adobe Analytics release notes](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html)
>* [Streaming Media Collection release notes](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
>* [CX Enterprise release notes](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)
>* [Customer Journey Analytics documentation updates](/help/release-notes/doc-changes.md)

