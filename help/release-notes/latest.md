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
# Current Customer Journey Analytics release notes (July 2026)

**Last update**: July 8, 2026

These release notes cover the July 2026 release period. Adobe Customer Journey Analytics releases operate on a [continuous delivery model](releases.md), which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## New or updated features

| Feature and description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| -----------|-----------|-----------|
| **Sub-event analysis** <br/>Sub-event analysis lets you analyze data at a level more granular than the event level. Instead of filtering on entire events, you can segment on individual containers within an event. <p>For example, you can segment on a specific product category without including all other products purchased in the same order. You can also define objects or arrays that are part of your event data as separate containers within a data view.</p><p>(Documentation link to follow.)</p> | July 15, 2026 | End of July, 2026 |
| **B2B Edition: Support for ad hoc and relational datasets** <br/>Ad hoc and relational datasets are now also supported in account-based connections in Customer Journey Analytics B2B Edition.<p>(Documentation link to follow.)</p> | | July 20, 2026 |
| **Content Analytics: Paid media data** <br/>Paid media is now available as a third channel for Content Analytics.<p>(Documentation link to follow.)</p> | | July 31, 2026 |
| **Connections Usage interface update** <br/>In the Usage interface when managing connections, you can now see usage details for each individual module, such as Customer Journey Analytics or Customer Journey Analytics B2B Edition. <p>Additionally, you can now break down usage reporting for each of the modules by month.</p><p>(Documentation link to follow.)</p> | | July 31, 2026 |
| **CX Enterprise Coworker: Validate your data when migrating from Adobe Analytics to Customer Journey Analytics** <br/>A new skill in CX Enterprise Coworker allows you to validate the data from your Customer Journey Analytics implementation against the data from your existing Adobe Analytics implementation. <p>This skill automatically compares each dimension, metric, and trend individually as needed. It can also compare all Adobe Analytics report suites against all Customer Journey Analytics data views. The skill then generates AI-driven insights and recommendations that you can implement to facilitate your migration to Customer Journey Analytics.</p><p>(Documentation link to follow.)</p> | | End of July, 2026 |
| **Inline classifications**<br/>[Inline classifications](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md#inline-classifications) enable you to rename or combine rows in a freeform table. And to create a derived field from the modified rows in a table. | | July 20, 2026 | 

### Fixes in Customer Journey Analytics

**Analysis Workspace**: AN-457527, AN-451161, AN-459034, AN-458071, AN-458398
**Components**: 
**Connections**: AN-457065
**Content Analytics**: 
**Guided analysis**: 
**Exports**: 
**Data views**: AN-453201
**Data ingestion**: 
**Implementation**: 
**Report Builder**: AN-457533, AN-453683
**Reporting**: AN-457607, AN-447692, AN-451259, AN-455713
**Segmentation**: 
**Scheduled reports**: AN-450715
**Shared metrics and dimensions**:
**Audience Analysis**: 
**Other**: AN-457063

## Postponed features

| Feature and description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| -----------|-----------|-----------|
| **Streaming media services: Support schedule data** <br/>You can now upload scheduled data of past live Streaming Media content to more easily and accurately track viewership.<p>The following are examples of live content that are supported with schedule data upload:</p><ul><li>FAST (Free Ad Supported TV) platforms</li><li>Local streams</li><li>Live sports</li></ul><p>Uploading schedule data allows you to track viewership data for individual programs that ran during the time you designate in the upload file. You can even gather viewership data for specific topics or program segments.</p><p>These capabilities are available regardless of how you implemented Streaming Media Collection.</p><p>Previously, it was difficult to accurately tie a given session to specific programs when analyzing live content, and it wasn't possible to tie a given session to individual topics or program segments.</p><p>For more information, see [Upload schedule data to track live content](https://experienceleague.adobe.com/en/docs/media-analytics/using/media-use-cases/track-schedule-data). | October 29, 2025 | TBD<p>(Originally planned for October 29, 2025)</p> |

>[!MORELIKETHIS]
>
>* [Previous Customer Journey Analytics release notes for 2026](/help/release-notes/2026.md)
>* [Adobe Analytics release notes](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html)
>* [Streaming Media Collection release notes](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
>* [CX Enterprise release notes](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)
>* [Customer Journey Analytics documentation updates](/help/release-notes/doc-changes.md)

