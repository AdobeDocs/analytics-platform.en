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
>abstract="Instead of sending data through an XDM object, you can send your entire data layer to Adobe through the data object.<br><br>This alternative upgrade method is mutually exclusive to using AppMeasurement logic, because both methods accomplish the same task."

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
| This option saves implementation time by allowing you to map data from your data layer to XDM, rather than populating an XDM object from scratch.  | This option introduces additional complexity over time, because any field you add to your data later in the future must be mapped to XDM in the datastream.<p>Because this option allows you to put your entire client-side data layer into the data object and send it to Adobe, this results in a significant amount of data that Adobe can't readily interpret. To allow Adobe to interpret the data, you must use datastream mapping to map every individual field to the desired XDM field.</p> | 

{style="table-layout:auto"}



