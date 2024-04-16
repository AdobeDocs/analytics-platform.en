---
title: Plan your migration from Adobe Analytics to Customer Journey Analytics
to Customer Journey Analytics
description: Plan your migration from Adobe Analytics to Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
---
# Migration guide: Plan your migration from Adobe Analytics to Customer Journey Analytics

Various migration methods exist for migrating from Adobe Analytics to Customer Journey Analytics. However, depending on your current Adobe Analytics implementation, some migration methods might not be available to your organization. 

Use the information below as general guidelines to help you understand which migration method looks most appropriate for your organization. 

Contact your Adobe representative if you need more specific advice, guidance, or support.

## Step 1 - Understand the benefits of Customer Journey Analytics

Customer Journey Analytics is the next generation of analytics. It allows multi-channel data collection (both online and offline data), combined with powerful report-time processing functionality (through the definition of components and derived fields in data views). 

As you plan your migration, learn how Customer Journey Analytics can benefit your organization. Following are some of the key benefits: (For a comprehensive list, as well as more information about each of these key features, see [Features available only in Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md#adobe-customer-journey-analytics-features-not-available-in-adobe-analytics).) 

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

## Step 2: Choose your Customer Journey Analytics migration method

After you decide to migrate to Customer Journey Analytics, you need to determine the optimal migration method for your organization.  

The method that you choose for migrating from Adobe Analytics to Customer Journey Analytics depends on the following factors: 

* Your existing Adobe Analytics implementation 

* Your goals for the future 

Use the following sections to determine which Customer Journey Analytics migration method best aligns with your organization's current implementation and future goals: 

### Assess the migration methods available to you based on your current Adobe Analytics implementation

There are various methods available for migrating from Adobe Analytics to Customer Journey Analytics.  

#### Understand migration methods  

In general, each migration method differs in the level of effort required to execute the migration, as well as in the long-term viability achieved after the migration completes.  

The following table lists each migration method, its level of effort, and its long-term viability: 

| Migration method | Level of effort | Long-term viability |
|---------|----------|---------|
| **New implementation of the Web SDK**</br>You can do a new Adobe Experience Platform Web SDK implementation to begin sending data to Adobe Experience Platform Edge Network <!-- what is the correct branding -->. <p>For organizations not yet on the Web SDK, this migration method is perhaps the most straightforward in getting data to Edge Network (requiring the fewest number of steps), but all of the work is done up front, such as creating the XDM schema.</p><p>The basic steps are:</p><ol><li>Create an XDM schema for your organization</li><li>Implement the Web SDK</li><li>Send data to Platform</li></ol>| High | High |
| **Migrate your Adobe Analytics implementation to use the Web SDK (Coming soon)**</br>If your Adobe Analytics implementation is AppMeasurement or the Analytics extension, you can migrate it to use the Adobe Experience Platform Web SDK to begin sending data to Edge Network prior to sending it to Customer Journey Analytics. <!-- what else? --><p>This is the easiest and smoothest way to get data to Edge Network; it requires more steps, but offers a more methodical transition with more tangible milestones.</p><p>The basic steps are:</p><ol><li>Move your existing Adobe Analytics implementation to the Web SDK and validate that everything is working there.</li><li>Create an XDM schema for your organization as you have time.</li><li>Use Data stream mapping to map all of the fields in the data object to your XDM schema.</li><li>Send data to Platform</li></ol> | Moderate | High |
| **Configure your existing Adobe Analytics Web SDK implementation to send data to Customer Journey Analytics**</br>If your Adobe Analytics implementation is already using the Web SDK, you can begin sending data to Customer Journey Analytics.<p>Before you send data to Customer Journey Analytics, consider updating your Adobe Analytics schema for the specific needs of your organization and any other Platform applications you will use.</p><p>The basic steps are:</p><ul><li>Begin sending data to Customer Journey Analytics.<!-- What's involved here? Just point it at CJA? --></li><li>(Optional) Create an XDM schema for your organization as you have time.</li><li>Use Data stream mapping to map all of the fields in the data object to your XDM schema.</li>  | Low | High |
| **Analytics Source Connector**</br>If your Adobe Analytics implementation is AppMeasurement or the Analytics extension, you can begin sending data to a data view in Customer Journey Analytics.<p>This is the easiest way to get data to Customer Journey Analytics, but is the least viable method in the long term.</p>  | Low | Low |

{style="table-layout:auto"}

Use the following diagram to help visualize where each migration method falls on the spectrum in terms of level of effort, as well as the long-term viability that each achieves:

![cja migration methods](assets/cja-migration-methods.png)

#### Migration methods available based on your Adobe Analytics implementation

Not all migration methods are available for each type of Adobe Analytics implementation. The following table shows which migration methods are available to you, based on your existing Adobe Analytics implementation: 

|Adobe Analytics implementation | Available migration methods |
|---------|----------|
| AppMeasurement | <ul><li>New implementation of the Web SDK</li><li>Migrate Adobe Analytics to the Web SDK (Coming soon)</li><li>Analytics Source Connector</li></ul>  | 
| Adobe Analytics extension | <ul><li>New implementation of the Web SDK</li><li>Migrate Adobe Analytics to the Web SDK (Coming soon)</li><li>Analytics Source Connector</li></ul> | 
| Web SDK | <ul><li>Configure the Adobe Analytics Web SDK implementation to send data to Customer Journey Analytics</li></ul> | 

{style="table-layout:auto"}

### Weigh the pros and cons of the migration methods available to you

The pros and cons of a given migration method differ depending on your existing Adobe Analytics implementation. 

Before you use the information below to determine which migration method is right for you, review the information in [Understand migration methods](#understand-migration-methods) if you haven't already.

#### AppMeasurement and Adobe Analytics extension

The following table shows the migration methods available for organizations who have implemented Adobe Analytics with AppMeasurement or the Adobe Analytics extension:

| Migration method | Pros | Cons |
|---------|----------|---------|
| **New implementation of the Web SDK** |<ul><li>Uses an XDM schema, a flexible schema to define any fields you need</li><li>Not reliant on Adobe Analytics nomenclature (prop, eVar, event, etc.)</li><li>No character limit concerns (100 chars for props)</li><li>Highly performant reporting and data availability because Adobe Experience Platform is built to power [real-time personalization use cases](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)</li><li>Future-proof (will receive all the latest features and functionality)</li><li>Consolidate tags for Adobe Experience Cloud data collection between other Experience Cloud products (AJO, RTCDP, etc.)</li><li>[First-party device IDs](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/first-party-device-ids.html) for enhanced accuracy of visitor identification</li></ul> | <ul><li>Most time-consuming and demanding migration method<p>Must re-create the full schema in XDM before you can start implementing the Web SDK</p></li></ul> |
| **Migrate Adobe Analytics to the Web SDK (Coming soon)** | <ul><li>Retains rules and data elements already configured in your Adobe Analytics implementation.</li><li>Enables you to move to the Web SDK without impacting your existing Adobe Analytics reporting.</li><li>Provides flexibility to create an XDM schema for your organization at a later time.</br>Does not require the Adobe Analytics Experience Event Field group in Customer Journey Analytics. <!-- With the new implementation, you're double-counting with 2 implementation; with the migration, you're double-counting, but both of them are through Edge Network. --></li><li>Not reliant on Adobe Analytics nomenclature (prop, eVar, event, etc.)</li><li>No character limit concerns (100 chars for props)</li><li>Highly performant reporting and data availability because Adobe Experience Platform is built to power [real-time personalization use cases](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)</li><li>Future-proof (will receive all the latest features and functionality)</li><li>Consolidate tags for Adobe Experience Cloud data collection between other Experience Cloud products (AJO, RTCDP, etc.)</li><li>[First-party device IDs](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/first-party-device-ids.html) for enhanced accuracy of visitor identification</li></ul> | <ul><li>Must conform to an XDM schema at some point in the future, using datastream mapping.</li><li>Incurs some technical debt. For example, legacy AppMeasurement or Analytics extension code can remain. </li></ul> |
| **Analytics Source Connector** | <ul><li>Least time-consuming and demanding migration method. <p>Data is migrated to Customer Journey Analytics quickly with minimal investment</p></li></ul> | <ul><li>Data is not sent to Edge Network and cannot be shared with other Adobe Experience Platform applications; it is constrained to Customer Journey Analytics only<li>Difficult to move to Web SDK in the future</li><li>Uses the Analytics Experience Event field group in your schema.</br>This field group adds many Adobe Analytics events that are not needed in your Customer Journey Analytics schema.  This can lead to a more cluttered, complex schema than what is otherwise needed for Customer Journey Analytics.</li><li>Highest level of [latency](/help/admin/guardrails.md#latencies) across all implementation methods</li></ul> |

{style="table-layout:auto"}

#### Web SDK

The following table shows the migration methods available for organizations who have implemented Adobe Analytics with the Web SDK:

| Migration method | Pros | Cons |
|---------|----------|---------|
| **Configure the Adobe Analytics Web SDK implementation to send data to Customer Journey Analytics** | This is the preferred migration option if your Adobe Analytics implementation is already using the Web SDK. <p>When using this implementation method, you can choose whether to use your existing Adobe Analytics schema, or to update to the XDM schema to better align with the needs of your organization as you begin to use other Platform applications.</p><p>**Using the Adobe Analytics schema**</p><p>Advantages of using the Adobe Analytics schema include:</p><ul><li>Ease of migration<p>If you are already sending data to Adobe Analytics with the Adobe Experience Platform Web SDK, you can add an additional service to your datastream to send data to Adobe Experience Platform (which then can be used in your Customer Journey Analytics configuration).</p></li></ul><p>Disadvantages of using the Adobe Analytics schema include:</p><ul><li>While using the Adobe Analytics schema doesn't limit you in terms of how it can be used with other Platform applications, it does result in a schema that is more complex than it otherwise could be. This is because the Adobe Analytics schema contains many objects that are specific to Adobe Analytics and that likely will not be used by your organization.<p>When changes to the schema are required, you have to sift through thousands of unused fields to find the field that requires updating.</p></li></ul><p>**Using the XDM schema**</p><p>Advantages of updating the XDM schema include:</p><ul><li>A streamlined schema that is tailored to the needs of your organization and the specific Platform applications that you use.</li><p>When changes to the schema are required, you don't have to sift through thousands of unused fields to find the field that requires updating.</p></ul><p>Disadvantages of updating the XDM schema include:</p><ul><li>Updating your schema is a time-consuming process that is required before you begin sending data to Customer Journey Analytics.</li></ul> | None |

{style="table-layout:auto"}

## Step 3: Begin the migration

After you [choose the migration method](#step-2-choose-your-customer-journey-analytics-migration-method) that is best for your organization, you can begin ingesting data into Customer Journey Analytics. 

The process for data ingestion for each migration method is described below:

|Migration method | Data ingestion process | 
|---------|----------|
| New implementation of the Web SDK | [Ingest data via the Adobe Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) | 
| Migrate your Adobe Analytics implementation to use the Web SDK | (Coming soon) | 
| Configure your existing Adobe Analytics Web SDK implementation to send data to Customer Journey Analytics | [Set up a datastream](/https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-datastream) in [Ingest data via the Adobe Experience Platform Web SDK](/https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk)  | 
| Analytics Source Connector | [Ingest and use data from traditional Adobe Analytics](/help/data-ingestion/analytics.md) | 

## Step 4: Determine how to retain historical data

Choose one of the following options to retain historical data when moving from Adobe Analytics to Customer Journey Analytics: 

* Utilize the [Analytics Source Connector](/help/data-ingestion/analytics.md).

  Regardless of the migration method that you choose (even if you migrate using the Web SDK), you can use the Analytics Source Connector to retain historical data from your Adobe Analytics environment. 

  You can use the Analytics Source Connector to retain historical data in the following ways:
  
  * Bring historical data into its own dedicated location, separate from your current data.

  * Map historical data in a way that allows you to tie it to your new data. <!-- Possible? Explain -->

* Maintain your existing Adobe Analytics implementation alongside your new Customer Journey Analytics implementation for a specific time frame (for example, 1 year). You can decommission the Adobe Analytics implementation after you have sufficient data in Customer Journey Analytics. 

  Contact your Adobe account representative to determine pricing for this option. 

## Step 5: Plan data mapping to the XDM schema

Working with your data team, identify your organization's ideal schema design for Customer Journey Analytics, then determine how you will map eVars and Props to XDM. 



## Step 6: Plan user onboarding

There are a few key differences between Customer Journey Analytics and Adobe Analytics that users need to be aware of. 

Like in Adobe Analytics, Analysis Workspace is the main user-facing tool in Customer Journey Analytics. However, there are some key differences when using Analysis Workspace in Customer Journey Analytics that users need to be aware of. 

You should give your users ample time (3 - 6 months) to become familiar with the key differences of Analysis Workspace in Customer Journey Analytics.

For information about some of the key differences between Adobe Analytics and Customer Journey Analytics, see [User Guide for Adobe Analytics users](help/getting-started/aa-to-cja-user.md).

## Step 7: Port the reporting API usage 

Port the reporting API usage from the Adobe Analytics reporting API to the Customer Journey Analytics reporting API. 

The Customer Journey Analytics reporting API is in the same format, but uses a different endpoint.

## Step 8: Plan Data Feeds and Data Warehouse replacements

If you currently use Data Feeds or Data Warehouse in Adobe Analytics, use the following table to learn about the various export options available in Customer Journey Analytics:

| Adobe Analytics | Customer Journey Analytics | 
|---------|----------|
| Data Feeds | Update your Data Feeds use cases to use any combination of alternative export methods that are available in Customer Journey Analytics: <ul><li>Raw dataset exports from Adobe Experience Platform to public cloud​</li><li>[Full Table Export](/help/analysis-workspace/export/export-cloud.md) (use person ID and/or timestamp for audience or event level exports)​</li><li>Customer Journey Analytics BI Extension (for direct integration with Power BI and Tableau)​</li><li>Adobe Experience Platform Query Service (for direct SQL access to data in Adobe Experience Platform)</li></ul> | 
| Data Warehouse | Change Adobe Analytics Data Warehouse exports to use [Full Table Export](/help/analysis-workspace/export/export-cloud.md) in Customer Journey Analytics.<p>Customer Journey Analytics Full Table Export is the evolution of Data Warehouse reports in Adobe Analytics, with many new, often-requested features that are not available in Data Warehouse today.</p> | 

{style="table-layout:auto"}

## Step 9: Migrate projects and components

The Component migration area in Adobe Analytics allows you to migrate projects and their associated components from Adobe Analytics to Customer Journey Analytics. 

The migration process includes:

* Re-creating Adobe Analytics projects in Customer Journey Analytics.

* Mapping dimensions and metrics from Adobe Analytics report suites to dimensions and metrics in Customer Journey Analytics data views.

Before you begin the migration, first [Prepare to migrate components and projects from Adobe Analytics to Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration.html). 

After you make all of the needed preparations, you can [Migrate components and projects from Adobe Analytics to Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/component-migration.html).

## Step 10: Get started with Customer Journey Analytics

Before you begin using Customer Journey Analytics, complete the steps outlined in [Customer Journey Analytics Getting Started](/help/getting-started/cja-getting-started.md).