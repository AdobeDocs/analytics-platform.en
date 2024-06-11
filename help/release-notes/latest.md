---
title: View the current Customer Journey Analytics release notes
description: Latest Customer Journey Analytics release notes
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
---
# Current Adobe Customer Journey Analytics release notes (May 2024)

**Last update**: June 6, 2024

These release notes cover the release period of May 15, 2024 through June 2024. Adobe Customer Journey Analytics releases operate on a [continuous delivery model](releases.md) which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## New or updated features 

| Feature | Description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **AI Assistant for Customer Journey Analytics** | Allows you to ask natural-language questions in the Customer Journey Analytics UI and get answers based on Customer Journey Analytics documentation. [Learn more](/help/ai-assistant.md)| | June 6, 2024 |
| **Transformation of B2B lookup datasets** | You can now [transform B2B lookup datasets](/help/connections/transform-datasets-b2b-lookups.md) when defining a connection. This transformation allows to support person-based lookups on B2B data. | | June 6, 2024 | 
| **BI Extension** | The BI extension enables SQL access to the data views that you have defined in Customer Journey Analytics. [Learn more](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/bi-extension)| | May 15, 2024 |
| **Audiences are published to a new "Audiences" section in Experience Platform** | Audiences that are published from Customer Journey Analytics are now available in the new "Audiences" section in Adobe Experience Platform.<p>Previously, audiences that were published from Customer Journey Analytics were available in Experience Platform under the "Segments" section.</p><p>This improvement provides the following benefits:</p><ul><li>Audiences no longer have a 1-hour delay before they appear in Experience Platform; they are available seconds after they are published.</li><li>Audiences can be sorted in Experience Platform by using the "Origin" column, which displays the application from which the audience was originally published.</li><li>Filter and sort options in Experience Platform enable you to more quickly find the relevant audiences.</li></ul> <p>(Updated documentation link to follow)</p>|  | Late May to early June, 2024 |
| **Streaming Media: Send web data to Adobe Experience Platform Edge Network with the Web SDK** | You can now use the Adobe Experience Platform Web SDK to send Streaming Media web data to Adobe Experience Platform Edge Network, allowing you to build more personalized campaigns and provide more personalized content, resulting in more tracking data to report on.<p>This enhancement provides a unified collection method for web implementations across all Platform solutions, such as Customer Journey Analytics, RT-CDP, AJO, and Event Forwarding. Previously, the only way to send Streaming Media web data to Edge Network was by using the Media Edge API. <p>[Learn more](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/edge-web-sdk)</p> | | May 29, 2024 |
| **Derived Fields - New Functions and Function Templates** |  Additional derived field functions ([Math](/help/data-views/derived-fields/derived-fields.md#math), [Next or Previous](/help/data-views/derived-fields/derived-fields.md#next-or-previous)) and [function templates](/help/data-views/derived-fields/derived-fields.md#function-templates). | | June 5, 2024 |
| **Share accounts and locations that are used for export and import** | Users can now make the accounts and locations they create available to all users in their organization. Only account and location owners and system administrators can edit and delete accounts and locations.<p>Previously, accounts and locations could be used only by the user who created them.</p><p>These settings are available when users configure cloud export accounts and configure cloud export locations.</p> <p>For more information, see [Configure cloud export accounts](/help/components/exports/cloud-export-accounts.md) and [Configure cloud export locations](/help/components/exports/cloud-export-locations.md).</p>  | June 12, 2024 | June 30, 2024 |
| **New documentation for upgrading from Adobe Analytics to Customer Journey Analytics** | For organizations upgrading from Adobe Analytics to Customer Journey Analytics, there are multiple upgrade options and many considerations to keep in mind based on an organization's current Adobe Analytics implementation and long-term goals. New documentation resources are now available to help you better understand:<ul><li>The various upgrade paths that exist</li><li>Which upgrade paths are available based on an organization's current Adobe Analytics implementation</li><li>The advantages and disadvantages of each upgrade path</li><li>Step-by-step guidance for each upgrade path</li><li>Considerations for handling historical data</li></ul>[Get started with the upgrade to Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/cja-upgrade-getstarted)| | Available now |
| **New documentation on Data Export use cases**| This new section outlines [data export use cases](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-usecases/data-export/overview) such as<ul><li>Data Backup</li><li>Data Validation</li><li>Data Lake, Data Warehouse or BI Tools</li><li>Readiness for AI/ML</li></ul> and how to implement them using Experience Platform and Customer Journey Analytics functionalities. | | Available now |

{style="table-layout:auto"}

## Fixes in Customer Journey Analytics

AN-342309; AN-342312; AN-345267; AN-345909; AN-346016; AN-346049; AN-346052; AN-346287; AN-346624; AN-347919

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
