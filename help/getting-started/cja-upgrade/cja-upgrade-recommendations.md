---
title: Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics
description: Learn about the recommended path when upgrading from Adobe Analytics to Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: yes
hidefromtoc: yes
exl-id: d35f8615-66f5-4823-b0b8-433852246dd2
---
# Upgrade from Adobe Analytics to Customer Journey Analytics

When upgrading from Adobe Analytics to Customer Journey Analytics, Adobe recommends a new implementation of the Experience Platform Web SDK, in conjunction with the Analytics source connector, as described in [Recommended upgrade steps for most organizations](#recommended-upgrade-steps-for-most-organizations).

Depending on several factors, such as timeline and resource constraints, the recommended upgrade steps might not be practical for your organization. In that case, use the [Adobe Analytics to Customer Journey Analytics upgrade questionnaire](https://gigazelle.github.io/cja-ttv/) to dynamically generate upgrade steps that are tailored to your organization's unique circumstances.

## Recommended upgrade steps for most organizations

>[!NOTE]
>
>The upgrade steps described in this section are the recommended upgrade steps that any organization could use to successfully upgrade from Adobe Analytics to Customer Journey Analytics.
>
>However, depending on several factors, such as timeline and resource constraints, the recommended upgrade steps might not be practical for your organization. In that case, use the [Adobe Analytics to Customer Journey Analytics upgrade questionnaire](https://gigazelle.github.io/cja-ttv/) to dynamically generate upgrade steps that are tailored to your organization's unique circumstances. 

The recommended process of upgrading from Adobe Analytics to Customer Journey Analytics is a new implementation of the Experience Platform Web SDK, which is the preferred data collection method for Customer Journey Analytics. In conjunction with the Web SDK, Adobe also recommends using the Analytics source connector to help with your transition to Customer Journey Analytics. Use the Analytics source connector to retain historical Adobe Analytics data and to perform side-by-side data comparison. 

After you have enough historical data using the Experience Platform Web SDK and you have fully transitioned to Customer Journey Analytics, the Analytics source connector can be turned off and the Web SDK can be used exclusively. 

### High-level recommended upgrade process

1. **Implement the Experience Platform Web SDK (for ongoing data collection)**

   A new implementation of the Experience Platform Web SDK is the best way to collect data for Customer Journey Analytics. It provides the best foundation to get the most out of Customer Journey Analytics because it is the most performant, straightforward, and future-proof method for implementing Customer Journey Analytics. 

   * Highly performant reporting and data availability because Adobe Experience Platform is built to power real-time personalization use cases

   * Consolidate implementation for Adobe Experience Cloud data collection between other Experience Cloud products (AJO, RTCDP, and so forth)

   * Not reliant on Adobe Analytics nomenclature (prop, eVar, event, and so forth)

1. **Set up the Adobe Analytics source connector (for bringing over historical data)**

   To help with a smooth transition to using the Experience Platform Web SDK with Customer Journey Analytics, Adobe also recommends using the Adobe Analytics source connector. This allows you to retain historical data and view data from your existing Adobe Analytics implementation in Customer Journey Analytics, side by side with the data from your new Experience Platform Web SDK implementation. 

   The Analytics source connector allows you to:

   * Bring your historical Adobe Analytics report suite data into Adobe Experience Platform and Customer Journey Analytics. 
   
     You can keep the Analytics source connector running for as long as you need to retain the historical Adobe Analytics data. 
   
   * View the data collected with your original Adobe Analytics implementation (either AppMeasurement, the Analytics Extension, or the Web SDK Extension) within Customer Journey Analytics. You can compare this data side-by-side with that of your new Web SDK implementation. 
   
     You can keep the Analytics source connector running until you are familiar and comfortable with the differences. <!--elaborate on what those differences are? -->
   
    The Analytics source connector as a stand-alone implementation is not a recommended long-term method for using Customer Journey Analytics. This is because of high latency, cluttered and complex schemas, reliance on Adobe Analytics nomenclature (prop, eVar, and so forth), and difficulty in eventually moving from the source connector to the recommended Web SDK implementation. 

### Detailed recommended upgrade steps

The following steps outline the recommended process for upgrading from Adobe Analytics to Customer Journey Analytics. 

Each step provides a high-level explanation of a more detailed process. Follow the link for each step and complete its associated tasks, then return to this page and continue to the next step in the process. 

1. [Plan your XDM schema architecture](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md).

1. [Create your desired custom schema in Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

   Consider the following options when creating your schema:

   * If you want to integrate Customer Journey Analytics with RTCDP, you must enable the **[!UICONTROL Profile]** option on your schema, as described in [Create an XDM schema to use with Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md). With this option enabled, when data is ingested into datasets based on this schema, that data is merged into the Real-Time Customer Profile.

   * If you want to include streaming media data, you must [configure your schema to ingest and use streaming data](/help/data-ingestion/streaming.md).

1. [Create a dataset in Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-dataset.md).

1. (Optional) If you use classification data in Adobe Analytics, you can add classification data to your dataset in Customer Journey Analytics.

   To do this, [create a lookup dataset for each dimension containing classification data](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md). 

1. For Adobe Analytics implementations using AppMeasurement or the Analytics extension (tags), [create a datastream in Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md). <!-- Is this correct? Will customers on the Web SDK already have a datastream that they only need to add AEP as a service to? Or does this step apply to everyone?-->

   For Adobe Analytics implementations using the Web SDK, a datastream already exists.

1. [Add Adobe Experience Platform as a service to your datastream](/help/getting-started/cja-upgrade/cja-upgrade-datastream-addplatform.md). 

1. (Optional) If you want to integrate Customer Journey Analytics with Adobe Journey Optimizer, use the personalization object in your implementation for use in Adobe Journey Optimizer.

1. Expand the section that describes how you want to implement the Experience Platform Web SDK for your Customer Journey Analytics implementation, then complete the associated steps:

   +++Manual implementation (JS file)

   1. [Add alloy.js to your site](https://experienceleague.adobe.com/en/docs/experience-platform/edge/fundamentals/installing-the-sdk#option-2-installing-the-prebuilt-standalone-version%22).

   1. Populate an XDM object and send it to the datastream.

   +++

   +++Tags

   1. [Implement the loader tag on your site](/help/getting-started/cja-upgrade/cja-upgrade-tag-loader.md).

   1. [Create a tag property and add the Adobe Experience Platform Web SDK extension](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md).

   1. [Add XDM data collection logic to your tag](/help/getting-started/cja-upgrade/cja-upgrade-tag-xdm.md).

   +++

   +++ API

   1. Use the Edge Network API to send data to the desired datastream.

   +++

1. Validate that your Web SDK implementation is sending data to a dataset.

1. [Create a connection in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-connection.md).

1. (Optional) Tie web data with data from other channels, such as call center data.

   You accomplish this by adding additional datasets to your Customer Journey Analytics connection.

1. [Create a data view in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md).

1. [Validate that data is flowing into Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-validate.md).

1. [Migrate projects and components](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration). 

   <!-- You might not want to do this, based on the schema? Ask Zach. Will it work if you have all new schema fields? What would you want to just build from scratch. Maybe everything? -->

1. (Optional) If you use marketing channels in Adobe Analytics, you can [create a marketing channel derived field in Customer Journey Analytics](/help/data-views/derived-fields/derived-fields.md#marketing-channels). 

   Derived fields are an important aspect of the real-time reporting in Customer Journey Analytics. A derived field allows you to define (often complex) data manipulations on the fly, through a customizable rule builder. 
   
   One use for derived fields is to define a derived Marketing Channel field that determines the proper marketing channel based on one or more conditions (for example URL parameter, page URL, page name).
   
   Use [the marketing channels function template](/help/data-views/derived-fields/derived-fields.md#marketing-channels) in derived fields to quickly create a derived field for marketing channels.

1. Compare data in Adobe Analytics from your old implementation to data in Customer Journey Analytics from your new implementation and make sure you understand any differences and why they exist. <!-- Expound on this. Link to somewhere? There will be a lot of differences. -->

1. (Optional) Bring historical data from Adobe Analytics using the Analytics source connector: 

   >[!NOTE]
   >
   >Use the following steps if you have not previously created an Analytics source connector. 
   >
   >If you are already using the Analytics source connector with Customer Journey Analytics, follow the steps in [Move from the Analytics source connector to the Web SDK for Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md).

   1. [Create an XDM schema for the Analytics source connector](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)
   
   1. If you don't already have an Analytics source connector, [create the Analytics source connector and map fields to your XDM schema](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md).

      Or

      If you already have an Analytics source connector, [map fields from the source connector to your XDM schema](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md).

   1. [Add the Analytics source connector dataset to the connection](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md).

1. Plan user onboarding. 

   Like in Adobe Analytics, Analysis Workspace is the main user-facing tool in Customer Journey Analytics. However, there are some key differences when using Analysis Workspace in Customer Journey Analytics that users need to be aware of.

   You should give your users ample time (3 - 6 months) to become familiar with the key differences of Analysis Workspace in Customer Journey Analytics.

   For information about some of the key differences between Adobe Analytics and Customer Journey Analytics, see [User Guide for Adobe Analytics users](/help/getting-started/aa-to-cja-user.md).

1. Learn about [feature support in Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md). Most Adobe Analytics features are supported in Customer Journey Analytics, and many additional features are available in Customer Journey Analytics.

1. When your Web SDK implementation is complete and you are comfortable with the data that you are collecting, you can disable AppMeasurement data collection. 

   For more information, see [Disable AppMeasurement data collection](/help/getting-started/cja-upgrade/cja-upgrade-disable-appmeasurement.md).

1. Disable the Analytics source connector after all Analytics source connector data leaves your data retention period.  

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
