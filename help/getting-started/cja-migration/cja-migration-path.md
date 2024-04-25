---
title: Choose your Customer Journey Analytics migration path
description: Learn the advantages and disadvantes of the possible migration paths when migrating to Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 9559ba10-cbaf-4243-9c85-a0a5f6e3bbff
---
# Step 2: Choose your migration path

+++Expand this section to see where the information on this page fits into the larger migration process. Make sure all previous migration steps are complete.

Before you continue with this section, first make sure you have completed all previous migration tasks.

The information on this page covers Step 2 of the migration, as highlighted in the table below: 

| Migration task | Details |
|---------|----------|
| **Step 1: [Get started with the migration](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Learn the benefits of migrating to Adobe Analytics and the basic migration process. |
| <span class="preview">**Step 2: Choose the migration path**</span> | <span class="preview">Various methods are available for migrating to Customer Journey Analytics. Choose the method that is best for your organization, depending on your organization's current Adobe Analytics environment and long-term goals.</span> | 
| **Step 3: [Send data to Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | The process for sending data to Adobe Experience Platform differs depending on the migration path that you chose in Step 2. | 
| **Step 4: [Retain historical data](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | Most organizations need to retain their historical Adobe Analytics data for a certain amount of time. Various options are available to accomplish this. | 
| **Step 5: [Perform additional implementation tasks](/help/getting-started/cja-getting-started.md)** | At this point in the migration process, you need to perform various tasks before your Customer Journey Analytics environment is ready to use.<p>These additional tasks apply to migrations from Adobe Analytics as well as new Customer Journey Analytics implementations.</p><p>These tasks include:</p><ul><li>Bringing other data into Experience Platform</li><li>Creating connections between Platform datasets and Customer Journey Analytics</li><li>Creating data views</li><li>Porting the reporting API usage</li><li>Accounting for Data Feeds and Data Warehouse</li><li>Migrating projects and components</li><li>Planning user onboarding</li></ul> <p>For more information, see [Customer Journey Analytics Getting Started](/help/getting-started/cja-getting-started.md).  |

{style="table-layout:auto"}

+++

After you decide to migrate to Customer Journey Analytics, you need to determine the optimal migration path for your organization.   

The path that you choose for migrating from Adobe Analytics to Customer Journey Analytics depends on the following factors: 

* Your existing Adobe Analytics implementation 

* Your goals for the future 

Use the information on this page to determine which Customer Journey Analytics migration path best aligns with your organization's current implementation and future goals.

To determine the optimal migration path for your organization, the following sections should be read sequentially: 

1. First, [understand the migration paths that are available](#understand-migration-methods).

1. Then, [assess which migration paths are available to you](#assess-the-migration-methods-available-to-you-based-on-your-current-adobe-analytics-implementation).

1. And finally, [weigh the advantages and disadvantages of each migration path](#weigh-the-advantages-and-disadvantages-of-the-migration-methods-available-to-you). 

## Understand migration paths  

Various migration paths exist for migrating from Adobe Analytics to Customer Journey Analytics. 

In general, each migration path differs in the level of effort required to execute the migration, as well as in the long-term viability achieved after the migration completes.  

The following table lists each migration path, its level of effort, and its long-term viability: 

| Migration path | Level of effort | Long-term viability |
|---------|----------|---------|
| **New implementation of the Experience Platform Web SDK**</br>While this is not technically a migration, you can begin using Customer Journey Analytics by doing a new implementation of the Experience Platform Web SDK to begin sending data to Adobe Experience Platform Edge Network and Customer Journey Analytics. <p>For organizations not yet on the Web SDK, this migration path is perhaps the most straightforward in getting data to Edge Network because it requires the fewest number of steps; however, because all of the work is done up front (such as creating the XDM schema), it requires a larger initial effort.</p><p>The basic steps are:</p><ol><li>Create an XDM schema for your organization.</li><li>Implement the Web SDK.</li><li>Send data to Platform.</li></ol>| High | High |
| **Migrate your Adobe Analytics implementation to use the Web SDK**</br>If your Adobe Analytics implementation is AppMeasurement or the Analytics extension, you can migrate it to use the Adobe Experience Platform Web SDK to begin sending data to Edge Network and Adobe Analytics, prior to sending it to Customer Journey Analytics.<p>For organizations not yet on the Web SDK, this is the easiest and smoothest way to get data to Edge Network; it requires more steps, but offers a more methodical transition from Adobe Analytics to Customer Journey Analytics, with more tangible milestones.</p><p>The basic steps are:</p><ol><li>Move your existing Adobe Analytics implementation to the Web SDK and validate that everything is working in Adobe Analytics.</li><li>Create an XDM schema for your organization as you have time.</li><li>Use Datastream mapping to map all of the fields in the data object to your XDM schema.</li><li>Send data to Platform.</li></ol> | Moderate | High |
| **Configure your existing Adobe Analytics Web SDK implementation**</br>If your Adobe Analytics implementation is already using the Adobe Experience Platform Web SDK, you can begin sending data to Customer Journey Analytics with minimal effort.<p>Before you send data to Customer Journey Analytics, consider updating your Adobe Analytics schema for the specific needs of your organization and any other Platform applications you will use.</p><p>The basic steps are:</p><ol><li>Begin sending data to Customer Journey Analytics.<!-- What's involved here? Just point it at CJA? --></li><li>(Optional) Create an XDM schema for your organization as you have time.</li><li>(Conditional) If you created an XDM schema, use datastream mapping to map all of the fields in the data object to your XDM schema.</li></ol>  | Low | High |
| **Use the Analytics Source Connector**</br>If your Adobe Analytics implementation is AppMeasurement or the Analytics extension, you can begin sending data to a data view in Customer Journey Analytics.<p>This is the easiest way to get data to Customer Journey Analytics, but is the least viable method in the long term.</p>  | Low | Low |

{style="table-layout:auto"}

Use the following diagram to help visualize where each migration path falls on the spectrum in terms of level of effort and long-term viability:

![cja migration paths](assets/cja-migration-methods.png)

## Assess the migration paths available to you based on your current Adobe Analytics implementation

Not all migration paths are available for each type of Adobe Analytics implementation. 

Use the information below to help you understand which migration path is most appropriate for your organization. 

Contact your Adobe representative if you need more specific advice, guidance, or support.

|Existing Adobe Analytics implementation | Available migration paths |
|---------|----------|
| AppMeasurement | <ul><li>New implementation of the Experience Platform Web SDK</li><li>Migrate Adobe Analytics to the Web SDK</li><li>Analytics Source Connector</li></ul>  | 
| Adobe Analytics extension | <ul><li>New implementation of the Experience Platform Web SDK</li><li>Migrate Adobe Analytics to the Web SDK</li><li>Analytics Source Connector</li></ul> | 
| Web SDK | <ul><li>Configure the Adobe Analytics Web SDK implementation to send data to Customer Journey Analytics</li></ul> | 

{style="table-layout:auto"}

## Weigh the advantages and disadvantages of the migration paths available to you

The advantages and disadvantages of a given migration path differ depending on your existing Adobe Analytics implementation. 

Before you use the information below to determine which migration path is right for you, review the information in [Understand migration paths](#understand-migration-methods) if you haven't already.

### For Adobe Analytics implementations using: AppMeasurement and Adobe Analytics extension

Following are the migration paths available for organizations who have implemented Adobe Analytics with AppMeasurement or the Adobe Analytics extension. Expand each section to view the advantages and disadvantages of each migration path.

**Migration paths:** 

+++New implementation of the Experience Platform Web SDK

| Advantages | Disadvantages |
|----------|---------|
|<ul><li>**Provides all the advantages of hosting data in Experience Edge Network**: <p>These advantages include:</p><ul><li>Highly performant reporting and data availability because Adobe Experience Platform is built to power [real-time personalization use cases](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)</li><li>Consolidate tags for Adobe Experience Cloud data collection between other Experience Cloud products (AJO, RTCDP, and so forth)</li><li>Not reliant on Adobe Analytics nomenclature (prop, eVar, event, and so forth)</li></ul></li><li>**Uses an XDM schema**: [XDM schemas](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) are a flexible schema to define any fields you need, and only those fields that are relevant. Using an XDM schema allows you to move away from the Adobe Analytics Experience Event Field group.</li><li>**No character limits**: The XDM schema has no character limits.</li><li>**Future-proof**: The Experience Platform Web SDK will receive all the latest features and functionality.</li><li>**Better accuracy of visitor identification**: The Experience Platform Web SDK uses [First-party device IDs](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/first-party-device-ids.html) for enhanced accuracy of visitor identification.</li></ul> | <ul><li>**Requires a new implementation from scratch**: The requirement to do a new implementation from scratch means the following disadvantages: </li><ul><li>**Time consuming**: This is the most time-consuming and demanding migration path because it requires that you start over with a new implementation.</li><li>**Must re-create the full schema in XDM**: Before you can start implementing the Web SDK, you have to re-create the full schema in XDM.</li><li>**Must re-create rules and data elements**: Before you can start implementing the Web SDK, you have to re-create any rule conditions and data elements from your Adobe Analytics implementation.</li></ul></ul> |

{style="table-layout:auto"}

+++

+++Migrate Adobe Analytics to the Experience Platform Web SDK

| Advantages | Disadvantages |
|----------|---------|
|<ul><li>**Provides all the advantages of hosting data in Experience Edge Network**: <p>These advantages include:</p><ul><li>Highly performant reporting and data availability because Adobe Experience Platform is built to power [real-time personalization use cases](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)</li><li>Consolidate tags for Adobe Experience Cloud data collection between other Experience Cloud products (AJO, RTCDP, and so forth)</li><li>Not reliant on Adobe Analytics nomenclature (prop, eVar, event, and so forth)</li></ul><li>**Uses your existing implementation**: While this approach requires some implementation changes, it does not require a completely new implementation from scratch. You can use your existing data layer and code with minimal changes to implementation logic without impacting your existing Adobe Analytics reporting.</li><li>**Provides flexibility to create an XDM schema for your organization at a later time**: You can migrate your existing Adobe Analytics implementation to use the Web SDK and validate that everything is working in Adobe Analytics, then create the XDM schema. This flexibility allows for a more methodical and thoughtful migration.</li><li>**Uses an XDM schema**: [XDM schemas](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) are a flexible schema to define any fields you need, and only those fields that are relevant. Using an XDM schema allows you to move away from the Adobe Analytics Experience Event Field group.</li><li>(when migrating from the Adobe Analytics tag extension) **Retains rules and data elements**: While it does require new rule actions, you can reuse your existing data elements and rule conditions with minimal changes.</li><li>**No character limits**: The XDM schema has no character limits.</li><li>**Future-proof**: The Experience Platform Web SDK will receive all the latest features and functionality.</li><li>**Better accuracy of visitor identification**: The Experience Platform Web SDK uses [First-party device IDs](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/first-party-device-ids.html) for enhanced accuracy of visitor identification.</li></ul> | <ul><li>**Requires mapping to send data to Platform**: When your organization is ready to use Customer Journey Analytics, you must send data to a data set in Adobe Experience Platform. This action requires that every field in the data object be an entry in the datastream mapping tool that assigns it to an XDM schema field. Mapping only needs to be done once for this workflow, and it doesn't involve making implementation changes. However, it is an extra step that is not required when sending data in an XDM object.</li><li>**Technical debt**: Because this approach uses a modified form of your existing implementation, it can be harder to track implementation logic and perform changes in the future when needed. </li><li>(When migrating from AppMeasurement only) **Implementation changes require developer intervention**: If you want to make changes to your Web SDK implementation, you must work with your development team to edit the code on your site. This does not apply when migrating to the Web SDK tag from the Analytics tag extension.</li></ul> |

{style="table-layout:auto"}

+++

+++Use the Analytics Source Connector

| Advantages | Disadvantages |
|----------|---------|
| <ul><li>Least time-consuming and demanding migration path. <p>Data is migrated to Customer Journey Analytics quickly with minimal investment</p></li></ul> | <ul><li>**Data is not sent to Edge Network**: <p>This results in the following disadvantages:</p><ul><li>More latency in reporting; not optimized for real-time personalization use cases.</li><li>Data cannot be shared with other Adobe Experience Platform applications; it is constrained to Customer Journey Analytics only</li><li>Reliant on Adobe Analytics nomenclature (prop, eVar, event, and so forth)</li></ul><li>Difficult to move to the Web SDK in the future</li><li>Uses the Analytics Experience Event field group in your schema.</br>This field group adds many Adobe Analytics events that are not needed in your Customer Journey Analytics schema.  This can lead to a more cluttered, complex schema than what is otherwise needed for Customer Journey Analytics.</li><li>Highest level of [latency](/help/admin/guardrails.md#latencies) across all implementation methods</li></ul> | 

{style="table-layout:auto"}

+++

### For Adobe Analytics implementations using: Web SDK

The following migration path is available for organizations who have implemented Adobe Analytics with the Experience Platform Web SDK:

**Migration path:**

+++Configure the Adobe Analytics Web SDK implementation to send data to Customer Journey Analytics

| Advantages | Disadvantages |
|----------|---------|
| This is the preferred migration path if your Adobe Analytics implementation is already using the Web SDK. <p>When using this implementation method, you can choose whether to use your existing Adobe Analytics schema, or you can update to the XDM schema to better align with the needs of your organization as you begin to use other Platform applications.</p><p>**Using the Adobe Analytics schema**</p><p>Advantages of using the Adobe Analytics schema include:</p><ul><li>Ease of migration<p>If you are already sending data to Adobe Analytics with the Adobe Experience Platform Web SDK, you can add an additional service to your datastream to send data to Adobe Experience Platform (which then can be used in your Customer Journey Analytics configuration).</p></li></ul><p>Disadvantages of using the Adobe Analytics schema include:</p><ul><li>While using the Adobe Analytics schema doesn't limit you in terms of how it can be used with other Platform applications, it does result in a schema that is more complex than it otherwise could be. This is because the Adobe Analytics schema contains many objects that are specific to Adobe Analytics that likely will not be used by your organization.<p>When changes to the schema are required, you have to sift through thousands of unused fields to find the field that requires updating.</p></li></ul><p>**Using the XDM schema**</p><p>Advantages of updating the XDM schema include:</p><ul><li>A streamlined schema that is tailored to the needs of your organization and the specific Platform applications that you use.</li><p>When changes to the schema are required, you don't have to sift through thousands of unused fields to find the field that requires updating.</p></ul><p>Disadvantages of updating the XDM schema include:</p><ul><li>Updating your schema is a time-consuming process that is required before you begin sending data to Customer Journey Analytics.</li></ul> | None |

{style="table-layout:auto"}

+++

## Next, send data to Adobe Experience Platform

After you use the information above to choose a migration path, learn how to [send data to Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md) depending on the migration path that you chose.
