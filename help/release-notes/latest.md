---
title: View the current Customer Journey Analytics release notes
description: Latest Customer Journey Analytics release notes
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
---
# Current Adobe Customer Journey Analytics release notes (April 2024)

**Last update**: April 17, 2024

These release notes cover the release period of April 10, 2024 through May 2024. Adobe Customer Journey Analytics releases operate on a [continuous delivery model](releases.md) which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## New or updated features 

| Feature | Description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Streaming Media: Send Roku data to Adobe Experience Platform Edge** | Now when [installing Media Analytics with Experience Platform Edge](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge), you can use the Adobe Experience Platform Roku SDK to send Streaming Media data to Adobe Experience Platform. |  | April 12, 2024 |
| **Exposed monthly reports in Reporting Activity Manager** | When viewing reporting activity for all connections in Reporting Activity Manager, a graph is now available that shows the [monthly reports/requests](https://experienceleague.adobe.com/en/docs/analytics-platform/using/reporting-activity-manager/reporting-activity#view-all-report-suites) that were run at the IMS Org level, for both the current and previous month.<p>**Note:** Data is available starting partway through the month of March, 2024. | | April 15, 2024 |
| **Intelligent Captions in mobile scorecards** | [Intelligent Captions](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dashboards/manage-scorecard#captions) can help non-analysts better make sense of their data without the help of analysts. They are now available in Customer Journey Analytics scorecards. |  | April 17, 2024 |
| **Permissions enhancement for project-only [!UICONTROL Workspace] components** | Previously, if one user (User A) shared a project with another user (User B), and gave User B edit access to the project, User B would be able to edit the project. However, User B would not be able to edit [!UICONTROL Quick Segments] embedded in the project. That limitation is now removed - User B can edit [!UICONTROL Quick Segments] and other project-only components that are embedded in the shared project. |  | April 17, 2024 |
| **Administrators can manage all locations in their organization** |  A new option on the [Locations page](https://experienceleague.adobe.com/en/docs/analytics/components/locations/locations-manager) allows Administrators to view and manage all locations in the organization. Previously, administrators could view and manage only the locations they created. |  | April 17, 2024 |
| **Adobe Product Analytics: Feature Matrix** | Fuel investment decisions by understanding what your core, power, one-time, and questionable features are. [!UICONTROL Feature matrix] measures events by frequency of use vs % active users and compares to median usage. | April 17, 2024 | April 30, 2024 |
| **Adobe Product Analytics: Enhanced Insights in Funnel** |  In the [Friction](https://experienceleague.adobe.com/en/docs/analytics-platform/using/guided-analysis/funnel/friction) view, the written insights have been enhanced to include categories, deltas and descriptions to further understandability of the chart and table. | April 17, 2024 | April 26, 2024 |
| **Adobe Product Analytics: Enhanced retention view** | Several capabilities have been added to the [Retention](https://experienceleague.adobe.com/en/docs/analytics-platform/using/guided-analysis/retention/retention-rates) rates view to drive deeper & customizable retention insights:<ul><li>Unlink start and return events</li><li>Compare multiple return events in a single view</li><li>Customize the retention model applied with on or after (unbounded), on each (bounded) and bracketed settings</li><li>Show & hide individual cohort rows in the chart</li></ul> | April 24, 2024 | May 8, 2024 |
| **Adobe Product Analytics: Compare events within a single Funnel step** | You can now compare events within a single funnel step in the [Friction](https://experienceleague.adobe.com/en/docs/analytics-platform/using/guided-analysis/funnel/friction) view. This is particularly useful when your journey has step options or a step where an A/B experiment is being run. | April 23, 2024 | May 3, 2024 |
| **B2B Schema Transformation for Person to Account** | Lets you transform datasets to better support person-based lookups in Customer Journey Analytics B2B reporting scenarios. This capability is available for datasets for B2B schemas based on the following classes:<ul><li>XDM Business Account Person Relation</li><li>XDM Business Opportunity Person Relation</li><li>XDM Business Marketing List Members</li><li>XDM Business Campaign Members</li></ul> | | May 1, 2024 |
| **Experience Edge bot detection** | [Bot detection](https://experienceleague.adobe.com/docs/experience-platform/datastreams/bot-detection.html) allows you to identify events generated by Web SDK, Mobile SDK and Server API as being generated by known spiders and bots. | | May 1, 2024 |
|**Derived fields: Next or Previous function** | These new features let you take a field as an input and then identify the n-previous or n-next value to get a better view into the user journey. This functionality could also be combined with other functions in [!UICONTROL Derived Fields], such as [!UICONTROL Concatenate], to create new dimensions. |  | May 1, 2024 |
|**Audiences are published to a new "Audiences" section in Experience Platform** | Audiences that are published from Customer Journey Analytics are now available in the new "Audiences" section in Adobe Experience Platform.<p>Previously, audiences that were published from Customer Journey Analytics were available in Experience Platform under the "Segments" section.</p><p>This improvement provides the following benefits:</p><ul><li>Audiences no longer have a 1-hour delay before they appear in Experience Platform; they are available seconds after they are published.</li><li>Audiences can be sorted in Experience Platform by using the "Origin" column, which displays the application from which the audience was originally published.</li><li>Filter and sort options in Experience Platform enable you to more quickly find the relevant audiences.</li></ul> |  | May 2024 |

{style="table-layout:auto"}

## Fixes in Customer Journey Analytics

AN-319662; AN-337894; AN-338469; AN-340147; AN-340200; AN-340443; AN-341594; AN-342442; AN-342976; AN-343020; AN-343469; AN-343703; AN-343938; AN-344614; AN-344677; 

## Important notices for Customer Journey Analytics Administrators

| Notice | Notice added or updated | Description |
| --- | --- | --- |
| **Updated links in Data views and Connections UIs** | February 15 | At the beginning of March, Adobe plans to update the following links in the Customer Journey Analytics product user interface. Please update your bookmarks accordingly.<ul><li>**Data views page, Data views Manager**: [Existing link](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/manager) > [New link](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/data-views)</li><li>**Create new data view**: [Existing link](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/new) > [New link](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/data-views/new)</li><li>**Edit data view**: [Existing link](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/edit/dv_65b9f6eba2c6554743236e88) > [New link](https://experience.adobe.com/#/@aresemeavalidationco/platform/analytics/#/apps/data-management/data-views/dv_62fde2e158324f2803c9e5d6/edit)</li><li>**Connections Manager**: [Existing link](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/manager) > [New link](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections)</li><li>**Connections Info**: [Existing link](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/view/dg_66749c92-784b-45bb-b114-e9e8377a2fc1) > [New link](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/dg_a2b297a6-9220-440d-a403-ee8fbf627cd8)</li><li>**Edit connection**: [Existing link](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/edit/dg_66749c92-784b-45bb-b114-e9e8377a2fc1) > [New link](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/dg_a2b297a6-9220-440d-a403-ee8fbf627cd8/edit)</li><li>**Create new connection**: [Existing link](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/new) > [New link](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/new/edit)</li></ul>| 

{style="table-layout:auto"}

## Related resources

* [Previous Customer Journey Analytics release notes for 2024](/help/release-notes/2024.md)
* [Adobe Analytics release notes](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html)
* [Media Analytics release notes](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* [Adobe Experience Cloud release notes](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)
* [Customer Journey Analytics documentation updates](/help/release-notes/doc-changes.md)
