---
title: Choose your schema for Customer Journey Analytics
description: Learn about the options available when choosing a schema for Customer Journey Analytics and the advantages and disadvantages of each
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: yes
hidefromtoc: yes
exl-id: a2b90ab2-2fcb-4bf4-a862-2f0675dc2fe2
---
# Choose your schema for Customer Journey Analytics

>[!NOTE]
>
>This documentation should be used as part of the [Adobe Analytics to Customer Journey Analytics upgrade questionnaire](https://gigazelle.github.io/cja-ttv/).

<!-- this page exists as the "Learn more" link in the info icons for the options "I am comfortable using my Adobe Analytics schema as a basis" and "I want to use a schema tailored to my organization" -->

When upgrading to Customer Journey Analytics, Adobe recommends creating a new XDM schema to better align with the needs of your organization as you begin to use other Platform services. Alternatively, you can choose to use your existing Adobe Analytics schema.

Consider the advantages and disadvantage of each.

## Create an XDM schema tailored to your organization (Recommended)

Adobe recommends creating a new XDM schema when upgrading to Customer Journey Analytics.

| Advantages | Disadvantages |
|----------|---------|
|<ul><p>Advantages of updating to your own XDM schema include:</p><ul><li>A streamlined schema that is tailored to the needs of your organization and the specific Platform applications that you use.</li><p>When changes to the schema are required, you don't have to sift through thousands of unused fields to find the field that requires updating.</p></ul> | <p>Disadvantages of updating to your own XDM schema include:</p><ul><li>Updating your schema is a time-consuming process that is required before you begin sending data to Platform.</li></ul> |

## Use your existing Adobe Analytics schema

The option to use your existing Adobe Analytics schema with Customer Journey Analytics is available only if your Adobe Analytics implementation is configured with the Adobe Experience Platform Web SDK. <!-- correct? Or can you do this with an AppMeasurement implementation?-->

| Advantages | Disadvantages |
|----------|---------|
|<p>Advantages of using the Adobe Analytics schema include:</p><ul><li>Ease of upgrade<p>If you are already sending data to Adobe Analytics with the Adobe Experience Platform Web SDK, you can add an additional service to your datastream to send data to Adobe Experience Platform (which then can be used in your Customer Journey Analytics configuration).</p></li></ul> | <p>Disadvantages of using the Adobe Analytics schema include:</p><ul><li>While using the Adobe Analytics schema doesn't limit you in terms of how it can be used with other Platform applications, it does result in a schema that is more complex than it otherwise could be. This is because the Adobe Analytics schema contains many objects that are specific to Adobe Analytics that are unlikely to be used by your organization.<p>When changes to the schema are required, you have to sift through thousands of unused fields to find the field that requires updating.</p></li></ul> |




<!-- Not sure about any of this: 

If you plan to use your Adobe Analytics schema, the following steps are required:

For Adobe Analytics implementations using AppMeasurement:

1. Datastream mapping

For Adobe Analytics implementations using the Web SDK:

1. 



the upgrade steps provided by the [Adobe Analytics to Customer Journey Analytics upgrade questionnaire](https://gigazelle.github.io/cja-ttv/).

If you want to create an XDM schema to use with Customer Journey Analytics, continue with [Create an XDM schema to use with Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).


Tags: (All 3 require data prep mapping. Would need to go into the datastream and map every single field to its appropriate place in XDM. Because whenever you use the data object, it always requires mapping. If you send something in the data object and it doesn't get mapped, the it is permanently lost and can't be recovered.)

1. Shim - Intercepts and instead of sending data to a report suite, it sends it to a Data View. (Data object)

1. Russ special - convert current implementation to a Web SDK implementation - put everything in the data object. 

1. Plop entire data layer into the data object and send that to the datastream. (not documented. Might be the Web SDK docs.)

-->
