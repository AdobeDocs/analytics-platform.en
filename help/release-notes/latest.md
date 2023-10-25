---
title: View the current Customer Journey Analytics release notes
description: Latest Customer Journey Analytics release notes
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
---
# Current Adobe Customer Journey Analytics release notes (October/November 2023)

**Last update**: October 25, 2023

These release notes cover the release period of October 16, 2023 through end of November 2023. Adobe Customer Journey Analytics releases operate on a [continuous delivery model](releases.md) which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## New or updated features 

| Feature | Description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **New capabilities to Usage view in Adobe Product Analytics** | The following features have been added to the [Usage view](/help/guided-analysis/types/usage.md):<ul><li>**Trend lines**: Trend lines are now supported. Click [!UICONTROL Overlays] above the chart to enable them.</li><li>**Query breakdowns**: You can now apply breakdowns to this view type. They are available as an option in the query rail.</li></ul> | N/A | October 25, 2023 |
| **Connections Detail Page - Skipped Records** | This capability gives you insight into why certain records were skipped during Customer Journey Analytics data ingestion. Possible reasons can include big visitor IDs (more than 1 million records), missing timestamps and missing person IDs. (Documentation to follow) | N/A | October 25, 2023 |
| **Documentation for CJA Data Views API** | See the [Data views API](https://developer.adobe.com/cja-apis/docs/endpoints/dataviews/) to learn how to programmatically create, modify, or delete data views. | N/A | October 16, 2023 |
| **Row count metrics for lookup and profile datasets** | These metrics were previously available only for event datasets. | N/A | October 16, 2023 | 
| **Export full tables to the cloud** | Customer Journey Analytics Full Table Export allows you to export millions of Workspace rows to cloud destinations. <p>Exporting full tables offers one-time or scheduled delivery of data tables designed within Workspace with support for up to five breakdowns, five metrics, filters, and calculated metrics, all in a concatenated table. It is the evolution of Data Warehouse reports in Adobe Analytics, with many new, often-requested features that are not available in Data Warehouse today.</p><p> Cloud export options include:</p><ul><li>Adobe Experience Platform Data Landing Zone</li><li>Amazon S3 Role ARN</li><li>Google Cloud Platform</li><li>Azure SAS</li><li>Azure RBAC</li><li>Snowflake</li></ul>For more information, see [Export Customer Journey Analytics reports to the cloud](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/export/export-cloud.html).| October 4, 2023 | October 19, 2023 |
| **Reporting Activity Manager** | The Reporting Activity Manager lets you see the reporting capacity for each connection in your organization. It provides administrators with detailed visibility into reporting consumption in order to easily diagnose and fix capacity issues during peak reporting times. Key features of the Reporting Activity Manager include:<ul><li>Cancel current reporting requests (including requests from guided analyses and full table exports)</li><li>Restrict subsequent requests for a defined time period</li></ul>In addition to canceling current requests, administrators can now restrict requests for a defined time period. Administrators can restrict requests by request, project, or user.  [Learn more](/help/reporting-activity-manager/reporting-activity-overview.md) | October 17, 2023 | October 24, 2023 |

{style="table-layout:auto"}

## Fixes in Customer Journey Analytics

AN-327661; AN-329282; AN-329383; AN-329808; AN-331030; AN-331087; AN-331105

## Important notices for Customer Journey Analytics Administrators

| Notice | Notice added or updated | Description |
| --- | --- | --- |
| N/A | N/A| N/A |

{style="table-layout:auto"}

## Related resources

* [Previous Customer Journey Analytics release notes for 2023](/help/release-notes/2023.md)
* [Adobe Analytics release notes](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=en)
* [Media Analytics release notes](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* [Adobe Experience Cloud release notes](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)
* [Customer Journey Analytics documentation updates](/help/release-notes/doc-changes.md)
