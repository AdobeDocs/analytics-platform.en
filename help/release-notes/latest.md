---
title: View the current Customer Journey Analytics release notes
description: Latest Customer Journey Analytics release notes
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
---
# Current Adobe Customer Journey Analytics release notes (September 2023)

**Last update**: September 7, 2023

These release notes cover the release period of September 13, 2023 through October 3, 2023. Adobe Customer Journey Analytics releases operate on a [continuous delivery model](releases.md) which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## New or updated features 

| Feature | Description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Support for A4T classifications in the Analytics Source Connector** | We are adding a correlation ID for easy joining of classification data for Adobe Target activities and experience events. | N/A | September 13, 2023 |
| **Updates to derived fields** | The following updates were made to the derived fields functionality:<ul><li>The [!UICONTROL Lookup] function has been renamed to [!UICONTROL Classify], with additional options to load CSV data. **(Releases Sept. 27, 2023)**</li><li>Additional functions are available to use when defining a derived field: [!UICONTROL Trim], [!UICONTROL Lowercase] and [!UICONTROL Lookup].</li><li>Derived field definitions now also support fields from [!UICONTROL Lookup] and [!UICONTROL Profile] datasets.</li></ul>[Learn more](/help/data-views/derived-fields/derived-fields.md) | N/A | September 13, 2023 |
| **Annotations in Product Analytics** | Guided analysis projects now support the ability to view annotations. Towards the end of September, see each respective view type in [Guided analysis](/help/guided-analysis/overview.md) for details around how it interacts with annotations. | N/A | September 27, 2023 |
| **Experience Edge device lookups** | Enable automatic device type data collection through the Experience Platform Edge network. This Experience Edge service benefits Customer Journey Analytics along with other Experience Platform apps. | N/A | September 27, 2023  |
| **Connections Details page - skipped records** | This capability gives you insight into why certain records were skipped during data ingestion. Possible reasons can include big visitor IDs (1 million+ records), missing timestamps and missing person IDs. (Documentation to follow) | N/A | September 29, 2023 |

{style="table-layout:auto"}

## Fixes in Customer Journey Analytics

AN-310972; AN-319509; AN-322245; AN-323411; AN-323719; AN-326101; AN-326125; AN-326888


## Important notices for Customer Journey Analytics Administrators

| Notice | Notice added or updated | Description |
| --- | --- | --- |
| N/A | N/A| N/A |

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
