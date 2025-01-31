---
title: Evaluate how long you need Adobe Analytics after upgrading to Customer Journey Analytics
description: Learn how to evaluate how long you need Adobe Analytics after upgrading to Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: yes
hidefromtoc: yes
---
# Evaluate how long you need Adobe Analytics after upgrading to Customer Journey Analytics

>[!NOTE]
>
>This documentation should be used as part of the [Adobe Analytics to Customer Journey Analytics upgrade questionnaire](https://gigazelle.github.io/cja-ttv/).

Most organizations will eventually disable Adobe Analytics after upgrading to Customer Journey Analytics. 

Consider the following when choosing if and when your organization should disable Adobe Analytics: 

## Perform side-by-side data comparison



## Retain historical data from Adobe Analytics



## Use Data Feeds or other Adobe Analytics features

A small set of features are not yet fully available in Customer Journey Analytics. If you need access to these features, it might be necessary to use Adobe Analytics in conjunction with Customer Journey Analytics until these features are available. 

Features not fully available in Customer Journey Analytics include Data Feeds and Contribution Analysis. For a full list of features that aren't yet supported, see [Customer Journey Analytics feature support](/help/getting-started/aa-vs-cja/cja-aa.md).


1. Perform 

the cost and complexity

Consider the following milestones related to removing Adobe Analytics:

1. Stop collecting data with the Analytics source connector. 

   After you are satisfied with side-by-side comparisons of your Adobe Analytics data and your Customer Journey Analytics data, you can stop collecting data with your Adobe Analytics implementation. New Adobe Analytics data will no longer flow to Customer Journey Analytics through the Analytics source connector. However, data that you collected from your Adobe Analytics environment prior to now is still available as historical data through the Analytics source connector.

1. Remove the Analytics source connector entirely. 

   After you have collected enough historical data with the new Web SDK implementation, you can remove the Analytics source connector entirely. Do this when you no longer need the historical data from your Adobe Analytics environment through the Analytics source connector, and you can rely solely on the historical data you collected with the new Web SDK implementation. 

## Weigh the advantages and disadvantages of the upgrade paths available to you

The advantages and disadvantages of a given upgrade path differ depending on your existing Adobe Analytics implementation. 

Before you use the information below to determine which upgrade path is right for you, review the information in [Understand upgrade paths](#understand-migration-methods) if you haven't already.

>[!NOTE]
>
>While each of the upgrade paths described in the following sections can be used independently, Adobe recommends a two-pronged upgrade approach when upgrading from Adobe Analytics to Customer Journey Analytics, regardless of your current Adobe Analytics implementation: **the Adobe Analytics source connector** and a **new implementation of the Experience Platform WebSDK**. 
><!-- For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md) -->

### For Adobe Analytics implementations using: AppMeasurement and Adobe Analytics extension

Following are the upgrade paths available for organizations who have implemented Adobe Analytics with AppMeasurement or the Adobe Analytics extension. Expand each section to view the advantages and disadvantages of each upgrade path.

#### Upgrade paths 

+++New implementation of the Experience Platform Web SDK

| Advantages | Disadvantages |
|----------|---------|
|<ul><li>**Provides all the advantages of hosting data in Experience Edge Network**: <p>These advantages include:</p><ul><li>Highly performant reporting and data availability because Adobe Experience Platform is built to power [real-time personalization use cases](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)</li><li>Consolidate implementation for Adobe Experience Cloud data collection between other Experience Cloud products (AJO, RTCDP, and so forth)</li><li>Not reliant on Adobe Analytics nomenclature (prop, eVar, event, and so forth)</li></ul></li><li>**Future-proof**: Future implementation updates are easier.</li></ul> | <ul><li>**Requires a new implementation from scratch**: The requirement to do a new implementation from scratch means the following disadvantages: </li><ul><li>**Time consuming**: This is the most time-consuming and demanding upgrade path because it requires that you start over with a new implementation.</li><li>**Must re-create the full schema in XDM**: Before you can start implementing the Web SDK, you have to re-create the full schema in XDM.</li><li>**Must re-create rules and data elements**: Before you can start implementing the Web SDK, you have to re-create any rule conditions and data elements from your Adobe Analytics implementation.</li></ul><li>**Does not account for retaining historical data:** Adobe recommends using the Analytics source connector in conjunction with a new implementation of the Experience Platform Web SDK in order to retain historical data after upgrading to Customer Journey Analytics. <!-- For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md) --></li><li>**Does not account for comparing data from your original implementation with that of your new implementation:** Adobe recommends using the Analytics source connector in conjunction with a new implementation of the Experience Platform Web SDK in order to compare data after upgrading to Customer Journey Analytics. <!-- For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md) --></li></ul> |

{style="table-layout:auto"}

+++

+++Migrate Adobe Analytics to the Experience Platform Web SDK

| Advantages | Disadvantages |
|----------|---------|
|<ul><li>**Provides all the advantages of hosting data in Experience Edge Network**: <p>These advantages include:</p><ul><li>Highly performant reporting and data availability because Adobe Experience Platform is built to power [real-time personalization use cases](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)</li><li>Consolidate implementation for Adobe Experience Cloud data collection between other Experience Cloud products (AJO, RTCDP, and so forth)</li><li>Not reliant on Adobe Analytics nomenclature (prop, eVar, event, and so forth)</li></ul><li>**Uses your existing implementation**: While this approach requires some implementation changes, it does not require a completely new implementation from scratch. You can use your existing data layer and code with minimal changes to implementation logic without impacting your existing Adobe Analytics reporting.</li><li>**Provides flexibility to create an XDM schema for your organization at a later time**: You can migrate your existing Adobe Analytics implementation to use the Web SDK and validate that everything is working in Adobe Analytics, then create the XDM schema. This flexibility allows for a more methodical and thoughtful upgrade to Customer Journey Analytics.</li></ul> | <ul><li>**Requires mapping to send data to Platform**: When your organization is ready to use Customer Journey Analytics, you must send data to a data set in Adobe Experience Platform. This action requires that every field in the data object be an entry in the datastream mapping tool that assigns it to an XDM schema field. Mapping only needs to be done once for this workflow, and it doesn't involve making implementation changes. However, it is an extra step that is not required when sending data in an XDM object.</li><li>**Technical debt**: Because this approach uses a modified form of your existing implementation, it can be harder to track implementation logic and perform changes in the future when needed. </li></ul> |

