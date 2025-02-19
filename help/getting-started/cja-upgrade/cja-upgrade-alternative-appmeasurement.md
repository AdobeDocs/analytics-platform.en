---
title: Alternate methods when upgrading to Customer Journey Analytics
description: Learn about the alternate methods when upgrading to Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: yes
hidefromtoc: yes
---
# Upgrade alternative: Use AppMeasurement data collection with the Experience Platform Web SDK and Customer Journey Analytics {#data-collection-appmeasurement}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-appmeasurement-logic"
>title="Use AppMeasurement logic with the Web SDK"
>abstract="Instead of sending data through an XDM object, send all your variables in AppMeasurement format through the data object.<br><br>This alternative upgrade method is mutually exclusive to sending your data layer to Adobe, because both methods accomplish the same task."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>Use the information on this page when answering questions in the [Customer Journey Analytics upgrade checklist](https://gigazelle.github.io/cja-ttv/). 

When upgrading to Customer Journey Analytics, Adobe [recommends a new implementation of the Experience Platform Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md). However, depending on several factors, such as timeline and resource constraints, the recommended upgrade steps might not be practical for your organization. 

You can use your AppMeasurement or Analytics extension data collection logic with the Web SDK and Customer Journey Analytics instead of collecting data with the XDM object. However, this alternative introduces additional complexity over time.

Consider the following advantages and disadvantages of using this upgrade alternative:

| Advantages | Disadvantages |
|----------|---------|
|<ul><li>**Provides all the advantages of hosting data in Experience Edge Network**: <p>These advantages include:</p><ul><li>Highly performant reporting and data availability because Adobe Experience Platform is built to power [real-time personalization use cases](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)</li><li>Consolidate implementation for Adobe Experience Cloud data collection between other Experience Cloud products (AJO, RTCDP, and so forth)</li><li>Not reliant on Adobe Analytics nomenclature (prop, eVar, event, and so forth)</li></ul><li>**Uses your existing implementation**: While this approach requires some implementation changes, it does not require a completely new implementation from scratch. You can use your existing data layer and code with minimal changes to implementation logic without impacting your existing Adobe Analytics reporting.<p>In other words, this option saves implementation time by allowing you to map your AppMeasurement logic to XDM, rather than populating an XDM object from scratch.</p></li><li>**Provides flexibility to create an XDM schema for your organization at a later time**: You can migrate your existing Adobe Analytics implementation to use the Web SDK and validate that everything is working in Adobe Analytics, then create the XDM schema. This flexibility allows for a more methodical and thoughtful upgrade to Customer Journey Analytics.</li></ul> | <ul><li>**Requires mapping to send data to Platform**: When your organization is ready to use Customer Journey Analytics, you must send data to a data set in Adobe Experience Platform. This action requires that every field in the data object be an entry in the datastream mapping tool that assigns it to an XDM schema field. Mapping only needs to be done once for this workflow, and it doesn't involve making implementation changes. However, it is an extra step that is not required when sending data in an XDM object.</li><li>**Technical debt**: Because this approach uses a modified form of your existing implementation, it can be harder to track implementation logic and perform changes in the future when needed. </li></ul> |

{style="table-layout:auto"}

## Basic steps

The basic steps for migrating an AppMeasurement or Analytics extension implementation to use the Web SDK to send data to Customer Journey Analytics are:

1. Migrate your Adobe Analytics implementation (either AppMeasurement or the Analytics extension) to use the Adobe Experience Platform Web SDK and begin sending data to Edge Network.

1. (Optional) Send data from Edge Network to Adobe Analytics. <!-- how do you do this? -->

   For more information, see the section below, [(Optional) Use the Web SDK to send data to Adobe Analytics and then to Customer Journey Analytics](#optional-use-the-web-sdk-to-send-data-to-adobe-analytics-and-then-to-customer-journey-analytics)

1. Send data to from Edge Network to Customer Journey Analytics.

   1. Create an XDM schema for your organization.

   1. Use datastream mapping to map all of the fields in the data object to your XDM schema.

## (Optional) Use the Web SDK to send data to Adobe Analytics and then to Customer Journey Analytics

You can perform this type of upgrade in stages by having the Experience Platform Web SDK send data to Adobe Analytics prior to sending data to Customer Journey Analytics. 

You can migrate your Adobe Analytics implementation (either AppMeasurement or the Analytics extension) to use the Adobe Experience Platform Web SDK to begin sending data to Edge Network and Adobe Analytics. This is an interim step before sending it to Customer Journey Analytics. 

### Basic steps

The basic steps for migrating an AppMeasurement or Analytics extension implementation to use the Web SDK to send data to Adobe Analytics are:

1. Migrate your Adobe Analytics implementation (either AppMeasurement or the Analytics extension) to use the Adobe Experience Platform Web SDK and begin sending data to Edge Network.

1. Send data from Edge Network to Adobe Analytics. <!-- how do you do this? -->

### Advantages and disadvantages

Consider the following advantages and disadvantages of using this upgrade alternative:

| Advantages | Disadvantages |
|----------|---------|
|<ul><li>**Provides all the advantages of hosting data in Experience Edge Network**: <p>These advantages include:</p><ul><li>Highly performant reporting and data availability because Adobe Experience Platform is built to power [real-time personalization use cases](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)</li><li>Consolidate implementation for Adobe Experience Cloud data collection between other Experience Cloud products (AJO, RTCDP, and so forth)</li><li>Not reliant on Adobe Analytics nomenclature (prop, eVar, event, and so forth)</li></ul><li>**Uses your existing implementation**: While this approach requires some implementation changes, it does not require a completely new implementation from scratch. You can use your existing data layer and code with minimal changes to implementation logic without impacting your existing Adobe Analytics reporting.<p>In other words, this option saves implementation time by allowing you to map your AppMeasurement logic to XDM, rather than populating an XDM object from scratch.</p></li><li>**Provides flexibility to create an XDM schema for your organization at a later time**: You can migrate your existing Adobe Analytics implementation to use the Web SDK and validate that everything is working in Adobe Analytics, then create the XDM schema. This flexibility allows for a more methodical and thoughtful upgrade to Customer Journey Analytics.</li></ul> | <ul><li>**Requires mapping to send data to Platform**: When your organization is ready to use Customer Journey Analytics, you must send data to a data set in Adobe Experience Platform. This action requires that every field in the data object be an entry in the datastream mapping tool that assigns it to an XDM schema field. Mapping only needs to be done once for this workflow, and it doesn't involve making implementation changes. However, it is an extra step that is not required when sending data in an XDM object.</li><li>**Technical debt**: Because this approach uses a modified form of your existing implementation, it can be harder to track implementation logic and perform changes in the future when needed. </li></ul> |

{style="table-layout:auto"}


## Use the Web SDK to send data directly to Customer Journey Analytics



### Basic steps

The basic steps for migrating an AppMeasurement or Analytics extension implementation to use the Web SDK to send data to Customer Journey Analytics are:

1. Migrate your Adobe Analytics implementation (either AppMeasurement or the Analytics extension) to use the Adobe Experience Platform Web SDK and begin sending data to Edge Network.

1. Send data to from Edge Network to Customer Journey Analytics.

   1. Create an XDM schema for your organization.

   1. Use datastream mapping to map all of the fields in the data object to your XDM schema.

### Advantages and disadvantages

This method is mutually exclusive with [sending your entire data layer to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md), because both methods accomplish the same task. 

Consider the following advantages and disadvantages of using this upgrade alternative:

| Advantages | Disadvantages |
|----------|---------|
| <ul><li>**Provides all the advantages of hosting data in Experience Edge Network**: <p>These advantages include:</p><ul><li>Highly performant reporting and data availability because Adobe Experience Platform is built to power [real-time personalization use cases](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)</li><li>Consolidate implementation for Adobe Experience Cloud data collection between other Experience Cloud products (AJO, RTCDP, and so forth)</li><li>Not reliant on Adobe Analytics nomenclature (prop, eVar, event, and so forth)</li></ul><li>**Uses your existing implementation**: While this approach requires some implementation changes, it does not require a completely new implementation from scratch. You can use your existing data layer and code with minimal changes to implementation logic without impacting your existing Adobe Analytics reporting.<p>In other words, this option saves implementation time by allowing you to map your AppMeasurement logic to XDM, rather than populating an XDM object from scratch.</p></li> <p>This method is preferable to sending your entire data layer to Adobe. It is more refined because you're sending props, evars, etc. All going through data.__adobe.analytics._variable-name_ All going to be under this.</p> | This option introduces additional complexity over time, because any field you add in the future must be mapped to XDM in the datastream.<p>Any time a new field is added to your implementation, you can do either of the following:</p><ul><li>**Option 1:** Populate a new arbitrary evar or new prop in the data object, then map it to the desired XDM field.<p>This process drives consistency for the client-side implementation, but it requires mapping.</p></li><li>**Option 2:** Leave the data object as a legacy implementation and start populating only the XDM object for all new fields.<p>This process doesn't require mapping, but it means that some of your variables are located only in a data object, while other variables are located only in an XDM object. Any time you need to troubleshooting your implementation, you need to go to two places. Make sure your internal workflows accommodate for this.</p></li></ul> | 

{style="table-layout:auto"}

## Choose whether to use the Web SDK to send data to Adobe Analytics before sending it to Customer Journey Analytics


Use the following sections to understand the advantages and disadvantages of each method. 

### Use AppMeasurement or Analytics extension data collection with Adobe Analytics

If your Adobe Analytics implementation is AppMeasurement or the Analytics extension, an alternative upgrade method is available that allows you to migrate your Adobe Analytics implementation to use the Adobe Experience Platform Web SDK to begin sending data to Edge Network and Adobe Analytics, prior to sending it to Customer Journey Analytics. 

Consider the following advantages and disadvantages of using this upgrade alternative:

| Advantages | Disadvantages |
|----------|---------|
|<ul><li>**Provides all the advantages of hosting data in Experience Edge Network**: <p>These advantages include:</p><ul><li>Highly performant reporting and data availability because Adobe Experience Platform is built to power [real-time personalization use cases](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)</li><li>Consolidate implementation for Adobe Experience Cloud data collection between other Experience Cloud products (AJO, RTCDP, and so forth)</li><li>Not reliant on Adobe Analytics nomenclature (prop, eVar, event, and so forth)</li></ul><li>**Uses your existing implementation**: While this approach requires some implementation changes, it does not require a completely new implementation from scratch. You can use your existing data layer and code with minimal changes to implementation logic without impacting your existing Adobe Analytics reporting.</li><li>**Provides flexibility to create an XDM schema for your organization at a later time**: You can migrate your existing Adobe Analytics implementation to use the Web SDK and validate that everything is working in Adobe Analytics, then create the XDM schema. This flexibility allows for a more methodical and thoughtful upgrade to Customer Journey Analytics.</li></ul> | <ul><li>**Requires mapping to send data to Platform**: When your organization is ready to use Customer Journey Analytics, you must send data to a data set in Adobe Experience Platform. This action requires that every field in the data object be an entry in the datastream mapping tool that assigns it to an XDM schema field. Mapping only needs to be done once for this workflow, and it doesn't involve making implementation changes. However, it is an extra step that is not required when sending data in an XDM object.</li><li>**Technical debt**: Because this approach uses a modified form of your existing implementation, it can be harder to track implementation logic and perform changes in the future when needed. </li></ul> |

{style="table-layout:auto"}

### Use AppMeasurement data collection with Customer Journey Analytics

This method is mutually exclusive with [sending your entire data layer to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md), because both methods accomplish the same task. 

Consider the following advantages and disadvantages of using this upgrade alternative:

| Advantages | Disadvantages |
|----------|---------|
| This option saves implementation time by allowing you to map your AppMeasurement logic to XDM, rather than populating an XDM object from scratch. <p>This method is preferable to sending your entire data layer to Adobe. It is more refined because you're sending props, evars, etc. All going through data.__adobe.analytics._variable-name_ All going to be under this.</p> | This option introduces additional complexity over time, because any field you add in the future must be mapped to XDM in the datastream.<p>Any time a new field is added to your implementation, you can do either of the following:</p><ul><li>**Option 1:** Populate a new arbitrary evar or new prop in the data object, then map it to the desired XDM field.<p>This process drives consistency for the client-side implementation, but it requires mapping.</p></li><li>**Option 2:** Leave the data object as a legacy implementation and start populating only the XDM object for all new fields.<p>This process doesn't require mapping, but it means that some of your variables are located only in a data object, while other variables are located only in an XDM object. Any time you need to troubleshooting your implementation, you need to go to two places. Make sure your internal workflows accommodate for this.</p></li></ul> | 

{style="table-layout:auto"}



## Basic steps

If you decide to use this upgrade alternative of migrating your AppMeasurement or Analytics extension implementation to use the Web SDK, a new step is added to the dynamically generated steps for your organization in the [Adobe Analytics to Customer Journey Analytics upgrade questionnaire](https://gigazelle.github.io/cja-ttv/). 

The basic steps for migrating an AppMeasurement or Analytics extension implementation to use the Web SDK are:

1. Begin sending data to Platform.

   If you are already sending data to Platform with your Adobe Analytics implementation, this step is not required. You simply need to create a connection between Platform datasets and Customer Journey Analytics, as described later in this process.

1. (Optional) Create an XDM schema for your organization as you have time.

1. (Conditional) If you created an XDM schema, use datastream mapping to map all of the fields in the data object to your XDM schema.

