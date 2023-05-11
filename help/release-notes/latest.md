---
title: View the current Customer Journey Analytics release notes
description: Latest CJA release notes
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
---
# Current Customer Journey Analytics (CJA) release notes (May 2023)

**Last update**: May 8, 2023

Customer Journey Analytics releases operate on a [continuous delivery model](releases.md) which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## Key features and updates

| Feature | Description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Backfill for non-production sandboxes** | When creating an Analytics Source Connector data flow in a non-production sandbox,  the backfill in non-production sandboxes will be limited to 3 months. It will remain at 13 months for production sandboxes. | N/A | April 26, 2023 | 
| **Link sharing for projects (no login required)** | You can now share read-only links to Analysis Workspace projects with people who don't have access to Adobe Analytics. This includes sharing with people outside of your organization, or those within your organization who are not provisioned for Adobe Analytics. [Learn more](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html?lang=en#share-public-link) <p>This functionality is enabled by default and can be disabled by the system administrator. [Learn more](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/user-preferences.html?lang=en#company-preferences)</p> | May 3, 2023 | June 2023 |
| **Updated Home screen for the Analytics dashboards app (Mobile App)** | The new updated Home screen allows you to view all of your scorecards in one consolidated scorecard list.  If you have access to more than one organization under one login, all scorecards from your organizations will be available in a single list. | N/A | May 10, 2023 | 
| **Derived fields** | This represents the initial release of Derived fields. A derived field allows you to define (often complex) data manipulations on the fly, through a customizable rule builder. You can further define the derived field as a component (metric or dimension) in Data views and then use the derived field as a component in Workspace.<p>This release supports a marketing channels template and the following functions:</p><ul><li>Concatenate</li><li>Case When</li><li>Find & Replace</li><li>Lookup</li><li>URL Parse</li></ul> <p>[Learn more](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/derived-fields.html)</p> | May 10, 2023 | TBD | 
| **Report Builder for CJA - Select data view from cell** | This feature allows users to select the data view for a data block from a cell. This is helpful if you create a workbook and you have multiple data views that have similar data construction and you want to be able to reuse a workbook multiple times, with different data views. [Learn more](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/select-data-view.html) | N/A | May 24, 2023 |
| **Sort components in Analysis Workspace** | <p>A new Sort option is now available when viewing components either in the left rail or in the Data Dictionary in Analysis Workspace. You can sort components by Recommended (those most commonly used), Alphabetical, or Categorical (type).</p><p>Previously, you could only search or filter components. [Learn more](/help/components/overview.md)</p> | N/A | May 10, 2023 | 
| **Delete rows containing dynamic dimensions from a Freeform table** | In a Freeform table in Analysis Workspace, you can now quickly delete specific rows that contain dynamic dimensions using the x icon. When doing so, a "Does not equal" filter rule is automatically applied.<p>Previously, the only way to delete rows that contained dynamic dimensions was to manually create a rule in the Filter dialog. [Learn more](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)</p> | N/A | May 10, 2023 |
| **New button to add a visualization within a panel** | A new button is now available at the bottom of each panel in Analysis Workspace, allowing you to quickly add a visualization. <p>Previously, the only methods for adding a visualization to a panel were to drag a visualization from the left rail, duplicate or copy an existing visualization, or create a blank panel. [Learn more](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)</p> | N/A | May 17, 2023 |
| **Deep Linking (Mobile App)** | Allows users to send links to scorecards that will lead them directly to the scorecard project in the app. This makes it even easier to share projects and boost engagement from a less technical audience. | N/A | May 17, 2023 |
| **Intelligent Captions** | Enrich storytelling for users with natural-language summaries of a Line visualization. | May 17, 2023 | June 1, 2023 | 

{style="table-layout:auto"}
  
## Fixes in Customer Journey Analytics

AN-316412; AN-317105; AN-318122; AN-317353 

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
