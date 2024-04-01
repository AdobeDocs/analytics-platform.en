---
title: Migration planning guide Adobe Analytics
to Customer Journey Analytics
description: Plan your migration from Adobe Analytics to Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
---
# Migration planning guide: Adobe Analytics to Customer Journey Analytics

## Step 1 - Understand the benefits of Customer Journey Analytics

Customer Journey Analytics is the next generation of analytics. It allows multi-channel data collection (both online and offline data), combined with powerful report-time processing functionality (through the definition of components and derived fields in data views). 

As you plan your migration, learn how Customer Journey Analytics can benefit your organization. Following are some of the key benefits: (For a comprehensive list, as well as more information about each of these key features, see [Features available only in Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md#adobe-customer-journey-analytics-features-not-available-in-adobe-analytics).) 

* Multi-channel reporting

  Customer Journey Analytics is combined with Experience Platform's ability to hold all kinds of data schemas and types. Collect and report on data from multiple channels, such as digital (Web), Point-of-Sale systems, mobile, CRM systems, and more.

* Report-time transformations in data views

  Data views in Customer Journey Analytics allow you to further interpret data from a connection. You can alter or remove data without changing your implementation, use substrings to manipulate dimensions, create metrics from any value, filter subevents, or use derived fields. All of these transformations are non-destructive. 

  For more information, see [Customer Journey Analytics data views](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md#customer-journey-analytics-data-views)

* Derived fields

  Derived fields allow for report-time transformations to your data. Data can be combined, corrected, or created on the fly and applies retroactively to all reporting.

* Transformation apply to historical and new data

  Data View manipulation can be applied to both historical and new data in a non-destructive manner. For more information, see [Data Views](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md).

* Combining Connections (report suites in Adobe Analytics)

  You can combine data from multiple Connections (report suites in Adobe Analytics) as if they were a single Connection.

* Unlimited customer dimensions and metrics

  Values can be numeric, text, objects, lists, or mixtures of all. Dimensions can be nested or hierarchical.

## Step 2: Choose your Customer Journey Analytics migration method

After you decide to migrate to Customer Journey Analytics, you need to determine the optimal migration method.  

The method that you choose for migrating from Adobe Analytics to Customer Journey Analytics depends on the following factors: 

* Your current Adobe Analytics implementation 

* Your goals for the future 

Use the following sections to determine which Customer Journey Analytics migration method best aligns with your organization's current environment and future goals: 

### Assess the migration methods available to you based on your current Adobe Analytics implementation

There are various options available for migrating from Adobe Analytics to Customer Journey Analytics.  

#### Understand migration methods  

In general, each migration method differs in the level of difficulty required to execute the migration, as well as in the end result achieved after the migration completes.  

The following table lists each migration method, its ease of migration, and the robustness of the migration based on the end result that it achieves: 

| Migration method | Ease of migration | End result |
|---------|----------|---------|
| WebSDK (re-implementation)  | Difficult | Most robust |
| WebSDK (without re-implementation)  | Moderate | Most robust |
| Adoption acceleration project | Moderate | Moderately robust |
| Analytics Source Connector | Easy | Least robust |

Use the following diagram to help visualize where each migration method falls on the spectrum in terms of ease of migration, as well as the end result that each achieves:

![cja migration methods](assets/cja-migration-methods.png)

#### Migration methods available based on your Adobe Analytics implementation

Not all migration methods are available for each type of Adobe Analytics implementation. The following table shows which migration methods are available to you, based on your current Adobe Analytics implementation: 

|Current Adobe Analytics implementation | Available migration methods |
|---------|----------|
| AppMeasurement | <ul><li>WebSDK (re-implementation)</li><li>Analytics Source Connector</li></ul>  | 
| Adobe Anlalytics extension | <ul><li>WebSDK (re-implementation)</li><li>Analytics Source Connector</li><li>Adoption acceleration project</li></ul> | 
| WebSDK | <ul><li>WebSDK (without re-implementation)</li></ul> | 

### Weigh the pros and cons of the migration methods available to you

The pros and cons of a given migration method differ depending on your current Adobe Analytics implementation. 

Before you use the information below to determine which migration method is right for you, review the information in [Understand migration methods](#understand-migration-methods) if you haven't already.

#### AppMeasurement 

AppMeasurement is the oldest supported form for Adobe Analytics implementations. Because of this, the methods available for migrating to Customer Journey Analytics are more limited.

The following table shows the migration methods available for organizations who have implemented Adobe Analytics with AppMeasurement:

| | Pros | Cons |
|---------|----------|---------|
| **WebSDK (re-implementation)** |<ul><li>Highly performant reporting (low latency) because the infrastructure is built around real-time data </li><li>Future-proof (will receive all the latest features and functionality)</li><li>Consolidate tags between other Experience Cloud products (AJO, RTCDP, etc.)</li></ul> | <ul><li>Most time-consuming and demanding migration method</li><li>Must re-create the full schema in XDM</li></ul> |
| **Analytics Source Connector** | <ul><li>Least time-consuming and demanding migration method: Data is migrated to Customer Journey Analytics quickly with minimal investment </li></ul> | <ul><li>Difficult to move to WebSDK in the future</li><li>Uses the Analytics Experience Event field group in your schema</li><li>This field group adds many Adobe Analytics events that are not needed in your Customer Journey Analytics schema.  This can lead to a more cluttered, complex schema than what is otherwise needed for Customer Journey Analytics.</li><li>Highest level of latency across all implementation methods</li><li>Data cannot be shared with other Adobe Experience Platform applications; it is constrained to Customer Journey Analytics only</li></ul> |

#### Adobe Analytics extension

The following table shows the migration methods available for organizations who have implemented Adobe Analytics with the Adobe Analytics extension:

| | Pros | Cons |
|---------|----------|---------|
| **WebSDK (re-implementation)** |<ul><li>Highly performant reporting (low latency) because the infrastructure is built around real-time data </li><li>Future-proof (will receive all the latest features and functionality)</li><li>Consolidate tags between other Experience Cloud products (AJO, RTCDP, etc.)</li></ul> | <ul><li>Most time-consuming and demanding migration method</li><li>Must re-create the full schema in XDM</li></ul> |
| **Analytics Source Connector** | <ul><li>Least time-consuming and demanding migration method: Data is migrated to Customer Journey Analytics quickly with minimal investment </li></ul> | <ul><li>Difficult to move to WebSDK in the future</li><li>Uses the Analytics Experience Event field group in your schema</li><li>This field group adds many Adobe Analytics events that are not needed in your Customer Journey Analytics schema.  This can lead to a more cluttered, complex schema than what is otherwise needed for Customer Journey Analytics.</li><li>Highest level of latency across all implementation methods</li><li>Data cannot be shared with other Adobe Experience Platform applications; it is constrained to Customer Journey Analytics only</li></ul> |
| **Adoption acceleration project** | <ul><li>Provides a good middle ground between a WebSDK re-implementation and using the Analytics Source Connector. </li><li>Quickest method for migrating to the Customer Journey Analytics WebSDK.</li></ul> |  |

#### Adobe Analytics WebSDK

The following table shows the migration methods available for organizations who have implemented Adobe Analytics with the WebSDK:

| | Pros | Cons |
|---------|----------|---------|
| **WebSDK (without re-implementation)** |<ul><li>The ideal migration method; available only with Adobe Analytics WebSDK implementations</li><li>Infrastructure is built around real-time data; this equates to highly performant reporting with low latency</li><li>Future-proof (will receive all the latest features and functionality)</li><li>Consolidate tags between other Experience Cloud products (AJO, RTCDP, etc.)</li></ul> | Slightly more difficult migration than the Analytics Source Connector, but with a much more robust end result. |
| **Analytics Source Connector** | <ul><li>Least time-consuming and demanding migration method: Data is migrated to Customer Journey Analytics quickly with minimal investment </li></ul> | <ul><li>Difficult to move to WebSDK in the future</li><li>Uses the Analytics Experience Event field group in your schema</li><li>This field group adds many Adobe Analytics events that are not needed in your Customer Journey Analytics schema.  This can lead to a more cluttered, complex schema than what is otherwise needed for Customer Journey Analytics.</li><li>Highest level of latency across all implementation methods</li><li>Data cannot be shared with other Adobe Experience Platform applications; it is constrained to Customer Journey Analytics only</li></ul> |

## Step 3: Plan data mapping


## Step 4: Plan user onboarding


## Step 5: Update porting applications

* Port API usage to CJA reporting API (new endpoint, same format)

* Change Adobe Analytics Data Warehouse exports to use Full Table Export in Customer Journey Analytics

* Update Data Feeds use cases to alternatives: ​

  * Raw dataset exports from AEP to public cloud​

  * CJA Full Table Export (use person ID and/or timestamp for audience or event level exports)​

  * CJA BI Extension (for direct integration with Power BI and Tableau)​

  * AEP Query Service (for direct SQL access to data in AEP).​


## Step 6: Migrate projects and components

The Component migration area in Adobe Analytics allows you to migrate projects and components from Adobe Analytics to Customer Journey Analytics. 

For more information, see [Prepare to migrate components and projects from Adobe Analytics to Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration).