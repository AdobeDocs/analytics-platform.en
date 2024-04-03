---
title: Migrate to Customer Journey Analytics using the Analytics Source Connector
description: Plan your migration from Adobe Analytics to Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
---
# Migration guide: Migrate to Customer Journey Analytics using the Analytics Source Connector

>[!IMPORTANT]
>
>Review the information in [Migration guide: Plan your migration from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-migration/cja-migration-planning.md) before migrating to Customer Journey Analytics as described in this article.


## Step 3: Prepare your existing data <!-- Only for ASC, because otherwise you're not technically migrating data? -->

Preparing your Adobe Analytics data for a seamless move to Customer Journey Analytics is critical to data integrity and reporting consistency.

### Collect identities

Perhaps the most critical component of understanding a customer journey is knowing who the customer is at each step. For Customer Journey Analytics, having an identifier that exists across all your channels and the corresponding data allows for stitching multiple sources together within Customer Journey Analytics.
Examples of identities might be a customer ID, account ID, or email ID. Whatever the identity (and there may be multiple), make sure you consider the following for each ID:

* ID exists or can be added to all data sources you want to bring into Customer Journey Analytics
* ID is populated on each row of data
* ID does not contain PII. Apply hashing to anything that might be sensitive.
* ID uses the same format across all sources (same length, same hashing method, etc.)

In datasets like Adobe Analytics, an identity may not exist on every row of data, but a secondary identity does. In this case, [Cross-channel Analysis (also known as "Stitching")](/help/stitching/overview.md) can be used to bridge the gap between rows when a customer is only identified by their ECID and when an identity is collected (for example, when a customer authenticates).

### Align your variables

The most straightforward method of transforming Adobe Analytics data into Customer Journey Analytics data is to ingest a [global report suite](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/global-rs.html) into Experience Platform using the [Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html). This connector maps your Adobe Analytics variables directly to an XDM schema and dataset in Experience Platform, which can in turn be easily connected to Customer Journey Analytics. 

A full global report suite may not always be feasible for an implementation. If you are planning to bring multiple report suites into Customer Journey Analytics, you have 2 options:

* Plan ahead to bring variables into alignment across those report suites. For example, eVar1 in report suite 1 may point to [!UICONTROL Page]. In report suite 2, eVar1 may point to [!UICONTROL Internal Campaign]. When brought into Customer Journey Analytics, these variables will mix into a single eVar1 dimension, leading to potentially confusing and inaccurate reporting.

* Use the [Data Prep](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html) feature to map variables. While it makes it easier if all report suites use the same common variable design, it's not required if you use the new Experience Platform [Data Prep](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html#mapping) feature. It allows you to reference a variable by its mapped value, which is at the datastream (or property) level.

If you have avoided moving to a global report suite due to issues with [!UICONTROL Uniques Exceeded] or [!UICONTROL Low Traffic], know that Customer Journey Analytics has no [cardinality limits on a dimension](/help/components/dimensions/high-cardinality.md). It allows for any unique value to appear and be counted.

Here is a use case on [combining report suites with different schemas](/help/use-cases/aa-data/combine-report-suites.md).

### (Re)Configure your Marketing Channels

Traditional Adobe Analytics Marketing Channel settings do not perform the same in Customer Journey Analytics. This is for two reasons:

* The level of processing on the Adobe Analytics data ingested into Adobe Experience Platform, and 

* The report-time nature of Customer Journey Analytics  

Adobe has published [updated best practices for Marketing Channel implementation](https://experienceleague.adobe.com/docs/analytics/components/marketing-channels/mchannel-best-practices.html). These updated recommendations  help you make the most of the capabilities already in Adobe Analytics with Attribution IQ. They will also set you up for success when transitioning to Customer Journey Analytics.

With the introduction of [Derived fields](../data-views/derived-fields/derived-fields.md) as part of Customer Journey Analytics Data views, Marketing Channels are also supported in a non-destructive and retro-active manner using the [Marketing Channel function template](../data-views/derived-fields/derived-fields.md#function-templates).