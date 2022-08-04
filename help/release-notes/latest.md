---
title: View the current Customer Journey Analytics release notes
description: Latest CJA release notes
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
---
# Current Customer Journey Analytics (CJA) release notes (July 2022)

**Last update**: August 4, 2022

## Key features

| Feature | Description | [Targeted Date](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| Support for numeric fields as lookup keys and lookup values | Useful if you want to classify string values with a numeric field such as a COGS or margin on a product SKU. Allowing metrics from lookups helps you get these data points into reporting. [Learn more](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html#numeric) | July 20, 2022 |
| Media Concurrent Viewer panel | Understand where peak concurrency occurred or where drop-offs happened. Get valuable insight into the quality of content and viewer engagement, and help with troubleshooting or planning for volume and scale. [Learn more](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-concurrent-viewers.html) | **August 9, 2022** |
| Media Playback Time Spent panel | Media Playback Time Spent provides valuable insight into viewer engagement and enables media organizations to derive deeper, more granular insights with minute-by-minute user engagement through advanced time spent analysis with day-parting capabilities. You can observe the amount of time spent viewing your media streams at a specific point in time. You can split the playback duration by different granularities, including new 5 minute, 15 minute, and 30-minute granularities.  [Learn more](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-playback-timespent/media-playback-time-spent.html) | **August 9, 2022** |
| First vs. Repeat Session Reporting | You can now discover if a particular session was a user's first-ever session. [Learn more](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=en#new-repeat) | August 17, 2022 |

{style="table-layout:auto"}

## Fixes

AN-288455; AN-288828; AN-289323

## Important notices for CJA Administrators

| Notice | Notice added or Updated | Description |
| --- | --- | --- |
| **Improved IP-to-geolocation mapping** | July 11, 2022 | Adobe's vendor for IP lookups, Digital Element, is upgrading to a new improved dataset (NetAcuity Pulse) for IP-to-geolocation mapping. Adobe Analytics will adopt this new dataset in the **October, 2022**, timeframe. The new database will be more accurate than previous versions. Some IP-to-geo mappings will change/improve when the new database is adopted.<p> CJA data provided through the Analytics Source Connector will also automatically take advantage of the new mappings. |

{style="table-layout:auto"}

>[!MORELIKETHIS]
>[Customer Journey Analytics documentation updates](/help/release-notes/doc-changes.md)
