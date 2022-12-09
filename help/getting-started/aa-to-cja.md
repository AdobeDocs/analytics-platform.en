---
title: Adobe Analytics to Customer Journey Analytics evolution
description: Steps to transform Adobe Analytics data into Customer Journey Analytics data
role: Admin
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: 5e3f0aa0-ba24-48c8-948c-ebb5c270f34d
---
# Adobe Analytics to Customer Journey Analytics evolution

As your organization evolves to use Customer Journey Analytics, explore these steps to prepare your data and to become aware of critical differences between the two technologies. This article is aimed at an administrator audience.

## Prepare your data

Preparing your Adobe Analytics data for a seamless move to Customer Journey Analytics is critical to data integrity and reporting consistency.

### 1. Collect identities {#identities}

Perhaps the most critical component of understanding a customer journey is knowing who the customer is at each step. For Customer Journey Analytics, having an identifier that exists across all your channels and the corresponding data allows for stitching multiple sources together within CJA. 
Examples of identities might be a customer ID, account ID, or email ID. Whatever the identity (and there may be multiple), make sure you consider the following for each ID:

* ID exists or can be added to all data sources you want to bring into CJA
* ID is populated on each row of data
* ID does not contain PII. Apply hashing to anything that might be sensitive. 
* ID uses the same format across all sources (same length, same hashing method, etc.)

In datasets like Adobe Analytics, an identity may not exist on every row of data, but a secondary identity does. In this case, Cross-channel Analytics (formerly known as "Field-based Stitching") can be used to bridge the gap between rows when a customer is only identified by their ECID and when an identity is collected (for example, when a customer authenticates). [Learn more](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html)

### 2. Align your variables {#variables}

The most straightforward method of transforming Adobe Analytics data into Customer Journey Analytics data is to ingest a [global report suite](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/global-rs.html) into Experience Platform using the [Adobe Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html). This connector maps your Adobe Analytics variables directly to an XDM schema and dataset in Experience Platform, which can in turn be easily connected to Customer Journey Analytics. 

A full global report suite may not always be feasible for an implementation. If you are planning to bring multiple report suites into Customer Journey Analytics, you have 2 options:

* Plan ahead to bring variables into alignment across those report suites. For example, eVar1 in report suite 1 may point to [!UICONTROL Page]. In report suite 2, eVar1 may point to [!UICONTROL Internal Campaign]. When brought into CJA, these variables will mix into a single eVar1 dimension, leading to potentially confusing and inaccurate reporting.

* Use the [Data Prep](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html) feature to map variables. While it makes it easier if all report suites use the same common variable design, it's not required if you use the new Experience Platform [Data Prep](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html#mapping) feature. It allows you to reference a variable by its mapped value, which is at the datastream (or property) level.

If you have avoided moving to a global report suite due to issues with [!UICONTROL Uniques Exceeded] or [!UICONTROL Low Traffic], know that CJA has no [cardinality limits on a dimension](/help/components/dimensions/high-cardinality.md). It allows for any unique value to appear and be counted.

Here is a use case on [combining report suites with different schemas](/help/use-cases/aa-data/combine-report-suites.md).

### 3. (Re)Configure your Marketing Channels {#marketing-channels}

Traditional Adobe Analytics Marketing Channel settings do not perform the same in CJA. This is for two reasons:

* The level of processing on the Adobe Analytics data ingested into Adobe Experience Platform, and 

* The report-time nature of Customer Journey Analytics  

