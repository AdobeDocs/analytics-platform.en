---
title: Add the Analytics source connector dataset to the connection
description: Learn how to add the Analytics source connector dataset to the connection
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: yes
hidefromtoc: yes
---
# Add the Analytics source connector dataset to the connection

>[!NOTE]
> 
>Follow the steps on this page only after you complete all previous upgrade steps. You can follow the [recommended upgrade steps](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations), or you can follow the upgrade steps that were dynamically generated for your organization with the [Adobe Analytics to Customer Journey Analytics upgrade questionnaire](https://gigazelle.github.io/cja-ttv/). 
>
>After you complete the steps on this page, continue following the recommended upgrade steps or the dynamically generated upgrade steps. 

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

   >[!IMPORTANT]
   >
   >    Be explicit as to the dates you request for backfill. The end date should be the date when you first started gathering data with your Web SDK implementation. 
   >
   >Alternatively, you can choose a date shortly after the date when you first started gathering data with your Web SDK implementation, then use segments to filter out the overlapping data. 



   | **[!UICONTROL Dataset backfill]** | Enable **[!UICONTROL Backfill all existing data]** to ensure that all existing data is backfilled.<br/><br/>Select **[!UICONTROL Request backfill]** to backfill historical data for a specific period. You can define up to 10 dataset backfill periods.<ol><li>Define the period by entering start and end data or selecting dates using ![Calendar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg).</li><li>Select **[!UICONTROL Queue backfill]** to add the backfill to the list, or **[!UICONTROL Cancel]** to cancel.</li></ol>For each entry, select ![Edit](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) to edit the period, or select ![Delete](https://spectrum.adobe.com/static/icons/ui_18/CrossSize500.svg) to delete the entry.<br/><br/>On backfills:<ul><li>You can backfill each dataset individually.</li><li>You prioritize new data added to a dataset in the connection, so this new data has the lowest latency.</li><li>Any backfill (historical) data is imported at a slower rate. The amount of historical data influences the latency.</li><li>The Analytics source connector imports up to 13 months of data (irrespective of size) for production sandboxes. The backfill in non-production sandboxes is limited to 3 months.</li></ul> |
   | **[!UICONTROL Transform dataset]** | For specific B2B lookup datasets, you can enable the transformation of a dataset for proper B2B person-based reporting scenarios. See [Transform datasets for B2B lookups](transform-datasets-b2b-lookups.md) for more information. |
   | **[!UICONTROL Backfill status]** | Possible status indicators are:<ul><li>Success</li><li>X backfill(s) processing</li><li>Off</li></ul> |
   | **[!UICONTROL Dataset ID]** | This ID is automatically generated. |
   | **[!UICONTROL Description]** | The description given to this dataset when it was created. |
   | **[!UICONTROL Dataset size]** | The dataset's size. |
   | **[!UICONTROL Schema]** | The schema based on which the dataset was created in Adobe Experience Platform. |
   | **[!UICONTROL Dataset]** | The name of the dataset. |
   | **[!UICONTROL Preview: *dataset name*]** | Previews the dataset with date, my ID, and Identifier columns. |
   | **[!UICONTROL Remove]** | You can delete or remove the dataset and change the Person ID without deleting the whole connection. Deleting or removing reduces the costs involved in data ingestion and the cumbersome process of recreating the whole connection and associated data views. |
   
   {style="table-layout:auto"}

1. They will have to edit their Web SDK connection that they already set up, and add the midvalues dataset (The Analytics source connector. This is typically named _the name of the report suite_ with midvalues suffix.) They'll add Datasets to the Connection and select the midvalues dataset. Make sure you're explicit as to the dates you request backfill to. You want to request it to the date that you start gathering data with your Web SDK implementation. Also possibly include segments for any overlapping date. So you could request everything and then use a segment to exclude data that you don't want. That way if you need to move up the date, then you could change the date in the filter. Downside would be that you might pay for double rows.  When they do that, they're going to see all schema fields from both their custom schema and their Analytics schema. So they'll need to be cognizant to select the right fields, and never select any Analytics fields, because they will be mapped as part of the source connector. Never select any Analytics field group fields because they'll be mapped. 

1. Continue following the [recommended upgrade steps](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) or the [dynamically generated upgrade steps](https://gigazelle.github.io/cja-ttv/).

