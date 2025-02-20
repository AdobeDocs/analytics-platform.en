---
title: Alternate methods when upgrading to Customer Journey Analytics
description: Learn about the alternate methods when upgrading to Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: yes
hidefromtoc: yes
---
# Upgrade alternative: Send your data layer to Customer Journey Analytics {#data-collection-data-layer}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-data-layer"
>title="Send data layer to Adobe"
>abstract="Instead of sending data through an XDM object, you can send your entire data layer to Adobe through the data object.<br><br>This option saves implementation time by allowing you to map your data layer to XDM, rather than populating an XDM object from scratch. However, this mapping is a large amount of work because there will be a significant amount of data that Adobe can't readily interpret. This option also introduces additional complexity over time because any field you add to your data later in the future must be mapped to XDM in the datastream."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>Use the information on this page when answering questions in the [Customer Journey Analytics upgrade checklist](https://gigazelle.github.io/cja-ttv/). 

When upgrading to Customer Journey Analytics, Adobe [recommends a new implementation of the Experience Platform Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md). However, depending on several factors, such as timeline and resource constraints, the recommended upgrade steps might not be practical for your organization. 

You can send your entire data layer to Customer Journey Analytics instead of collecting data with the XDM object. However, this alternative introduces additional complexity over time.

This method is mutually exclusive with [using your AppMeasurement data collection logic with Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md), because both methods accomplish the same task. 

Following are the advantages and disadvantages of using this upgrade alternative:

| Advantages | Disadvantages |
|----------|---------|
| <ul><li>**Provides all the advantages of hosting data in Experience Edge Network**: <p>These advantages include:</p><ul><li>Highly performant reporting and data availability because Adobe Experience Platform is built to power [real-time personalization use cases](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)</li><li>Consolidate implementation for Adobe Experience Cloud data collection between other Experience Cloud products (AJO, RTCDP, and so forth)</li><li>Not reliant on Adobe Analytics nomenclature (prop, eVar, event, and so forth)</li></ul><li>**Uses your existing implementation**: While this approach requires some implementation changes, it does not require a completely new implementation from scratch. It allows you to map data from your data layer to XDM, rather than populating an XDM object from scratch.</li></ul> | <ul><li>**Requires mapping to send data to Platform**: When your organization is ready to use Customer Journey Analytics, you must send data to a data set in Adobe Experience Platform. <p>Because this option allows you to put your entire client-side data layer into the data object and send it to Adobe, this results in a significant amount of data that Adobe can't readily interpret. To allow Adobe to interpret the data, you must use datastream mapping to map every individual field to the desired XDM field.</p></li><li>**Introduces additional complexity over time**: Any field you add to your data later in the future must be mapped to XDM in the datastream.</li></ul> | 

{style="table-layout:auto"}



