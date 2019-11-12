---
title: Customer Journey Analytics glossary
description: Customer Journey Analytics glossary.
---

# Customer Journey Analytics glossary

Some Customer Journey Analytics terminology differs from how it has traditionally been used in Adobe Analytics:

|Adobe Analytics term|New Customer Journey Analytics term|Description|
|---|---|---|
|Segment| Filter|Filters in Customer Journey Analytics behave the same as segments. Only the terminology has changed.|
|Report Suite| N/A|Report suites in the traditional Adobe Analytics sense no longer exist. Instead, you create (virtual) data views from the Platform datasets that you established connections to.|
|Virtual report suite|Data view|A virtual report suite is a segmented view of a parent report suite. The main difference between a virtual report suite and a data view in CJA is that the virtual report suite is a subset of a "base" or "parent" report suite and, as such, inherited some of its settings. Since parent/base report suites no longer exist, you define data views with their own settings. |
|Classification|Lookup dataset|...|
|Customer attribute|Profile dataset|If you capture enterprise customer data in a customer relationship management (CRM) database, you can upload the data into a Profile dataset in Adobe Experience Platform. Once you create a connection to that dataset in Customer Journey Analytics and create a data view, leverage the data in Workspace.|
|Login company|Experience Cloud organization|See [Organizations and account linking](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html#topic_C31CB834F109465A82ED57FF0563B3F1).|


## Adobe Experience Platform (AEP) glossary

Adobe Experience Platform: Adobe Experience Platform standardizes data and content across the enterprise, powering real-time consumer profiles, enabling data science, and accelerating content velocity to drive experience personalization across the customer journey.
Dataset: A dataset is a storage and management construct for a collection of data, typically a table, that contains schema (columns) and fields (rows).

