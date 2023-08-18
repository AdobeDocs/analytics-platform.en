---
title: View the current Customer Journey Analytics release notes
description: Latest Customer Journey Analytics release notes
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
---
# Current Adobe Customer Journey Analytics release notes (August 2023)

**Last update**: August 17, 2023

These release notes cover the release period of August 9 to September 13, 2023. Adobe Customer Journey Analytics releases operate on a [continuous delivery model](releases.md) which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## New or updated features 

| Feature | Description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Report Builder enhancements**  | <ul><li>You can download a scheduled task from the Workbooks tab then title it, save it, and share it. [Learn more](/help/report-builder/schedule-reportbuilder.md)</li><li>Start date as dimension allows you to surface the start date of the data block as a dimension in the data block output. [Learn more](/help/report-builder/create-a-data-block.md) </li></ul>| N/A | August 17, 2023 |
| **Currency Conversion** |  Customer Journey is adding the  ability to support multiple currencies. You can convert a currency into another currency in data views settings. [Learn more](/help/data-views/component-settings/format.md) | N/A | August 31, 2023 |
| **Support for A4T classifications in the Analytics Source Connector** | We are adding a correlation ID for easy joining of classification data for Adobe Target activities and experience events. | N/A | August 31, 2023 |
| **Reporting Activity Manager** | Provides administrators with detailed visibility into reporting consumption for each connection, allowing admins to easily diagnose and then fix capacity issues during peak reporting times. | N/A | September 6, 2023 |
| **PowerBI & Tableau access to Customer Journey Analytics data views** | The Adobe Customer Journey Analytics SQL Connector enables SQL access to data views that you have defined in Customer Journey Analytics. Data engineers and analysts more familiar with Power BI, Tableau, or other business intelligence and visualization tools can now create reports and dashboards based on the same data views that Customer Journey Analytics users are using for their Analysis Workspace projects. [Learn more](/help/data-views/sql-connector.md)| N/A | September 13, 2023 |

{style="table-layout:auto"}

## Fixes in Customer Journey Analytics

AN-309141; AN-319198; AN-324576; AN-324939; AN-325138; AN-325554

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
