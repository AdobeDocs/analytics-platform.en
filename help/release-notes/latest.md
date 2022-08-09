---
title: View the current Customer Journey Analytics release notes
description: Latest CJA release notes
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
---
# Current Customer Journey Analytics (CJA) release notes (August 2022)

**Last update**: August 8, 2022

## Key features

| Feature | Description | [Targeted Date](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| **Audience publishing to Real-time Customer Profile**| Allows you to publish audiences discovered in CJA to Adobe Experience Platform/Real-time Customer Profile for customer targeting and personalization. [Learn more](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/audiences-overview.html?lang=en) | August 5, 2022 | 
| **Media Concurrent Viewer panel** | Understand where peak concurrency occurred or where drop-offs happened. Get valuable insight into the quality of content and viewer engagement, and help with troubleshooting or planning for volume and scale. [Learn more](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-concurrent-viewers.html) | August 9, 2022 |
| **Media Playback Time Spent panel** | Media Playback Time Spent provides valuable insight into viewer engagement and enables media organizations to derive deeper, more granular insights with minute-by-minute user engagement through advanced time spent analysis with day-parting capabilities. You can observe the amount of time spent viewing your media streams at a specific point in time. You can split the playback duration by different granularities, including new 5 minute, 15 minute, and 30-minute granularities.  [Learn more](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-playback-timespent/media-playback-time-spent.html) | August 9, 2022 |
| **First vs. Repeat Session Reporting** | You can now discover if a particular session was a user's first-ever session. [Learn more](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=en#new-repeat) | August 17, 2022 |
| **CJA support for Data Governance labels and policies** | Automates the integration between CJA and Adobe Experience Platform privacy labels and policies. Data labels created on datasets consumed by Platform are surfaced in CJA data views to stop or warn users who create metrics and/or dimensions from sensitive fields. Additionally, when data is exported from CJA (via reporting, export, API, etc.) additional warnings or labels will be added to notify users that a report contains sensitive information that needs to be treated in a specific way. | August 17, 2022 |
| **CJA Report Builder support for Data Governance labels and policies** | To follow. | August 17, 2022 |
| **Experiment Panel for CJA (Generic Lift and Confidence)** | Allows customers to analyze the results of A/B tests in CJA. | August 17, 2022 |
| **Date field support in CJA** | Allowing CJA to report on date and datetime fields. | August 17, 2022 |

{style="table-layout:auto"}

## Fixes

TBD

## Important notices for CJA Administrators

| Notice | Notice added or Updated | Description |
| --- | --- | --- |
| **Improved IP-to-geolocation mapping** | July 11, 2022 | Adobe's vendor for IP lookups, Digital Element, is upgrading to a new improved dataset (NetAcuity Pulse) for IP-to-geolocation mapping. Adobe Analytics will adopt this new dataset in the **October 2022** timeframe. The new database will be more accurate than previous versions. Some IP-to-geo mappings will change/improve when the new database is adopted.<p> CJA data provided through the Analytics Source Connector will also automatically take advantage of the new mappings. |

{style="table-layout:auto"}

>[!MORELIKETHIS]
>[Customer Journey Analytics documentation updates](/help/release-notes/doc-changes.md)
