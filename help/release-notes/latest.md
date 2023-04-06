---
title: View the current Customer Journey Analytics release notes
description: Latest CJA release notes
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
---
# Current Customer Journey Analytics (CJA) release notes (April 2023)

**Last update**: April 6, 2023

Customer Journey Analytics releases operate on a [continuous delivery model](releases.md) which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## Key features and updates

| Feature | Description | [Start of Rollout](/help/release-notes/releases.md) | [General Availability](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- | --- |
| **Row/column filtering for Analytics Source Connector streaming** | The Analytics Source Connector in Adobe Experience Platform now allows for filtering of Analytics data which is used to populate profiles in [Real-Time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=en). Row-level filtering helps reduce the number of events associated with profiles. Column-level filtering helps reduce the richness of the events themselves, thus enabling you to optimize the use of profile entitlements. This filtering applies only to data sent to Real-Time Customer Profile and [Identity Service](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=en). **Filtering does not impact the data which is sent to Data Lake for use in applications such as Customer Journey Analytics**. [Learn more](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en#filtering-for-profile) | N/A | March 29, 2023 |
| **Data Dictionary in Analysis Workspace** | The Data Dictionary helps both users and administrators keep track of and better understand the components (dimensions, metrics) in their CJA environment. [Learn more](/help/components/data-dictionary/data-dictionary-overview.md) | March 8, 2023 | **Temporarily unavailable** |
| **Link sharing for projects (no login required) - Private beta access only** | You can now share read-only links to Analysis Workspace projects with people who don't have access to CJA. You can share project links with people outside of your organization, or those within your organization who are not provisioned for CJA. [Learn more](/help/analysis-workspace/curate-share/share-projects.md)<p>To join the private beta, contact your Adobe Account Team. | April 26, 2023 | June 2023 |

{style="table-layout:auto"}
  
## Fixes in Customer Journey Analytics

AN-313118; AN-313390; AN-314135; AN-316381; AN-316811

## Important notices for CJA Administrators

| Notice | Notice added or updated | Description |
| --- | --- | --- |
| N/A | N/A | N/A |

{style="table-layout:auto"}

## Related resources

* [Previous CJA release notes for 2023](/help/release-notes/2023.md)
* [Adobe Analytics release notes](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=en)
* [Media Analytics release notes](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* [Adobe Experience Cloud release notes](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)
* [Customer Journey Analytics documentation updates](/help/release-notes/doc-changes.md)
