---
title: View the current Customer Journey Analytics release notes
description: Latest CJA release notes
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
---
# Current Customer Journey Analytics (CJA) release notes (September 2022)

**Last update**: September 6, 2022

## Key features

| Feature | Description | [Targeted Date](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| **Cross-region support for Analytics Source Connector** | You can now ingest report suites from any region (United States, United Kingdom, or Singapore). However, these report suites have to be mapped to the same organization as the Experience Platform Sandbox instance in which the source connection is being created. [Learn more](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en) | August 24, 2022 |
| **First Session Reporting** | You can now discover if a particular session was a user's first-ever session. [Learn more](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=en#new-repeat) | August 24, 2022 |
| **Combo Charts visualization in Workspace** |  Combo charts let you compare metrics more easily and intuitively within Workspace. [Learn more](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/visualizations/combo-charts.html?lang=en)  | September 14, 2022 |
| **Customer AI Integration** | Lets you ingest Customer AI models scores in CJA for further analysis in CJA Analysis workspace. Learn more - coming soon | October 3, 2022  |
| **Attribution AI Integration** | Lets you ingest the Attribution AI models scores in CJA for further analysis in CJA Analysis workspace. Learn more - coming soon | October 3, 2022 |

{style="table-layout:auto"}

## Fixes

AN-298412

## Important notices for CJA Administrators

| Notice | Notice added or Updated | Description |
| --- | --- | --- |
| **Improved IP-to-geolocation mapping** | July 11, 2022 | Adobe's vendor for IP lookups, Digital Element, is upgrading to a new improved dataset (NetAcuity Pulse) for IP-to-geolocation mapping. Adobe Analytics will adopt this new dataset in the **October 2022** timeframe. The new database will be more accurate than previous versions. Some IP-to-geo mappings will change/improve when the new database is adopted.<p> CJA data provided through the Analytics Source Connector will also automatically take advantage of the new mappings. |

{style="table-layout:auto"}

>[!MORELIKETHIS]
>[Customer Journey Analytics documentation updates](/help/release-notes/doc-changes.md)
