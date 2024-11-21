---
title: Create an XDM schema for the Analytics source connector
description: Learn how to create an XDM schema for the Analytics source connector
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: yes
hidefromtoc: yes
exl-id: fad62c04-b435-466a-ab3c-cf2d174ddbfb
---
# Create an XDM schema for the Analytics source connector

>[!NOTE]
> 
>Follow the steps on this page only after you complete all previous upgrade steps. You can follow the [recommended upgrade steps](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations), or you can follow the upgrade steps that were dynamically generated for your organization with the [Adobe Analytics to Customer Journey Analytics upgrade questionnaire](https://gigazelle.github.io/cja-ttv/). 
>
>After you complete the steps on this page, continue following the recommended upgrade steps or the dynamically generated upgrade steps. 

## Understand how the Analytics source connector can bring historical data into Customer Journey Analytics

You can use the Analytics source connector to bring Adobe Analytics report suite data into Adobe Experience Platform. This data can then be used as historical data in Customer Journey Analytics.

This process assumes that you want to [create an XDM schema when upgrading to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md), because you want a streamlined schema that is tailored to the needs of your organization and the specific Platform applications that you use. 

To use the Analytics source connector to bring historical data into Customer Journey Analytics, you need to: 

1. Create an XDM schema for the Analytics source connector, as described below.

1. If you don't already have an Analytics source connector, [create the Analytics source connector and map fields to your XDM schema](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md).

   Or

   If you already have an Analytics source connector, [map fields from the source connector to your XDM schema](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md).

1. [Add the Analytics source connector dataset to the connection](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)

## Create an XDM schema for the Analytics source connector

You should have already [created a new XDM schema](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md) for your Experience Platform Web SDK implementation to use with Customer Journey Analytics. This schema should contain any field groups for fields that you plan to collect data on. 

In addition to the XDM schema you already created for your Web SDK implementation, you now need to create a second XDM schema to use with the Analytics source connector to bring historical data into Customer Journey Analytics. 

This second schema needs to contain:

* All field groups (including any custom field groups) that are included in the schema that you created for your Web SDK implementation. (Any custom fields that aren't part of a default field group should have been added to your Web SDK schema as part of a custom field group.)

* The Adobe Analytics ExperienceEvent Template field group

To create the XDM schema to use with the Analytics source connector:

1. In Adobe Experience Platform, begin creating a new XDM schema as described in [Create an XDM schema to use with Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

1. Add all field groups (including any custom field groups) that are included in the schema that you created for your Web SDK implementation.

1. After you finish adding these field groups, add the Adobe Analytics ExperienceEvent field group: 

   In the **[!UICONTROL Field groups]** section, select **[!UICONTROL Add]** to add an additional field group. 

   ![Add field group to schema](assets/schema-add-field-group.png)

1. Search for and select the **[!UICONTROL Adobe Analytics ExperienceEvent Template]** field group.

   ![Add the Adobe Analytics ExperienceEvent field group](assets/schema-experienceevent.png)

1. Select **[!UICONTROL Add field groups]**.

1. Select **[!UICONTROL Save]** to save your schema.

1. Continue following the [recommended upgrade steps](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) or the [dynamically generated upgrade steps](https://gigazelle.github.io/cja-ttv/).
