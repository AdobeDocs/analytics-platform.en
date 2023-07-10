---
title: View the current Customer Journey Analytics release notes
description: Latest Customer Journey Analytics release notes
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
---
# Current Adobe Customer Journey Analytics release notes (July 2023)

**Last update**: July 10, 2023

Adobe Customer Journey Analytics releases operate on a [continuous delivery model](releases.md) which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## New or updated features 

| Feature | Description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Adobe Product Analytics** | A new project type that allows product teams to quickly self-serve their data needs so that they can make more data-driven product decisions. It is built on top of the existing connection and data view workflows in Customer Journey Analytics. No implementation or configuration changes are needed. [Learn more](/help/guided-analysis/overview.md)<p>Product Analytics is a paid add-on to Customer Journey Analytics. If your organization would like to be provisioned to use this feature, contact your Adobe Account Team. | N/A | July 17, 2023 |
| **Derived fields** | This represents the initial release of Derived fields. A derived field allows you to define (often complex) data manipulations on the fly, through a customizable rule builder. You can further define the derived field as a component (metric or dimension) in data views and then use the derived field as a component in Workspace.<p>This release supports a marketing channels template and the following functions:</p><ul><li>Concatenate</li><li>Case When</li><li>Find & Replace</li><li>Lookup</li><li>URL Parse</li></ul> <p>[Learn more](/help/data-views/derived-fields/derived-fields.md)</p> | May 10, 2023 | August 2, 2023 | 
| **Expanded lookup support for Profile and Lookup data** |  Provides the ability to add datasets as lookups of fields within Profile or Lookup datasets. Previously, only Event datasets were supported. [Learn more] | June 21, 2023 | July 12, 2023 |
| **Report Builder enhancements**  | <ul><li>Filter from cell for multiple data blocks. You can change the filters on multiple data blocks from a cell. Use a predefined cell, assign it to multiple data blocks, and update the data based on the filters defined in the cell. [Learn more](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/select-data-view.html?lang=en)</li><li>Show and hide row and column headers. You can show or hide data block table headers, or row and column headers to reformat the table and align data blocks in a report. [Learn more](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/create-a-data-block.html?lang=en#build-the-data-block)</li></ul>| N/A | July 12, 2023 |
| **Experience Edge geo lookups** | Adobe Experience Edge is adding a geo lookup service that provides unified geographic data to all Experience Edge users (Adobe Analytics, Customer Journey Analytics, Adobe Target, Adobe Media Analytics, Adobe Experience Platform, etc.). | N/A | July 26, 2023 |
| **Audience Analysis - Beta** | Customers need a way to analyze segments and audiences that were targeted in particular ways using the Real-Time Customer Profile. Customers of Adobe Journey Optimizer, Real-Time Customer Data Platform, etc., will be able to use Customer Journey Analytics for reporting on their activation efforts. The ability to see whether an activation campaign (email for example) resulted in onsite or offsite conversions is critical to any activation effort. | Beta start: August 1, 2023 | End of year 2023 |

{style="table-layout:auto"}

## Fixes in Customer Journey Analytics

TBD

## Important notices for Customer Journey Analytics Administrators

| Notice | Notice added or updated | Description |
| --- | --- | --- |
| Changes to how Customer Journey Analytics processes data | June 22, 2023| We recently changed how we process data in Customer Journey Analytics.<ul><li>Any event data with a timestamp less than 24 hours old is streamed in.</li><li>Any event data with a timestamp more than 24 hours old (even if it's in the same batch as newer data) is considered backfill and will be ingested at a lower priority.</li></ul> |

{style="table-layout:auto"}

## End-of-life (EOL) notices

| EOL Product or Feature | Date added or updated | Description |
| --- | --- | --- |
| **Migration to AdobeIO OAuth Server-to-Server credentials** | May 11, 2023 |  Adobe Analytics API, Customer Journey Analytics API, and Livestream customers using AdobeIO JWT credentials must migrate to AdobeIO OAuth Server-to-Server credentials by **January 1, 2025**. AdobeIO will not allow new JWT credentials to be created beginning May 1, 2024. Customers using JWT must create a new OAuth Server-to-Server credential or migrate their existing JWT credential to an OAuth Server-to-Server credential. Customers must also update their client applications to use the new OAuth Server-to-Server credentials. <ul><li>[Migrating from Service Account (JWT) credentials](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Using the new OAuth Server-to-Server credentials](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[FAQs](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}


## Related resources

* [Previous Customer Journey Analytics release notes for 2023](/help/release-notes/2023.md)
* [Adobe Analytics release notes](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=en)
* [Media Analytics release notes](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* [Adobe Experience Cloud release notes](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)
* [Customer Journey Analytics documentation updates](/help/release-notes/doc-changes.md)
