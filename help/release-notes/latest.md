---
title: Current Customer Journey Analytics Release Notes
description: View the latest Customer Journey Analytics release notes, including new features, fixed issues, and postponed releases for the current period.
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
TQID: 'https://experienceleague.adobe.com/EQKhna8E33DddZQGWe3ASBKMY9r-UsfuUcJg7DMwH0w'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
    internal-label: Administration
subfeature_v2:
  - id: ad333ea6-e90d-4c8f-8d61-9f8690784d6f
    internal-label: Templates
  - id: ad5685a0-8296-4a0c-814c-658c10b4af12
    internal-label: Content Analytics
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
    internal-label: Metrics
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
    internal-label: Segments
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
  - id: a8e39571-4463-4aa3-8b3f-4e2341ecf3b3
    internal-label: Release notes
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
# Current Customer Journey Analytics release notes (October 2026)

**Last update**: October 7, 2026

These release notes cover the October 2026 release period. Adobe Customer Journey Analytics releases operate on a [continuous delivery model](releases.md), which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## New or updated features

| Feature and description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| -----------|-----------|-----------|
| **Analyze LLM customer experiences in Analysis Workspace with Conversation Insights**<br/>Customer Journey Analytics now brings unstructured chat data into Analysis Workspace, allowing you to report on LLM-powered browsing and buying experiences that occur across your properties.<p>With this capability, you can:</p><ul><li>Collect prompts, responses, and agent metadata from conversational agents (either your organization's custom agents or Adobe Brand Concierge) via Web SDK.</li><li>Analyze intent, tone, and sentiment so you can understand what customers are asking, how your agent responds, and how your customers feel about their interactions.</li><li>Analyze at scale using your existing schema, datasets, and data views, then surface insights in Analysis Workspace.</li><li>Connect conversations to outcomes by tying agent interactions to your broader customer journeys, so you can measure real impact on conversion, engagement, and more.</li></ul><p>Previously, LLM-powered experiences were difficult to measure and nearly impossible to connect to your existing customer journeys.</p><p>For more information, see [Conversation Insights](/help/conversation-insights/overview.md).</p> | | October 8, 2026<p>(Originally planned for September 22, 2026)</p> |
| **Automatically generate component descriptions** <br/>You can now automatically generate descriptions for dimensions, metrics, calculated metrics, segments, and date ranges. This allows Workspace users to understand which components to use, especially in organizations with large component libraries. <p>You can generate a description for a single component, or generate descriptions for many components at the same time.</p> <p>(Documentation link to follow.)<!--For more information, see [Automatically generate descriptions](/help/components/add-component-descriptions.md#automatically-generate-descriptions).--></p> | | October 28, 2026 |
| **Adobe Brand Visibility integration**<br/>Connect Adobe Brand Visibility with your organization's Customer Journey Analytics data so you can measure how AI-driven discovery translates into real website engagement and business outcomes.<p>(Documentation link to follow.)</p> | | October 2026 |


### Fixes in Customer Journey Analytics

**Analysis Workspace**: AN-495340, AN-494789, AN-493307, AN-468900
**Components**: AN-492523
**Connections**: AN-492236
**Content Analytics**: 
**Guided analysis**: AN-495592
**Exports**: AN-495077, AN-494337, AN-486563, AN-469919, AN-462560, AN-462372
**Data views**: AN-492093, AN-467770, AN-455367, AN-444467
**Data ingestion**: AN-496439, AN-495339, AN-493456, AN-491984, AN-490515, AN-490479, AN-470065
**Implementation**: 
**Report Builder**: AN-496602, AN-494224, AN-493737, AN-493508, AN-493505, AN-492806, AN-468981, AN-454376
**Reporting**: AN-495661, AN-493562, AN-487058, AN-478768
**Segmentation**: 
**Scheduled reports**: AN-491103, AN-468049
**Shared metrics and dimensions**: AN-493722
**Audience Analysis**: AN-469101
**Other**: AN-493865

## Postponed features

| Feature and description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| -----------|-----------|-----------|
| **Total population reporting**<br/>You can now analyze and report on entities defined in profile and lookup datasets that exist in a Customer Journey Analytics connection. That analysis and reporting go beyond time-based series of events from event datasets. <p>This ability enables new classes of queries, metrics, and audience definitions that reflect the full scope of a business's customer base.</p><p>(Documentation link to follow.)</p> | | TBD<p>(Originally planned for September 22, 2026)</p> |
| **Streaming media services: Support schedule data** <br/>You can now upload schedule data of past live Streaming Media content to more easily and accurately track viewership.<p>The following are examples of live content that is supported with schedule data upload:</p><ul><li>FAST (Free Ad-Supported TV) platforms</li><li>Local streams</li><li>Live sports</li></ul><p>Uploading schedule data allows you to track viewership data for individual programs that ran during the time you designate in the upload file. You can even gather viewership data for specific topics or program segments.</p><p>These capabilities are available regardless of how you implemented Streaming Media Collection.</p><p>Previously, it was difficult to accurately tie a given session to specific programs when analyzing live content, and it wasn't possible to tie a given session to individual topics or program segments.</p><p>For more information, see [Upload schedule data to track live content](https://experienceleague.adobe.com/en/docs/media-analytics/using/media-use-cases/track-schedule-data).</p> | October 29, 2025 | TBD<p>(Originally planned for October 29, 2025)</p> |

>[!MORELIKETHIS]
>
>* [Previous Customer Journey Analytics release notes for 2026](/help/release-notes/2026.md)
>* [Adobe Analytics release notes](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html)
>* [Streaming Media Collection release notes](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
>* [CX Enterprise release notes](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)
>* [Customer Journey Analytics documentation updates](/help/release-notes/doc-changes.md)

