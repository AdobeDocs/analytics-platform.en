---
title: Add the Analytics source connector dataset to the connection
description: Learn how to add the Analytics source connector dataset to the connection
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: yes
hidefromtoc: yes
exl-id: 424485a3-a076-4656-83b6-733f16cc2326
---
# Add the Analytics source connector dataset to the connection

>[!NOTE]
> 
>Follow the steps on this page only after you complete all previous upgrade steps. You can follow the [recommended upgrade steps](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations), or you can follow the upgrade steps that were dynamically generated for your organization with the [Adobe Analytics to Customer Journey Analytics upgrade questionnaire](https://gigazelle.github.io/cja-ttv/). 
>
>After you complete the steps on this page, continue following the recommended upgrade steps or the dynamically generated upgrade steps. 

>[!NOTE]
>
>The information on this page assumes the following:
>
>* You are upgrading from Adobe Analytics to Customer Journey Analytics.
>* You are using the Web SDK for your future Customer Journey Analytics data collection.
>* You want to use the Analytics source connector to bring your historical Adobe analytics data into Customer Journey Analytics. 

## Understand how the Analytics source connector can bring historical data into Customer Journey Analytics

You can use the Analytics source connector to bring Adobe Analytics report suite data into Adobe Experience Platform. This data can then be used as historical data in Customer Journey Analytics.

This process assumes that you want to [create an XDM schema when upgrading to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md), because you want a streamlined schema that is tailored to the needs of your organization and the specific Platform applications that you use. 

To use the Analytics source connector to bring historical data into Customer Journey Analytics, you need to: 

1. [Create an XDM schema for the Analytics source connector](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)

1. [Create the Analytics source connector and map fields](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md)

1. Add the Analytics source connector dataset to the connection, as described below.

## Add the Analytics source connector dataset to the connection

After you [create an Analytics source connector for historical data](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md), a dataset is automatically created for the Analytics data. 

You need to add this automatically created dataset to the same connection that you created for your Web SDK implementation. Doing so brings the Analytics data into the same data view in Customer Journey Analytics as your Web SDK data. 

To add the automatically created dataset to the same connection that you created for your Web SDK implementation:

1. In Customer Journey Analytics, select the **[!UICONTROL Connections]** tab.

1. Select the connection that you [created for your Web SDK implementation](/help/getting-started/cja-upgrade/cja-upgrade-connection.md).

1. Select **[!UICONTROL Edit]**.

   ![Edit connection](assets/connection-add-dataset.png)

1. Select **[!UICONTROL Add datasets]** in the upper-right.

   ![Edit connection](assets/connection-add-dateset2.png)

1. Scroll to or search for the dataset that was automatically created when you created the Analytics source connector. 

   The name of this dataset is the name of your report suite, followed by `midValues`. For example: `My report suite midValues`

1. Select the checkbox next to the dataset name, then select **[!UICONTROL Next]**.

   ![Edit connection](assets/connection-add-dataset3.png)

1. Specify the following information:

   <!-- Copied from help/connections/create-connection.md. Should we single source? -->

   | Setting | Description |
   | --- | --- |
   | **[!UICONTROL Person ID]** | Only available for event and profile datasets. Select a Person ID from the drop-down list of available identities. These identities were defined in the dataset schema in the Experience Platform. See below for information on how to use Identity Map as a Person ID.<p>If there are no Person IDs to choose from, that means one or more Person IDs have not been defined in the schema. See [Define identity fields in the UI](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/ui/fields/identity) for more information. <p>The value for the selected Person ID is considered to be case sensitive. For example, `abc123` and `ABC123` are two different values. |
   | **[!UICONTROL Timestamp]** | For event and summary datasets only, this setting is automatically set to the default timestamp field from event-based schemas in Experience Platform. |
   | **[!UICONTROL Timezone]** | Only available for summary data. Select the appropriate timezone for the time-series summary data. |
   | **[!UICONTROL Data source type]** | Select a type of data source. <br/>Types of data sources include: <ul><li>[!UICONTROL Web data]</li><li>[!UICONTROL Mobile App data]</li><li>[!UICONTROL POS data]</li><li>[!UICONTROL CRM data]</li><li>[!UICONTROL Survey data]</li><li>[!UICONTROL Call Center data]</li><li>[!UICONTROL Product data]</li><li> [!UICONTROL Accounts data]</li><li> [!UICONTROL Transaction data]</li><li>[!UICONTROL Customer Feedback data]</li><li> [!UICONTROL Other]</li></ul>This field is used to survey the types of data sources in use. |

   {style="table-layout:auto"}

1. In the **[!UICONTROL Import new data]** section, leave the **[!UICONTROL Import all new data]** option disabled. 

   Because you are using the Analytics source connector dataset for historical data, you don't want to bring over future data that is collected into this dataset.

1. In the **[!UICONTROL Dataset backfill]** section, select **[!UICONTROL Request backfill]**. 

1. Define the period that you want the backfill to include by entering the start and end dates or by selecting the the calendar icon ![Calendar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg). 

   The Analytics source connector imports 13 months of data (irrespective of size) for production sandboxes. The backfill in non-production sandboxes is 3 months.

   >[!IMPORTANT]
   >
   >Be explicit when specifying the dates you request for backfill. The end date should be the date when you first started gathering data with your Web SDK implementation. 
   >
   >Alternatively, you can choose a date shortly after the date when you first started gathering data with your Web SDK implementation, then use segments to filter out the overlapping data. 

   <!-- Include any of the following?  Make sure you're explicit as to the dates you request backfill to. You want to request it to the date that you start gathering data with your Web SDK implementation. Also possibly include segments for any overlapping date. So you could request everything and then use a segment to exclude data that you don't want. That way if you need to move up the date, then you could change the date in the filter. Downside would be that you might pay for double rows.  When they do that, they're going to see all schema fields from both their custom schema and their Analytics schema. So they'll need to be cognizant to select the right fields, and never select any Analytics fields, because they will be mapped as part of the source connector. Never select any Analytics field group fields because they'll be mapped.  -->

1. Select **[!UICONTROL Queue backfill]**.

1. Select **[!UICONTROL Add datasets]**, then select **[!UICONTROL Save]** to save the connection.

1. Continue following the [recommended upgrade steps](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) or the [dynamically generated upgrade steps](https://gigazelle.github.io/cja-ttv/).
