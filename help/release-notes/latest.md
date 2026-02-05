---
title: Current Customer Journey Analytics release notes
description: View the latest Customer Journey Analytics release notes
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
---
# Current Customer Journey Analytics release notes (February 2026)

**Last update**: February 6, 2026

These release notes cover the February 2026 release period. Adobe Customer Journey Analytics releases operate on a [continuous delivery model](releases.md), which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## New or updated features 

| Feature and description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| ----------- | ------- | ---- |
| **Header overrides** <p>You can specify a header name and secret header value in Content Analytics.  This [header overrides configuration](/help/content-analytics/config/guided.md#header-overrides) ensures that Content Analytics sends custom HTTP headers to bypass any bot detection or gate traffic technologies you have implemented.</p> |  | February 2, 2026 |
| **Include multiple dimension columns in a freeform table**<p>You can now include up to 5 dimension columns in a freeform table, allowing you to view multiple dimension items side by side. Each row of dimension items behaves like a single concatenated dimension item.</p><p>You can apply filters, sorting, breakdowns, and more to freeform tables with multiple dimension columns to create a deeper and more custom analysis.</p><p>Previously, you could include only 1 dimension column in a freeform table.</p><p>For more information, see [Include multiple dimension columns in a freeform table](/help/analysis-workspace/visualizations/freeform-table/freeform-table-multidimensions.md).</p> | January 28, 2026 | February 18, 2026 |
| **Sort tables by multiple columns**<p>You can now sort the data of a freeform table by multiple columns in Analysis Workspace, whether they are dimensions or metrics.</p><p>When you sort data for multiple columns, data is sorted according to the priority you assign to each column. Priority numbering is displayed next to the sort icon.</p><p>For more information, see [Filter and sort freeform tables](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).</p> | January 28, 2026 | February 18, 2026 |
| **Full table export improvements**<p>Full table export includes the following enhancements:</p><p>Export creation and configuration enhancements</p><ul><li>Create an export from the Exports page. Previously, you could only create an export from Analysis Workspace by right-clicking the table.</li><li>Add a new account or location when creating an export.</li><li>Automate file name creation and folder placement of data feed files. This allows file names to be predictable and organized into folders in a logical way. Previously, file names were unpredictable and grouped into a single folder.</li><li>Support for exporting data as Parquet files for improved data warehouse compatibility. Previously, only CSV and JSON were supported.</li></ul><p>Export management enhancements</p><ul><li>Renew or cancel one or more exports from the Exports page.</li><li>Resend one or more exports from the Logs page.</li><li>Email individual users or groups when an export fails or is about to expire.</li><li>More precise error messages for failed exports.</li></ul><p>Calculated metric, segment, and dimension enhancements</p><ul><li>Support for more calculated metric functions. Previously, only simple math functions were supported.</li><li>Apply segments when creating an export.</li><li>Support for double-data type dimensions for improved precision.</li></ul><p>Administrative enhancements</p><ul><li>Administrators can now view all exports and logs, regardless of who created them.</li></ul> | February 18, 2026 | March 4, 2026 |
| **Support for data mirror**  <p>With support for model-based schemas and change data capture (CDC) functionality for specific source connectors in Experience Platform, Customer Journey Analytics will be able to support [data mirror](/help/data-mirror/data-mirror.md) functionality of data warehouse solutions like [!DNL Snowflake], [!DNL Azure Databricks], and [!DNL Google BigQuery].</p><p>Contact your Adobe Account Team to access the beta.</p> | Beta release: September 24, 2025 | TBD |
| **Update to the Approximate Count Distinct function**<p>The HLL probabilistic algorithm used in the Approximate Count Distinct function will soon be updated. The resulting output for numbers utilizing this function might change slightly from historical numbers, as follows:<ul><li>When counting very small amounts of unique values, the results will be improved to use exact counts rather than using estimates.</li><li>When counting anything larger, count estimates will retain the same accuracy as prior to this update (estimates are accurate within 5 percent of the exact number, 95 percent of the time).</li></ul><p>For more information about the Approximate Count Distinct function, see [Approximate Count Distinct](/help/components/calc-metrics/cm-adv-functions.md#approximate-count-distinct) in [Advanced functions](/help/components/calc-metrics/cm-adv-functions.md) |  | March 2026 | 
| **Streaming media services: Support schedule data** <p>You can now upload scheduled data of past live Streaming Media content to more easily and accurately track viewership.</p><p>The following are examples of live content that are supported with schedule data upload:</p><ul><li>FAST (Free Ad Supported TV) platforms</li><li>Local streams</li><li>Live sports</li></ul><p>Uploading schedule data allows you to track viewership data for individual programs that ran during the time you designate in the upload file. You can even gather viewership data for specific topics or program segments.</p><p>These capabilities are available regardless of how you implemented Streaming Media Collection.</p><p>Previously, it was difficult to accurately tie a given session to specific programs when analyzing live content, and it wasn't possible to tie a given session to individual topics or program segments.</p><p>For more information, see [Upload schedule data to track live content](https://experienceleague.adobe.com/en/docs/media-analytics/using/media-use-cases/track-schedule-data)</p>| October 29, 2025 | First half of 2026<p>(Originally planned to release on October 29, 2025)</p> |

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
