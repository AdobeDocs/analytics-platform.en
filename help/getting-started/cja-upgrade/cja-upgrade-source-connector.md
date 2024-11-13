---
title: Use the Analytics source connector for historical data
description: Learn how to use the Analytics source connector to bring historical data into Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: yes
hidefromtoc: yes
---
# Create the Analytics source connector for historical data

>[!NOTE]
> 
>Follow the steps on this page only after you complete all previous upgrade steps. You can follow the [recommended upgrade steps](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations), or you can follow the upgrade steps that were dynamically generated for your organization with the [Adobe Analytics to Customer Journey Analytics upgrade questionnaire](https://gigazelle.github.io/cja-ttv/). 
>
>After you complete the steps on this page, continue following the recommended upgrade steps or the dynamically generated upgrade steps. 

You can use the Analytics source connector to bring Adobe Analytics report suite data into Adobe Experience Platform. This data can then be used as historical data in Customer Journey Analytics.

The following steps assume that you want to [create an XDM schema when upgrading to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md), because you want a streamlined schema that is tailored to the needs of your organization and the specific Platform applications that you use. 

## Create an XDM schema that includes the Adobe Analytics field group

You should have already [created a new XDM schema](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md) for your Experience Platform Web SDK implementation to use with Customer Journey Analytics. This schema should contain any custom field groups for fields that you plan to collect data on. 

In addition to the XDM schema you already created for your Web SDK implementation, you now need to create a second XDM schema to use with the Analytics source connector to bring historical data into Customer Journey Analytics. 

This second schema needs to contain:

* Your custom schema for your organization (Need to turn your custom schema into 1 or more field groups. This is the same schema as they created for the Web SDK) -  Add all the same field groups that you added to your Web SDK schema. Add any custom fields to your own custom field group. 

* The Adobe Analytics ExperienceEvent field group

To create the XDM schema to use with the Analytics source connector:

1. In Adobe Experience Platform, begin creating a new XDM schema as described in [Create an XDM schema to use with Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

1. In the new schema, create a field for each Adobe Analytics variable included in your Adobe Analytics data layer. <!-- Not sure about this step -->  
   Use the data object in Adobe Experience Platform to send your Adobe Analytics data layer to the Edge Network. For more information, see [data](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/sendevent/data) in the Adobe Experience Platform documentation. <!-- Does this actually describe what they need to do??? -->

1. After you finish adding your Adobe Analytics variables, add the Adobe Analytics ExperienceEvent field group: 

   In the **[!UICONTROL Field groups]** section, select **[!UICONTROL Add]** to add an additional field group. 

   ![Add field group to schema](assets/schema-add-field-group.png)

1. Search for and select the **[!UICONTROL Adobe Analytics ExperienceEvent Template]** field group. <!-- Is this the correct field group? -->

   ![Add the Adobe Analytics ExperienceEvent field group](assets/schema-experienceevent.png)

1. Select **[!UICONTROL Add field groups]**.

1. Select **[!UICONTROL Save]** to save your schema.

1. Continue with the following section, [Create the source connector](#create-the-source-connector).

## Create the source connector

With your XDM schema created, you need to create the Adobe Analytics source connector to use for historical data. 

For more comprehensive, general guidelines on creating a source connector, see [Create an Adobe Analytics source connection in the UI](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html).

To create an Adobe Analytics source connector to use for historical data:

1. In the Platform UI, In the **[!UICONTROL Connections]** section in the left rail, select **[!UICONTROL Sources]**.

1. Select **[!UICONTROL Adobe applications]** from the list of [!UICONTROL CATEGORIES].

1. Select **[!UICONTROL Add data]** in the Adobe Analytics tile.

    ![Adobe Experience Platform window with Sources selected along with Adobe applications and Add data highlighted.](./assets/sources-overview.png)

1. Select **[!UICONTROL Report suite]**, then from the list of report suites, select the report suite that contains the historical data that you want to use in Customer Journey Analytics. 

    ![Adobe Experience Platform window showing the Report suites list](./assets/report-suites.png)

1. Select **[!UICONTROL Next]** in the upper-right corner of the screen.

1. Select **[!UICONTROL Custom schema]**, then select the schema that you created in the previous section, [Create an XDM schema that includes the Adobe Analytics field group](#create-a-second-xdm-schema-that-includes-the-adobe-analytics-field-group), as the [!UICONTROL Target schema]. <!-- Deleted this, because I changed this from choosing the default schemawe're pointing them now at the schema they just created: "Adobe Experience Platform  automatically creates the schema and the corresponding dataset to map all standard fields from the selected Adobe Analytics report suite." -->

    <!-- add screenshot -->

1. Select **[!UICONTROL Next]** in the upper-right corner of the screen.

1. Name the data flow and (optionally) provide a description.

    ![Adobe Experience Platform window highlighting the Dataflow detail section](./assets/dataflow-detail.png)

1. Select **[!UICONTROL Next]** in the upper-right corner of the screen.

1. Review the connection, then select **[!UICONTROL Finish]**.

    ![Adobe Experience Platform window highlighting the Connect and Data type sections for review](./assets/review.png)

1. Continue with the following section, [Map Adobe Analytics variables to custom fields in your XDM schema](#datastream-mapping).

<!-- What about this info? "After the connection is created, the dataflow is automatically created to populate a dataset with the Adobe Analytics data from your report suite. The dataflow ingests up to 13 months of historical data for production sandboxes. The backfill in non-production sandboxes is limited to three months.

When the initial ingestion completes, your Adobe Analytics report suite data is ready to be used by Customer Journey Analytics." -->


## Map Adobe Analytics variables to custom fields in your XDM schema {#datastream-mapping}

Use datastream mapping to map every field in the data object to be an entry in the datastream mapping tool that assigns it to a custom field in your XDM schema. 

After you create your new schema and create the Analytics source connector, you need to map the fields in your source data to that of the target event schema in Platform. To do this, use Data Prep in Adobe Experience Platform.


Mapping every Analytics dimension to a custom schema dimension. 

They will have to edit their Web SDK connection that they already set up, and add the midvalues dataset (The Analytics source connector. This is typically named _the name of the report suite_ with midvalues suffix.) They'll add Datasets to the Connection and select the midvalues dataset. Make sure you're explicit as to the dates you request backfill to. You want to request it to the date that you start gathering data with your Web SDK implementation. Also possibly include segments for any overlapping date. So you could request everything and then use a segment to exclude data that you don't want. That way if you need to move up the date, then you could change the date in the filter. Downside would be that you might pay for double rows.  When they do that, they're going to see all schema fields from both their custom schema and their Analytics schema. So they'll need to be cognizant to select the right fields, and never select any Analytics fields, because they will be mapped as part of the source connector. Never select any Analytics field group fields because they'll be mapped. 
