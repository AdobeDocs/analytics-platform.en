---
title: Current Customer Journey Analytics release notes
description: View the latest Customer Journey Analytics release notes
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
---
# Current Customer Journey Analytics release notes (January 2026)

**Last update**: February 2, 2026

These release notes cover the January 2026 release period. Adobe Customer Journey Analytics releases operate on a [continuous delivery model](releases.md), which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## New or updated features 

| Feature | Description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Header overrides** | You can specify in header name and secret header value in Content Analytics.  This [header overrides configuration](/help/content-analytics/config/guided.md#header-overrides) ensures that Content Analytics sends custom HTTP headers to bypass any bot detection or gate traffic technologies you have implemented. |  | February 2, 2026 |
| **Analyze audiences from Experience Platform Profile datasets in Customer Journey Analytics** | You can now ingest audience membership data from Experience Platform Profile datasets into a Customer Journey Analytics connection. Audiences become available as new dimensions for use in Analysis Workspace.<p>This is made possible through a new capability in Customer Journey Analytics to ingest XDM object-maps, which makes it possible to ingest Profile AudienceIDs.</p><p>Previously, only simple XDM maps could be ingested into Customer Journey Analytics.</p><p>In addition to being able to add audience data as dimensions to any project in Analysis Workspace, the following new Workspace templates are also available:</p><ul><li>Audience Analytics Overview</li><li>Consent Policy Overview</li></ul><p>For more information, see [Audience analysis overview](/help/connections/audience-analysis/audience-analysis-overview.md).</p> | October 22, 2025 | January 22, 2026 |
| **Data storytelling: Generate slide presentations from Workspace reports** | You can now automatically generate a slide presentation (in .pptx format) that is based on an Analysis Workspace report. Workspace detects key insights in your report and converts them into stakeholder-ready slides.<p>This feature reduces the time and effort required to surface findings, build executive narratives, and communicate business impact.</p><p>For more information, see [Data storytelling: Generate slide presentations from Workspace reports](/help/analysis-workspace/curate-share/generate-slides.md).</p> | October 22, 2025 | January 28, 2026 |
| **Include multiple dimension columns in a freeform table** | You can now include up to 5 dimension columns in a freeform table, allowing you to view multiple dimension items side by side. Each row of dimension items behaves like a single concatenated dimension item.<p>You can apply filters, sorting, breakdowns, and more to freeform tables with multiple dimension columns to create a deeper and more custom analysis.</p><p>Previously, you could include only 1 dimension column in a freeform table.</p><p>For more information, see [Include multiple dimension columns in a freeform table](/help/analysis-workspace/visualizations/freeform-table/freeform-table-multidimensions.md).</p> | January 28, 2026 | February 18, 2026 |
| **Sort tables by multiple columns** | You can now sort the data of a freeform table by multiple columns in Analysis Workspace, whether they are dimensions or metrics.<p>When you sort data for multiple columns, data is sorted according to the priority you assign to each column. Priority numbering is displayed next to the sort icon.</p><p>For more information, see [Filter and sort freeform tables](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).</p> | January 28, 2026 | February 18, 2026 |
| **Combine data sources from multiple IMS orgs** | You can now use the Analytics Source Connector to combine multiple data sources from multiple IMS orgs. This allows organzations to have a combined view of their customer data, even when that customer data is spread across multiple IMS orgs. <p>**Note:** This configuration is available only by submitting a request to Adobe Customer Care.</p>  <p>(Documentation link to follow.)</p> |  | January 30, 2026 |
| **Stitching in connections** | The stitching process in Customer Journey Analytics is now more simple. Instead of duplicating a dataset and applying stitching on the duplicated dataset, stitching is now done on the ingestion of data into Customer Journey Analytics, which removes the requirement of duplicated datasets and schemas. <p>Furthermore, you [initiate stitching yourself through an updated Connections interface](/help/stitching/use-stitching-ui.md), instead of having to request stitching through Adobe Customer Care. | October 28, 2025 | January 30, 2026 |
| **Support for data mirror**  | With support for model-based schemas and change data capture (CDC) functionality for specific source connectors in Experience Platform, Customer Journey Analytics will be able to support [data mirror](/help/data-mirror/data-mirror.md) functionality of data warehouse solutions like [!DNL Snowflake], [!DNL Azure Databricks], and [!DNL Google BigQuery].<p>Contact your Adobe Account Team to access the beta.</p> | Beta release: September 24, 2025 | TBD |
| **Streaming media services: Support schedule data** | You can now upload scheduled data of past live Streaming Media content to more easily and accurately track viewership.<p>The following are examples of live content that are supported with schedule data upload:</p><ul><li>FAST (Free Ad Supported TV) platforms</li><li>Local streams</li><li>Live sports</li></ul><p>Uploading schedule data allows you to track viewership data for individual programs that ran during the time you designate in the upload file. You can even gather viewership data for specific topics or program segments.</p><p>These capabilities are available regardless of how you implemented Streaming Media Collection.</p><p>Previously, it was difficult to accurately tie a given session to specific programs when analyzing live content, and it wasn't possible to tie a given session to individual topics or program segments.</p><p>For more information, see [Upload schedule data to track live content](https://experienceleague.adobe.com/en/docs/media-analytics/using/media-use-cases/track-schedule-data)</p>| October 29, 2025 | First half of 2026<p>(Originally planned to release on October 29, 2025)</p> |

## Fixes in Customer Journey Analytics

**Analysis Workspace**: AN-423389, AN-423316, AN-422636, AN-422482, AN-422121, AN-422116, AN-422027, AN-421134, AN-420187, AN-406271, AN-406188, AN-405997, AN-405983, AN-405796, AN-405033, AN-404893, AN-404871, AN-404842, AN-404713, AN-404502, AN-404353, AN-404352, AN-404048, AN-403241, AN-402523, AN-400795, AN-396149, AN-390990, AN-390646, AN-383484, AN-376980, AN-371729, AN-347570, AN-404835
**Components**: 
**Content Analytics**:
**Guided analysis**: AN-421274
**Exports**: 
**Data views**: AN-421891, AN-404627
**Implementation**: 
**Report Builder**: AN-422120, AN-421937, AN-406296, AN-402951, AN-399748
**Reporting**: 
**Segmentation**: 
**Scheduled reports**: AN-423087, AN-422686
**Shared metrics and dimensions**: 
**Other**: AN-422946, AN-422775, AN-422273, AN-422100, AN-420045, AN-404891, AN-390912


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
