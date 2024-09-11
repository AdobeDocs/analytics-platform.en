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
| **Intelligent Alerts** | Intelligent Alerts in Customer Journey Analytics allow you to be notified immediately when abnormal events occur in your data.<p>You can set alerts to be triggered based on anomaly thresholds, changed percentages, or specific data points. Alerts provide granular controls that integrate with Anomaly Detection, triggering when you need them most.</p><p>The process of using Intelligent Alerts in Customer Journey Analytics is nearly identical to using Intelligent Alerts in Adobe Analytics. One key difference is that hourly alerts are not available in Customer Journey Analytics. This difference is because data ingestion for the various kinds of event data that can be ingested is complete only after a delay, typically ranging from 3 to 9 hours past the data event time. [Learn more](/help/analysis-workspace/c-intelligent-alerts/intellligent-alerts.md)|  | Mid September 2024 |
| **Updates to the Adobe Analytics source connector** | The dataset activity page does not display information about batches since the Analytics Source Connector is entirely managed by Adobe. You can monitor that data is flowing by looking at the metrics around ingested records. Read the guide on [creating a source connection for Analytics data](https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics) for more information. |  | Available now |
| **Usage Analytics** | See how your organization uses Customer Journey Analytics. Enabling this feature creates a dataset in Adobe Experience Platform that collects data when anyone in your organization uses Analysis Workspace. A connection and a data view are also automatically created, giving you access to dimensions like top project types, most active users, and most popular components used in projects. (Documentation link to follow) |  |  Sept. 18, 2024 |
| **Guided analysis: Embed in Workspace** |  Combine multiple guided analyses into a single view in Analysis Workspace. (Documentation link to follow) | September 22, 2024  | October 2, 2024 |


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
