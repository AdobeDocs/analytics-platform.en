---
title: View the current Customer Journey Analytics release notes
description: Latest CJA release notes
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
---
# Current Customer Journey Analytics release notes (April 2022)

>[!NOTE]
>
>This page contains pre-release information that is subject to change.

**Last update**: April 13, 2022

## Key features

| Feature | Description | [Targeted Date](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| Dimension substrings | Provides multiple methods to extract the desired part of a string for use as dimension items. This feature also allows you to treat a string dimension as an array if the string contains delimited values. [Learn more](../data-views/component-settings/substring.md) | April 20, 2022 |
| Data prep for Analytics Source Connector | The [Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en) is now integrated with the [Data Prep](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html) capabilities provided by Adobe Experience Platform. RTCDP, CJA & AJO customers can now extend the Analytics field group with additional field groups and leverage 100+ Data Prep operators to enrich the Analytics data during ingestion into AEP. RTCDP Customers can now enable multiple Data Prep-enabled report suites for Profile. CJA customers who are ingesting multiple report suites via the Analytics Source Connector now have a means to deconflict column differences between report suites. For example, if Search Term is stored in eVar1 in one report suite and in eVar2 in another report suite, using Data Prep you can extend the Analytics field group with a new column that merges the values from the two eVars. | April 25, 2022 |

{style="table-layout:auto"}

>[!MORELIKETHIS]
>[Customer Journey Analytics documentation updates](/help/release-notes/doc-changes.md)
