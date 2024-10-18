---
title: Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics
description: Learn about the recommended path when upgrading from Adobe Analytics to Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
---
# Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics

Customer Journey Analytics is the next generation of analytics. It allows multi-channel data collection (both online and offline data), combined with powerful report-time processing functionality (through the definition of components and derived fields in data views). 

Regardless of your current Adobe Analytics implementation, Adobe recommends a two-pronged upgrade approach when upgrading from Adobe Analytics to Customer Journey Analytics: the Adobe Analytics source connector and a new implementation of the Experience Platform WebSDK.

When used together, this two-pronged approach lays the best foundation for a successful upgrade from Adobe Analytics to Customer Journey Analytics. 

1. **Implement the Experience Platform WebSDK**

   A new implementation of the Experience Platform WebSDK is the second piece of the two-pronged upgrade approach to Customer Journey Analytics. 

   <!-- This will be the defacto way to collect data moving forward, and the Analytics source connector will eventually be turned off. -->
   
   A new implementation of the Experience Platform WebSDK is the most performant, straightforward, and future-proof method for implementing Customer Journey Analytics. It provides the best foundation to get the most out of Customer Journey Analytics, by providing the following benefits:

   * Highly performant reporting and data availability because Adobe Experience Platform is built to power real-time personalization use cases

   * Consolidate implementation for Adobe Experience Cloud data collection between other Experience Cloud products (AJO, RTCDP, and so forth)

   * Not reliant on Adobe Analytics nomenclature (prop, eVar, event, and so forth)

1. **Set up the Adobe Analytics source connector**

   The Analytics source connector is an essential piece of a two-pronged upgrade approach to Customer Journey Analytics. 

   The Analytics source connector allows you to:

   * Bring your historical Adobe Analytics report suite data into Adobe Experience Platform and Customer Journey Analytics. 
   
     You can keep the Analytics source connector running for as long as you need to retain the historical Adobe Analytics data. 
   
   * View the data collected with your original Adobe Analytics implementation (either AppMeasurement, the Analytics Extension, or the WebSDK Extension) within Customer Journey Analytics. You can compare this data side-by-side with that of your new WebSDK implementation. 
   
     You can keep the Analytics source connector running until you are familiar and comfortable with the differences. <!--elaborate on what those differences are? -->

   The Analytics source connector as a stand-alone implementation is not a recommended long-term method for upgrading to Customer Journey Analytics. This is because of high latency, cluttered and complex schemas, reliance on Adobe Analytics nomenclature (prop, eVar, and so forth), and difficulty in eventually moving from the source connector to the recommended WebSDK implementation.
   











