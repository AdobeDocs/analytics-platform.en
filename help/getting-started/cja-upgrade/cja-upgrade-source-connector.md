---
title: Use the Analytics source connector for historical data
description: Learn how to use the Analytics source connector to bring historical data into Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: yes
hidefromtoc: yes
---
# Use the Analytics source connector for historical data

>[!NOTE]
> 
>Follow the steps on this page only after you complete all previous upgrade steps. You can follow the [recommended upgrade steps](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations), or you can follow the upgrade steps that were dynamically generated for your organization with the [Adobe Analytics to Customer Journey Analytics upgrade questionnaire](https://gigazelle.github.io/cja-ttv/). 
>
>After you complete the steps on this page, continue following the recommended upgrade steps or the dynamically generated upgrade steps. 

You can use the Analytics source connector to bring Adobe Analytics report suite data into Adobe Experience Platform. This data can then be used as historical data in Customer Journey Analytics.

The following steps assume that you want to [create an XDM schema when upgrading to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md), because you want a streamlined schema that is tailored to the needs of your organization and the specific Platform applications that you use. Doing so means that when changes to the schema are required, you don't have to sift through thousands of unused fields to find the field that requires updating.

## Create a second XDM schema that includes the Adobe Analytics field group

You should have already [created a new XDM schema](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md) to use with Adobe Experience Platform and Customer Journey Analytics. This schema should contain any custom field groups for fields that you plan to collect data on. 

In addition to the XDM schema you already created, you now need to create a second schema to use with the Analytics source connector in bringing over historical data. 

This second schema needs to contain:

* All the fields that are included in the XDM schema that you previously created

* The Adobe Analytics ExperienceEvent field group

To create the XDM schema to use with the Analytics source connector:

1. Begin creating a new XDM schema, then add all of the same fields and field groups as the XDM schema that you created for your Web SDK implementation.

   Return to this page before saving your schema.

   For information about how to create a schema, see [Create an XDM schema to use with Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

1. While creating the schema, in the **[!UICONTROL Field groups]** section, select **[!UICONTROL Add]** to add an additional field group. 

   ![Add field group to schema](assets/schema-add-field-group.png)

1. Search for and select the **[!UICONTROL Adobe Analytics ExperienceEvent Full Extension]** field group.

   ![Add the Adobe Analytics ExperienceEvent field group](assets/schema-experienceevent.png)

1. Select **[!UICONTROL Add field groups]**.

1. Select **[!UICONTROL Save]** to save your schema.

1. Continue with the following section, [Create the source connector](#create-the-source-connector).

## Create the source connector

To create an Adobe Analytics source connector to use for historical data:

1. In the Platform UI, select **[!UICONTROL Sources]**, from the left rail.

2. Select **[!UICONTROL Adobe applications]** from the list of [!UICONTROL CATEGORIES].

3. Select **[!UICONTROL Set up]** or **[!UICONTROL Add data]** in the Adobe Analytics tile.

    ![Adobe Experience Platform window with Sources selected along with Adobe applications and Add data highlighted.](./assets/sources-overview.png)

4. Select **[!UICONTROL Report suite]**. From the list of report suites, select the one you want to use. 

    ![Adobe Experience Platform window showing the Report suites list](./assets/report-suites.png)

    Select **[!UICONTROL Next]**.

5. Select **[!UICONTROL Custom schema]**, then select the schema that you created in the previous section, [Create a second XDM schema that includes the Adobe Analytics field group](#create-a-second-xdm-schema-that-includes-the-adobe-analytics-field-group), as the [!UICONTROL Target schema]. <!-- Deleted this, because I changed this from choosing the default schemawe're pointing them now at the schema they just created: "Adobe Experience Platform  automatically creates the schema and the corresponding dataset to map all standard fields from the selected Adobe Analytics report suite." -->

    <!-- add screenshot -->

    Select **[!UICONTROL Next]**.

6. Name the data flow and (optionally) provide a description.

    ![Adobe Experience Platform window highlighting the Dataflow detail section](./assets/dataflow-detail.png)

    Select **[!UICONTROL Next]**.

7. Review the connection and select **[!UICONTROL Finish]**.

    ![Adobe Experience Platform window highlighting the Connect and Data type sections for review](./assets/review.png)


Once the connection is created, the dataflow is automatically created to populate a dataset with the Adobe Analytics data from your report suite. The dataflow ingests up to 13 months of historical data for production sandboxes. The backfill in non-production sandboxes is limited to three months.

When the initial ingestion completes, your Adobe Analytics report suite data is ready to be used by Customer Journey Analytics.

See [Create an Adobe Analytics source connection in the UI](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html) for a much more comprehensive tutorial.

## Map Adobe Analytics variables to custom fields in your XDM schema

Use datastream mapping to map every field in the data object be an entry in the datastream mapping tool that assigns it to a custom field in your XDM schema. 
