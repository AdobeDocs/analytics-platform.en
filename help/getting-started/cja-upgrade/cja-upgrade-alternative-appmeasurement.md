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



