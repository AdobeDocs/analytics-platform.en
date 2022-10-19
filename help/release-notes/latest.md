---
title: View the current Customer Journey Analytics release notes
description: Latest CJA release notes
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
---
# Customer Journey Analytics (CJA) release notes (October 2022)

**Last update**: October 18, 2022

Customer Journey Analytics releases operate on a [continuous delivery model](releases.md) which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## Related resources

* [Previous CJA release notes for 2022](/help/release-notes/2022.md)

* [Adobe Analytics release notes](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=en)

* [Media Analytics release notes](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)

* [Adobe Experience Cloud release notes](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)

## Key features and updates

| Feature | Description | [Targeted Date](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| **Experimentation Panel** | This new Workspace panel allows CJA users to evaluate the lift and confidence of any A/B experiment from any source - online, offline, from Adobe solutions, Adobe Journey Optimizer, and even BYO data. [Learn more](/help/analysis-workspace/c-panels/experimentation.md) | October 5, 2022 |
| **[!UICONTROL Key metric summary] visualization** |  The [!UICONTROL Key metric summary] visualization lets you see how an important metrics is trending within a single timeframe. It also lets you compare metric performance across two timeframes. Learn more  | Phased rollout starting October 5, 2022 |
| **Date field support in CJA** | Allows CJA to report on date and date-time fields. [Learn more](/help/data-views/data-views-usecases.md#date) | October 5, 2022 |
| **Mobile app: Custom detail views**| Custom detail views allow you to be even more targeted about what information you share with your audience, by letting them focus on what's most important. You can alter the layout of the detail view associated with each scorecard tile and you can add text to better explain what the end user may see in the data. [Learn more](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/create-scorecard.html?lang=en)| October 5, 2022 |
| **Case-insensitive multi-value variables** | For case-insensitive multi-value variables, the values stored in `mvvar1` - `mvvar3` will no longer be automatically lowercased. Instead, data passed through the Analytics Source Connector to Adobe Experience Platform and CJA will reflect the original case that was passed in from the page. | October 24, 2022 |

{style="table-layout:auto"}

## Important notices for CJA Administrators

| Notice | Notice added or Updated | Description |
| --- | --- | --- |
| **Default landing page** | September 29, 2023 | The [new landing page](/help/getting-started/landing.md) that was introduced earlier this year will become the default experience for all users in **January 2023**. The current page will be deprecated and everyone will be required to use the new experience. |
| **Improved IP-to-geolocation mapping** | September 29, 2022 | Adobe's vendor for IP lookups, Digital Element, is upgrading to a new improved dataset (NetAcuity Pulse) for IP-to-geolocation mapping. Adobe Analytics has postponed the adoption of this new dataset to **January of 2023**. The new database will be more accurate than previous versions. Some IP-to-geo mappings will change/improve when the new database is adopted.<p> CJA data provided through the [!UICONTROL Analytics Source Connector] will also automatically take advantage of the new mappings. |
| **[!UICONTROL Anomaly detection] auto-run conditions** | September 29, 2022 | Today, [!UICONTROL Anomaly detection] auto-runs on all columns of time-series freeform tables. To ensure data is available for analysis and projects load faster, Adobe will change how [!UICONTROL Anomaly detection] auto-runs. Starting **October 26, 2022**, Anomaly detection will auto-run only on the first metric column in a table. You can configure column settings to run [!UICONTROL Anomaly detection] on other columns, if needed. |

{style="table-layout:auto"}

>[!MORELIKETHIS]
>[Customer Journey Analytics documentation updates](/help/release-notes/doc-changes.md)
