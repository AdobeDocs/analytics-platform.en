---
title: View the current Customer Journey Analytics release notes
description: Latest Customer Journey Analytics release notes
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
---
# Current Adobe Customer Journey Analytics release notes (September 2024)

**Last update**: September 11, 2024

These release notes cover the release period of September 11, 2024 through early October. Adobe Customer Journey Analytics releases operate on a [continuous delivery model](releases.md), which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## New or updated features 

| Feature | Description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Additional information in the "Used in" column in the calculated metric manager and filter manager** | The "Used in" column in the calculated metric manager and filters manager contains the following new reporting areas:<ul><li>**Report Builder**: Shows the number of calculated metrics or filters that are being used in the Report Builder.</li><li>**Ad hoc components**: Shows the number of ad hoc calculated metrics or ad hoc filters that are being used in projects. These ad hoc calculated metrics and filters (otherwise known as "quick calculated metrics" and "quick filters") can be used only in the project where they were created, so they are reported separately from the "Project" reporting area in the "Used in" column.</li></ul>For more information, see [Calculated metrics manager](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/cja-calcmetrics/cm-workflow/cm-manager) and [Filters manager](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/cja-filters/manage-filters).|  | Sept 11, 2024 |
| **Alerts** | Alerts in Customer Journey Analytics allow you to be notified based on changed percentages or specific data points.<p>Depending on your Customer Journey Analytics package, you can also use alerts to be triggered based on anomaly thresholds. These alerts (also known as "Intelligent Alerts"), provide granular controls that integrate with Anomaly Detection, triggering when you need them most.</p><p>The process of using alerts in Customer Journey Analytics is nearly identical to using alerts in Adobe Analytics. One key difference is that hourly alerts are not available in Customer Journey Analytics. This difference is because data ingestion for the various kinds of event data that can be ingested is complete only after a delay, typically ranging from 3 to 9 hours past the data event time.</p><p>For more information about the differences when using alerts in Customer Journey Analytics from Adobe Analytics, see [Alerts feature comparison](/help/components/c-intelligent-alerts/alerts-feature-comparison.md).</p><p>To learn more about alerts, see [Alerts overview](/help/components/c-intelligent-alerts/intelligent-alerts.md)|  | September 13, 2024 |
| **Updates to the Adobe Analytics source connector** | The dataset activity page does not display information about batches since the Analytics Source Connector is entirely managed by Adobe. You can monitor that data is flowing by looking at the metrics around ingested records. Read the guide on [creating a source connection for Analytics data](https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics) for more information. |  | Available now |
| **Guided analysis: Embed in Workspace** |  Combine multiple guided analyses into a single view in Analysis Workspace. (Documentation link to follow) | October 2, 2024  | October 31, 2024 |
|**Audiences are published to a new "Audiences" section in Experience Platform** | Audiences that are published from Customer Journey Analytics are now available in the new "Audiences" section in Adobe Experience Platform.<p>Previously, audiences that were published from Customer Journey Analytics were available in Experience Platform under the "Segments" section.</p><p>This improvement provides the following benefits:</p><ul><li>Audiences no longer have a 1-hour delay before they appear in Experience Platform; they are available seconds after they are published.</li><li>Audiences can be sorted in Experience Platform by using the "Origin" column, which displays the application from which the audience was originally published.</li><li>Filter and sort options in Experience Platform enable you to find the relevant audiences more quickly.</li></ul> <p>For more information, see [Use Customer Journey Analytics audiences in Experience Platform](/help/components/audiences/publish.md#use-customer-journey-analytics-audiences-in-experience-platform) in the article, [Create and publish audiences](/help/components/audiences/publish.md).</p>|  | October 3, 2024 |

## Fixes in Customer Journey Analytics

AN-352461; AN-355446: AN-355665

## Important notices for Customer Journey Analytics Administrators

| Notice | Notice added or updated | Description |
| --- | --- | --- |
| N/A | | | 

{style="table-layout:auto"}

## Related resources

* [Previous Customer Journey Analytics release notes for 2024](/help/release-notes/2024.md)
* [Adobe Analytics release notes](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html)
* [Streaming Media Collection Add-on release notes](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* [Adobe Experience Cloud release notes](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)
* [Customer Journey Analytics documentation updates](/help/release-notes/doc-changes.md)
