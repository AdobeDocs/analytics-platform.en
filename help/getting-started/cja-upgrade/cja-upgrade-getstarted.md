---
title: Get started with the upgrade to Customer Journey Analytics
description: Plan your upgrade from Adobe Analytics to Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: fd3b36ab-72c1-469a-b2c7-419813c82425
---
# Step 1: Get started with the upgrade to Customer Journey Analytics

<!--

>[!AVAILABILITY]
>
>The information on this page is being replaced with the following more comprehensive upgrade information: <ul><li>**Recommended upgrade steps**<p>For detailed information, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).</p></li><li>**Customer Journey Analytics Upgrade Guide**<p>A new upgrade guide is available that dynamically generates upgrade steps that are tailored for your organization and your unique circumstances.</p><p>To access the guide from Customer Journey Analytics, select the **[!UICONTROL Workspace]** tab, then select **[!UICONTROL Upgrade to Customer Journey Analytics]** in the left panel. Follow the on-screen instructions.</p></li></ul>

-->

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

## Understand the upgrade process

<!-- Include a graphic of the end-to-end process, as well as links to each step of the process -->
The information on this page covers Step 1 of the upgrade process, as highlighted in the table below. Complete all steps in this table to upgrade from Adobe Analytics to Customer Journey Analytics. 

| Upgrade task | Details |
|---------|----------|
| <span class="preview">**Step 1: Get started with the upgrade**</span> | <span class="preview">Learn the benefits of upgrading to Customer Journey Analytics and the basic upgrade process.</span> |
| **Step 2: [Choose the upgrade path](/help/getting-started/cja-upgrade/cja-upgrade-path.md)** | Various methods are available for upgrading to Customer Journey Analytics. Choose the method that is best for your organization, depending on your organization's current Adobe Analytics environment and long-term goals. | 
| **Step 3: [Send data to Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)** | The process for sending data to Adobe Experience Platform differs depending on the upgrade path that you chose in Step 2. | 
| **Step 4: [Retain historical data](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)** | Most organizations need to retain their historical Adobe Analytics data for a certain amount of time. Various options are available to accomplish this. | 
| **Step 5: [Perform additional implementation tasks](/help/getting-started/cja-getting-started.md)** | At this point in the upgrade process, you need to perform various tasks before your Customer Journey Analytics environment is ready to use.<p>These additional tasks apply to upgrades from Adobe Analytics as well as new Customer Journey Analytics implementations.</p><p>These tasks include:</p><ul><li>Bringing other data into Experience Platform</li><li>Creating connections between Platform datasets and Customer Journey Analytics</li><li>Creating data views</li><li>Porting the reporting API usage</li><li>Accounting for Data Feeds and Data Warehouse</li><li>Migrating projects and components</li><li>Planning user onboarding</li></ul> <p>For more information, see [Customer Journey Analytics Getting Started](/help/getting-started/cja-getting-started.md).  |

{style="table-layout:auto"}

## First, choose the upgrade path

Various methods are available for upgrading to Customer Journey Analytics. [Choose the method that is best for your organization](/help/getting-started/cja-upgrade/cja-upgrade-path.md). 

The upgrade path that you choose depends on your organization's current Adobe Analytics environment and long-term goals.
