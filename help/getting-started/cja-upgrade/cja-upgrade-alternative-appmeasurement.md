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
>abstract="Instead of sending data through an XDM object, send all your variables in AppMeasurement format through the data object.<br><br>This option saves implementation time by allowing you to map your AppMeasurement logic to XDM, rather than populating an XDM object from scratch. However, it introduces additional complexity over time because any field you add in the future must be mapped to XDM in the datastream."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>Use the information on this page when answering questions in the [Customer Journey Analytics upgrade checklist](https://gigazelle.github.io/cja-ttv/). 

When upgrading to Customer Journey Analytics, Adobe [recommends a new implementation of the Experience Platform Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md). However, depending on several factors, such as timeline and resource constraints, the recommended upgrade steps might not be practical for your organization. 

You can use your AppMeasurement or Analytics extension data collection logic with the Web SDK in order to send data to Platform and Customer Journey Analytics, instead of collecting data with the XDM object. However, this alternative introduces additional complexity over time.

## Advantages and disadvantages

This method is mutually exclusive with [sending your entire data layer to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md), because both methods accomplish the same task. (This method is preferable to sending your entire data layer to Adobe. It is more refined because props and evars all go through data.__adobe.analytics._variable-name_.)

Consider the following advantages and disadvantages of using this upgrade alternative:

| Advantages | Disadvantages |
|----------|---------|
|<ul><li>**Provides all the advantages of hosting data in Experience Edge Network**: <p>These advantages include:</p><ul><li>Highly performant reporting and data availability because Adobe Experience Platform is built to power [real-time personalization use cases](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)</li><li>Consolidate implementation for Adobe Experience Cloud data collection between other Experience Cloud products (AJO, RTCDP, and so forth)</li><li>Not confined to Adobe Analytics nomenclature (prop, eVar, event, and so forth)</li></ul><li>**Uses your existing implementation**: While this approach requires some implementation changes, it does not require a completely new implementation from scratch. It allows you to map your AppMeasurement logic to XDM, rather than populating an XDM object from scratch.</li></ul> | <ul><li>**Requires mapping to send data to Platform**: When your organization is ready to use Customer Journey Analytics, you must send data to a data set in Adobe Experience Platform. This action requires that every field in the data object be an entry in the datastream mapping tool that assigns it to an XDM schema field. Mapping only needs to be done once for this workflow, and it doesn't involve making implementation changes. However, it is an extra step that is not required when sending data in an XDM object.</li><li>**Introduces additional complexity over time**: Any field you add in the future must be mapped to XDM in the datastream.<p>Any time a new field is added to your implementation, you can do either of the following:</p><ul><li>**Option 1:** Populate a new arbitrary evar or new prop in the data object, then map it to the desired XDM field.<p>This process drives consistency for the client-side implementation, but it requires mapping.</p></li><li>**Option 2:** Leave the data object as a legacy implementation and start populating only the XDM object for all new fields.<p>This process doesn't require mapping, but it means that some of your variables are located only in a data object, while other variables are located only in an XDM object. Any time you need to troubleshoot your implementation, you need to go to two places. Make sure your internal workflows accommodate for this.</p></li></ul> </li></ul> |

{style="table-layout:auto"}

## Basic steps

The basic steps for migrating an Adobe Analytics implementation (either AppMeasurement or the Analytics extension) to use the Web SDK to send data to Customer Journey Analytics are:

1. (Optional) Migrate your Adobe Analytics implementation to use the Adobe Experience Platform Web SDK and begin sending data to Edge Network. 

   This is an optional step that allows you to migrate your existing Adobe Analytics implementation to use the Web SDK and validate that everything is working in Adobe Analytics. After this is configured and the data in Adobe Analytics is satisfactory, you can send data from Edge Network to Customer Journey Analytics. 

   This flexibility allows for a more methodical and thoughtful upgrade to Customer Journey Analytics.

   For information about how to do this, see the following articles in the Adobe Analytics documentation:

   * [Migrate to the Web SDK using tags](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk)

   * [Migrate to the Web SDK using JavaScript](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk)

1. Send data from Edge Network to Customer Journey Analytics.

   1. Send all your variables in AppMeasurement format through the data object.

      For more information, see [Data object variable mapping to Adobe Analytics](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/data-var-mapping).

   1. If you haven't already, create an XDM schema for your organization.

      For more information, see [Create a custom schema to use with your Customer Journey Analytics Web SDK implementation](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

   1. Use datastream mapping to map all of the fields in the data object to your XDM schema.

      For more information, see [Mapping](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep?lang=en#mapping) in [Data Prep for Data Collection](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep) in the Experience Platform documentation.

