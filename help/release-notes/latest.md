---
title: View the current Customer Journey Analytics release notes
description: Latest Customer Journey Analytics release notes
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
---
# Current Adobe Customer Journey Analytics release notes (June 2024)

**Last update**: June 12, 2024

These release notes cover the release period of June 6, 2024 through July 2024. Adobe Customer Journey Analytics releases operate on a [continuous delivery model](releases.md) which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## New or updated features 

| Feature | Description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **AI Assistant for Customer Journey Analytics** | Allows you to ask natural-language questions in the Customer Journey Analytics UI and get answers based on Customer Journey Analytics documentation. [Learn more](/help/ai-assistant.md)| | June 6, 2024 | 
| **Graph-based stitching: Stitching Using UIS Graph Export** | Through Graph-based stitching, you can use the Identity graph to get a better view of the customer journey by:<ul><li>Joining datasets with different identifiers without having to extract, transform and load additional data to reflect a single identifier.</li><li>Improving coverage of preferred or golden identity for a single dataset by sharing identities across datasets.</li><li>Aligning profiles created in Real-Time Customer Data Platform and Journey Optimizer with people in Customer Journey Analytics.</li></ul>(Documentation link to follow) |  | June 28, 2024 |
| **B2B Schema Transformation for Person to Account** | To support person-based lookups on B2B data (including accounts, opportunities, marketing lists and campaigns), you can transform B2B lookup datasets. This transformation is available only for datasets with data for B2B lookup schemas, based on the following classes:<ul><li>XDM Business Account Person Relation</li><li>XDM Business Opportunity Person Relation</li><li>XDM Business Marketing List Members</li><li>XDM Business Campaign Members</li></ul>[Learn more](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-connections/transform-datasets-b2b-lookups) |  | June 5, 2024 |
| **Derived Fields - Math Function** |  Lets you do simple math operators within data views to answer questions about your users. For example, you can combine product, warranty and shipping revenue. <p>[Learn more](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/derived-fields#math)</p>| | June 5, 2024 |
| **Derived Fields - Derived Fields - Next or Previous Function** | Lets you look at what the next or previous value is. For example, what were the previous marketing channels someone interacted with prior to the selected marketing channel? Or, what was the page users interacted with prior to or after the selected page? What is the most popular channel users interact with before going in-store? <p>[Learn more](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/derived-fields#next-or-previous)</p>| | June 12, 2024 |
| **Derived Fields - Summary Function** | Provides the ability to apply aggregation-type functions to metrics or dimensions at event, session, and user levels. (Documentation link to follow) | | June 26, 2024 |
| **Derived Fields - Deduplication Function** | Helps prevent the repeated counting of a value. Can be applied at the User or Session level or based on the unique value of a dimension. (Documentation link to follow) |  | June 26, 2024 |
| **Ingestion Prioritization and Latency** | You can now ingest your events data in Customer Journey Analytics within 90 minutes (SLT), regardless of whether the data is 24 hours, 48 hours, or 7 days old. Note that this capability differs based on the SKU package your company purchased:<ul><li>CJA Priority Ingestion Basic: 24-hour-old data within 90-minute SLT processing (available for CJA Foundation and CJA Select)</li><li>CJA Priority Ingestion Intermediate: 72-hour-old data within 90-minute SLT processing (available for CJA Prime)</li><li>CJA Priority Ingestion Advanced: 1-week-old data within 90-minute SLT processing (available for CJA Ultimate)</li></ul>|  | June 12, 2024 |
| **Administrator settings to control accounts and locations that are used for export and import** | A new ["Admin settings" tab in the Locations manager](https://experienceleague.adobe.com/en/docs/analytics/components/locations/locations-manager) gives administrators control over whether users can create and edit accounts and locations. These settings apply when users [configure cloud import and export accounts](https://experienceleague.adobe.com/en/docs/analytics/components/locations/configure-import-accounts) and [configure cloud import and export locations](https://experienceleague.adobe.com/en/docs/analytics/components/locations/configure-import-locations). Administrators can also limit the types of accounts (Google Cloud Platform, Azure RBAC, Amazon S3, and so forth) that users can create and use.<p>Previously, any user could create, edit, and use accounts and locations for any type of account. |  | June 18, 2024 |
| **Share accounts and locations that are used for export and import** | Users can now make the accounts and locations they create available to all users in their organization. Only account and location owners and system administrators can edit and delete accounts and locations. Previously, accounts and locations could be used only by the user who created them. These settings are available when users [configure cloud export accounts](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/exports/cloud-export-accounts) and [configure cloud export locations](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/exports/cloud-export-locations).|  | June 18, 2024 |
| **Select multiple filters when they are available in the drop-down menu in a freeform table** |When multiple filters have been added to a freeform table as a drop-down menu, users of the freeform table can now select more than one filter at a time. The freeform table is filtered to include any of the selected filters. Previously, users could select only one filter at a time in a filter drop-down menu.<p>(Documentation link to follow.)<!---For more information, see "Add filters to a project" in "Use components in Analysis Workspace."---> |  | June 19, 2024 |
| **Table of contents for Workspace projects** | A new table of contents is now available for projects. The table of contents provides links that enable users to quickly jump to panels and visualizations within the project. The table of contents can be enabled for individual projects or for all projects for a given user.<p>(Documentation link to follow.)<!---For more information, see "Display the project table of contents" in "Create projects".---> |  | June 19, 2024 |
| **Create hyperlinks for dimension items in a freeform table** |<ul><li>You can create hyperlinks for one or more dimension items to make them clickable within a freeform table in Analysis Workspace. </li><li>You can create hyperlinks for dimension items that have URL values, or you can create custom URLs for dimension items that have non-URL values.</li><li>You can create dynamic custom URLs for multiple dimension items by using variables. Variables can reference the value of a dimension item or they can reference the breakdown dimension.</li></ul>(Documentation link to follow.)<!---For more information, see "Add hyperlinks to dimensions in a freeform table."---> |  | June 19, 2024 |
|**Audiences are published to a new "Audiences" section in Experience Platform** | Audiences that are published from Customer Journey Analytics are now available in the new "Audiences" section in Adobe Experience Platform.<p>Previously, audiences that were published from Customer Journey Analytics were available in Experience Platform under the "Segments" section.</p><p>This improvement provides the following benefits:</p><ul><li>Audiences no longer have a 1-hour delay before they appear in Experience Platform; they are available seconds after they are published.</li><li>Audiences can be sorted in Experience Platform by using the "Origin" column, which displays the application from which the audience was originally published.</li><li>Filter and sort options in Experience Platform enable you to more quickly find the relevant audiences.</li></ul> <p>(Documentation link to follow)</p>|  | July 14, 2024 |

{style="table-layout:auto"}

## Fixes in Customer Journey Analytics

AN-345454; AN-349816; AN-349905; AN-350617

## Important notices for Customer Journey Analytics Administrators

| Notice | Notice added or updated | Description |
| --- | --- | --- |
| N/A | | | 

{style="table-layout:auto"}

## Related resources

* [Previous Customer Journey Analytics release notes for 2024](/help/release-notes/2024.md)
* [Adobe Analytics release notes](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html)
* [Media Analytics release notes](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* [Adobe Experience Cloud release notes](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)
* [Customer Journey Analytics documentation updates](/help/release-notes/doc-changes.md)
