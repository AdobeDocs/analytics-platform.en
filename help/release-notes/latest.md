---
title: View the current Customer Journey Analytics release notes
description: Latest Customer Journey Analytics release notes
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
---
# Current Adobe Customer Journey Analytics release notes (July 2024)

**Last update**: July 24, 2024

These release notes cover the release period of July 17, 2024 through August 2024. Adobe Customer Journey Analytics releases operate on a [continuous delivery model](releases.md), which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## New or updated features 

| Feature | Description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Intelligent Alerts** | Intelligent Alerts are now available in Customer Journey Analytics, allowing you to be notified immediately when abnormal events occur in your data.<p>You can set alerts to be triggered based on anomaly thresholds, changed percentages, or specific data points. Alerts provide granular controls that integrate with Anomaly Detection, triggering when you need them most.</p><p>The process of using Intelligent Alerts in Customer Journey Analytics is nearly identical to using Intelligent Alerts in Adobe Analytics. One key difference is that hourly alerts are not available in Customer Journey Analytics. This difference is because data ingestion for the various kinds of event data that can be ingested is complete only after a delay, typically ranging from 3 to 9 hours past the data event time.</p><p>(Updated documentation links to follow)</p><!--<p>[Learn more](/help/analysis-workspace/c-intelligent-alerts/intellligent-alerts.md)</p> --> |  | TBD |
| **Administrator settings to control the accounts and locations that are used when exporting reports to the cloud** | A new ["Admin settings" tab in the Locations manager](/help/components/exports/manage-export-locations.md#configure-company-wide-settings-administrators-only) gives administrators control over whether users can create and edit accounts and locations.<p>These settings apply when users [configure cloud export accounts](/help/components/exports/cloud-export-accounts.md) and [configure cloud export locations](/help/components/exports/cloud-export-locations.md).</p><p>Administrators can also limit the types of accounts that users can create and use. Account types include Google Cloud Platform, Azure RBAC, Amazon S3, AEP Data Landing Zone, Snowflake, and so forth.</p><p>Previously, any user could create, edit, and use accounts and locations for any type of account.</p> | July 11, 2024 | July 19, 2024 |
| **Summary-level Data Sources** | Allows you to bring in time-series data that does not have a person ID. This time-series data can be used to support various use cases, such as:<ul><li>Presenting high-level performance indicators as part of or next to event-level data. This can include something as simple as a date and a single metric value or include multiple dimensions and metrics, like  advertising impressions, email opens, advertising spend, cost of good sold, and more.</li><li>Uploading targets or goals at a daily, weekly, monthly or quarterly basis and positioning these targets or goals against event-level metrics to help visualize how metrics are trending against the organizational targets or goals.</li></ul><p>(Updated documentation links to follow)</p> |  | July 31, 2024 |
| **Derived Fields - Deduplicate function** | The [Deduplicate function](/help/data-views/derived-fields/derived-fields.md#deduplicate) in Derived Fields helps you to prevent counting a value multiple times.|  | July 17, 2024 |
| **Guided Analysis provisioning for CJA customers** | Guided analysis enables users to self-serve high quality data and insights about the customer journey through guided workflows, built on the cross-channel data of Customer Journey Analytics. <p>Cross-functional teams, from marketing to product, can connect in real time to use and understand these reports.</p><p>Up to 11 guided analysis views are now available within CJA packages. [Learn more](https://experienceleague.adobe.com/en/docs/analytics-platform/using/guided-analysis/overview)</p> |  | July 17, 2024 |
| **Share accounts and locations that are used for export and import** | Users can now make the accounts and locations they create available to all users in their organization. Only account and location owners and system administrators can edit and delete accounts and locations. Previously, accounts and locations could be used only by the user who created them. These settings are available when users [configure cloud export accounts](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/exports/cloud-export-accounts) and [configure cloud export locations](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/exports/cloud-export-locations).| June 12, 2024 | Mid-July 2024 |
|**Audiences are published to a new "Audiences" section in Experience Platform** | Audiences that are published from Customer Journey Analytics are now available in the new "Audiences" section in Adobe Experience Platform.<p>Previously, audiences that were published from Customer Journey Analytics were available in Experience Platform under the "Segments" section.</p><p>This improvement provides the following benefits:</p><ul><li>Audiences no longer have a 1-hour delay before they appear in Experience Platform; they are available seconds after they are published.</li><li>Audiences can be sorted in Experience Platform by using the "Origin" column, which displays the application from which the audience was originally published.</li><li>Filter and sort options in Experience Platform enable you to find the relevant audiences more quickly.</li></ul> <p>(Documentation link to follow)</p>|  | TBD |

{style="table-layout:auto"}

## Fixes in Customer Journey Analytics

AN-306000; AN-288748; AN-351547; AN-351110

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
