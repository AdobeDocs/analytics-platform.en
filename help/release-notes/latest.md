---
title: Current Customer Journey Analytics release notes
description: View the latest Customer Journey Analytics release notes
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
---
# Current Adobe Customer Journey Analytics release notes (April 2025)

**Last update**: April 16, 2025

These release notes cover the release period of March 27 to May 15, 2025. Adobe Customer Journey Analytics releases operate on a [continuous delivery model](releases.md), which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## New or updated features 

| Feature | Description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Updates to "No Value" line item on numeric dimensions** | For numeric dimensions, this update lets you<ul><li>Use the "No Value" dimension item in a segment.</li><li>Perform a breakdown in a report on the "No Value" line item.</li></ul> [Learn more](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/component-settings/no-value-options#numeric)  | March 27, 2025 |
| **Adobe Content Analytics** |  Adobe Content Analytics allows you to quickly and easily investigate large volumes of content data to uncover trends, spot anomalies, identify content fatigue, and gain insights from content exposure.<p>Out of the box, you can save time with pre-built reporting templates and new features like Asset Inspector. This capability lets you not only visualize the asset in-line with your data, but also open each asset for summarized details including performance, placements, attributes and more.<p>You can investigate this new set of content data within the context of the complete customer journey to answer important business questions, assess content performance, enhance segmentation, identify optimization opportunities, and define new audiences for activation.<p>Content Analytics is an add-on to Customer Journey Analytics. [Learn more](https://experienceleague.adobe.com/en/docs/analytics-platform/using/content-analytics/content-analytics) |  | March 27, 2025 |
| **Media Collection: Adobe Source Connector updates for new Media Reporting XDM** | The Analytics Source Connector automatically maps streaming media data in Adobe Analytics to the same fields used by the Web SDK. Previously, data was mapped to both the old and new locations, but only the new location will be used in the future. [Learn more](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/xdm-var-mapping) |  | March 31, 2025 |
| **Updated XDM fields for collecting Streaming Media data into Adobe Experience Platform** | A new XDM field group, `mediaReporting`, is available for collecting Streaming Media data into Adobe Experience Platform. The new `mediaReporting` field group replaces the `media.mediaTimed` field group that was previously used.<p>During a transitional period of three months, data ingestion on `media.mediaTimed` fields will continue. However, at the end of July 2025, `the media.mediaTimed` fields will be fully deprecated and no longer visible in the Adobe Experience Platform Schema UI, and data will only be sent using the `mediaReporting` fields.<p>Customers who implemented the Analytics source connector to collect Streaming Media data into Platform before April 22, 2025, must migrate their existing configurations to send data using the new field group. This migration must be complete by the end of July 2025. Please contact your Adobe Consulting Services or Account team for migration support. No action is required for customers who implement the Analytics source connector after April 22, 2025. |  | April 22, 2025  |
| **Terminology change: "Filters" to "Segments"** | Previously, Adobe Customer Journey Analytics referred to segments as "filters". This terminology has now been brought in line with Adobe Analytics. "Filters" are now called "segments". (Obviously, search filters are still called "filters".) The UI has been updated and the documentation is in the process of being updated.|  | April 16, 2025 |
| **Stitching: Retrieve persistent and transient IDs from XDM IdentityMap** |  This feature provides support for using identities stored in the XDM identityMap in the stitching process. The identityMap can be used for the persistent or transient ID for field-based stitching and can be used for the persistent ID for graph-based stitching.  You can use either a specific namespace or primary identity from the identityMap. (Documentation link to follow)|  | April 25, 2025 |
| **Shared metrics and dimensions across data views** | Allows you to apply dimension and metric settings across multiple data views. Changes made to a shared dimension or metric apply to all instances of that dimension or metric across all applicable data views. This interface allows Customer Journey Analytics admins to more easily manage components when many data views are used. (Documentation link to follow) |  | April 30, 2025 |


## Fixes in Customer Journey Analytics

**Admin Console**: AN-370228
**Analysis Workspace**: AN-371933; AN- 371933; AN-371979
**Audiences**: AN-373032
**Component settings**: AN-367400
**Derived fields**: AN-370614; AN-370959
**Export locations**: AN-371670
**Full table export**: AN-360492; AN-369204; AN-370755;AN-372294; AN-372363; AN-372754; AN-373040; AN-373081; AN-373168
**Journey Canvas**: AN-373294
**Mobile app**: AN-363169; AN-368496; AN-371766
**Product usage**: AN-369501
**Reporting**: AN-369085; AN-371094; AN-372580


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
