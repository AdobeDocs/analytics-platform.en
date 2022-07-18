---
title: View the current Customer Journey Analytics release notes
description: Latest CJA release notes
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
---
# Current Customer Journey Analytics (CJA) release notes (July 2022)

**Last update**: July 13, 2022

>[!NOTE]
>
>This page contains pre-release information and is subject to change.

## Key features

| Feature | Description | [Targeted Date](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| First vs. Repeat Session Reporting | You can now discover if a particular session was a user's first-ever session. [Learn more](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=en#new-repeat) | July 20, 2022 |
| Support for numeric fields as lookup keys and lookup values | Useful if you want to classify string values with a numeric field such as a COGS or margin on a product SKU. Allowing metrics from lookups helps you get these data points into reporting. [Learn more](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html#numeric) | July 20, 2022 |

## Fixes

AN-288455; AN-288828; AN-289323

## Important notices for CJA Administrators

| Notice | Added or Updated | Description |
| --- | --- | --- |
| Improved IP-to-geolocation mapping | July 11, 2022 | Adobe's vendor for IP lookups, Digital Element, is upgrading to a new improved dataset (NetAcuity Pulse) for IP-to-geolocation mapping. Adobe Analytics will adopt this new dataset in the October, 2022, timeframe. The new database will be more accurate than previous versions. Some IP-to-geo mappings will change/improve when the new database is adopted.<p> CJA data provided through the Analytics Source Connector will also automatically take advantage of the new mappings. |

>[!MORELIKETHIS]
>[Customer Journey Analytics documentation updates](/help/release-notes/doc-changes.md)
