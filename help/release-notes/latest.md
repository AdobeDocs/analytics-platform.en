---
title: View the current Customer Journey Analytics release notes
description: Latest Customer Journey Analytics release notes
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
---
# Current Adobe Customer Journey Analytics release notes (August 2024)

**Last update**: August 14, 2024

These release notes cover the release period of August 14, 2024 through September 2024. Adobe Customer Journey Analytics releases operate on a [continuous delivery model](releases.md), which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## New or updated features 

| Feature | Description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Summary-level Data Sources** | Allows you to bring in time-series data that does not have a person ID. This time-series data can be used to support various use cases, such as:<ul><li>Presenting high-level performance indicators as part of or next to event-level data. This can include something as simple as a date and a single metric value or include multiple dimensions and metrics, like  advertising impressions, email opens, advertising spend, cost of good sold, and more.</li><li>Uploading targets or goals at an hourly or daily basis and positioning these targets or goals against event-level metrics to help visualize how metrics are trending against the organizational targets or goals.</li></ul><p>(Updated documentation links to follow)</p> |  | August 13, 2024 |
|**Audiences are published to a new "Audiences" section in Experience Platform** | Audiences that are published from Customer Journey Analytics are now available in the new "Audiences" section in Adobe Experience Platform.<p>Previously, audiences that were published from Customer Journey Analytics were available in Experience Platform under the "Segments" section.</p><p>This improvement provides the following benefits:</p><ul><li>Audiences no longer have a 1-hour delay before they appear in Experience Platform; they are available seconds after they are published.</li><li>Audiences can be sorted in Experience Platform by using the "Origin" column, which displays the application from which the audience was originally published.</li><li>Filter and sort options in Experience Platform enable you to find the relevant audiences more quickly.</li></ul> <p>(Documentation link to follow)</p>| August 14, 2024 | August 22, 2024 |
| **Intelligent Alerts** | Intelligent Alerts are now available in Customer Journey Analytics, allowing you to be notified immediately when abnormal events occur in your data.<p>You can set alerts to be triggered based on anomaly thresholds, changed percentages, or specific data points. Alerts provide granular controls that integrate with Anomaly Detection, triggering when you need them most.</p><p>The process of using Intelligent Alerts in Customer Journey Analytics is nearly identical to using Intelligent Alerts in Adobe Analytics. One key difference is that hourly alerts are not available in Customer Journey Analytics. This difference is because data ingestion for the various kinds of event data that can be ingested is complete only after a delay, typically ranging from 3 to 9 hours past the data event time.</p><p>(Updated documentation links to follow)</p><!--<p>[Learn more](/help/analysis-workspace/c-intelligent-alerts/intellligent-alerts.md)</p> --> |  | TBD |

{style="table-layout:auto"}

## Fixes in Customer Journey Analytics

AN-354359; AN-351646; AN-346873; AN-352504; AN-353755; AN-354199; AN-354268; AN-354791; AN-354598; AN-354462; AN-354547; 

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
