---
title: Configure your existing Adobe Analytics Web SDK implementation to send data to Platform
description: Learn about configuring your existing Adobe Analytics Web SDK implementation
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: yes
hidefromtoc: yes
exl-id: 1459a512-bfa8-4805-97e8-5b6acc6e4ac9
---
# Configure your existing Adobe Analytics Web SDK implementation to send data to Platform {#existing-websdk-implementation}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-remove-aa-from-datastream"
>title="Remove Adobe Analytics as a service from the datastream"
>abstract="With Web SDK data fully functional, work with your Platform administrator to remove Adobe Analytics as a service from the datastream. Before you do this, make sure that your users have transitioned from using Adobe Analytics to Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

If your Adobe Analytics implementation is already using the Adobe Experience Platform Web SDK, you can begin sending data to Platform by setting up a datastream. Or, if you are already sending data to Platform, you simply need to create a connection between Platform datasets and Customer Journey Analytics.


## Advantages and disadvantages

Consider the following advantages and disadvantages of configuring your existing Adobe Analytics Web SDK implementation to send data to Platform:

| Advantages | Disadvantages |
|----------|---------|
| This is the preferred upgrade path if your Adobe Analytics implementation is already using the Web SDK.<ul><li>**Provides all the advantages of hosting data in Experience Edge Network**: <p>These advantages include:</p><ul><li>Highly performant reporting and data availability because Adobe Experience Platform is built to power [real-time personalization use cases](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)</li><li>Consolidate implementation for Adobe Experience Cloud data collection between other Experience Cloud products (AJO, RTCDP, and so forth)</li><li>Not reliant on Adobe Analytics nomenclature (prop, eVar, event, and so forth)</li></ul><li>**Uses your existing implementation**: While this approach requires some implementation changes, it does not require a completely new implementation from scratch. You can use your existing data layer and code with minimal changes to implementation logic without impacting your existing Adobe Analytics reporting.</li><li>**Provides an option to use an XDM schema**: You can choose to use your existing Adobe Analytics schema or create an XDM schema and map fields in the data object to your XDM schema. [XDM schemas](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) are a flexible schema to define any fields you need, and only those fields that are relevant. <p>See "Using your own XDM schema" below for more information about the advantages of using your own XDM schema.</p></li><li>**Retains rules and data elements**: While it does require new rule actions, you can reuse your existing data elements and rule conditions with minimal changes.</li><li>**Future-proof**: If you choose to use your own XDM schema, then future implementation updates are easier.</li></ul> | <ul><li>**Requires mapping to send data to Platform**: When your organization is ready to use Customer Journey Analytics, you must send data to a data set in Adobe Experience Platform. This action requires that every field in the data object be an entry in the datastream mapping tool that assigns it to an XDM schema field. Mapping only needs to be done once for this workflow, and it doesn't involve making implementation changes. However, it is an extra step that is not required when sending data in an XDM object.</li><li>**Introduces additional complexity over time**: Any field you add in the future must be mapped to XDM in the datastream.<p>Any time a new field is added to your implementation, you can do either of the following:</p><ul><li>**Option 1:** Populate a new arbitrary evar or new prop in the data object, then map it to the desired XDM field.<p>This process drives consistency for the client-side implementation, but it requires mapping.</p></li><li>**Option 2:** Leave the data object as a legacy implementation and start populating only the XDM object for all new fields.<p>This process doesn't require mapping, but it means that some of your variables are located only in a data object, while other variables are located only in an XDM object. Any time you need to troubleshoot your implementation, you need to go to two places. Make sure your internal workflows accommodate for this.</p></li></ul> |

{style="table-layout:auto"}

## Implementation steps

1. Begin sending data from Edge Network to Platform. Send all your variables in AppMeasurement format through the data object.

   For more information, see [Data object variable mapping to Adobe Analytics](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/data-var-mapping).
  
1. Choose your schema.

   You can choose whether to use your existing Adobe Analytics schema, or you can create an XDM schema to better align with the needs of your organization as you begin to use other Platform services.

   Adobe recommends creating an XDM schema. For more information, see [Create a custom schema to use with your Customer Journey Analytics Web SDK implementation](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

   +++Use the Adobe Analytics schema

   | Advantages | Disadvantages |
   |----------|---------|
   |<p>Advantages of using the Adobe Analytics schema include:</p><ul><li>Ease of upgrade<p>If you are already sending data to Adobe Analytics with the Adobe Experience Platform Web SDK, you can add an additional service to your datastream to send data to Adobe Experience Platform (which then can be used in your Customer Journey Analytics configuration).</p></li></ul> | <p>Disadvantages of using the Adobe Analytics schema include:</p><ul><li>While using the Adobe Analytics schema doesn't limit you in terms of how it can be used with other Platform applications, it does result in a schema that is more complex than it otherwise could be. This is because the Adobe Analytics schema contains many objects that are specific to Adobe Analytics that are unlikely to be used by your organization.<p>When changes to the schema are required, you have to sift through thousands of unused fields to find the field that requires updating.</p></li></ul> |

   +++

   +++Create an XDM schema

   | Advantages | Disadvantages |
   |----------|---------|
   |<ul><p>Advantages of updating to your own XDM schema include:</p><ul><li>A streamlined schema that is tailored to the needs of your organization and the specific Platform applications that you use.</li><p>When changes to the schema are required, you don't have to sift through thousands of unused fields to find the field that requires updating.</p></ul> | <p>Disadvantages of updating to your own XDM schema include:</p><ul><li>Updating your schema is a time-consuming process that is required before you begin sending data to Platform.</li></ul> |

   +++

1. Use datastream mapping to map all of the fields in the data object to your XDM schema.

   For more information, see [Mapping](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep?lang=en#mapping) in [Data Prep for Data Collection](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep) in the Experience Platform documentation.

{{upgrade-final-step}}
