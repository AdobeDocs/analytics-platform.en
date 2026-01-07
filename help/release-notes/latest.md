---
title: Current Customer Journey Analytics release notes
description: View the latest Customer Journey Analytics release notes
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
---
# Current Customer Journey Analytics release notes (January 2026)

**Last update**: January 8, 2026

These release notes cover the January 2026 release period. Adobe Customer Journey Analytics releases operate on a [continuous delivery model](releases.md), which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## New or updated features 

| Feature | Description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Data storytelling: Generate slide presentations from Workspace reports** | You can now automatically generate a slide presentation (in .pptx format) that is based on an Analysis Workspace report. Workspace detects key insights in your report and converts them into stakeholder-ready slides.<p>This feature reduces the time and effort required to surface findings, build executive narratives, and communicate business impact.</p><p>(Documentation link to follow.)<!--For more information, see [Data storytelling: Generate slide presentations from Workspace reports](/help/analysis-workspace/curate-share/generate-slides.md).--></p> | October 22, 2025 | January 14, 2026 |
| **Analyze audiences from Experience Platform Profile datasets in Customer Journey Analytics** | You can now ingest audience membership data from Experience Platform Profile datasets into a Customer Journey Analytics connection. Audiences become available as new dimensions for use in Analysis Workspace.<p>This is made possible through a new capability in Customer Journey Analytics to ingest XDM object-maps, which makes it possible to ingest Profile AudienceIDs.</p><p>Previously, only simple XDM maps could be ingested into Customer Journey Analytics.</p><p>In addition to being able to add audience data as dimensions to any project in Analysis Workspace, the following new Workspace templates are also available:</p><ul><li>Audience Analytics Overview</li><li>Consent Policy Overview</li><p><!--For more information, see "Audience analysis overview" (https://experienceleague.corp.adobe.com/docs/analytics-platform/using/cja-dataviews/audience-analysis/audience-analysis-overview.html).-->(Documentation link to follow.)</p> | October 22, 2025 | January 14, 2026 |
| **Include multiple dimension columns in a freeform table** | You can now include up to 5 dimension columns in a freeform table, allowing you to view multiple dimension items side by side. Each row of dimension items behaves like a single concatenated dimension item.<p>You can apply filters, sorting, breakdowns, and more to freeform tables with multiple dimension columns to create a deeper and more custom analysis.</p><p>Previously, you could include only 1 dimension column in a freeform table.</p><p><!-- For more information, see [Include multiple dimension columns in a freeform table](/help/analysis-workspace/visualizations/freeform-table/freeform-table-multidimensions.md).--> (Documentation link to follow.)</p> | January 28, 2026 | February 18, 2026 |
| **Sort tables by multiple columns** | You can sort the data of a freeform table by any columns in Analysis Workspace, whether they are dimensions or metrics.<p>When you sort data for multiple columns, data is sorted according to the priority you assign to each column. Priority numbering is displayed next to the sort icon.</p><p>(Documentation link to follow.)<!-- For more information, see "Filter and sort freeform tables". (need to move info to this article from "Include multiple dimension columns in a freeform table") --></p> | January 28, 2026 | February 18, 2026 |
| **Side solution for cross-IMS** | Customers can manually request through a Jira ticket to use the Analytics Source Connector to combine multiple data sources from multiple IMS orgs.<p>(Documentation link to follow.)</p> |  | January 30, 2026 |
| **Stitching in connections** | Simplifies Customer Journey Analytics stitching. Instead of duplicating a dataset and applying stitching on the duplicated dataset, stitching is now done on the ingestion of data into Customer Journey Analytics, which removes the requirement of duplicated datasets and schemas. <p>Furthermore, instead of having to request stitching through customer support, you can now [initiate stitching yourself from an updated Connections UI](/help/stitching/use-stitching-ui.md).</p><p> *The previously communicated releases dates were postponed due to additional efforts required and the holiday season. A phased rollout is now planned to ensure stability and minimize disruption during the holiday period.*</p> | October 28, 2025 | January 30, 2026 |
| **Support for data mirror**  | With support for model-based schemas and change data capture (CDC) functionality for specific source connectors in Experience Platform, Customer Journey Analytics will be able to support [data mirror](/help/data-mirror/data-mirror.md) functionality of data warehouse solutions like [!DNL Snowflake], [!DNL Azure Databricks], and [!DNL Google BigQuery].<p>Contact your Adobe Account Team to access the beta.</p> | Beta release: September 24, 2025 | TBD |
| **Streaming media services: Support schedule data** | You can now upload scheduled data of past live Streaming Media content to more easily and accurately track viewership.<p>The following are examples of live content that are supported with schedule data upload:</p><ul><li>FAST (Free Ad Supported TV) platforms</li><li>Local streams</li><li>Live sports</li></ul><p>Uploading schedule data allows you to track viewership data for individual programs that ran during the time you designate in the upload file. You can even gather viewership data for specific topics or program segments.</p><p>These capabilities are available regardless of how you implemented Streaming Media Collection.</p><p>Previously, it was difficult to accurately tie a given session to specific programs when analyzing live content, and it wasn't possible to tie a given session to individual topics or program segments.</p><p>For more information, see [Upload schedule data to track live content](https://experienceleague.adobe.com/en/docs/media-analytics/using/media-use-cases/track-schedule-data)</p>| October 29, 2025 | First half of 2026<p>(Originally planned to release on October 29, 2025)</p> |

## Fixes in Customer Journey Analytics

**Analysis Workspace**: AN-400507, AN-400265, AN-399209, AN-397146, AN-394992, AN-390795
**Components**: 
**Content Analytics**:
**Exports**: AN-399012, AN-388578
**Guided Analysis**: 
**Implementation**: AN-397551, AN-397550, AN-397190, AN-396127
**Report Builder**: AN-401127, AN-400618, AN-392971, AN-391692
**Reporting**: 
**Segmentation**: 
**Scheduled reports**: 
**Shared metrics and dimensions**: 
**Other**: 


## Important notices for Customer Journey Analytics Administrators

| Notice | Notice added or updated | Description |
| --- | --- | --- |
| N/A |  |  |

## Related resources

* [Previous Customer Journey Analytics release notes for 2025](/help/release-notes/2025.md)
* [Adobe Analytics release notes](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html)
* [Streaming Media Collection release notes](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* [Adobe Experience Cloud release notes](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)
* [Customer Journey Analytics documentation updates](/help/release-notes/doc-changes.md)
