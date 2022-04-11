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

>[!IMPORTANT]
>
>These release notes contain pre-release information that is subject to change.

**Last update**: March 17, 2022

## Key features

| Feature | Description | [Targeted Date](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
<<<<<<< Updated upstream
| Annotations in Workspace | Annotations in Workspace enable you to effectively communicate contextual data nuances and insights to your organization. [Learn more](/help/components/annotations/overview.md) | March 23, 2022 |
=======
| Dimension substrings | Analytics customers often use delimiters and classification rule builder to get around the limit to the number of eVars they have access to. For example they may put into an eVar something like "A | B | C" and really want to report on "A", "B", and "C" as separate dimensions. Classification rule builder has served this use case in Analytics. However, this approach does not scale as well in CJA, as it can create very large lookup files. To solve this problem, we have broken out these delimited fields at query time rather than use a lookup. This allows us to give a more stable reporting experience for customers with extensive delimited fields. Learn more (to follow) | April 20, 2022 |
| Analytics Data Transformations for CJA | Customers who are ingesting multiple report suites (via Adobe Source Connector) with different implementations need a mechanism to deconflict columns. For example, eVar1 in one report suite might be set to "Product Name", and to "Home Page" in another report suite. That way, CJA can ingest the data without creating conflicted, mixed-semantic columns. We are leveraging [Data Prep](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html) functionality in Adobe Experience Platform to apply custom transforms to data after it has been sent to bulk ingestion by the Adobe Source Connector. The transformations will be applied by Data Prep prior to the data landing in data lake. | April 25, 2022 |
>>>>>>> Stashed changes

{style="table-layout:auto"}

>[!MORELIKETHIS]
>[Customer Journey Analytics documentation updates](/help/release-notes/doc-changes.md)
