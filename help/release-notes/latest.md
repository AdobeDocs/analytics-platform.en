---
title: Current Customer Journey Analytics Release Notes
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
| **Use Analytics data in LLM Optimizer**<br>Connect LLM Optimizer with your organization's Customer Journey Analytics data so you can measure how AI-driven discovery translates into real website engagement and business outcomes. | | August 14, 2026 |
| **Journey canvas enhancements**<br>The following Journey canvas enhancements are now available:<ul><li>Compare the journey to a prior time frame. Compare the current journey to the journey 4 weeks prior, 2 quarters prior, 1 year prior, or to a custom date range.</li><li>For a selected node, show the top dimension items that come after the selected node at any point in the journey. Use this when the selected node is the key event in your analysis and you want to see what people do at any point afterward.<p>Previously, only the top immediate nodes could be shown before or after the selected node. </p></li><li>Change the shape and style of arrows between nodes. Drag arrows between nodes to change the shape (curviture) of the arrow, and right-click an arrow to change its style to any of the following: solid, dashed, dotted, dashed-dot, or animated.</li></ul><p></p>For more information, see [Configure a Journey canvas visualization](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md). |  | August 18, 2026 |
| **Consent policy filtering and reporting**<br>You can now report on which visitors match your Adobe Experience Platform consent policies. (Consent policy dimensions and metrics are added to the data views in your connection.)<p>Additionally, you can exclude non-consenting visitors before their data is ingested into Customer Journey Analytics.</p><p>For more information, see Consent reporting and filtering overview.</p> | | |
| **Support for additional data usage labels**<br>Customer Journey Analytics now supports the following additional data usage labels for elements within a dataset:<ul><li>C2 – Restrict third-party data export</li><li>C3 – Restrict directly identifiable data combination</li><li>C9 – Restrict data science </li></ul><p>For more information, see [Labels, policies, and marketing actions](/help/data-views/data-governance.md).</p> | | |
| **Migration Planner: Adobe Analytics to Customer Journey Analytics**<br>The Migration Planner provides a migration wizard that automates some of the most complex and time-consuming tasks associated with an upgrade from Adobe Analytics to Customer Journey Analytics, including XDM schema creation and migration from AppMeasurement or the Analytics extension (tags) to the Experience Platform Web SDK. <p>(Documentation link to follow.)</p> | | End of August or September |

### Fixes in Customer Journey Analytics

**Analysis Workspace**: 
**Components**: 
**Connections**:
**Content Analytics**: 
**Guided analysis**: 
**Exports**: 
**Data views**: 
**Data ingestion**: 
**Implementation**: 
**Report Builder**:
**Reporting**: 
**Segmentation**: 
**Scheduled reports**: 
**Shared metrics and dimensions**:
**Audience Analysis**: 
**Other**: 

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

