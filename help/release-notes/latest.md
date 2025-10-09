---
title: Current Customer Journey Analytics release notes
description: View the latest Customer Journey Analytics release notes
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
---
# Current Customer Journey Analytics release notes (October 2025)

**Last update**: October 10, 2025

These release notes cover the release period of October through early November, 2025. Adobe Customer Journey Analytics releases operate on a [continuous delivery model](releases.md), which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## New or updated features 

| Feature | Description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Filter criteria included in line visualizations and sparklines** | Any filter criteria that you apply to a freeform table can be included in sparklines and connected line visualizations.<p>You can configure sparklines and line visualizations to include filter criteria by selecting the sparkline in the metric column header.</p><p>(Documentation link to follow.) | | October 15, 2025|
| **Real-time reporting** | Real-time reporting in Customer Journey Analytics displays and updates data and visualizations within one or more panels in Analysis Workspace in real time.<br/><br/>(Documentation link to follow.) | September 18,  2025 (Originally planned to release on August 15, 2025) | October 27, 2025 |
| **Support for data mirror**  | With support for model-based schemas and change data capture (CDC) functionality for specific source connectors in Experience Platform, Customer Journey Analytics will be able to support data mirror functionality of data warehouse solutions like [!DNL Snowflake], [!DNL Azure Databricks], and [!DNL Google BigQuery].<p>Contact your Adobe Account Team to access the beta.</p><p>(Documentation link to follow.)</p> | Beta release: September 24, 2025 | TBD |
| **Stitching in connections** | Simplifies Customer Journey Analytics stitching. Instead of duplicating a dataset and applying stitching on the duplicated dataset, stitching is now done on the ingestion of data into Customer Journey Analytics, which removes the requirement of duplicated datasets and schemas. <p>Furthermore, instead of having to request stitching through customer support, you can now initiate stitching yourself from an updated Connections UI.</p><p> *The previously communicated releases dates are pushed due to additional efforts required. The new release dates overlap with the holiday season, which introduces additional release constraints. A phased rollout is now planned to ensure stability and minimize disruption during the holiday period.*</p> <p>(Documentation link to follow.)</p> | October 28, 2025 | April 30, 2026 |
| **Streaming media services: Support schedule data** | You can now upload scheduled data of past live Streaming Media content to more easily and accurately track viewership.<p>The following are examples of live content that are supported with schedule data upload:</p><ul><li>FAST (Free Ad Supported TV) platforms</li><li>Local streams</li><li>Live sports</li></ul><p>Uploading schedule data allows you to track viewership data for individual programs that ran during the time you designate in the upload file. You can even gather viewership data for specific topics or program segments.</p><p>These capabilities are available regardless of how you implemented Streaming Media Collection.</p><p>Previously, it was difficult to accurately tie a given session to specific programs when analyzing live content, and it wasn't possible to tie a given session to individual topics or program segments.</p><p>(Documentation link to follow.)<!--For more information, see [Upload schedule data to track live content](https://experienceleague.adobe.com/en/docs/media-analytics/using/media-use-cases/track-schedule-data)--></p>|  | October 29, 2025 |
| **Analytics source connector: Search report suites in Experience Platform** | Customers with a high number of report suites can now search for the report suite they want to connect to within the Analytics Source Connector dataflow workflow. <p>Previously, customers had to paginate through a potentially long list of report suites.</p><p>(Documentation link to follow.) | | October 30, 2025 |
| **Streaming Media: Updated XDM fields for collecting Streaming Media data into Adobe Experience Platform** | When collecting Streaming Media data into Adobe Experience Platform, the XDM field paths shown under the heading of "XDM Field Path" of the Streaming Media parameters documentation should no longer be used. Instead, customers who implemented the Analytics source connector to collect Streaming Media data into Platform before May 9, 2025 must migrate their existing configurations to the mediaReporting field paths, as shown under the heading of "Reporting XDM Field Path" of the Streaming Media parameters documentation.<p> These field paths are found on the following pages and are marked as "Deprecated": [Audio and video parameters](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters), [Ad parameters](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/ad-parameters), [Chapter parameters](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/chapter-parameters), [Player state parameters](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/player-state-parameters), and [Quality parameters](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/quality-parameters). (No action is required for customers who implement the Analytics source connector after May 9, 2025, and are already using only mediaReporting XDM paths.)</p><p>Data ingestion on the deprecated XDM field paths will continue until the end of October 2025. After that time, deprecated field paths will be fully removed and no longer visible in the Adobe Experience Platform Schema UI, and data will be sent only using the mediaReporting field paths.</p><p>For more information, see [Migrate an Analytics Source Connector implementation to updated XDM Streaming Media fields](https://experienceleague.adobe.com/en/docs/media-analytics/using/media-use-cases/xdm-updates/updated-xdm-fields).</p><p>Please contact your Adobe Consulting Services or Account team for migration support. </p> |  | October 2025 |

## Fixes in Customer Journey Analytics

**Analysis Workspace**: AN-391719, AN-380838, AN-389402, AN-389373, AN-390851, AN-391593, AN-391404, AN-393064, AN-379337
**Components**: AN-393810
**Content Analytics**: 
**Guided Analysis**: 
**Platform**: 
**Report Builder**: AN-387741, AN-386777, AN-388720, AN-389343
**Reporting**: AN-391439, AN-391228, AN-393620, AN-393640, AN-391334, AN-393304
**Segmentation**: 
**Scheduled reports**: AN-391150, AN-390474
**Shared metrics and dimensions**: 
**Other**: AN-387858


## Important notices for Customer Journey Analytics Administrators

| Notice | Notice added or updated | Description |
| --- | --- | --- |
| N/A | | | 

## Related resources

* [Previous Customer Journey Analytics release notes for 2025](/help/release-notes/2025.md)
* [Adobe Analytics release notes](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html)
* [Streaming Media Collection release notes](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* [Adobe Experience Cloud release notes](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)
* [Customer Journey Analytics documentation updates](/help/release-notes/doc-changes.md)
