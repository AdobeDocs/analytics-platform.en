---
title: Current Customer Journey Analytics release notes
description: View the latest Customer Journey Analytics release notes
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
---
# Current Customer Journey Analytics release notes (February 2026)

**Last update**: February 12, 2026

These release notes cover the February 2026 release period. Adobe Customer Journey Analytics releases operate on a [continuous delivery model](releases.md), which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## New or updated features 

| Feature and description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| ----------- | ------- | ---- |
| **Header overrides** <p>You can specify a header name and secret header value in Content Analytics. This [header overrides configuration](/help/content-analytics/config/guided.md#header-overrides) ensures that Content Analytics sends custom HTTP headers to bypass any bot detection or gate traffic technologies you have implemented.</p> |  | February 2, 2026 |
| **Include multiple dimension columns in a freeform table**<p>You can now include up to 5 dimension columns in a freeform table, allowing you to view multiple dimension items side by side. Each row of dimension items behaves like a single concatenated dimension item.</p><p>You can apply filters, sorting, breakdowns, and more to freeform tables with multiple dimension columns to create a deeper and more custom analysis.</p><p>Previously, you could include only 1 dimension column in a freeform table.</p><p>For more information, see [Include multiple dimension columns in a freeform table](/help/analysis-workspace/visualizations/freeform-table/freeform-table-multidimensions.md).</p> | January 28, 2026 | February 18, 2026 |
| **Sort tables by multiple columns**<p>You can now sort the data of a freeform table by multiple columns in Analysis Workspace, whether they are dimensions or metrics.</p><p>When you sort data for multiple columns, data is sorted according to the priority you assign to each column. Priority numbering is displayed next to the sort icon.</p><p>For more information, see [Filter and sort freeform tables](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).</p> | January 28, 2026 | February 18, 2026 |
| **Full table export improvements**<p>Full table export includes the following enhancements:</p><p>Export creation and configuration enhancements</p><ul><li>Create an export from the Exports page. Previously, you could only create an export from Analysis Workspace by right-clicking the table.</li><li>Add a new account or location when creating an export.</li><li>Automate file name creation and folder placement of exported files. This allows file names to be predictable and organized into folders in a logical way. Previously, file names were unpredictable and grouped into a single folder.</li><li>Support for exporting data as Parquet files for improved data warehouse compatibility. Previously, only CSV and JSON were supported.</li></ul><p>Export management enhancements</p><ul><li>Renew or cancel one or more exports from the Exports page.</li><li>Resend one or more exports from the Logs page.</li><li>Email individual users or groups when an export fails or is about to expire.</li><li>More precise error messages for failed exports.</li></ul><p>Calculated metric, segment, and dimension enhancements</p><ul><li>Support for more calculated metric functions. Previously, only simple math functions were supported.</li><li>Apply segments when creating an export.</li><li>Support for double-data type dimensions for improved precision.</li></ul><p>Administrative enhancements</p><ul><li>Administrators can now view all exports and logs, regardless of who created them.</li></ul><p>(Documentation link to follow.)</p> | February 18, 2026 | March 4, 2026 |
| **Content Analytics: Scatter visualization thumbnails and previews** <p>When viewing a scatter visualization in Content Analytics, a thumbnail of the asset now displays when you hover over a dot in the chart. This thumbnail allows you to quickly and easily see what content is being represented in the chart.</p><p>(Documentation link to follow.)</p> | February 17, 2026 | March 2, 2026 |
| **Content Analytics: Bar visualization thumbnails and previews** <p>When viewing a horizontal bar visualization in Content Analytics, a thumbnail of the asset now displays when you hover over a bar in the chart. This thumbnail allows you to quickly and easily see what content is being represented in the chart.</p><p>(Documentation link to follow.)</p>| February 23, 2026 | March 9, 2026 |
| **Update to the Approximate Count Distinct function**<p>The HLL probabilistic algorithm used in the Approximate Count Distinct function will soon be updated. The resulting output for numbers utilizing this function might change slightly from historical numbers, as follows:<ul><li>When counting very small amounts of unique values, the results will be improved to use exact counts rather than using estimates.</li><li>When counting anything larger, count estimates will retain the same accuracy as prior to this update (estimates are accurate within 5 percent of the exact number, 95 percent of the time).</li></ul><p>For more information about the Approximate Count Distinct function, see [Approximate Count Distinct](/help/components/calc-metrics/cm-adv-functions.md#approximate-count-distinct) in [Advanced functions](/help/components/calc-metrics/cm-adv-functions.md)</p> |  | March 2026 | 
| **Support for data mirror**  <p>With support for model-based schemas and change data capture (CDC) functionality for specific source connectors in Experience Platform, Customer Journey Analytics will be able to support [data mirror](/help/data-mirror/data-mirror.md) functionality of data warehouse solutions like [!DNL Snowflake], [!DNL Azure Databricks], and [!DNL Google BigQuery].</p><p>Contact your Adobe Account Team to access the beta.</p> | Beta release: September 24, 2025 | TBD |
| **Streaming media services: Support schedule data** <p>You can now upload schedule data of past live Streaming Media content to more easily and accurately track viewership.</p><p>The following are examples of live content that are supported with schedule data upload:</p><ul><li>FAST (Free Ad Supported TV) platforms</li><li>Local streams</li><li>Live sports</li></ul><p>Uploading schedule data allows you to track viewership data for individual programs that ran during the time you designate in the upload file. You can even gather viewership data for specific topics or program segments.</p><p>These capabilities are available regardless of how you implemented Streaming Media Collection.</p><p>Previously, it was difficult to accurately tie a given session to specific programs when analyzing live content, and it wasn't possible to tie a given session to individual topics or program segments.</p><p>For more information, see [Upload schedule data to track live content](https://experienceleague.adobe.com/en/docs/media-analytics/using/media-use-cases/track-schedule-data)</p>| October 29, 2025 | First half of 2026<p>(Originally planned to release on October 29, 2025)</p> |
| **Combine report suites from multiple IMS orgs**<p>You can use the Analytics Source Connector to combine report suites from multiple IMS orgs. This [cross-IMS data mapping](/help/getting-started/aa-vs-cja/mapping-data-ims-orgs.md) feature allows organzations to have a combined view of their customer data, even when that customer data is spread across multiple IMS organizations. <p>**Note:** This configuration is available only by submitting a request to Adobe Customer Care.</p> |  | February 12, 2026 |

## Fixes in Customer Journey Analytics

**Analysis Workspace**: AN-421930, AN-424997, AN-424194, AN-425515, AN-425254, AN-423174, AN-428834, AN-306540, AN-426014, AN-427801
**Components**: 
**Content Analytics**:
**Guided analysis**: 
**Exports**: AN-422041, AN-421599, AN-422112
**Data views**: 
**Implementation**: 
**Report Builder**: AN-391415, AN-425125
**Reporting**: AN-425817, AN-424362, AN-425752, AN-425278, AN-422249, AN-403446, AN-424727, AN-426791, AN-427985
**Segmentation**: AN-428905, AN-428232
**Scheduled reports**: AN-425484, AN-425137
**Shared metrics and dimensions**: 
**Other**: AN-428833, AN-425074


## Important notices for Customer Journey Analytics Administrators

| Notice | Notice added or updated | Description |
| --- | --- | --- |
| **TLS 1.2 cipher suites removal** | February 11, 2026 | Notice to admins: Adobe plans to remove support for the following TLS 1.2 cipher suites from Adobe data collection servers on May 27, 2026.<ul><li>`TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_256_CBC_SHA`</li></ul><p>No customer action is required for most implementations. This change primarily affects Analytics data sent from legacy native applications that use outdated TLS libraries, and a small number of web visitors on obsolete browsers or operating systems. Removing support for these cipher suites enhances security and aligns Adobe with modern encryption standards. Less than 0.1% of data collection traffic currently relies on these cipher suites.</p> |

## Related resources

* [Previous Customer Journey Analytics release notes for 2025](/help/release-notes/2025.md)
* [Adobe Analytics release notes](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html)
* [Streaming Media Collection release notes](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* [Adobe Experience Cloud release notes](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)
* [Customer Journey Analytics documentation updates](/help/release-notes/doc-changes.md)
