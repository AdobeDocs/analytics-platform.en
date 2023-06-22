---
title: Customer Journey Analytics glossary
description: Customer Journey Analytics glossary.
exl-id: 7f8aac93-0103-4ead-b25b-3d9994a271af
solution: Customer Journey Analytics
feature: CJA Basics
---
# Customer Journey Analytics glossary

Some Customer Journey Analytics terms differ from how they have traditionally been used in Adobe Analytics:

| New Customer Journey Analytics term | Adobe Analytics term | Description |
| --- | --- | --- |
| Lookup dataset | Classification | Use lookup to retrieve the value from the specified dataset for a key/matching key (in an event dataset) where there is a 1-to-1 relationship. For example, you could specify "tracking_code" as the key that matches the "tracking_code" in the event dataset.|
|Profile dataset|Customer attribute|If you capture enterprise customer data in a customer relationship management (CRM) database, you can upload the data into a Profile dataset in Adobe Experience Platform. Once you create a connection to that dataset in Customer Journey Analytics and create a data view, leverage the data in Workspace. |
| Experience Cloud organization | Login company | See [Organizations and account linking](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html#topic_C31CB834F109465A82ED57FF0563B3F1). |
| N/A | Report Suite | Report suites in the traditional Adobe Analytics sense no longer exist. Instead, you create (virtual) [data views](/help/data-views/create-dataview.md) from the Platform datasets that you established connections to. |
| Filter | Segment | Segments are now filters. Filters in Customer Journey Analytics behave the same as segments. Only the terminology has changed. |
| Data view | Virtual report suite | In Adobe Analytics, a virtual report suite is a filtered view of a parent report suite. The main difference between a virtual report suite and a data view in Customer Journey Analytics is that the virtual report suite is a subset of a "base" or "parent" report suite and, as such, inherits some of its settings. Since parent/base report suites no longer exist, you define data views with their own settings. |

## Adobe Experience Platform glossary

Adobe Experience Platform standardizes data and content across the enterprise, powering real-time consumer profiles, enabling data science, and accelerating content velocity to drive experience personalization across the customer journey.
See the [Adobe Experience Platform Glossary](https://experienceleague.adobe.com/docs/experience-platform/landing/glossary.html)for more information.
