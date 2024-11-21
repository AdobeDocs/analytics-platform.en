---
title: Create the Analytics source connector and map fields
description: Learn how to create the Analytics source connector and map fields
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: yes
hidefromtoc: yes
exl-id: f96565a2-f556-4b45-b88e-984613614d2e
---
# Create the Analytics source connector and map fields

>[!NOTE]
> 
>Follow the steps on this page only after you complete all previous upgrade steps. You can follow the [recommended upgrade steps](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations), or you can follow the upgrade steps that were dynamically generated for your organization with the [Adobe Analytics to Customer Journey Analytics upgrade questionnaire](https://gigazelle.github.io/cja-ttv/). 
>
>After you complete the steps on this page, continue following the recommended upgrade steps or the dynamically generated upgrade steps. 

## Understand how the Analytics source connector can bring historical data into Customer Journey Analytics

You can use the Analytics source connector to bring Adobe Analytics report suite data into Adobe Experience Platform. This data can then be used as historical data in Customer Journey Analytics.

This process assumes that you want to [create an XDM schema when upgrading to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md), because you want a streamlined schema that is tailored to the needs of your organization and the specific Platform applications that you use. 

To use the Analytics source connector to bring historical data into Customer Journey Analytics, you need to: 

1. [Create an XDM schema for the Analytics source connector](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)

1. If you don't already have an Analytics source connector, create the Analytics source connector and map fields to your XDM schema, as described below.

   Or

   If you already have an Analytics source connector, [map fields from the source connector to your XDM schema](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md).

1. [Add the Analytics source connector dataset to the connection](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)

## Create the Analytics source connector and map fields

With your XDM schema created, you need to create the Adobe Analytics source connector to use for historical data. (For more comprehensive, general guidelines on creating a source connector, see [Create an Adobe Analytics source connection in the UI](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html).)

To create an Adobe Analytics source connector to use for historical data:

1. In the Platform UI, In the **[!UICONTROL Connections]** section in the left rail, select **[!UICONTROL Sources]**.

1. Select **[!UICONTROL Adobe applications]** from the list of [!UICONTROL CATEGORIES].

1. Select **[!UICONTROL Add data]** in the Adobe Analytics tile.

    ![Adobe Experience Platform window with Sources selected along with Adobe applications and Add data highlighted.](./assets/sources-overview.png)

1. Select **[!UICONTROL Report suite]**, then from the list of report suites, select the report suite that contains the historical data that you want to use in Customer Journey Analytics. 

    ![Adobe Experience Platform window showing the Report suites list](./assets/report-suites.png)

1. Select **[!UICONTROL Next]** in the upper-right corner of the screen.

1. Select **[!UICONTROL Custom schema]**, then select the schema that you created in [Create an XDM schema that includes the Adobe Analytics field group](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md). <!-- Deleted this, because I changed this from choosing the default schemawe're pointing them now at the schema they just created: "Adobe Experience Platform  automatically creates the schema and the corresponding dataset to map all standard fields from the selected Adobe Analytics report suite." -->

    <!-- add screenshot -->

1. Map each Adobe Analytics dimension to a custom XDM schema dimension. 

   1. In the **[!UICONTROL Map standard fields]** section, select the **[!UICONTROL Custom]** tab.

   1. Select **[!UICONTROL Add new mapping]**. 

   ![map schema fields](assets/schema-mapping.png)

   1. In the **[!UICONTROL Source field]**, select an Adobe Analytics field from the Adobe Analytics ExperienceEvent Template field group. Then, in the **[!UICONTROL Target field]**, select the XDM field that you want to map it to. 

   1. Repeat this process for each field in the Adobe Analytics ExperienceEvent Template field group that you are using to collect data in Adobe Analytics.

1. Select **[!UICONTROL Next]** in the upper-right corner of the screen.

1. Name the data flow and (optionally) provide a description.

    ![Adobe Experience Platform window highlighting the Dataflow detail section](./assets/dataflow-detail.png)

1. Select **[!UICONTROL Next]** in the upper-right corner of the screen.

1. Review the connection, then select **[!UICONTROL Finish]**.

   ![Adobe Experience Platform window highlighting the Connect and Data type sections for review](./assets/review.png)

   After the connection is created, the dataflow is automatically created to populate a dataset with the Adobe Analytics data from your report suite. The dataflow ingests up to 13 months of historical data for production sandboxes. The backfill in non-production sandboxes is limited to three months.

   If you are using the Analytics source connector to bring historical data into your Customer Journey Analytics Web SDK implementation, then you need to add this automatically created dataset to the connection that you created for your Web SDK implementation.

1. Continue following the [recommended upgrade steps](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) or the [dynamically generated upgrade steps](https://gigazelle.github.io/cja-ttv/).
