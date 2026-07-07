---
title: Current Customer Journey Analytics release notes
description: View the latest Customer Journey Analytics release notes
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
hold: true
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
| **Sub-event analysis** <br/>Sub-event analysis lets you analyze data at a level more granular than the event level. Instead of filtering on entire events, you can segment on individual containers within an event. <p>For example, you can segment on a specific product category without including all other products purchased in the same order. You can also define objects or arrays that are part of your event data as separate containers within a data view.</p> | July 15, 2026 | End of July, 2026 |
| **CJA B2B: Support for ad hoc and relational datasets** <br/>Ad-hoc and relational datasets are now also supported in CJA B2B account-based connections.<p>(Documentation link to follow.)</p>  | | July 20, 2026 |
| **Paid media data** <br/>Paid media is added as a third channel for Content Analytics.<p>(Documentation link to follow.)</p> | | July 31, 2026 |
| **Connections Usage UI update** <br/>You can see usage details for each individual module, such as Customer Journey Analytics, Customer Journey Analytics B2B Edition. Additionally, you can breakdown usage reporting for each of the modules by month.<p>(Documentation link to follow.)</p> | | July 31, 2026 |
| **CX Enterprise Coworker: Validate your data when migrating from Adobe Analytics to Customer Journey Analytics** <br/>A new skill in CX Enterprise Coworker allows you to validate the data from your Customer Journey Analytics implementation against the data from your existing Adobe Analytics implementation. <p>This skill automatically compares each dimension, metric, and trend, then generates AI-driven insights and recommendations that you can implement to facilitate your migration to Customer Journey Analytics.</p><p>(Documentation link to follow.)</p> | | End of July, 2026 |

### Fixes in Customer Journey Analytics

**Analysis Workspace**: AN-456858, AN-455865, AN-455706, AN-455592, AN-455484, AN-455180, AN-454999, AN-454170, AN-454145, AN-453793, AN-452921, AN-452009, AN-451958, AN-451643, AN-451600, AN-451525, AN-451477, AN-451262, AN-451161, AN-450772, AN-443594, AN-434416
**Components**: 
**Connections**: AN-457065, AN-453705
**Content Analytics**: AN-451203, AN-447596
**Guided analysis**: 
**Exports**: AN-452006, AN-451989, AN-440567
**Data views**: AN-451198
**Implementation**: 
**Report Builder**: AN-440912, AN-457586, AN-457533, AN-455713, AN-455623, AN-455063, AN-454512, AN-454053, AN-453977, AN-453781, AN-453683, AN-451974, AN-451735, AN-451731, AN-451190, AN-449813, AN-447173, AN-447139, AN-446184, AN-445794, AN-445354, AN-442819
**Reporting**: AN-454589, AN-454517, AN-453982, AN-451822, AN-451497, AN-451463, AN-451259, AN-451215, AN-450661, AN-447699, AN-448375, AN-447692
**Segmentation**: 
**Scheduled reports**: AN-451980, AN-451882, AN-450715
**Shared metrics and dimensions**:
**Audience Analysis**: AN-449656, AN-450400
**Other**: AN-457063, AN-454140, AN-453937, AN-453825, AN-452959, AN-452934, AN-452296, AN-451781, AN-450974

## Postponed features

| Feature and description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| -----------|-----------|-----------|
| **Streaming media services: Support schedule data** <br/>You can now upload scheduled data of past live Streaming Media content to more easily and accurately track viewership.<p>The following are examples of live content that are supported with schedule data upload:</p><ul><li>FAST (Free Ad Supported TV) platforms</li><li>Local streams</li><li>Live sports</li></ul><p>Uploading schedule data allows you to track viewership data for individual programs that ran during the time you designate in the upload file. You can even gather viewership data for specific topics or program segments.</p><p>These capabilities are available regardless of how you implemented Streaming Media Collection.</p><p>Previously, it was difficult to accurately tie a given session to specific programs when analyzing live content, and it wasn't possible to tie a given session to individual topics or program segments.</p><p>For more information, see [Upload schedule data to track live content](https://experienceleague.adobe.com/en/docs/media-analytics/using/media-use-cases/track-schedule-data) | October 29, 2025 | TBD<p>(Originally planned for October 29, 2025)</p> |

>[!MORELIKETHIS]
>
>* [Previous Customer Journey Analytics release notes for 2026](/help/release-notes/2026.md)
>* [Adobe Analytics release notes](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html)
>* [Streaming Media Collection release notes](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
>* [CX Enterprise release notes](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)
>* [Customer Journey Analytics documentation updates](/help/release-notes/doc-changes.md)

