---
title: Add the Analytics source connector dataset to the connection
description: Learn how to add the Analytics source connector dataset to the connection
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 424485a3-a076-4656-83b6-733f16cc2326
---
# Add the Analytics source connector dataset to the connection {#upgrade-source-connector-dataset}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-dataset"
>title="Add the Analytics source connector dataset to your connection"
>abstract="Now that historical data from your Analytics report suite is in Adobe Experience Platform, add that dataset to your existing connection that you created when initially configuring Customer Journey Analytics. Once this step is complete, historical data in Customer Journey Analytics is available.<br><br>Adding a dataset to a connection in Customer Journey Analytics is straightforward, taking only a few minutes to complete."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}} 

## Understand how the Analytics source connector can bring historical data into Customer Journey Analytics

You can use the Analytics source connector to bring Adobe Analytics report suite data into Adobe Experience Platform. This data can then be used as historical data in Customer Journey Analytics.

This process assumes that you want to [create an XDM schema when upgrading to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md), because you want a streamlined schema that is tailored to the needs of your organization and the specific Platform applications that you use. 

To use the Analytics source connector to bring historical data into Customer Journey Analytics, you need to: 

1. [Create an XDM schema for the Analytics source connector](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)

1. If you don't already have an Analytics source connector, [create the Analytics source connector and map fields to your XDM schema](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md).

   Or

   If you already have an Analytics source connector, [map fields from the source connector to your XDM schema](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md).

1. Add the Analytics source connector dataset to the connection, as described below.

## Add the Analytics source connector dataset to the connection

After you [create an Analytics source connector for historical data](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md), a dataset is automatically created for the Analytics data. 

You need to add this automatically created dataset to the same connection that you created for your Web SDK implementation. Doing so brings the Analytics data into the same data view in Customer Journey Analytics as your Web SDK data. 

To add the automatically created dataset to the same connection that you created for your Web SDK implementation:

1. In Customer Journey Analytics,  select **[!UICONTROL Connections]**, optionally from **[!UICONTROL Data management]**, in the top menu.

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
   | **[!UICONTROL Person ID]** | Only available for event and profile datasets. Select a Person ID from the drop-down menu of available identities. These identities were defined in the dataset schema in the Experience Platform. See below for information on how to use Identity Map as a Person ID.<p>If there are no Person IDs to choose from, that means one or more Person IDs have not been defined in the schema. See [Define identity fields in the UI](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/ui/fields/identity) for more information. <p>The value for the selected Person ID is considered to be case sensitive. For example, `abc123` and `ABC123` are two different values. |
   | **[!UICONTROL Timestamp]** | For event and summary datasets only, this setting is automatically set to the default timestamp field from event-based schemas in Experience Platform. |
   | **[!UICONTROL Timezone]** | Only available for summary data. Select the appropriate timezone for the time-series summary data. |
   | **[!UICONTROL Data source type]** | Select a type of data source. <br/>Types of data sources include: <ul><li>[!UICONTROL Web data]</li><li>[!UICONTROL Mobile App data]</li><li>[!UICONTROL POS data]</li><li>[!UICONTROL CRM data]</li><li>[!UICONTROL Survey data]</li><li>[!UICONTROL Call Center data]</li><li>[!UICONTROL Product data]</li><li> [!UICONTROL Accounts data]</li><li> [!UICONTROL Transaction data]</li><li>[!UICONTROL Customer Feedback data]</li><li> [!UICONTROL Other]</li></ul>This field is used to survey the types of data sources in use. |

   {style="table-layout:auto"}

1. In the **[!UICONTROL Import new data]** section, leave the **[!UICONTROL Import all new data]** option disabled. 

   Because you are using the Analytics source connector dataset for historical data, you don't want to bring over future data that is collected into this dataset.

1. In the **[!UICONTROL Dataset backfill]** section, select **[!UICONTROL Request backfill]**. 

1. Define the period that you want the connection backfill into Customer Journey Analytics to include by entering the start and end dates or by selecting the the calendar icon ![Calendar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg).

   Be explicit when specifying the dates you request for backfill. Depending on several factors, you might want to do any of the following:
   
   * Choose an end date that is the same date as when you first started gathering data with your Web SDK implementation. 

   * Choose an end date that is shortly after the date when you first started gathering data with your Web SDK implementation, then use data view segments to segment out the overlapping data. 

   * Choose an end date that results in a greater overlap in data, then use data view segments to segment out the overlapping data.  
   
     **Note:** This option would result in increased costs because there would be more rows in the connection. 

   <!-- Include any of the following?  Make sure you're explicit as to the dates you request backfill to. You want to request it to the date that you start gathering data with your Web SDK implementation. Also possibly include segments for any overlapping date. So you could request everything and then use a segment to exclude data that you don't want. That way if you need to move up the date, then you could change the date in the segment. Downside would be that you might pay for double rows.  When they do that, they're going to see all schema fields from both their custom schema and their Analytics schema. So they'll need to be cognizant to select the right fields, and never select any Analytics fields, because they will be mapped as part of the source connector. Never select any Analytics field group fields because they'll be mapped.  -->

1. Select **[!UICONTROL Queue backfill]**.

1. Select **[!UICONTROL Add datasets]**, then select **[!UICONTROL Save]** to save the connection.

1. (Conditional) If you are using lookup datasets, you must create the lookup dataset and add it to your connection. For more information, see [Create lookup datasets to classify data in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md). 

   This is required only if you did not already do it when configuring your Web SDK implementation.

{{upgrade-final-step}}
