---
title: Upgrade shortcut Migrate an AppMeasurement or Analytics extension implementation to use the Web SDK
description: Learn about the recommended path when upgrading from Adobe Analytics to Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: yes
hidefromtoc: yes
---
# Upgrade shortcut: Migrate an AppMeasurement or Analytics extension implementation to use the Web SDK

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_migrate_aa_to_websdk"
>title="Migrate Analytics implementation to use Web SDK"
>abstract="Instead of sending data through an XDM object, you can send all your variables in AppMeasurement format through the data object. This shortcut allows you to continue using your AppMeasurement logic to send data to Platform."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
>
>This documentation should be used as part of the [Adobe Analytics to Customer Journey Analytics upgrade questionnaire](https://gigazelle.github.io/cja-ttv/).

When upgrading to Customer Journey Analytics, Adobe [recommends a new implementation of the Experience Platform Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md). However, depending on several factors, such as timeline and resource constraints, the recommended upgrade steps might not be practical for your organization. 

If your Adobe Analytics implementation is AppMeasurement or the Analytics extension, an upgrade shortcut is available that allows you to migrate your Adobe Analytics implementation to use the Adobe Experience Platform Web SDK to begin sending data to Edge Network and Adobe Analytics, prior to sending it to Customer Journey Analytics.

## Advantages and disadvantages

Consider the following advantages and disadvantage of the upgrade shortcut to migrate your AppMeasurement or Analytics extension implementation to use the Web SDK:

| Advantages | Disadvantages |
|----------|---------|
|<ul><li>**Provides all the advantages of hosting data in Experience Edge Network**: <p>These advantages include:</p><ul><li>Highly performant reporting and data availability because Adobe Experience Platform is built to power [real-time personalization use cases](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)</li><li>Consolidate implementation for Adobe Experience Cloud data collection between other Experience Cloud products (AJO, RTCDP, and so forth)</li><li>Not reliant on Adobe Analytics nomenclature (prop, eVar, event, and so forth)</li></ul><li>**Uses your existing implementation**: While this approach requires some implementation changes, it does not require a completely new implementation from scratch. You can use your existing data layer and code with minimal changes to implementation logic without impacting your existing Adobe Analytics reporting.</li><li>**Provides flexibility to create an XDM schema for your organization at a later time**: You can migrate your existing Adobe Analytics implementation to use the Web SDK and validate that everything is working in Adobe Analytics, then create the XDM schema. This flexibility allows for a more methodical and thoughtful upgrade to Customer Journey Analytics.</li></ul> | <ul><li>**Requires mapping to send data to Platform**: When your organization is ready to use Customer Journey Analytics, you must send data to a data set in Adobe Experience Platform. This action requires that every field in the data object be an entry in the datastream mapping tool that assigns it to an XDM schema field. Mapping only needs to be done once for this workflow, and it doesn't involve making implementation changes. However, it is an extra step that is not required when sending data in an XDM object.</li><li>**Technical debt**: Because this approach uses a modified form of your existing implementation, it can be harder to track implementation logic and perform changes in the future when needed. </li></ul> |

{style="table-layout:auto"}

### Basic steps

If you decide to take the upgrade shortcut to migrate your AppMeasurement or Analytics extension implementation to use the Web SDK, a new step is added to the dynamically generated steps for your organization in the [Adobe Analytics to Customer Journey Analytics upgrade questionnaire](https://gigazelle.github.io/cja-ttv/). 

The basic steps for migrating an AppMeasurement or Analytics extension implementation to use the Web SDK are:

1. Begin sending data to Platform.

   If you are already sending data to Platform with your Adobe Analytics implementation, this step is not required. You simply need to create a connection between Platform datasets and Customer Journey Analytics, as described later in this process.

1. (Optional) Create an XDM schema for your organization as you have time.

1. (Conditional) If you created an XDM schema, use datastream mapping to map all of the fields in the data object to your XDM schema.

