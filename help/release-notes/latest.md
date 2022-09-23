---
title: View the current Customer Journey Analytics release notes
description: Latest CJA release notes
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
---
# Current Customer Journey Analytics (CJA) release notes (September 2022)

**Last update**: September 14, 2022

Customer Journey Analytics releases operate on a [continuous delivery model](releases.md) which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## Related resources

* [Previous CJA release notes for 2022](/help/release-notes/2022.md)

* [Adobe Analytics release notes](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=en)

* [Media Analytics release notes](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)

* [Adobe Experience Cloud release notes](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)

## Key features

| Feature | Description | [Targeted Date](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| **Cross-region support for Analytics Source Connector** | You can now ingest report suites from any region (United States, United Kingdom, or Singapore). However, these report suites have to be mapped to the same organization as the Experience Platform Sandbox instance in which the source connection is being created. [Learn more](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html) | August 24, 2022 |
| **First Session Reporting** | Discover if a particular session was a user's first-ever session. [Learn more](/help/data-views/data-views-usecases.md) | August 24, 2022 |
| **Experimentation Panel for CJA** | This new Workspace panel allows CJA users to evaluate the lift and confidence of any A/B experiment from any source - online, offline, from Adobe solutions, Adobe Journey Optimizer, and even BYO (bring-your-own) data. [Learn more](/help/analysis-workspace/c-panels/experimentation.md) | [Limited release](/help/release-notes/releases.md) starting September 14, 2022 |
| **Combo Charts visualization in Workspace** | Combo charts let you compare metrics more easily and intuitively within Workspace. [Learn more](/help/analysis-workspace/visualizations/combo-charts.md)  | September 14, 2022 |
| **CJA support for Data Governance labels and policies** | Automates the integration between CJA and Adobe Experience Platform privacy labels and policies. Data labels created on datasets consumed by Platform are surfaced in CJA data views to stop or warn users who create metrics and/or dimensions from sensitive fields. Additionally, when data is exported from CJA (via Workspace or Report Builder reporting, export, API, etc.) additional warnings or labels will be added to notify users that a report contains sensitive information that needs to be treated in a specific way. [Learn more](/help/data-views/data-governance.md)  | September 14, 2022 |

{style="table-layout:auto"}

## Fixes

AN-298412

## Important notices for CJA Administrators

| Notice | Notice added or Updated | Description |
| --- | --- | --- |
| **Improved IP-to-geolocation mapping** | September 9, 2022 | Adobe's vendor for IP lookups, Digital Element, is upgrading to a new improved dataset (NetAcuity Pulse) for IP-to-geolocation mapping. Adobe Analytics will adopt this new dataset on **October 5, 2022**. The new database will be more accurate than previous versions. Some IP-to-geo mappings will change/improve when the new database is adopted.<p> CJA data provided through the Analytics Source Connector will also automatically take advantage of the new mappings. |

{style="table-layout:auto"}

>[!MORELIKETHIS]
>[Customer Journey Analytics documentation updates](/help/release-notes/doc-changes.md)
