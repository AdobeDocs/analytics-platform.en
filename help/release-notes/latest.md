---
title: View the current Customer Journey Analytics release notes
description: Latest Customer Journey Analytics release notes
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
---
# Current Adobe Customer Journey Analytics release notes (October 2023)

**Last update**: October 4, 2023

These release notes cover the release period of October 4, 2023 through October 24, 2023. Adobe Customer Journey Analytics releases operate on a [continuous delivery model](releases.md) which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## New or updated features 

| Feature | Description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Export full tables to the cloud** | Customer Journey Analytics Full Table Export allows you to export millions of Workspace rows to cloud destinations. Exporting full tables offers one-time or scheduled delivery of data tables designed within Workspace with support for up to five breakdowns, five metrics, filters, and calculated metrics, all in a concatenated table. It is the evolution of Data Warehouse reports in Adobe Analytics, with many new, often-requested features that are not available in Data Warehouse today. Cloud export options include:<ul><li>Adobe Experience Platform Data Landing Zone</li><li>Amazon S3 Role ARN</li><li>Google Cloud Platform</li><li>Azure SAS</li><li>Azure RBAC</li><li>Snowflake</li></ul>For more information, see [Export Customer Journey Analytics reports to the cloud](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/export/export-cloud.html).| October 4, 2023 | October 19, 2023 |
| **New columns available when managing components** | The following new columns are now available in the [Calculated metrics manager](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-calcmetrics/cm-workflow/cm-manager.html) and the [Filters manager](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/manage-filters.html) when managing components:<ul><li>Used in</li><li>Last used</li></ul>This information can help you determine whether a component is valuable to users in your organization, where it is used, and if it needs to be deleted or modified. You can use the Data Dictionary along with this information to help you keep track of and better understand how components are being used in your organization. | September 23, 2023 | October 4, 2023 |
| **Reporting Activity Manager** | The Reporting Activity Manager lets you see the reporting capacity for each connection in your organization. It provides administrators with detailed visibility into reporting consumption in order to easily diagnose and fix capacity issues during peak reporting times. Key features of the Reporting Activity Manager include:<ul><li>Cancel current reporting requests (including requests from guided analyses and full table exports)</li><li>Restrict subsequent requests for a defined time period</li></ul>In addition to canceling current requests, administrators can now restrict requests for a defined time period. Administrators can restrict requests by request, project, or user.  Learn more (coming soon) | October 17, 2023 | October 23, 2023 |
| **Migrate Adobe Analytics projects and any included components to Customer Journey Analytics** | You can now migrate your Adobe Analytics projects to Customer Journey Analytics. This process simplifies the transition from Adobe Analytics to Customer Journey Analytics. When you migrate projects to Customer Journey Analytics, assets are mapped from an Adobe Analytics report suite to a Customer Journey Analytics data view. **You migrate projects to Customer Journey Analytics from the Adobe Analytics interface.** [Learn more](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration.html) | N/A | October 4, 2023 |
| **Adobe Product Analytics: Show/Hide Series** |  Click on the chart legend or table rows to control the visibility of series in your visualizations.  Learn more (coming soon) | N/A | October 3, 2023 |
| **Annotations in Adobe Product Analytics** | Guided analysis projects now support the ability to view annotations. Refer to each view type in [Guided analysis](/help/guided-analysis/overview.md) for details around how it interacts with annotations. Learn more (coming soon)| N/A | October 3, 2023 |

{style="table-layout:auto"}

## Fixes in Customer Journey Analytics

AN-325940; AN-326468; AN-328301; AN-328640; AN-329370 

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
