---
title: Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics
description: Learn about the recommended path when upgrading from Adobe Analytics to Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: yes
hidefromtoc: yes
---
# Upgrade from Adobe Analytics to Customer Journey Analytics

Before you begin the upgrade process from Adobe Analytics to Customer Journey Analytics, first understand the recommended upgrade steps.

Depending on several factors, such as timeline and resource constraints, the recommended upgrade steps might not be practical for your organization. After you understand the recommended upgrade steps, complete the questionnaire to dynamically generate upgrade steps that are tailored to your organization's unique circumstances.

## 1. Understand the recommended upgrade steps

>[!NOTE]
>
>The upgrade steps described in this section are the recommended upgrade steps that any organization could use to successfully upgrade from Adobe Analytics to Customer Journey Analytics.
>
>However, depending on several factors, such as timeline and resource constraints, the recommended upgrade steps might not be practical for your organization. After you understand the recommended upgrade steps, complete the [Adobe Analytics to Customer Journey Analytics upgrade questionnaire](https://gigazelle.github.io/cja-ttv/) to dynamically generate upgrade steps that are tailored to your organization's unique circumstances. 

The recommended steps when upgrading from Adobe Analytics to Customer Journey Analytics is a new implementation of the Experience Platform Web SDK, which is the preferred data collection method for Customer Journey Analytics. In conjunction with the Web SDK, Adobe also recommends using the Analytics source connector in order to retain historical Adobe Analytics data and to perform side-by-side data comparison. 

After fully transitioning to Customer Journey Analytics, the Analytics source connector can be turned off and the Experience Platform Web SDK can be used exclusively. 

1. **Implement the Experience Platform Web SDK**

   A new implementation of the Experience Platform Web SDK is the best way to collect data for Customer Journey Analytics. It provides the best foundation to get the most out of Customer Journey Analytics because it is the most performant, straightforward, and future-proof method for implementing Customer Journey Analytics. 

   * Highly performant reporting and data availability because Adobe Experience Platform is built to power real-time personalization use cases

   * Consolidate implementation for Adobe Experience Cloud data collection between other Experience Cloud products (AJO, RTCDP, and so forth)

   * Not reliant on Adobe Analytics nomenclature (prop, eVar, event, and so forth)

1. **Set up the Adobe Analytics source connector**

   To help with a smooth transition to using the Experience Platform Web SDK with Customer Journey Analytics, Adobe also recommends using the Adobe Analytics source connector. This allows you to retain historical data and view data from your existing Adobe Analytics implementation in Customer Journey Analytics, side by side with the data from your new Experience Platform Web SDK implementation. 

   The Analytics source connector allows you to:

   * Bring your historical Adobe Analytics report suite data into Adobe Experience Platform and Customer Journey Analytics. 
   
     You can keep the Analytics source connector running for as long as you need to retain the historical Adobe Analytics data. 
   
   * View the data collected with your original Adobe Analytics implementation (either AppMeasurement, the Analytics Extension, or the Web SDK Extension) within Customer Journey Analytics. You can compare this data side-by-side with that of your new Web SDK implementation. 
   
     You can keep the Analytics source connector running until you are familiar and comfortable with the differences. <!--elaborate on what those differences are? -->
   
    The Analytics source connector as a stand-alone implementation is not a recommended long-term method for using Customer Journey Analytics. This is because of high latency, cluttered and complex schemas, reliance on Adobe Analytics nomenclature (prop, eVar, and so forth), and difficulty in eventually moving from the source connector to the recommended Web SDK implementation. 

## 2. Dynamically generate upgrade steps for your organization

Depending on several factors, such as timeline and resource constraints, the recommended upgrade steps described in [Understand the recommended upgrade steps](#1-understand-the-recommended-upgrade-steps) might not be practical for your organization. 

To view the dynamically generated upgrade steps for your organization's unique circumstances:

1. Complete the [Adobe Analytics to Customer Journey Analytics upgrade questionnaire](https://gigazelle.github.io/cja-ttv/). 

   After completing this questionnaire, step-by-step instructions are provided to you, outlining the optimal upgrade steps that are unique to your organization. These are the upgrade steps that best align with your existing Adobe Analytics environment and your goals for Customer Journey Analytics.
   
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