Adobe has published [updated best practices for Marketing Channel implementation](https://experienceleague.adobe.com/docs/analytics/components/marketing-channels/mchannel-best-practices.html). These updated recommendations  help you make the most of the capabilities already in Adobe Analytics with Attribution IQ. They will also set you up for success when transitioning to Customer Journey Analytics.

### 4. Decide on using Analytics Source Connector vs. Experience Platform SDKs {#connector-vs-sdk}

Adobe Analytics customers can easily leverage their report suites in the Adobe Experience Platform and Customer Journey Analytics using the Analytics Source Connector. For information on using the Analytics Source Connector, see [Create an Adobe Analytics source connection in the UI](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en).

As [Experience Edge](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html) data collection evolves, you will likely migrate to either the [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/web-sdk.html) or [Adobe Experience Platform Mobile SDK](https://experienceleague.adobe.com/docs/mobile.html) with the Adobe Experience Platform Edge Network. While a typical implementation of the SDKs will send data into Adobe Analytics, a new opportunity presents itself for sending data directly to Adobe Experience Platform. It can then be ingested into Customer Journey Analytics, while also maintaining data sent to Adobe Analytics. 

This method greatly expands possibilities for data collection: There is no longer a limitation on the number of fields or the need to map data elements to props, eVars, and events like in Analytics. You can use unlimited schema elements of different types and represent them in multiple ways using CJA [Data Views](/help/data-views/data-views.md). Speed of data availability increases when sent directly to Adobe Experience Platform, as the time for data processing through Adobe Analytics is removed. 

**Advantages of using Experience Platform SDKs:**

* Flexible schema to define any fields you need
* Not reliant on Adobe Analytics nomenclature (prop, eVar, event, etc.)
* No character limit concerns (100 chars for props)
* Faster data availability in Adobe Experience Platform to power [real-time personalization use cases](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=en)
* [First-party device IDs](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/first-party-device-ids.html?lang=en) for enhanced accuracy of visitor identification

**Drawbacks to using Experience Platform SDKs**

The following Adobe Analytics features or components are not supported:

* Marketing Channels
* Bot Filtering
* Geo, Domain, Device Lookups
* Analytics for Target (A4T)

## Prepare for critical differences

### Get comfortable with Report-time Processing {#report-time}

The reporting in Adobe Analytics relies on a significant amount of data pre-processing to generate results like the persistence that you see in [!UICONTROL eVars]. By contrast, Customer Journey Analytics runs those calculations at report run time.

[!UICONTROL Report time processing] opens the ability to apply settings that are retroactive and create multiple versions of variable persistence without needing to change how the underlying data is collected. 

This shift will result in some differences in how data is reported, especially for any variables that may have a long expiration window. You can begin by evaluating how report-time processing may impact your reporting using a [virtual report suite](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html). 

### Identify critical Segments and Calculated Metrics {#segments-calcmetrics}

Adobe Analytics segments (called [!UICONTROL filters] in CJA) and calculated metrics are not compatible with Customer Journey Analytics. In many cases, these components can be rebuilt in CJA using the new schemas and data available. 

To make the transition as smooth as possible for users when they transition between the systems, plan ahead by

1. Identifying the most critical of these components.

1. Documenting their definitions, and 

1. Identifying what fields will be required in the data to replicate them in CJA as [Filters](/help/components/filters/filters-overview.md) and [Calculated Metrics](/help/components/calc-metrics/calc-metr-overview.md).

Here are a couple of videos to guide you:

* [Move Adobe Analytics segments to Customer Journey Analytics](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/moving-adobe-analytics-segments-to-customer-journey-analytics.html)

* [Move your Calculated Metrics from Adobe Analytics to Customer Journey Analytics](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/components/calc-metrics/moving-your-calculated-metrics-from-adobe-analytics-to-customer-journey-analytics.html?lang=en)

### Other considerations

* Using the power of CJA data views, you have a lot more flexibility in the definition of metrics and dimensions within Customer Journey Analytics. For example, you can use the value of a dimension to become the definition of a metric. [Learn more](/help/use-cases/data-views/data-views-usecases.md)

* If you have defined a custom calendar in Adobe Analytics, you will have similar [custom calendar capabilities](/help/components/date-ranges/custom-date-ranges.md) within CJA. You need to ensure that your calendar is properly defined.

* In Customer Journey Analytics, you can define a custom visit/session timeout as well as define a metric that will start a new session. You can create data views with different session definitions to get insights above and beyond what was possible in Adobe Analytics. This capability may be particularly beneficial for mobile datasets.

* Consider providing a data dictionary for your users – or extend the SDR to include the Experience Platform field name for schema elements.

## Next steps

After moving to CJA, if you notice any data discrepancies, you can compare your original Adobe Analytics data with the Adobe Analytics data that is now in Customer Journey Analytics. [Learn more](/help/troubleshooting/compare.md)
