---
title: View the current Customer Journey Analytics release notes
description: Latest CJA release notes
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
---
# Current Customer Journey Analytics (CJA) release notes (June 2023)

**Last update**: June 9, 2023

Customer Journey Analytics releases operate on a [continuous delivery model](releases.md) which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## Release highlights {#highlights}

| Feature | Description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Intelligent Captions** | Enrich storytelling for users with natural-language summaries of a [!UICONTROL Line] visualization. [Learn more](/help/analysis-workspace/visualizations/intelligent-captions.md)| May 17, 2023 | June 1, 2023 | 
| **Link sharing for projects (no login required)** | You can now share read-only links to Analysis Workspace projects with people who don't have access to Adobe Analytics. This includes sharing with people outside of your organization, or those within your organization who are not provisioned for Adobe Analytics. [Learn more](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html?lang=en#share-public-link) <p>This functionality is enabled by default and can be disabled by the system administrator. [Learn more](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/user-preferences.html?lang=en#company-preferences)</p> | May 3, 2023 | June 6, 2023 |
| **Derived fields** | This represents the initial release of Derived fields. A derived field allows you to define (often complex) data manipulations on the fly, through a customizable rule builder. You can further define the derived field as a component (metric or dimension) in Data views and then use the derived field as a component in Workspace.<p>This release supports a marketing channels template and the following functions:</p><ul><li>Concatenate</li><li>Case When</li><li>Find & Replace</li><li>Lookup</li><li>URL Parse</li></ul> <p>[Learn more](/help/data-views/derived-fields/derived-fields.md)</p> | May 10, 2023 | June 21, 2023 | 
| **PowerBI & Tableau access to CJA data views** | The Customer Journey Analytics (CJA) SQL Connector enables SQL access to data views that you have defined in CJA. Data engineers and analysts more familiar with Power BI, Tableau, or other business intelligence and visualization tools can now create reports and dashboards based on the same data views that CJA users are using for their Analysis Workspace projects. [Learn more](/help/data-views/sql-connector.md)|  | June 30, 2023 |
| **Experience Edge geo lookups** | You will be able to build reports using geolocation data in CJA once Experience Edge Geo Lookups are enabled for your datastream. |  | June 30, 2023 |
| **Expanded lookup support to profile and lookup data** | You will be able to add lookup datasets to not only event datasets, but also to profile and lookup datasets.  | June 21, 2023 | July 12, 2023 |
| **Support for currency conversion** | CJA will support currency conversion as part of formatting a metric component in a data view. | June 21, 2023 | July 19, 2023 |

{style="table-layout:auto"}

## Other new features or updates {#other-new}

| Feature | Description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Adobe Journey Optimizer data views** | CJA Admins have access to some extra data views in CJA, entitled "AJO Data view (Sandbox-name)". These data views are used to power the reports in Adobe Journey Optimizer (AJO). They can also be used to perform deeper analysis of AJO activities in CJA. [Learn more](https://experienceleague.adobe.com/docs/journey-optimizer/using/campaigns/content-experiment/reporting-configuration.html). | | May 25, 2023 |
| **Backfill for non-production sandboxes** | When creating an Analytics Source Connector data flow in a non-production sandbox,  the backfill in non-production sandboxes will be limited to 3 months. It will remain at 13 months for production sandboxes. | N/A | April 26, 2023 | 
| **Link sharing for projects (no login required)** | You can now share read-only links to Analysis Workspace projects with people who don't have access to Adobe Analytics. This includes sharing with people outside of your organization, or those within your organization who are not provisioned for Adobe Analytics. [Learn more](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/share-projects.html?lang=en#share-public-link) <p>This functionality is enabled by default and can be disabled by the system administrator. [Learn more](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/user-preferences.html?lang=en#ims-organization-preferences)</p> | May 3, 2023 | June 6, 2023 |
| **Updated Home screen for the Analytics dashboards app (Mobile App)** | The new updated Home screen allows you to view all of your scorecards in one consolidated scorecard list.  If you have access to more than one organization under one login, all scorecards from your organizations will be available in a single list. [Learn more](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/executive.html#use-dashboards) | N/A | May 10, 2023 | 
| **Derived fields** | This represents the initial release of Derived fields. A derived field allows you to define (often complex) data manipulations on the fly, through a customizable rule builder. You can further define the derived field as a component (metric or dimension) in Data views and then use the derived field as a component in Workspace.<p>This release supports a marketing channels template and the following functions:</p><ul><li>Concatenate</li><li>Case When</li><li>Find & Replace</li><li>Lookup</li><li>URL Parse</li></ul> <p>[Learn more](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/derived-fields.html)</p> | May 10, 2023 | August 2, 2023 | 
| **Report Builder for CJA - Select data view from cell** | This feature allows users to select the data view for a data block from a cell. This is helpful if you create a workbook and you have multiple data views that have similar data construction and you want to be able to reuse a workbook multiple times, with different data views. [Learn more](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/select-data-view.html) | N/A | May 24, 2023 |
| **Updated Learning page for CJA** | The Learning tab on the Customer Journey Analytics landing page now contains content specific to CJA, including content focused on transitioning to CJA from Adobe Analytics.<p>The following additional enhancements are also available on the Learning tab:</p><ul><li>Improved design that shows more learning content on a single page with improved navigation</li><li>Ability to personalize learning content by experience level (Beginner, Intermediate, and Advanced)</li></ul><p>Previously, the Learning tab in CJA contained identical information to the Learning tab in Adobe Analytics.</p> [Learn more](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/landing.html?lang=en#navigate-learning) | N/A | June 30, 2023 |
| **Sort components in Analysis Workspace** | <p>A new Sort option is now available when viewing components either in the left rail or in the Data Dictionary in Analysis Workspace. You can sort components by Recommended (those most commonly used), Alphabetical, or Categorical (type).</p><p>Previously, you could only search or filter components. [Learn more](/help/components/overview.md)</p> | N/A | TBD | 

{style="table-layout:auto"}
  
## Fixes in Customer Journey Analytics

AN-318343; AN-319453

## Important notices for CJA Administrators

| Notice | Notice added or updated | Description |
| --- | --- | --- |
| N/A | N/A | N/A |

## End-of-life (EOL) notices {#eol}

| EOL Product or Feature | Date added or updated | Description |
| --- | --- | --- |
| **Migration to AdobeIO OAuth Server-to-Server credentials** | May 11, 2023 |  Adobe Analytics API, CJA API, and Livestream customers using AdobeIO JWT credentials must migrate to AdobeIO OAuth Server-to-Server credentials by **January 1, 2025**. AdobeIO will not allow new JWT credentials to be created beginning May 1, 2024. Customers using JWT must create a new OAuth Server-to-Server credential or migrate their existing JWT credential to an OAuth Server-to-Server credential. Customers must also update their client applications to use the new OAuth Server-to-Server credentials. <ul><li>[Migrating from Service Account (JWT) credentials](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Using the new OAuth Server-to-Server credentials](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[FAQs](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## Related resources

* [Previous CJA release notes for 2023](/help/release-notes/2023.md)
* [Adobe Analytics release notes](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=en)
* [Media Analytics release notes](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* [Adobe Experience Cloud release notes](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)
* [Customer Journey Analytics documentation updates](/help/release-notes/doc-changes.md)
