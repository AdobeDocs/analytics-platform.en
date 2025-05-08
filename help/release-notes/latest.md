---
title: Current Customer Journey Analytics release notes
description: View the latest Customer Journey Analytics release notes
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
---
# Current Adobe Customer Journey Analytics release notes (May 2025)

**Last update**: May 8, 2025

These release notes cover the release period of April 22 to June 18, 2025. Adobe Customer Journey Analytics releases operate on a [continuous delivery model](releases.md), which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## New or updated features 

| Feature | Description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Customer Journey Analytics B2B Edition** |  Customer Journey Analytics B2B Edition helps B2B companies align their marketing, sales, and product teams by providing actionable account insights that drive revenue growth. With the account placed at the center of the data model, all analysis focuses on the account journey. Adding a new layer of entities (accounts, opportunities, and buying groups) on top of person and time-based events, creates a complete picture of the B2B marketing and revenue lifecycle. [Documentation lonk to follow]|  |  June 18, 2025 |
| **Data Insights Agent**  | The Data Insights Agent, part of the AI Assistant in Customer Journey Analytics, is a generative AI conversation agent. It uses components from your data view and your actual data to quickly and efficiently answer data-centric questions by building relevant visualizations in Analysis Workspace. [Documentation link to follow]|  | May 28, 2025  |
| **Add and view comments in Analysis Workspace projects** | A new [commenting feature](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/build-workspace-project/comment-projects) in Analysis Workspace allows you to share insights and ask questions within the context of an Analysis Workspace project. This can streamline discussions about the data, keeping conversations within the context of the data that is being discussed. You can <ul><li>Comment on any Analysis Workspace project to which you have access</li><li>Comment on a specific point in a visualization or make general comments about a project</li><li>Tag other users to notify them about your comments</li><li>Manage existing comments (edit, pin, resolve, and so forth)</li></ul>Customer Journey Analytics administrators can [disable commenting at the organization level](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/user-preferences#ims-organization-preferences). Project owners can [disable commenting at the project level](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/build-workspace-project/create-projects). |  |  May 29, 2025 |
| **Increase in full table export limits** | Adobe increased the number of columns you can use with [full table export](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/export/export-cloud#comparison-of-full-table-export-in-customer-journey-analytics-to-data-warehouse-in-adobe-analytics) from 5 dimensions and 5 metrics to 10 dimensions and 10 metrics. This applies to all Customer Journey Analytics tiers. There is no change in the entitlements for the number of rows which can be exported. |  |  April 30, 2025 |
| **Updated XDM fields for collecting Streaming Media data into Adobe Experience Platform** | When collecting Streaming Media data into Adobe Experience Platform, the XDM field paths shown under the heading of "XDM Field Path" of the Streaming Media parameters documentation should no longer be used. These field paths are found on the following pages and are marked as "Deprecated": [Audio and video parameters](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters), [Ad parameters](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/ad-parameters), [Chapter parameters](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/chapter-parameters), [Player state parameters](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/player-state-parameters), and [Quality parameters](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/quality-parameters). <p>Instead, customers should migrate to the `mediaReporting` field paths, as shown under the heading of "Reporting XDM Field Path" of the Streaming Media parameters documentation referenced above.<p>During a transitional period of three months, data ingestion on the deprecated XDM field paths will continue. However, at the end of July 2025, deprecated field paths will be fully removed and no longer visible in the Adobe Experience Platform Schema UI, and data will be sent only using the `mediaReporting` field paths.<p>Customers who implemented the Analytics source connector to collect Streaming Media data into Platform before April 22, 2025 must migrate their existing configurations to use the new field paths. This migration must be complete by the end of July 2025. Please contact your Adobe Consulting Services or Account team for migration support. No action is required for customers who implement the Analytics source connector after April 22, 2025.</p> |  | April 22, 2025  |
| **Stitching: Retrieve persistent and transient IDs from XDM IdentityMap** |  This feature provides support for using identities stored in the XDM identityMap in the stitching process. The identityMap can be used for the persistent or transient ID for field-based stitching and can be used for the persistent ID for graph-based stitching.  You can use either a specific namespace or primary identity from the identityMap. Learn more [here](https://experienceleague.adobe.com/en/docs/analytics-platform/using/stitching/fbs#identitymap) and [here](https://experienceleague.adobe.com/en/docs/analytics-platform/using/stitching/gbs#identitymap)|  | April 28, 2025 |
| **Shared metrics and dimensions across data views** | Allows you to apply dimension and metric settings across multiple data views. Changes made to a shared dimension or metric apply to all instances of that dimension or metric across all applicable data views. This interface allows Customer Journey Analytics admins to more easily manage components when many data views are used. [Learn more](/help/data-views/shared-metrics-dimensions/smd-overview.md) |  | April 30, 2025 |
| **Event Depth dimension**  |  A new [Event Depth dimension](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/component-reference#required-standard-components) was added to the list of required standard components for a data view. |  | May 8, 2025 |
| **Analysis Workspace left panel no longer opens and closes on hover** | The left panel in Analysis Workspace is used to add things like components, panels, and visualizations to your project. The option to temporarily open the left panel by hovering over one of the icons on the far left is no longer available. Instead, simply click one of these icons to keep the panel open, then click the same icon to close it. |  | May 29, 2025  |
| **Disable the manifest file when exporting full tables** | Will allow you to disable the manifest file that is included by default when exporting full tables from Analysis Workspace. |  | End of May, 2025 |


## Fixes in Customer Journey Analytics

**Admin Console**: 
**Analysis Workspace**: AN-361874; AN-371360; AN-373079; AN-374382; AN-374447; AN-375277; AN-375680
**Audiences**: AN-372343
**Connections**: AN-373121; AN-372996
**Data deletion**: AN-375450
**Derived fields**: AN-373689
**Export locations**: AN-374167
**Journey Canvas**: AN-373319
**Report Builder**: AN-369786
**Reporting**: AN-377326


## Important notices for Customer Journey Analytics Administrators

| Notice | Notice added or updated | Description |
| --- | --- | --- |
| N/A | | | 

## Related resources

* [Previous Customer Journey Analytics release notes for 2025](/help/release-notes/2025.md)
* [Adobe Analytics release notes](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html)
* [Streaming Media Collection release notes](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* [Adobe Experience Cloud release notes](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)
* [Customer Journey Analytics documentation updates](/help/release-notes/doc-changes.md)
