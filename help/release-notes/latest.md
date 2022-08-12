---
title: View the current Customer Journey Analytics release notes
description: Latest CJA release notes
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
---
# Current Customer Journey Analytics (CJA) release notes (August 2022)

**Last update**: August 12, 2022

## Key features

| Feature | Description | [Targeted Date](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| **Media Concurrent Viewer panel** | Understand where peak concurrency occurred or where drop-offs happened. Get valuable insight into the quality of content and viewer engagement, and help with troubleshooting or planning for volume and scale. [Learn more](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-concurrent-viewers.html) | August 9, 2022 |
| **Media Playback Time Spent panel** | Media Playback Time Spent provides valuable insight into viewer engagement and enables media organizations to derive deeper, more granular insights with minute-by-minute user engagement through advanced time spent analysis with day-parting capabilities. You can observe the amount of time spent viewing your media streams at a specific point in time. You can split the playback duration by different granularities, including new 5 minute, 15 minute, and 30-minute granularities.  [Learn more](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-playback-timespent/media-playback-time-spent.html) | August 9, 2022 |
| **Audience publishing to Real-time Customer Profile**| Allows you to publish audiences discovered in CJA to Adobe Experience Platform/Real-time Customer Profile for customer targeting and personalization. [Learn more](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/audiences-overview.html?lang=en) | August 17, 2022 | 
| **CJA support for Data Governance labels and policies** | Automates the integration between CJA and Adobe Experience Platform privacy labels and policies. Data labels created on datasets consumed by Platform are surfaced in CJA data views to stop or warn users who create metrics and/or dimensions from sensitive fields. Additionally, when data is exported from CJA (via Workspace or Report Builder reporting, export, API, etc.) additional warnings or labels will be added to notify users that a report contains sensitive information that needs to be treated in a specific way. [Learn more](/help/data-views/data-governance.md) | August 17, 2022 |
| **Date field support in CJA** | Allows CJA to report on date and date-time fields. [Learn more](/help/data-views/data-views-usecases.md#date) | August 17, 2022 |
| **Experiment Panel for CJA (Generic Lift and Confidence)** | This new Workspace panel allows CJA users to evaluate the lift and confidence of any A/B experiment from any source - online, offline, from Adobe solutions, Adobe Journey Optimizer, and even BYO data. More information to follow. | August 24, 2022 |
| **Cross-region support for Analytics Source Connector** | You can now ingest report suites from any region (United States, United Kingdom, or Singapore). However, these report suites have to be mapped to the same organization as the Experience Platform Sandbox instance in which the source connection is being created. [Learn more](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en) | August 24, 2022 |
| **First vs. Repeat Session Reporting** | You can now discover if a particular session was a user's first-ever session. [Learn more](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=en#new-repeat) | August 24, 2022 |

{style="table-layout:auto"}

## Fixes

AN-297141

## Important notices for CJA Administrators

| Notice | Notice added or Updated | Description |
| --- | --- | --- |
| **Improved IP-to-geolocation mapping** | July 11, 2022 | Adobe's vendor for IP lookups, Digital Element, is upgrading to a new improved dataset (NetAcuity Pulse) for IP-to-geolocation mapping. Adobe Analytics will adopt this new dataset in the **October 2022** timeframe. The new database will be more accurate than previous versions. Some IP-to-geo mappings will change/improve when the new database is adopted.<p> CJA data provided through the Analytics Source Connector will also automatically take advantage of the new mappings. |

{style="table-layout:auto"}

>[!MORELIKETHIS]
>[Customer Journey Analytics documentation updates](/help/release-notes/doc-changes.md)
