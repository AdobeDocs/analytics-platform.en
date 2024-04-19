---
title: Plan your migration from Adobe Analytics to Customer Journey Analytics
to Customer Journey Analytics
description: Plan your migration from Adobe Analytics to Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
---
# Step 1: Get started with the migration to Customer Journey Analytics

Customer Journey Analytics is the next generation of analytics. It allows multi-channel data collection (both online and offline data), combined with powerful report-time processing functionality (through the definition of components and derived fields in data views). 

Before you begin the process of migrating from Adobe Analytics to Customer Journey Analytics, you should understand the benefits of Customer Journey Analytics, as well as the steps required in order to successfully migrate.

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

## Understand the migration process

<!-- Include a graphic of the end-to-end process, as well as links to each step of the process -->
This page represents Step 1 of the migration, as shown in the following table. Complete all steps in this table to migrate from Adobe Analytics to Customer Journey Analytics.

| Task | Details |
|---------|----------|
| **Step 1: [Get started with the migration](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Learn the benefits of migrating to Adobe Analytics and the basic migration process. |
| **Step 2: [Choose the migration method](/help/getting-started/cja-migration/cja-migration-method.md)** | Various methods are available for migrating to Customer Journey Analytics. Choose the method that is best for your organization, depending on your organization's current Adobe Analytics environment and long-term goals. | 
| **Step 3: [Send data to Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | The process for sending data to Adobe Experience Platform differs depending on the migration method that you chose in Step 1. | 
| **Step 4: [Plan data mapping to the XDM schema](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [XDM schemas](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) are used in Adobe Experience Platform to describe the structure of data in a consistent and reusable way. By defining data consistently across systems, it becomes easier to retain meaning and therefore gain value from data.<p>Most migration methods require that you either create a new XDM schema, or map your existing Adobe Analytics schema to XDM by using datastream mapping.</p>  |
| **Step 5: [Retain historical data](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | Most organizations need to retain their historical Adobe Analytics data for a certain amount of time. Various options are available to accomplish this.  | 
| **Step 6: [Plan user onboarding](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | You should give your users ample time (3 - 6 months) to become familiar with the key differences of Analysis Workspace in Customer Journey Analytics. | 
| **Step 7: [Port the reporting API usage](/help/getting-started/cja-migration/cja-migration-api.md)** | The Customer Journey Analytics reporting API is in the same format, but uses a different endpoint. Port the reporting API usage from the Adobe Analytics reporting API to the Customer Journey Analytics reporting API. | 
| **Step 8: [Replace Data Feeds and Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)** | Decide how you will use the export options available in Customer Journey Analytics in order to replace the Data Feeds and Data Warehouse features you were using in Adobe Analytics.  |
| **Step 9: [Migrate projects and components](/help/getting-started/cja-migration/cja-migration-projects.md)** | The Component migration area in Adobe Analytics allows you to migrate projects and their associated components from Adobe Analytics to Customer Journey Analytics.  |

{style="table-layout:auto"}

## First, choose the migration method

Various methods are available for migrating to Customer Journey Analytics. [Choose the method that is best for your organization](/help/getting-started/cja-migration/cja-migration-method.md). 

The migration method you choose depends on your organization's current Adobe Analytics environment and long-term goals.