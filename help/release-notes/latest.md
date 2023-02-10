---
title: View the current Customer Journey Analytics release notes
description: Latest CJA release notes
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
---
# Current Customer Journey Analytics (CJA) release notes (February 2023)

**Last update**: February 6, 2023

Customer Journey Analytics releases operate on a [continuous delivery model](releases.md) which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## Key features and updates

| Feature | Description | [Start of Rollout](/help/release-notes/releases.md) | [General Availability](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- | --- |
| **Update to CJA Audiences** | After you have created an audience, Adobe creates an Experience Platform streaming segment for each new CJA Audience. A streaming segment will only be created if your organization is set up for streaming segmentation. [Learn more](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/publish.html#after-audience-created) | N/A | February 3, 2023 |
|  **Hide comparison date ranges in Mobile Scorecards** |  With Mobile Scorecards, you can now hide comparison date ranges. | N/A/ | February 8, 2023 |
| **Calendar updates in Workspace** |<ul><li>Anchor Panel Dates: You can make the date range components relative to the panel calendar. [Learn more](/help/components/date-ranges/calendar.md)</li><li>Calendar styling updates: The calendar styles throughout the UI have been upgraded to present a more consistent and easy-to-use workflow.</li><li>Calendar formula updates: If you use relative dates, all calendar formulas will reflect the start of the panel date range. [Learn more](/help/components/date-ranges/calendar.md)</li></ul> | N/A |  February 8, 2023 |
| **Row/column filtering for Adobe Analytics Source Connector streaming** | The Analytics Source Connector in Adobe Experience Platform now allows for filtering of Analytics data which is used to populate profiles in [Real-Time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=en).<p>Row-level filtering helps reduce the number of events associated with profiles. Column-level filtering helps reduce the richness of the events themselves, thus enabling you to optimize the use of profile entitlements. This filtering applies only to data sent to Real-Time Customer Profile and [Identity Service](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=en).<p>**Filtering does not impact the data which is sent to Data Lake for use in applications such as Customer Journey Analytics**. [Learn more](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en#filtering-for-profile)| N/A | February 22, 2023 |

{style="table-layout:auto"}
  
## Fixes in Customer Journey Analytics

AN-309106

## Important notices for CJA Administrators

| Notice | Notice added or updated | Description |
| --- | --- | --- |
| No current notices | N/A | N/A |

{style="table-layout:auto"}

## Related resources

* [Previous CJA release notes for 2023](/help/release-notes/2023.md)
* [Adobe Analytics release notes](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=en)
* [Media Analytics release notes](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* [Adobe Experience Cloud release notes](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)
* [Customer Journey Analytics documentation updates](/help/release-notes/doc-changes.md)
