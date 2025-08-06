---
title: Current Customer Journey Analytics release notes
description: View the latest Customer Journey Analytics release notes
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
---
# Current Adobe Customer Journey Analytics release notes (July 2025)

**Last update**: July 22, 2025


These release notes cover the release period of July 11, 2025 to August 15, 2025. Adobe Customer Journey Analytics releases operate on a [continuous delivery model](releases.md), which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## New or updated features 

| Feature | Description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Map visualization** | The map visualization is a visualization in Analysis Workspace that allows you to build a visual map of any metric (including calculated metrics). It is useful for identifying and comparing metric data across different geographic regions.<p>Previously, the map visualization was available only in Adobe Analytics.</p><p>The map visualization in Customer Journey Analytics contains the following improvements from the map visualization in Adobe Analytics:</p><ul><li>Use any segment from your data view as a data source.</li><li>Accuracy up to a single meter by configuring the dimension in your data view.</li><li>A new selection tool allows you to create a segment, audience, trend, or breakdown from any area you select in the visualization.</li></ul><p>For more information, see [Map](/help/analysis-workspace/visualizations/map.md).</p> |  | August 13, 2025 |
| **Real-time reporting** | Real-time reporting in Customer Journey Analytics displays and updates data and visualizations within one or more panels in Analysis Workspace in real time. | | August 15, 2025|
| **Deleted projects are immediately unavailable by URL and are deleted from scheduled deliveries**  |  Projects that are deleted are immediately deleted from scheduled deliveries and are no longer accessible by their URL.<p>Previously, projects were included in scheduled deliveries and could be accessed with their URL for 60 days after being deleted.</p><p>For more information about deleting projects, see [Projects overview](/help/analysis-workspace/build-workspace-project/freeform-overview.md).</p> | |  August 2025 |
| **Projects downloaded as PDFs are downloaded to your workstation** | When downloading a project as a PDF, the PDF is downloaded to the downloads folder on your workstation. <p>Previously, downloading a project as a PDF launched the PDF in a new browser tab with a unique URL.</p><p>For more information, see [Download projects and data](/help/analysis-workspace/export/download-send.md).</p> |  | August 25, 2025 |
| **Support for ad hoc schemas** | You can now ingest ad hoc data (from ad hoc schemas) from Experience Platform into Customer Journey Analytics. <p>(Documentation link to follow.)</p> |  | August 28, 2025 |
| **Create metrics and dimensions based on user-defined map fields from the Platform schema** | User-defined map fields that you define in your Experience Platform schema are now available for use in Customer Journey Analytics.<p>You can use the following map fields when creating metrics and dimensions in Customer Journey Analytics:</p><ul><li>String to String</li><li>String to Integer</li></ul><p>For more information about map fields in Experience Platform, see [Define map fields in the UI](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/ui/fields/map).</p> |  | End of August |
| **Streaming Media: Updated XDM fields for collecting Streaming Media data into Adobe Experience Platform** | When collecting Streaming Media data into Adobe Experience Platform, the XDM field paths shown under the heading of "XDM Field Path" of the Streaming Media parameters documentation should no longer be used. Instead, customers who implemented the Analytics source connector to collect Streaming Media data into Platform before May 9, 2025 must migrate their existing configurations to the mediaReporting field paths, as shown under the heading of "Reporting XDM Field Path" of the Streaming Media parameters documentation.<p> These field paths are found on the following pages and are marked as "Deprecated": [Audio and video parameters](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters), [Ad parameters](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/ad-parameters), [Chapter parameters](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/chapter-parameters), [Player state parameters](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/player-state-parameters), and [Quality parameters](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/quality-parameters). (No action is required for customers who implement the Analytics source connector after May 9, 2025, and are already using only mediaReporting XDM paths.)</p><p>Data ingestion on the deprecated XDM field paths will continue until the end of October 2025. After that time, deprecated field paths will be fully removed and no longer visible in the Adobe Experience Platform Schema UI, and data will be sent only using the mediaReporting field paths.</p><p>For more information, see [Migrate an Analytics Source Connector implementation to updated XDM Streaming Media fields](https://experienceleague.adobe.com/en/docs/media-analytics/using/media-use-cases/xdm-updates/updated-xdm-fields).</p><p>Please contact your Adobe Consulting Services or Account team for migration support. </p> |  | October 2025 |

## Fixes in Customer Journey Analytics

**Analysis Workspace**: AN-387014; AN-387500
**Components**: AN-387293
**Content Analytics**: AN-387595
**Guided Analysis**: AN-382273
**Report Builder**: AN-382775
**Reporting**: AN-382020; AN-387827
**Segmentation**: AN-382102
**Shared metrics and dimensions**: AN-378451


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
