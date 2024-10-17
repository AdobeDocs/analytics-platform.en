---
title: Upgrade from Adobe Analytics to Customer Journey Analytics
description: Plan your upgrade from Adobe Analytics to Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
---
# Upgrade from Adobe Analytics to Customer Journey Analytics

Customer Journey Analytics is the next generation of analytics. It allows multi-channel data collection (both online and offline data), combined with powerful report-time processing functionality (through the definition of components and derived fields in data views). 

Before you begin the process of upgrading from Adobe Analytics to Customer Journey Analytics, you should understand the benefits of Customer Journey Analytics, as well as the steps required to successfully upgrade.

## Understand the benefits of Customer Journey Analytics 

 Following are some of the key benefits: (For a comprehensive list, as well as more information about each of these key features, see [Features available only in Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md#adobe-customer-journey-analytics-features-not-available-in-adobe-analytics).) 

* [Multi-channel reporting](/help/getting-started/aa-to-cja-user.md#changes-to-data-architecture)

  Customer Journey Analytics is combined with Experience Platform's ability to hold all kinds of data schemas and types. Collect and report on data from multiple channels, such as digital (Web), Point-of-Sale systems, mobile, CRM systems, and more.

* [Report-time transformations in data views](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md#customer-journey-analytics-data-views)

  Data views in Customer Journey Analytics allow you to further interpret data from a connection. You can alter or remove data without changing your implementation, use substrings to manipulate dimensions, create metrics from any value, filter subevents, or use derived fields. All of these transformations are non-destructive. 

* [Transformations apply to historical and new data](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)

  Data View manipulation can be applied to both historical and new data in a non-destructive manner.

* [Derived fields](/help/data-views/derived-fields/derived-fields.md)

  Derived fields allow for report-time transformations to your data. Data can be combined, corrected, or created on the fly and applies retroactively to all reporting.

* [Data views replace virtual report suites](/help/getting-started/aa-to-cja-user.md#changes-to-the-concept-of-virtual-report-suites)

  Data views take the concept of virtual report suites as they exist today and expand it to enable additional controls on the data made available by connections. These changes make general settings like timezone and session time-out intervals configurable and retroactive. 

* [Unlimited customer dimensions and metrics](/help/getting-started/aa-to-cja-user.md#changes-to-the-concept-of-evars-and-props)

  Values can be numeric, text, objects, lists, or mixtures of all. Dimensions can be nested or hierarchical.

## Recommended upgrade process

Regardless of your current Adobe Analytics implementation, Adobe recommends using both the Adobe Analytics source connector and a new implementation of the WebSDK when upgrading from Adobe Analytics to Customer Journey Analytics:

1. **Implement the Adobe Analytics source connector**

   During the upgrade to Customer Journey Analytics, the Analytics source connector is an essential piece of a two-pronged upgrade approach. 

   The Analytics source connector allows you to:

   * Bring your historical Adobe Analytics report suite data into Adobe Experience Platform and Customer Journey Analytics.
   
   * Make side-by-side comparisons within Customer Journey Analytics of your historical Adobe Analytics data and new data that is being collected directly into Adobe Experience Platform.

   The Analytics source connector as a stand-alone implementation is not a recommended long-term method for upgrading to Customer Journey Analytics. This is due to high latency, cluttered and complex schemas, reliance of Adobe Analytics nomenclature (prop, eVar, and so forth), and difficulty in moving from the source connector to the recommended WebSDK implementation.

1. **Implement the WebSDK**

   Having 
