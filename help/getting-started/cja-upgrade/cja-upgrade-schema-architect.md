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
# Architect your schema for use with Customer Journey Analytics {#upgrade-schema-architect}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-architect"
>title="Architect a schema"
>abstract="Discuss within your organization the requirements of data collection, and determine how you want to build a schema for use in Adobe Experience Platform. This step appears because you want to use the recommended process of using a schema tailored to your organization. Performing this step correctly is pivotal, as a schema that all teams within your organization align on makes data ingestion significantly easier.<br><br>The estimated time to bring together all relevant parties in your organization to align upon a unified schema is 1-2 months. This time frame heavily depends on the number of teams required to coordinate, and the number of dimensions + metrics to align on."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>Follow the steps on this page only after you complete all previous upgrade steps. You can follow the [recommended upgrade steps](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations), or you can follow the upgrade steps that were dynamically generated for your organization with the [Adobe Analytics to Customer Journey Analytics upgrade questionnaire](https://gigazelle.github.io/cja-ttv/). 
>
>After you complete the steps on this page, continue following the recommended upgrade steps or the dynamically generated upgrade steps. 

Adobe recommends creating a custom Experience Data Model (XDM) schema to use with the Web SDK when upgrading from Adobe Analytics to Customer Journey Analytics. Alternatively, you could use the default Adobe Analytics schema, which uses the Adobe Analytics ExperienceEvent field group.  

A custom XDM schema allows for a streamlined schema that is tailored to the needs of your organization and the specific Platform applications that you use. Unlike the default Adobe Analytics schema that uses the Adobe Analytics ExperienceEvent field group, when changes to a custom XDM schema are required, you don't have to sift through thousands of unused fields to find the field that requires updating.

For more information about these schema options, see [Choose your schema for Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md).

Review the following sections as you begin architecting your XDM schema.

## Avoid Adobe Analytics restrictions in your XDM schema

The underlying architecture of Customer Journey Analytics provides for much more flexibility than Adobe Analytics. Creating a new XDM schema is a key way to unlock that flexibility. When you upgrade to Customer Journey Analytics, make sure that you avoid carrying forward unnecessary Adobe Analytics restrictions into your schema.

| Adobe Analytics data architecture | XDM schema architecture | 
|---------|----------|
| Individual metrics are added to the Analytics data architecture.<br/>For example, in Adobe Analytics, you have a different eVar for each event.  | Create individual metrics in the data view rather than in the XDM schema. Doing so provides more flexibility in if you need to make changes at a later time.<br/>For example, in Customer Journey Analytics, you have a single event in the schema, and use create events in the data view.  | 
| Props and eVars are required to create custom variables. | B2 | 
| A3 | B3 | 

## Identify your data team and other stakeholders throughout your organization


## Consider other Adobe Experience Platform applications used in your organization



1. Continue following the [recommended upgrade steps](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) or the [dynamically generated upgrade steps](https://gigazelle.github.io/cja-ttv/).
