---
title: Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics
description: Learn about the recommended path when upgrading from Adobe Analytics to Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: yes
hidefromtoc: yes
---
# Upgrade from Adobe Analytics to Customer Journey Analytics

Before you begin the upgrade process from Adobe Analytics to Customer Journey Analytics, first understand the recommended upgrade steps.

>[!NOTE]
>
>The upgrade steps described in this section are the recommended upgrade steps that any organization could use to successfully upgrade from Adobe Analytics to Customer Journey Analytics.
>
>However, depending on several factors, such as timeline and resource constraints, the recommended upgrade steps might not be practical for your organization. In that case, use the [Adobe Analytics to Customer Journey Analytics upgrade questionnaire](https://gigazelle.github.io/cja-ttv/) to dynamically generate upgrade steps that are tailored to your organization's unique circumstances. 

## Recommended upgrade steps for most organizations

The recommended steps when upgrading from Adobe Analytics to Customer Journey Analytics is a new implementation of the Experience Platform Web SDK, which is the preferred data collection method for Customer Journey Analytics. In conjunction with the Web SDK, Adobe also recommends using the Analytics source connector in order to retain historical Adobe Analytics data and to perform side-by-side data comparison. 

After fully transitioning to Customer Journey Analytics, the Analytics source connector can be turned off and the Experience Platform Web SDK can be used exclusively. 

### High-level recommended upgrade process

1. **Implement the Experience Platform Web SDK**

   A new implementation of the Experience Platform Web SDK is the best way to collect data for Customer Journey Analytics. It provides the best foundation to get the most out of Customer Journey Analytics because it is the most performant, straightforward, and future-proof method for implementing Customer Journey Analytics. 

   * Highly performant reporting and data availability because Adobe Experience Platform is built to power real-time personalization use cases

   * Consolidate implementation for Adobe Experience Cloud data collection between other Experience Cloud products (AJO, RTCDP, and so forth)

   * Not reliant on Adobe Analytics nomenclature (prop, eVar, event, and so forth)

1. **Set up the Adobe Analytics source connector**

   To help with a smooth transition to using the Experience Platform Web SDK with Customer Journey Analytics, Adobe also recommends using the Adobe Analytics source connector. This allows you to retain historical data and view data from your existing Adobe Analytics implementation in Customer Journey Analytics, side by side with the data from your new Experience Platform Web SDK implementation. 

   The Analytics source connector allows you to:

   * Bring your historical Adobe Analytics report suite data into Adobe Experience Platform and Customer Journey Analytics. 
   
     You can keep the Analytics source connector running for as long as you need to retain the historical Adobe Analytics data. 
   
   * View the data collected with your original Adobe Analytics implementation (either AppMeasurement, the Analytics Extension, or the Web SDK Extension) within Customer Journey Analytics. You can compare this data side-by-side with that of your new Web SDK implementation. 
   
     You can keep the Analytics source connector running until you are familiar and comfortable with the differences. <!--elaborate on what those differences are? -->
   
    The Analytics source connector as a stand-alone implementation is not a recommended long-term method for using Customer Journey Analytics. This is because of high latency, cluttered and complex schemas, reliance on Adobe Analytics nomenclature (prop, eVar, and so forth), and difficulty in eventually moving from the source connector to the recommended Web SDK implementation. 

### Detailed recommended upgrade steps

The following steps show the recommended process for upgrading from Adobe Analytics to Customer Journey Analytics. 

Depending on your organization's unique environment and requirements, these recommended steps might not be suitable for your organization. In that case, use the [Adobe Analytics to Customer Journey Analytics upgrade questionnaire](https://gigazelle.github.io/cja-ttv/) to dynamically generate upgrade steps that are tailored to your organization's unique circumstances. 

1. [Plan your XDM schema architecture](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md).

1. [Create your desired custom schema in Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

1. [Create a dataset in Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-dataset.md).

1. Expand the section that describes your current Adobe Analytics implementation, then complete the associated steps:

   +++For Adobe Analytics implementations using AppMeasurement

   1. [Create a datastream in Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md). <!-- Is this correct? Will customers on the Web SDK already have a datastream that they only need to add AEP as a service to? Or does this step apply to everyone?-->

   +++

   +++For Adobe Analytics implementations using the Analytics extension (tags)

   1. [Create a datastream in Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md). <!-- Is this correct? Will customers on the Web SDK already have a datastream that they only need to add AEP as a service to? Or does this step apply to everyone?-->

   +++

   +++ For Adobe Analytics implementations using the Web SDK

   No additional steps are required.

   +++

1. [Add Adobe Experience Platform as a service to your datastream](/help/getting-started/cja-upgrade/cja-upgrade-datastream-addplatform.md). 

1. Use the following table to identify any Adobe Analytics features that you want to continue using in Customer Journey Analytics, then use the provided information to learn how to configure those features as part of the upgrade to Customer Journey Analytics:
   
   | Adobe Analytics feature | Implementation requirements for Customer Journey Analytics  | Additional information |
   |---------|----------|---------|
   | Classification data | Create a lookup dataset for each dimension containing classification data. |  |
   | Marketing channels | Create a marketing channel derived field. |  |
   | Activity map overlay and link tracking | N/A | Adobe is currently working on Activity Map overlay support for Customer Journey Analytics. |
   | Data Feeds | No configuration required during implementation.<br/>[Learn about the various export options in Customer Journey Analytics](/help/analysis-workspace/export/export-project-overview.md). | While a direct replacement for Data Feeds is not yet available in Customer Journey Analytics, you can export Customer Journey Analytics reports from Analysis Workspace for use in third-party tools or to combine with outside data. |
   | Data Warehouse | No configuration required during implementation.<br/>[Learn about Full Table Export in Customer Journey Analytics](/help/analysis-workspace/export/export-cloud.md). | Customer Journey Analytics Full Table Export is the evolution of Data Warehouse reports in Adobe Analytics, with many new, often-requested features that are not available in Data Warehouse today. |
   | Streaming Media data |  |  |

1. (Optional) Bring historical data from Adobe Analytics using the Analytics source connector.  
   
   For more information, see [Use a source connector](/help/data-ingestion/sources.md#use-a-source-connector) in [Ingest and use data using source connectors](/help/data-ingestion/sources.md).

1. Use the following table to identify any Customer Journey Analytics features that you want, then use the provided information to learn how to configure those features as part of the upgrade to Customer Journey Analytics:
   
   | Customer Journey Analytics features you want | Implementation requirements for Customer Journey Analytics | Additional information |
   |---------|----------|---------|
   | Tie web data with data from other channels, such as call center data | After you create a connection (as described in a later step), add additional datasets to your connection in Customer Journey Analytics. |  |
   | Integrate with RTCDP | Enable profile in your schema and create a profile dataset for use in RTCDP | This must be done while creating your XDM schema. |
   | Integrate with Adobe Journey Optimizer | Use the personalization object in your implementation for use in Adobe Journey Optimizer |  |

1. Expand the section that describes your desired Customer Journey Analytics implementation, then complete the associated steps:

   +++Manual implementation (JS file)

   1. [Add alloy.js to your site](https://experienceleague.adobe.com/en/docs/experience-platform/edge/fundamentals/installing-the-sdk#option-2-installing-the-prebuilt-standalone-version%22).

   +++

   +++Tags

   1. [Create a tag property in Adobe Experience Platform data collection](https://experienceleague.adobe.com/en/docs/experience-platform/tags/get-started/quick-start#create-a-property).

   +++

   +++ API

   1. Use the Edge Network API to send data to the desired datastream.

   +++

1. [Create a connection in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-connection.md).

1. [Create a data view in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md).

1. [Validate that data is flowing into Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-validate.md).

1. [Migrate projects and components](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration). 

1. Compare data from your old implementation to that from your new implementation and make sure you understand any differences and why they exist. 

1. Plan user onboarding. 

   Like in Adobe Analytics, Analysis Workspace is the main user-facing tool in Customer Journey Analytics. However, there are some key differences when using Analysis Workspace in Customer Journey Analytics that users need to be aware of.

   You should give your users ample time (3 - 6 months) to become familiar with the key differences of Analysis Workspace in Customer Journey Analytics.

   For information about some of the key differences between Adobe Analytics and Customer Journey Analytics, see [User Guide for Adobe Analytics users](/help/getting-started/aa-to-cja-user.md).

1. Disable AppMeasurement data collection.

1. Disable the Analytics source connector.  

   With the Experience Platform Web SDK implementation, the Analytics source connector is needed only for historical Adobe Analytics data and to compare data from your original implementation with that of your new implementation.
   
   When you have enough historical data from your new implementation and you are familiar with the reporting differences in Customer Journey Analytics, you should turn off the Analytics source connector.   

## Dynamically generate upgrade steps for your organization

Depending on several factors, such as timeline and resource constraints, the recommended upgrade steps described in [Understand the recommended upgrade steps](#1-understand-the-recommended-upgrade-steps) might not be practical for your organization. 

To dynamically generate upgrade steps for your organization's unique circumstances:

1. Complete the [Adobe Analytics to Customer Journey Analytics upgrade questionnaire](https://gigazelle.github.io/cja-ttv/). 

   After completing this questionnaire, step-by-step instructions are provided to you, outlining the optimal upgrade steps that are unique to your organization requirements. These are the upgrade steps that best align with your existing Adobe Analytics environment and your goals for Customer Journey Analytics.
   
1. Follow the generated step-by-step instructions to upgrade to Customer Journey Analytics. 

<!--

Customer Journey Analytics is the next generation of analytics. It allows multi-channel data collection (both online and offline data), combined with powerful report-time processing functionality (through the definition of components and derived fields in data views). 



When upgrading from Adobe Analytics to Customer Journey Analytics, no single set of upgrade steps exist that are optimal for every organization.

Adobe recommends using the dynamically generated upgrade steps that are unique to your organization. These upgrade steps are generated after you complete an upgrade questionnaire, which helps you understand the best way for your organization to upgrade to Customer Journey Analytics. 

Generic upgrade steps are also available.

1. **Implement the Experience Platform Web SDK**

   A new implementation of the Experience Platform Web SDK provides the best foundation to get the most out of Customer Journey Analytics. 
   
   It is the most performant, straightforward, and future-proof method for implementing Customer Journey Analytics:

   * Highly performant reporting and data availability because Adobe Experience Platform is built to power real-time personalization use cases

   * Consolidate implementation for Adobe Experience Cloud data collection between other Experience Cloud products (AJO, RTCDP, and so forth)

   * Not reliant on Adobe Analytics nomenclature (prop, eVar, event, and so forth)

1. **Set up the Adobe Analytics source connector**

   The Analytics source connector is a recommended part of the piece when upgrading to Customer Journey Analytics. 

   The Analytics source connector allows you to:

   * Bring your historical Adobe Analytics report suite data into Adobe Experience Platform and Customer Journey Analytics. 
   
     You can keep the Analytics source connector running for as long as you need to retain the historical Adobe Analytics data. 
   
   * View the data collected with your original Adobe Analytics implementation (either AppMeasurement, the Analytics Extension, or the Web SDK Extension) within Customer Journey Analytics. You can compare this data side-by-side with that of your new Web SDK implementation. 
   
     You can keep the Analytics source connector running until you are familiar and comfortable with the differences. <!--elaborate on what those differences are? -->

<!--

   When you no longer need the Analytics source connector because you have enough historical data from your new implementation and you are familiar with the reporting differences in Customer Journey Analytics, you should turn off the Analytics source connector. With the Experience Platform Web SDK implementation, the Analytics source connector is not needed.  
   
   The Analytics source connector as a stand-alone implementation is not a recommended long-term method for using Customer Journey Analytics. This is because of high latency, cluttered and complex schemas, reliance on Adobe Analytics nomenclature (prop, eVar, and so forth), and difficulty in eventually moving from the source connector to the recommended Web SDK implementation. 
   
-->









