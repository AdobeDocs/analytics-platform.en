---
title: Customer Journey Analytics glossary
description: Customer Journey Analytics glossary.
exl-id: 7f8aac93-0103-4ead-b25b-3d9994a271af
solution: Customer Journey Analytics
feature: Basics
role: User
autotag-review: '2026-05-19T09:29:03.007Z'
TQID: 'https://experienceleague.adobe.com/BxQ-hPP9Uh5gfdnEaVOWkfVG8UVj0KVhhmFqKtMXtRA'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
    internal-label: Administration
  - id: b3197353-f189-4932-8378-3f3bc40e6071
    internal-label: Data management
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: cf731116-8803-4027-85aa-9c0a126e8321
    internal-label: Dataset configuration
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
    internal-label: Segments, Segments (CJA)
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
---
# Customer Journey Analytics glossary

Some Customer Journey Analytics terms differ from how they have traditionally been used in Adobe Analytics:

| New Customer Journey Analytics term | Adobe Analytics term | Description |
| --- | --- | --- |
| Lookup dataset | Classification | Use lookup to retrieve the value from the specified dataset for a key/matching key (in an event dataset) where there is a 1-to-1 relationship. For example, you could specify "tracking_code" as the key that matches the "tracking_code" in the event dataset.|
|Profile dataset|Customer attribute|If you capture enterprise customer data in a customer relationship management (CRM) database, you can upload the data into a Profile dataset in Adobe Experience Platform. Once you create a connection to that dataset in Customer Journey Analytics and create a data view, leverage the data in Workspace. |
| CX Enterprise (Experience Cloud) organization | Login company | See [Organizations and account linking](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html#topic_C31CB834F109465A82ED57FF0563B3F1). |
| N/A | Report Suite | Report suites in the traditional Adobe Analytics sense no longer exist. Instead, you create (virtual) [data views](/help/data-views/create-dataview.md) from the Platform datasets that you established connections to. |
| Segment | Segment | Segments used to be "filters". They have been renamed to "segments". |
| Data view | Virtual report suite | In Adobe Analytics, a virtual report suite is a filtered view of a parent report suite. The main difference between a virtual report suite and a data view in Customer Journey Analytics is that the virtual report suite is a subset of a "base" or "parent" report suite and, as such, inherits some of its settings. Since parent/base report suites no longer exist, you define data views with their own settings. |

## Adobe Experience Platform glossary

Adobe Experience Platform standardizes data and content across the enterprise, powering real-time consumer profiles, enabling data science, and accelerating content velocity to drive experience personalization across the customer journey.
See the [Adobe Experience Platform Glossary](https://experienceleague.adobe.com/docs/experience-platform/landing/glossary.html)for more information.