{style="table-layout:auto"}

+++

+++Use the Analytics Source Connector

| Advantages | Disadvantages |
|----------|---------|
| <ul><li>Least time-consuming and demanding upgrade path. <p>Data is migrated to Customer Journey Analytics quickly with minimal investment</p></li></ul> | <ul><li>**Data is not sent to Edge Network**: <p>This results in the following disadvantages:</p><ul><li>Highest level of [latency](/help/technotes/guardrails.md#latencies) in reporting across all upgrade paths; not optimized for real-time personalization use cases.</li><li>Data cannot be shared with other Adobe Experience Platform applications; it is constrained to Customer Journey Analytics only</li><li>Reliant on Adobe Analytics nomenclature (prop, eVar, event, and so forth)</li></ul><li>**Difficult to move to the Web SDK in the future**: Eventually, you will likely want access to the advantages provided by the Experience Platform Web SDK. In order to start using the Experience Platform Web SDK, you must do a new implementation.</li><li>**Uses the Analytics Experience Event field group in your schema**: This field group adds many Adobe Analytics events that are not needed in your Customer Journey Analytics schema.  This can lead to a more cluttered, complex schema than what is otherwise needed for Customer Journey Analytics.</li></ul><p>Because of these disadvantages, Adobe recommends using the Analytics source connector in conjunction with a new implementation of the Experience Platform Web SDK. <!-- For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md) --></p> | 

{style="table-layout:auto"}

+++

### For Adobe Analytics implementations using: Web SDK

The following upgrade path is available for organizations who have implemented Adobe Analytics with the Experience Platform Web SDK. 

When choosing this upgrade path, you also need to choose your schema.

#### Upgrade path

+++Configure the Adobe Analytics Web SDK implementation to send data to Platform

| Advantages | Disadvantages |
|----------|---------|
| This is the preferred upgrade path if your Adobe Analytics implementation is already using the Web SDK.<ul><li>**Provides all the advantages of hosting data in Experience Edge Network**: <p>These advantages include:</p><ul><li>Highly performant reporting and data availability because Adobe Experience Platform is built to power [real-time personalization use cases](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)</li><li>Consolidate implementation for Adobe Experience Cloud data collection between other Experience Cloud products (AJO, RTCDP, and so forth)</li><li>Not reliant on Adobe Analytics nomenclature (prop, eVar, event, and so forth)</li></ul><li>**Uses your existing implementation**: While this approach requires some implementation changes, it does not require a completely new implementation from scratch. You can use your existing data layer and code with minimal changes to implementation logic without impacting your existing Adobe Analytics reporting.</li><li>**Provides an option to use an XDM schema**: You can choose to use your existing Adobe Analytics schema or create an XDM schema and map fields in the data object to your XDM schema. [XDM schemas](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) are a flexible schema to define any fields you need, and only those fields that are relevant. <p>See "Using your own XDM schema" below for more information about the advantages of using your own XDM schema.</p></li><li>**Retains rules and data elements**: While it does require new rule actions, you can reuse your existing data elements and rule conditions with minimal changes.</li><li>**Future-proof**: If you choose to use your own XDM schema, then future implementation updates are easier.</li></ul> | If you choose this, do you have to keep both AA and CJA in perpetuity? Or can you disable AA?  |

{style="table-layout:auto"}

+++

#### Choose your schema

If you chose the upgrade path that allows you to configure the Adobe Analytics Web SDK implementation to send data to Platform, you can choose the schema that you want to use.

You can choose whether to use your existing Adobe Analytics schema, or you can update to your own XDM schema to better align with the needs of your organization as you begin to use other Platform services.

+++Use the Adobe Analytics schema with the Adobe Analytics Web SDK implementation

| Advantages | Disadvantages |
|----------|---------|
|<p>Advantages of using the Adobe Analytics schema include:</p><ul><li>Ease of upgrade<p>If you are already sending data to Adobe Analytics with the Adobe Experience Platform Web SDK, you can add an additional service to your datastream to send data to Adobe Experience Platform (which then can be used in your Customer Journey Analytics configuration).</p></li></ul> | <p>Disadvantages of using the Adobe Analytics schema include:</p><ul><li>While using the Adobe Analytics schema doesn't limit you in terms of how it can be used with other Platform applications, it does result in a schema that is more complex than it otherwise could be. This is because the Adobe Analytics schema contains many objects that are specific to Adobe Analytics that are unlikely to be used by your organization.<p>When changes to the schema are required, you have to sift through thousands of unused fields to find the field that requires updating.</p></li></ul> |

+++

+++Use your own XDM schema with the Adobe Analytics Web SDK implementation

| Advantages | Disadvantages |
|----------|---------|
|<ul><p>Advantages of updating to your own XDM schema include:</p><ul><li>A streamlined schema that is tailored to the needs of your organization and the specific Platform applications that you use.</li><p>When changes to the schema are required, you don't have to sift through thousands of unused fields to find the field that requires updating.</p></ul> | <p>Disadvantages of updating to your own XDM schema include:</p><ul><li>Updating your schema is a time-consuming process that is required before you begin sending data to Platform.</li></ul> |

+++

