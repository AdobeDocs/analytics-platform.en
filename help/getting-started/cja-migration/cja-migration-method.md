---
title: Choose your Customer Journey Analytics migration method
description: Learn the advantages and disadvantes of the possible migration methods when migrating to Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: yes
hidefromtoc: yes
---
# Step 2: Choose your Customer Journey Analytics migration method

+++The information on this page is part of a larger migration process. Expand this section to see where this information fits within the migration process. </br></br>You must complete all previous migration steps before continuing with the information on this page.

Before you continue with this section, first make sure you have completed all previous migration tasks.

The information on this page covers Step 2, as highlighted in the table below: 

| Migration task | Details |
|---------|----------|
| **Step 1: [Get started with the migration](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Learn the benefits of migrating to Adobe Analytics and the basic migration process. |
| <span class="preview">**Step 2: [Choose the migration method](/help/getting-started/cja-migration/cja-migration-method.md)**</span> | <span class="preview">Various methods are available for migrating to Customer Journey Analytics. Choose the method that is best for your organization, depending on your organization's current Adobe Analytics environment and long-term goals.</span> | 
| **Step 3: [Send data to Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | The process for sending data to Adobe Experience Platform differs depending on the migration method that you chose in Step 1. | 
| **Step 4: [Plan data mapping to the XDM schema](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [XDM schemas](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) are used in Adobe Experience Platform to describe the structure of data in a consistent and reusable way. By defining data consistently across systems, it becomes easier to retain meaning and therefore gain value from data.<p>Most migration methods require that you either create a new XDM schema, or map your existing Adobe Analytics schema to XDM by using datastream mapping.</p>  |
| **Step 5: [Retain historical data](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | Most organizations need to retain their historical Adobe Analytics data for a certain amount of time. Various options are available to accomplish this.  | 
| **Step 6: [Plan user onboarding](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | You should give your users ample time (3 - 6 months) to become familiar with the key differences of Analysis Workspace in Customer Journey Analytics. | 
| **Step 7: [Port the reporting API usage](/help/getting-started/cja-migration/cja-migration-api.md)** | The Customer Journey Analytics reporting API is in the same format, but uses a different endpoint. Port the reporting API usage from the Adobe Analytics reporting API to the Customer Journey Analytics reporting API. | 
| **Step 8: [Replace Data Feeds and Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)** | Decide how you will use the export options available in Customer Journey Analytics in order to replace the Data Feeds and Data Warehouse features you were using in Adobe Analytics.  |
| **Step 9: [Migrate projects and components](/help/getting-started/cja-migration/cja-migration-projects.md)** | The Component migration area in Adobe Analytics allows you to migrate projects and their associated components from Adobe Analytics to Customer Journey Analytics.  |

{style="table-layout:auto"}

+++

After you decide to migrate to Customer Journey Analytics, you need to determine the optimal migration method for your organization.  

The method that you choose for migrating from Adobe Analytics to Customer Journey Analytics depends on the following factors: 

* Your existing Adobe Analytics implementation 

* Your goals for the future 

Use the following sections to determine which Customer Journey Analytics migration method best aligns with your organization's current implementation and future goals: 

## Understand migration methods  

Various migration methods exist for migrating from Adobe Analytics to Customer Journey Analytics. 

In general, each migration method differs in the level of effort required to execute the migration, as well as in the long-term viability achieved after the migration completes.  

The following table lists each migration method, its level of effort, and its long-term viability: 

| Migration method | Level of effort | Long-term viability |
|---------|----------|---------|
| **New implementation of the Web SDK**</br>You can do a new Adobe Experience Platform Web SDK implementation to begin sending data to Adobe Experience Platform Edge Network <!-- what is the correct branding -->. <p>For organizations not yet on the Web SDK, this migration method is perhaps the most straightforward in getting data to Edge Network (requiring the fewest number of steps), but all of the work is done up front, such as creating the XDM schema.</p><p>The basic steps are:</p><ol><li>Create an XDM schema for your organization</li><li>Implement the Web SDK</li><li>Send data to Platform</li></ol>| High | High |
| **Migrate your Adobe Analytics implementation to use the Web SDK**</br>If your Adobe Analytics implementation is AppMeasurement or the Analytics extension, you can migrate it to use the Adobe Experience Platform Web SDK to begin sending data to Edge Network prior to sending it to Customer Journey Analytics. <!-- what else? --><p>This is the easiest and smoothest way to get data to Edge Network; it requires more steps, but offers a more methodical transition with more tangible milestones.</p><p>The basic steps are:</p><ol><li>Move your existing Adobe Analytics implementation to the Web SDK and validate that everything is working there.</li><li>Create an XDM schema for your organization as you have time.</li><li>Use Data stream mapping to map all of the fields in the data object to your XDM schema.</li><li>Send data to Platform</li></ol> | Moderate | High |
| **Configure your existing Adobe Analytics Web SDK implementation to send data to Customer Journey Analytics**</br>If your Adobe Analytics implementation is already using the Web SDK, you can begin sending data to Customer Journey Analytics.<p>Before you send data to Customer Journey Analytics, consider updating your Adobe Analytics schema for the specific needs of your organization and any other Platform applications you will use.</p><p>The basic steps are:</p><ol><li>Begin sending data to Customer Journey Analytics.<!-- What's involved here? Just point it at CJA? --></li><li>(Optional) Create an XDM schema for your organization as you have time.</li><li>Use Data stream mapping to map all of the fields in the data object to your XDM schema.</li></ol>  | Low | High |
| **Analytics Source Connector**</br>If your Adobe Analytics implementation is AppMeasurement or the Analytics extension, you can begin sending data to a data view in Customer Journey Analytics.<p>This is the easiest way to get data to Customer Journey Analytics, but is the least viable method in the long term.</p>  | Low | Low |

{style="table-layout:auto"}

Use the following diagram to help visualize where each migration method falls on the spectrum in terms of level of effort, as well as the long-term viability that each achieves:

![cja migration methods](assets/cja-migration-methods.png)

## Assess the migration methods available to you based on your current Adobe Analytics implementation

Not all migration methods are available for each type of Adobe Analytics implementation. 

Use the information below as general guidelines to help you understand which migration method is most appropriate for your organization. 

Contact your Adobe representative if you need more specific advice, guidance, or support.

|Adobe Analytics implementation | Available migration methods |
|---------|----------|
| AppMeasurement | <ul><li>New implementation of the Web SDK</li><li>Migrate Adobe Analytics to the Web SDK</li><li>Analytics Source Connector</li></ul>  | 
| Adobe Analytics extension | <ul><li>New implementation of the Web SDK</li><li>Migrate Adobe Analytics to the Web SDK</li><li>Analytics Source Connector</li></ul> | 
| Web SDK | <ul><li>Configure the Adobe Analytics Web SDK implementation to send data to Customer Journey Analytics</li></ul> | 

{style="table-layout:auto"}

## Weigh the advantages and disadvantages of the migration methods available to you

The advantages and disadvantages of a given migration method differ depending on your existing Adobe Analytics implementation. 

Before you use the information below to determine which migration method is right for you, review the information in [Understand migration methods](#understand-migration-methods) if you haven't already.

### AppMeasurement and Adobe Analytics extension

The following table shows the migration methods available for organizations who have implemented Adobe Analytics with AppMeasurement or the Adobe Analytics extension:

| Migration method | Advantages | Disadvantages |
|---------|----------|---------|
| **New implementation of the Web SDK** |<ul><li>Uses an XDM schema, a flexible schema to define any fields you need</li><li>Not reliant on Adobe Analytics nomenclature (prop, eVar, event, etc.)</li><li>No character limit concerns (100 chars for props)</li><li>Highly performant reporting and data availability because Adobe Experience Platform is built to power [real-time personalization use cases](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)</li><li>Future-proof (will receive all the latest features and functionality)</li><li>Consolidate tags for Adobe Experience Cloud data collection between other Experience Cloud products (AJO, RTCDP, etc.)</li><li>[First-party device IDs](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/first-party-device-ids.html) for enhanced accuracy of visitor identification</li></ul> | <ul><li>Most time-consuming and demanding migration method<p>Must re-create the full schema in XDM before you can start implementing the Web SDK</p></li></ul> |
| **Migrate Adobe Analytics to the Web SDK** | <ul><li>Retains rules and data elements already configured in your Adobe Analytics implementation.</li><li>Enables you to move to the Web SDK without impacting your existing Adobe Analytics reporting.</li><li>Provides flexibility to create an XDM schema for your organization at a later time.</br>Does not require the Adobe Analytics Experience Event Field group in Customer Journey Analytics. <!-- With the new implementation, you're double-counting with 2 implementation; with the migration, you're double-counting, but both of them are through Edge Network. --></li><li>Not reliant on Adobe Analytics nomenclature (prop, eVar, event, etc.)</li><li>No character limit concerns (100 chars for props)</li><li>Highly performant reporting and data availability because Adobe Experience Platform is built to power [real-time personalization use cases](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)</li><li>Future-proof (will receive all the latest features and functionality)</li><li>Consolidate tags for Adobe Experience Cloud data collection between other Experience Cloud products (AJO, RTCDP, etc.)</li><li>[First-party device IDs](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/first-party-device-ids.html) for enhanced accuracy of visitor identification</li></ul> | <ul><li>Must conform to an XDM schema at some point in the future, using datastream mapping.</li><li>Incurs some technical debt. For example, legacy AppMeasurement or Analytics extension code can remain. </li></ul> |
| **Analytics Source Connector** | <ul><li>Least time-consuming and demanding migration method. <p>Data is migrated to Customer Journey Analytics quickly with minimal investment</p></li></ul> | <ul><li>Data is not sent to Edge Network and cannot be shared with other Adobe Experience Platform applications; it is constrained to Customer Journey Analytics only<li>Difficult to move to Web SDK in the future</li><li>Uses the Analytics Experience Event field group in your schema.</br>This field group adds many Adobe Analytics events that are not needed in your Customer Journey Analytics schema.  This can lead to a more cluttered, complex schema than what is otherwise needed for Customer Journey Analytics.</li><li>Highest level of [latency](/help/admin/guardrails.md#latencies) across all implementation methods</li></ul> |

{style="table-layout:auto"}

### Web SDK

The following table shows the migration methods available for organizations who have implemented Adobe Analytics with the Web SDK:

| Migration method | Advantages | Disadvantages |
|---------|----------|---------|
| **Configure the Adobe Analytics Web SDK implementation to send data to Customer Journey Analytics** | This is the preferred migration method if your Adobe Analytics implementation is already using the Web SDK. <p>When using this implementation method, you can choose whether to use your existing Adobe Analytics schema, or you can update to the XDM schema to better align with the needs of your organization as you begin to use other Platform applications.</p><p>**Using the Adobe Analytics schema**</p><p>Advantages of using the Adobe Analytics schema include:</p><ul><li>Ease of migration<p>If you are already sending data to Adobe Analytics with the Adobe Experience Platform Web SDK, you can add an additional service to your datastream to send data to Adobe Experience Platform (which then can be used in your Customer Journey Analytics configuration).</p></li></ul><p>Disadvantages of using the Adobe Analytics schema include:</p><ul><li>While using the Adobe Analytics schema doesn't limit you in terms of how it can be used with other Platform applications, it does result in a schema that is more complex than it otherwise could be. This is because the Adobe Analytics schema contains many objects that are specific to Adobe Analytics that likely will not be used by your organization.<p>When changes to the schema are required, you have to sift through thousands of unused fields to find the field that requires updating.</p></li></ul><p>**Using the XDM schema**</p><p>Advantages of updating the XDM schema include:</p><ul><li>A streamlined schema that is tailored to the needs of your organization and the specific Platform applications that you use.</li><p>When changes to the schema are required, you don't have to sift through thousands of unused fields to find the field that requires updating.</p></ul><p>Disadvantages of updating the XDM schema include:</p><ul><li>Updating your schema is a time-consuming process that is required before you begin sending data to Customer Journey Analytics.</li></ul> | None |

{style="table-layout:auto"}

## Next, send data to Adobe Experience Platform

After you use the information above to choose a migration method, learn how to [send data to Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md) depending on the migration method that you chose.