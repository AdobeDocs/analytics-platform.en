---
title: Alternate methods when upgrading to Customer Journey Analytics
description: Learn about the alternate methods when upgrading to Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: yes
hidefromtoc: yes
---
# Upgrade alternative: Use AppMeasurement data collection with Customer Journey Analytics {#data-collection-data-layer}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-appmeasurement-logic"
>title="Use AppMeasurement logic with the Web SDK"
>abstract="Instead of sending data through an XDM object, send all your variables in AppMeasurement format through the data object.<br><br>This alternative upgrade method is mutually exclusive to sending your data layer to Adobe, because both methods accomplish the same task."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>Use the information on this page when answering questions in the [Customer Journey Analytics upgrade checklist](https://gigazelle.github.io/cja-ttv/). 

You can continue to use your AppMeasurement data collection logic with Customer Journey Analytics instead of collecting data with the XDM object.   However, this alternative introduces additional complexity over time.

This method is mutually exclusive with [sending your entire data layer to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md), because both methods accomplish the same task. 

Following are the advantages and disadvantages of using this upgrade alternative:

| Advantages | Disadvantages |
|----------|---------|
| This option saves implementation time by allowing you to map your AppMeasurement logic to XDM, rather than populating an XDM object from scratch. <p>This method is preferable to sending your entire data layer to Adobe. It is more refined because you're sending props, evars, etc. All going through data.__adobe.analytics._variable-name_ All going to be under this.</p> | This option introduces additional complexity over time, because any field you add in the future must be mapped to XDM in the datastream.<p>Any time a new field is added to your implementation, you can do either of the following:</p><ul><li>**Option 1:** Populate a new arbitrary evar or new prop in the data object, then map it to the desired XDM field.<p>This process drives consistency for the client-side implementation, but it requires mapping.</p></li><li>**Option 2:** Leave the data object as a legacy implementation and start populating only the XDM object for all new fields.<p>This process doesn't require mapping, but it means that some of your variables are located only in a data object, while other variables are located only in an XDM object. Any time you need to troubleshooting your implementation, you need to go to two places. Make sure your internal workflows accommodate for this.</p></li></ul> | 

{style="table-layout:auto"}

### Advantages

This option saves implementation time by allowing you to map your AppMeasurement logic to XDM, rather than populating an XDM object from scratch. 

This method is preferable to sending your data layer to Adobe. It is more refined because you're sending props, evars, etc. All going through data.__adobe.analytics._variable-name_ All going to be under this. 

### Disadvantages

This option introduces additional complexity over time, because any field you add in the future must be mapped to XDM in the datastream. 

Any time a new field is added to your implementation, you can do either of the following:

**Option 1:** Populate a new arbitrary evar or new prop in the data object, then map it to the desired XDM field.

This process drives consistency for the client-side implementation, but it requires mapping. 

**Option 2:** Leave the data object as a legacy implementation and start populating only the XDM object for all new fields. 

This process doesn't require mapping, but it means that some of your variables are located only in a data object, while other variables are located only in an XDM object. Any time you need to troubleshooting your implementation, you need to go to two places. Make sure your internal workflows accommodate for this.

## Send your data layer to Adobe without additional configuration

Instead of sending data through an XDM object, you can send your entire data layer to Adobe through the data object.  

## Advantages

This option saves implementation time by allowing you to map data from your data layer to XDM, rather than populating an XDM object from scratch. 

## Disadvantages

This option introduces additional complexity over time, because any field you add to your data later in the future must be mapped to XDM in the datastream.  

You are taking the entire client-side data layer and shoving it in the data object and sending it to Adobe. There's going to be a lot of data that Adobe won't know how to interpret until they use datastream mapping to map every individual field to the desired XDM field. 







Configure the Adobe Analytics Web SDK implementation to send data to Platform

| Advantages | Disadvantages |
|----------|---------|
| This is the preferred upgrade path if your Adobe Analytics implementation is already using the Web SDK.<ul><li>**Provides all the advantages of hosting data in Experience Edge Network**: <p>These advantages include:</p><ul><li>Highly performant reporting and data availability because Adobe Experience Platform is built to power [real-time personalization use cases](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)</li><li>Consolidate implementation for Adobe Experience Cloud data collection between other Experience Cloud products (AJO, RTCDP, and so forth)</li><li>Not reliant on Adobe Analytics nomenclature (prop, eVar, event, and so forth)</li></ul><li>**Uses your existing implementation**: While this approach requires some implementation changes, it does not require a completely new implementation from scratch. You can use your existing data layer and code with minimal changes to implementation logic without impacting your existing Adobe Analytics reporting.</li><li>**Provides an option to use an XDM schema**: You can choose to use your existing Adobe Analytics schema or create an XDM schema and map fields in the data object to your XDM schema. [XDM schemas](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) are a flexible schema to define any fields you need, and only those fields that are relevant. <p>See "Using your own XDM schema" below for more information about the advantages of using your own XDM schema.</p></li><li>**Retains rules and data elements**: While it does require new rule actions, you can reuse your existing data elements and rule conditions with minimal changes.</li><li>**Future-proof**: If you choose to use your own XDM schema, then future implementation updates are easier.</li></ul> | None |

{style="table-layout:auto"}



