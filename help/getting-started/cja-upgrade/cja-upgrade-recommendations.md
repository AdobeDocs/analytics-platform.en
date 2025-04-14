---
title: Upgrade from Adobe Analytics to Customer Journey Analytics
description: Learn about the recommended steps when upgrading from Adobe Analytics to Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: d35f8615-66f5-4823-b0b8-433852246dd2
---
# Upgrade from Adobe Analytics to Customer Journey Analytics

When upgrading from Adobe Analytics to Customer Journey Analytics, you can follow the [recommended upgrade steps](#recommended-upgrade-steps-for-most-organizations). Or you can [dynamically generate upgrade steps](#dynamically-generate-upgrade-steps-for-your-organization) for your organization's unique circumstances.

## Recommended upgrade steps for most organizations {#upgrade-process}

The recommended process of upgrading from Adobe Analytics to Customer Journey Analytics is a new implementation of the Experience Platform Web SDK, which is the preferred data collection method for Customer Journey Analytics. In conjunction with the Web SDK, Adobe also recommends using the Analytics source connector to help with your transition to Customer Journey Analytics. Use the Analytics source connector to retain historical Adobe Analytics data and to perform side-by-side data comparison. 

After you have enough historical data using the Experience Platform Web SDK and you have fully transitioned to Customer Journey Analytics, the Analytics source connector can be turned off and the Web SDK can be used exclusively. 

>[!NOTE]
>
>If the upgrade steps described in this section are not practical for your organization, use the Customer Journey Analytics Upgrade Guide to dynamically generate upgrade steps that are tailored to your organization's unique circumstances. (To access the guide from Customer Journey Analytics, select the **[!UICONTROL Workspace]** tab, then select **[!UICONTROL Upgrade to Customer Journey Analytics]** in the left panel. Follow the on-screen instructions.)

### High-level recommended upgrade process {#high-level-upgade-process}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-historical-data"
>title="Historical data from Adobe Analytics"
>abstract="Bring your historical Adobe Analytics report suite data into Adobe Experience Platform and Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

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
   
    The Analytics source connector as a stand-alone implementation is not a recommended long-term method for using Customer Journey Analytics. This is because of high latency, cluttered and complex schemas, reliance on Adobe Analytics nomenclature (prop, eVar, and so forth), and difficulty in eventually moving from the Analytics source connector to the recommended Web SDK implementation. 

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

   For Adobe Analytics implementations using the Web SDK, a datastream already exists. For more information, see [Configure your existing Adobe Analytics Web SDK implementation to send data to Platform](/help/getting-started/cja-upgrade/cja-upgrade-existing-adobe-analytics-websdk.md).

1. [Add Adobe Experience Platform as a service to your datastream](/help/getting-started/cja-upgrade/cja-upgrade-datastream-addplatform.md). 

1. (Optional) If you want to integrate Customer Journey Analytics with Adobe Journey Optimizer, use the personalization object in your implementation for use in Adobe Journey Optimizer.

1. Expand the section that describes how you want to implement the Experience Platform Web SDK for your Customer Journey Analytics implementation, then complete the associated steps:

   +++Manual implementation (JS file)

   1. [Add alloy.js to your site](https://experienceleague.adobe.com/en/docs/experience-platform/edge/fundamentals/installing-the-sdk#option-2-installing-the-prebuilt-standalone-version%22).

   1. Populate an XDM object and send it to the datastream.

   +++

   +++Tags

   1. [Create a tag property and add the Adobe Experience Platform Web SDK extension](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md).

   1. [Add the Adobe Experience Platform Web SDK extension to your tag property](/help/getting-started/cja-upgrade/cja-upgrade-tag-extension.md)

   1. [Implement the loader tag on your site](/help/getting-started/cja-upgrade/cja-upgrade-tag-loader.md).   

   1. [Add XDM data collection logic to your tag](/help/getting-started/cja-upgrade/cja-upgrade-tag-xdm.md).

   +++

   +++ API

   1. Use the Edge Network API to send data to the desired datastream.

   +++

1. [Validate that your Web SDK implementation is sending data to a dataset](/help/getting-started/cja-upgrade/cja-upgrade-dataset-ingestion.md).

1. [Create a connection in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-connection.md).

1. (Optional) Tie web data with data from other channels, such as call center data.

   You accomplish this by adding additional datasets to your Customer Journey Analytics connection, as described in [Import call center and web data](/help/use-cases/cross-channel/call-center.md).

1. [Create a data view in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md).

1. [Validate that data is flowing into the data view in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-validate.md).

1. In your Adobe Analytics environment, [use the Analytics Inventory](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/analytics-inventory) to see a comprehensive overview of your Adobe Analytics environment, including the number of projects and components, report suites, users, and more. 

1. [Migrate projects and components](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration). 

   <!-- You might not want to do this, based on the schema? Ask Zach. Will it work if you have all new schema fields? What would you want to just build from scratch. Maybe everything? -->

1. (Optional) If you use marketing channels in Adobe Analytics, you can [create a marketing channel derived field in Customer Journey Analytics](/help/data-views/derived-fields/derived-fields.md#marketing-channels). 

   Derived fields are an important aspect of the real-time reporting in Customer Journey Analytics. A derived field allows you to define (often complex) data manipulations on the fly, through a customizable rule builder. 
   
   One use for derived fields is to define a derived Marketing Channel field that determines the proper marketing channel based on one or more conditions (for example, URL parameter, page URL, or page name).
   
   Use [the marketing channels function template](/help/data-views/derived-fields/derived-fields.md#marketing-channels) in derived fields to quickly create a derived field for marketing channels.

1. Compare data in Adobe Analytics from your old implementation to data in Customer Journey Analytics from your new implementation and make sure you understand any differences and why they exist. <!-- Expound on this. Link to somewhere? There will be a lot of differences. -->

1. Bring historical data from Adobe Analytics using the Analytics source connector: 

   >[!NOTE]
   >
   >Use the following steps if you have not previously created an Analytics source connector. 
   >
   >If you are already using the Analytics source connector with Customer Journey Analytics, follow the steps in [Transition from the Analytics source connector to the Web SDK for Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md).

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

1. Disable Adobe Analytics when your Customer Journey Analytics Web SDK implementation is complete and you are comfortable with the data that you are collecting. 

   Adobe recommends that you keep your Adobe Analytics environment running for a period of time after implementing Customer Journey Analytics. 
   
   For more information about the uses of Adobe Analytics during and after an upgrade, as well as the suggested timing of disabling Adobe Analytics, see [Evaluate how long you need Adobe Analytics after upgrading to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-fully-move.md).

## Dynamically generate upgrade steps for your organization

Depending on several factors, such as timeline and resource constraints, the recommended upgrade steps described in [Understand the recommended upgrade steps](#recommended-upgrade-steps-for-most-organizations) might not be practical for your organization. In this case, you can dynamically generate upgrade steps for your organization's unique circumstances. The process of generating these steps differs depending on whether you already have access to Customer Journey Analytics.

### For customers who have access to Customer Journey Analytics

To dynamically generate upgrade steps for your organization's unique circumstances:

1. Complete the Customer Journey Analytics Upgrade Guide.

   In Customer Journey Analytics, select the **[!UICONTROL Workspace]** tab, then select **[!UICONTROL Upgrade to Customer Journey Analytics]** in the left panel. Follow the on-screen instructions.

   After completing this upgrade guide, step-by-step instructions are provided to you, outlining the optimal upgrade steps that are unique to your organization requirements. These are the upgrade steps that best align with your existing Adobe Analytics environment and your goals for Customer Journey Analytics. The upgrade steps are available as a shareable link or as a downloadable .csv file.
   
1. Follow the generated step-by-step instructions to upgrade to Customer Journey Analytics. 

### For customers who do not yet have access to Customer Journey Analytics

To dynamically generate upgrade steps for your organization's unique circumstances:

1. Contact your Adobe Account Team to complete the Customer Journey Analytics Upgrade Guide.

   Your Adobe Account Team can take you through the upgrade guide and provide you with a .csv file that contains the questions, your answers, and the dynamically generated upgrade steps that are unique to your organization.  
   
   Prior to contacting your Adobe Account Team, familiarize yourself with the questions that are included in the Customer Journey Analytics Upgrade Guide and determine your answers. The Customer Journey Analytics Upgrade Guide contains the following questions and possible answers:

   
   | Question | Available answers | Additional information |
   |---------|----------|---------|
   | Select the option that describes your current Adobe Analytics implementation. This information can affect alternative upgrade options that might be available to you when upgrading to Customer Journey Analytics. | Select one: <ul><li>**AppMeasurement:**<br/>A JavaScript implementation that loads AppMeasurement.js on a page, and sends data to Adobe using the s object (for example, s.eVar1).</li><li>**Adobe Analytics extension (tags):** <br/>A tags implementation that loads Adobe Experience Platform Data Collection (formerly known as Launch). The tag has the Adobe Analytics extension installed.</li><li>**Experience Platform Web SDK extension (tags):**<br/>A tags implementation that loads Adobe Experience Platform Data Collection (formerly known as Launch). The tag has the Web SDK extension installed.</li><li>**Experience Platform Web SDK (alloy.js):** A JavaScript implementation that loads the Web SDK library (alloy.js) on a page, and sends data to Adobe using a JSON payload.</li><li>**Bulk Data Insertion API:**<br/> An implementation that uses the data insertion API or bulk data insertion API.</li><li>**Experience Platform Mobile SDK:**<br/> An implementation that uses the Adobe Experience Platform Mobile SDK.</li><li>**AppMeasurement using a third-party tag management tool:**<br/> An implementation that uses a third-party tag management tool.</li><li>**A non-Adobe Analytics product:**<br/> An implementation that collects data for a product other than Adobe Analytics, such as Google Analytics. Selecting this option disables several options in the upgrade guide that don't apply when upgrading to Customer Journey Analytics from a non-Adobe Analytics product. </li><li>**I don't know:**<br/> If you're not the person that manages your implementation, you can temporarily select this option.</li></ul><p>Select if applicable:<ul><li>**Our implementation currently uses the Analytics source connecto:**<br/>The Analytics source connector allows you to easily get value from Customer Journey Analytics, but requires that you pay for both Adobe Analytics and Customer Journey Analytics. This guide can help you move towards an independent Web SDK implementation.</li></ul></p> | <ul><li>[Understand your Adobe Analytics implementation and how it affects your upgrade to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-analytics-implementation.md#understand-your-adobe-analytics-implementation-and-how-it-affects-your-upgrade-to-customer-journey-analytics)</li><li>[Transition from the Analytics source connector to the Web SDK for Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md)</li></ul> |
   | Most Adobe Analytics features are readily available in Customer Journey Analytics. However, the following features require consideration during the upgrade process. Select any that you plan to use. | Select all that apply:<ul><li>**Historical data from Adobe Analytics:**</br>Bring your historical Adobe Analytics report suite data into Adobe Experience Platform and Customer Journey Analytics.</li><li>**Components and projects from Adobe Analytics:**</br>Components from Adobe Analytics include: Projects (with their associated freeform tables and visualizations), segments, and calculated metrics.</li><li>**Acivity map overlay and link tracking:**</br>A browser extension that allows you to see link tracking data as an overlay on your site.</li><li>**Classification data:**</br>Group or categorize data as separate dimensions.</li><li>**Marketing channels:**</br>Create rules that categorize how customers arrive on your site.</li><li>**Data Warehouse:**</br>Export processed data from Adobe Analytics in spreadsheet format.</li><li>**Data Feeds:**An exact replacement for Data Feeds is not yet available in Customer Journey Analytics. However, similar functionality can be achieved with capabilities such as full table export, Platform dataset export, BI tool integration, and the reporting API.</br></li><li>**Streaming media data:**</br>An add-on to Adobe Analytics and Customer Journey Analytics that specializes in data collection of media, such as audio, video, or streamed content.</li></ul> | <ul><li>[Understand Adobe Analytics feature support when upgrading to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-adobe-analytics-features.md)</li></ul> |
   | Most new features are readily available in Customer Journey Analytics. However, the following features require consideration during the upgrade process. Select any that you plan to use. | Select all that apply:<ul><li>**Tie collected data with data from other sources (e.x. contact center data):**</br>(Recommended) Tie data from various web, mobile, and offline properties to create a single, consolidated view of customer behavior. This ability to combine analytics data from other channels is the primary use case for Customer Journey Analytics.</li><li>**Stitch hits from other datasets using a custom dimension:**<br/>If any of your datasets don't share a primary identifier (such as an Experience Cloud ID), you can still stitch that data together using another dimension, such as login username or email address.</li><li>**Integrate with Adobe Journey Optimizer:**<br/>Deliver connected, contextual, and personalized experiences to customers.</li><li>**Integrate with Adobe Real-Time CDP:**<br/>Combine profile data from multiple sources to generate audiences and segments based on user traits.</li><li>**Integrate with Adobe Target (A4T):**<br/>Adobe recommends integrating with Adobe Journey Optimizer for personalization use cases. Integrating with Adobe Target is possible, but a short-term solution.</li><li>**Integrate with Adobe Audience Manager:**<br/>Adobe recommends integrating with Adobe Real-time CDP for audience-based use cases. Integrating with Audience Manager is possible, but a short-term solution.</li></ul> | [Understand features unique to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-customer-journey-analytics-features.md) |
   | Select how you plan to ultimately use Adobe Analytics and Customer Journey Analytics: | Select one: <ul><li>**I intend to fully move to Customer Journey Analytics from Adobe Analytics:**<br/>(Recommended) Adobe recommends that you transition fully from Adobe Analytics to Customer Journey Analytics. During the transition period, you should plan to run Adobe Analytics alongside Customer Journey Analytics in order to perform side-by-side data comparisons. When you are comfortable with the data, you can disable Adobe Analytics.</li><li>**I intend to keep both Analytics products:**<br/>(Not recommended) If you select this option, your contract with Adobe includes both Adobe Analytics and Customer Journey Analytics, which can be more expensive for your organization over time.</li></ul> | [Evaluate when to disable Adobe Analytics after upgrading to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-fully-move.md) |
   | Select how you want to configure your Customer Journey Analytics schema: | Select one: <ul><li>**I want to use a schema tailored to my organization:**</br>(Recommended) Customizing your schema allows your organization to track only what you need and avoid the overhead tied to messy and unneeded fields. This option includes field groups added by the Web SDK and field groups custom to your organization.</li><li>**I want to use the default Adobe Analytics schema:**</br>(Not recommended) The Adobe Analytics schema contains more than a thousand fields, which can lead to cluttered and complex schema. Your organization would be forced to continue adhering to the concept of props and eVars, which is a legacy concept not used in Customer Journey Analytics. Integrating with other Adobe Experience Platform services is more difficult.</li></ul> | [Choose your schema for Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md) |
   | Select your preferred way of implementing Customer Journey Analytics: | <ul><li>**Manual implementation (alloy.js):**<br/>Include the Web SDK library (alloy.js) on each page your site.</li><li>**Tags:**<br/>(Recommended) If you are not yet using Tags, install the tag loader on your site. If you are already using Tags, you can add the Web SDK extension to your tag property. This option includes implementations using tags within Adobe Experience Platform Data Collection and third-party tag management systems.</li><li>**API:**<br/>Use the data collection API to send data directly to a datastream. Both non-authenticated (client-to-server) and authenticated (server-to-server) types are supported.</li></ul> | [Understand Web SDK implementation options when upgrading to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-websdk-implementation.md) |
   | (Optional) Select an alternative upgrade method | <ul><li>**Soley use the Analytics source connector:**<br/>(Not recommended) You can use the Analytics source connector as the sole implementation path for Customer Journey Analytics.<p>This option saves implementation time by quickly sending data to Customer Journey Analytics. However, it includes various shortcomings, such as higher latency and difficulty moving off of Adobe Analytics in the future.</p></li><li>**I want to use my AppMeasurement logic with the Web SDK:**<br/>Instead of sending data through an XDM object, send all your variables in AppMeasurement format through the data object.<p>This option saves implementation time by allowing you to map your AppMeasurement logic to XDM, rather than populating an XDM object from scratch. However, it introduces additional complexity over time because any field you add in the future must be mapped to XDM in the datastream.</p></li><li>**I want to send my data layer to Adobe without additional configuration:**<br/>Instead of sending data through an XDM object, you can send your entire data layer to Adobe through the data object.<p>This option saves implementation time by allowing you to map your data layer to XDM, rather than populating an XDM object from scratch. However, this mapping is a large amount of work because there will be a significant amount of data that Adobe can't readily interpret. This option also introduces additional complexity over time because any field you add to your data later in the future must be mapped to XDM in the datastream.</p></li></ul> | <ul><li>[Upgrade alternative: Use the Analytics source connector exclusively to upgrade to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-source-connector.md)</li><li>[Upgrade alternative: Use AppMeasurement data collection with the Experience Platform Web SDK and Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md)</li><li>[Upgrade alternative: Send your data layer to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-data-layer.md)</li></ul> |

   After completing this upgrade guide with your Adobe Account Team, you will be provided with a .csv file that contains the questions, your answers, and the dynamically generated upgrade steps that best align with your existing Adobe Analytics environment and your goals for Customer Journey Analytics.
   
1. Follow the generated step-by-step instructions in the .csv file to upgrade to Customer Journey Analytics. 

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
