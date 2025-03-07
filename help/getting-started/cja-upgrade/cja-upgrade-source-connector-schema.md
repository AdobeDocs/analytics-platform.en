---
title: Create a custom schema for the Analytics source connector
description: Learn how to create a custom schema for the Analytics source connector
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: yes
hidefromtoc: yes
exl-id: fad62c04-b435-466a-ab3c-cf2d174ddbfb
---
# Create a custom schema for the Analytics source connector {#create-custom-schema}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-create-schema"
>title="Create a schema for the Analytics source connector"
>abstract="This schema is a combination of the Adobe Analytics ExperienceEvent field group with all field groups that make up your organization's custom schema. It allows you to map the fields used by the Analytics source connector to your organization's schema, and is only used for historical data.<br><br>While technical in nature, creating this schema can be completed in hours, possibly faster if you know exactly which field groups make up your organization's custom schema."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

## Understand how the Analytics source connector can bring historical data into Customer Journey Analytics

You can use the Analytics source connector to bring Adobe Analytics report suite data into Adobe Experience Platform. This data can then be used as historical data in Customer Journey Analytics.

This process assumes that you want to [create a custom schema to use with your Customer Journey Analytics Web SDK implementation](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md), because you want a streamlined schema that is tailored to the needs of your organization and the specific Platform applications that you use. 

To use the Analytics source connector to bring historical data into Customer Journey Analytics, you need to: 

1. Create a custom schema for the Analytics source connector, as described below.

1. If you don't already have an Analytics source connector, [create the Analytics source connector and map fields to your custom schema](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md).

   Or

   If you already have an Analytics source connector, [map fields from the source connector to your XDM schema](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md).

1. [Add the Analytics source connector dataset to the connection](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)

## Create a custom schema for the Analytics source connector

You should have already [created a new custom schema](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md) for your Experience Platform Web SDK implementation to use with Customer Journey Analytics. This schema should contain any field groups for fields that you plan to collect data on. 

You now need to use those same field groups from your Web SDK schema and add them to a new schema that you can use with the Analytics source connector. 

This schema for the Analytics source connector needs to contain:

* All field groups (including any custom field groups that you created) that are included in your custom schema that you created for your Web SDK implementation. (Any custom fields that aren't part of a default field group should have been added to your Web SDK schema as part of a custom field group.)

* The Adobe Analytics ExperienceEvent Template field group

To create the custom schema to use with the Analytics source connector:

1. In Adobe Experience Platform, begin creating a new custom schema as described in [Create a custom schema to use with your Customer Journey Analytics Web SDK implementation](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

1. Add all field groups (including any custom field groups) that are included in the schema that you created for your Web SDK implementation.

1. After you finish adding these field groups, add the Adobe Analytics ExperienceEvent field group: 

   In the **[!UICONTROL Field groups]** section, select **[!UICONTROL Add]** to add an additional field group. 

   ![Add field group to schema](assets/schema-add-field-group.png)

1. Search for and select the **[!UICONTROL Adobe Analytics ExperienceEvent Template]** field group.

   ![Add the Adobe Analytics ExperienceEvent field group](assets/schema-experienceevent.png)

1. Select **[!UICONTROL Add field groups]**.

1. Select **[!UICONTROL Save]** to save your schema.

1. {{upgrade-final-step}}
