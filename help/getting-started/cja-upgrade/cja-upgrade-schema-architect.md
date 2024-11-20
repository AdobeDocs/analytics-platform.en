---
title: Architect your schema for use with Customer Journey Analytics
description: Learn about the recommended path when upgrading from Adobe Analytics to Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: yes
hidefromtoc: yes
exl-id: f932110a-ca9d-40d1-9459-064ef9cd23da
---
# Architect your schema for use with Customer Journey Analytics

>[!NOTE]
> 
>Follow the steps on this page only after you complete all previous upgrade steps. You can follow the [recommended upgrade steps](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations), or you can follow the upgrade steps that were dynamically generated for your organization with the [Adobe Analytics to Customer Journey Analytics upgrade questionnaire](https://gigazelle.github.io/cja-ttv/). 
>
>After you complete the steps on this page, continue following the recommended upgrade steps or the dynamically generated upgrade steps. 

Adobe recommends creating an Experience Data Model (XDM) schema when upgrading to Customer Journey Analytics. An XDM schema allows for a streamlined schema that is tailored to the needs of your organization and the specific Platform applications that you use. When changes to the schema are required, you don't have to sift through thousands of unused fields to find the field that requires updating.  

Review the following sections as you begin architecting your XDM schema.

## Avoid Adobe Analytics restrictions in your XDM schema

The underlying architecture of Customer Journey Analytics provides for much more flexibility than Adobe Analytics. Creating a new XDM schema is a key way to unlock that flexibility. When you upgrade to Customer Journey Analytics, make sure that you avoid carrying forward unnecessary Adobe Analytics restrictions into your schema.

| Adobe Analytics data architecture | XDM schema architecture | 
|---------|----------|
| Individual metrics are added to the Analytics data architecture. | Create individual metrics in the data view rather than in the XDM schema. Doing so provides more flexibility in if you need to make changes at a later time. | 
| Props and eVars are required to create custom variables. | B2 | 
| A3 | B3 | 

## Identify your data team and other stakeholders throughout your organization


## Consider other Adobe Experience Platform applications used in your organization



1. Continue following the [recommended upgrade steps](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) or the [dynamically generated upgrade steps](https://gigazelle.github.io/cja-ttv/).
