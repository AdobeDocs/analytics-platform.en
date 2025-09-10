---
title: Current Customer Journey Analytics release notes
description: View the latest Customer Journey Analytics release notes
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
---
# Current Adobe Customer Journey Analytics release notes (August 2025)

**Last update**: September 4, 2025


These release notes cover the release period of August 13 through September 16, 2025. Adobe Customer Journey Analytics releases operate on a [continuous delivery model](releases.md), which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## New or updated features 

| Feature | Description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Updates to the Usage interface** | The [Usage interface](/help/connections/manage-connections.md#usage) now adds information about core data volume and average row size.<p>For more information, see [Manage connections](/help/connections/manage-connections.md#usage).</p> | | September 4, 2025 |
| **Improvements when migrating projects and components to Customer Journey Analytics** | The following improvements are now available when migrating projects and components from Adobe Analytics to Customer Journey Analytics:<ul><li>Migrate multiple projects at one time.<br/>You can migrate up to 20 projects at one time.<br/>Previously, you could migrate only one project at a time.</li><li>Update mappings for dimensions and metrics that were already mapped with a previous project migration.<br/>You can now update these mappings each time you migrate a project, even if the same dimensions and metrics were previously mapped with a prior migration.<br/>Previously, any mappings you chose were permanent for all future project migrations.</li><li>Improved performance for organizations with high numbers of projects.</li></ul><p>This feature is available from the Adobe Analytics interface. For more information, see [Migrate components and projects from Adobe Analytics to Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/component-migration/component-migration).</p> | September 15, 2025 | September 18, 2025 |
| **Lookup keys limit increased up to 1 billion** | The maximum number of unique keys for a lookup dataset is now up to 1 billion, depending on your Customer Journey Analytics entitlement. <p>Previously, the maximum number was 10 million for all entitlements.<p>For more information, see [Guardrails](/help/technotes/guardrails.md).</p> | | September 18, 2025 |
| **Support for ad hoc schemas** | [Ad hoc schemas](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/tutorials/ad-hoc) are used in various data ingestion workflows for Experience Platform, including ingesting CSV files and creating certain kinds of source connections. <p>This feature enables the support for using ad hoc schemas in Customer Journey Analytics. As part of the definition of a connection, you can now select a dataset based on an ad hoc schema and use the data in your data view and workspace projects.</p> <p>(Documentation link to follow.)</p> |  | September 18, 2025 (Originally planned to release on August 28, 2025) |
| **Real-time reporting** | Real-time reporting in Customer Journey Analytics displays and updates data and visualizations within one or more panels in Analysis Workspace in real time.<br/><br/>(Documentation link to follow.) | | September 18,  2025 (Originally planned to release on August 15, 2025)|
| **Support for data mirror**  | With support for model-based schemas and change data capture (CDC) functionality for specific source connectors in Experience Platform, Customer Journey Analytics will be able to support data mirror functionality of data warehouse solutions for Snowflake, Databricks and Google BigQuery. <p>Contact your Adobe Account Team to access the beta.</p><p>(Documentation link to follow.)</p> | Beta release starting September 24 | TBD |
| **Streaming Media: Updated XDM fields for collecting Streaming Media data into Adobe Experience Platform** | When collecting Streaming Media data into Adobe Experience Platform, the XDM field paths shown under the heading of "XDM Field Path" of the Streaming Media parameters documentation should no longer be used. Instead, customers who implemented the Analytics source connector to collect Streaming Media data into Platform before May 9, 2025 must migrate their existing configurations to the mediaReporting field paths, as shown under the heading of "Reporting XDM Field Path" of the Streaming Media parameters documentation.<p> These field paths are found on the following pages and are marked as "Deprecated": [Audio and video parameters](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters), [Ad parameters](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/ad-parameters), [Chapter parameters](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/chapter-parameters), [Player state parameters](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/player-state-parameters), and [Quality parameters](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/quality-parameters). (No action is required for customers who implement the Analytics source connector after May 9, 2025, and are already using only mediaReporting XDM paths.)</p><p>Data ingestion on the deprecated XDM field paths will continue until the end of October 2025. After that time, deprecated field paths will be fully removed and no longer visible in the Adobe Experience Platform Schema UI, and data will be sent only using the mediaReporting field paths.</p><p>For more information, see [Migrate an Analytics Source Connector implementation to updated XDM Streaming Media fields](https://experienceleague.adobe.com/en/docs/media-analytics/using/media-use-cases/xdm-updates/updated-xdm-fields).</p><p>Please contact your Adobe Consulting Services or Account team for migration support. </p> |  | October 2025 |
| **Stitching in connections** | Simplifies Customer Journey Analytics stitching. Instead of duplicating a dataset and applying stitching on the duplicated dataset, stitching is now done on the ingestion of data into Customer Journey Analytics, which removes the requirement of duplicated datasets and schemas. <p>Furthermore, instead of having to request stitching through customer support, you can now initiate stitching yourself from an updated Connections UI.</p><p> *The previously communicated releases dates are pushed due to additional efforts required. The new release dates overlap with the holiday season, which introduces additional release constraints. A phased rollout is now planned to ensure stability and minimize disruption during the holiday period.*</p> <p>(Documentation link to follow.)</p> | End of October 2025 | End of January 2026 |

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
