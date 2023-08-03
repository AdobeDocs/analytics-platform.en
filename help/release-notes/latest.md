---
title: View the current Customer Journey Analytics release notes
description: Latest Customer Journey Analytics release notes
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
---
# Current Adobe Customer Journey Analytics release notes (July 2023)

**Last update**: July 13, 2023

Adobe Customer Journey Analytics releases operate on a [continuous delivery model](releases.md) which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## New or updated features 

| Feature | Description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Report Builder enhancements**  | <ul><li>Download scheduled tasks from the History tab where you can view the history of scheduled tasks. Download the workbook from that task. [Learn more]</li><li>Start date as dimension: allows users to surface the start date of the data block as a dimension in the data block output. [Learn more]</li></ul>| N/A | August 17, 2023 |
| **Reporting Activity Manager** | Provides administrators with detailed visibility into reporting consumption for each connection, allowing admins to easily diagnose and then fix capacity issues during peak reporting times. | N/A | September 6, 2023 |

{style="table-layout:auto"}

## Fixes in Customer Journey Analytics

AN-324576; AN-325138; 

## Important notices for Customer Journey Analytics Administrators

| Notice | Notice added or updated | Description |
| --- | --- | --- |
| **Changes to how Customer Journey Analytics processes data** | June 22, 2023| We recently changed how we process data in Customer Journey Analytics.<ul><li>Any event data with a timestamp less than 24 hours old is streamed in.</li><li>Any event data with a timestamp more than 24 hours old (even if it's in the same batch as newer data) is considered backfill and will be ingested at a lower priority.</li></ul> |

{style="table-layout:auto"}

## End-of-life (EOL) notices

| EOL Product or Feature | Date added or updated | Description |
| --- | --- | --- |
| **Migration to Adobe I/O OAuth Server-to-Server credentials** | May 11, 2023 |  Adobe Analytics API, Customer Journey Analytics API, and Livestream customers using Adobe I/O JWT credentials must migrate to Adobe I/O OAuth Server-to-Server credentials by **January 1, 2025**. Adobe I/O will not allow new JWT credentials to be created beginning May 1, 2024. Customers using JWT must create a new OAuth Server-to-Server credential or migrate their existing JWT credential to an OAuth Server-to-Server credential. Customers must also update their client applications to use the new OAuth Server-to-Server credentials. <ul><li>[Migrating from Service Account (JWT) credentials](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Using the new OAuth Server-to-Server credentials](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[FAQs](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}


## Related resources

* [Previous Customer Journey Analytics release notes for 2023](/help/release-notes/2023.md)
* [Adobe Analytics release notes](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=en)
* [Media Analytics release notes](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* [Adobe Experience Cloud release notes](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)
* [Customer Journey Analytics documentation updates](/help/release-notes/doc-changes.md)
