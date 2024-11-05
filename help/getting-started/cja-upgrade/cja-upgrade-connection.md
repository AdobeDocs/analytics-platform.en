---
title: Create a schema for Customer Journey Analytics
description: Learn about the recommended path when upgrading from Adobe Analytics to Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: yes
hidefromtoc: yes
---
# Create and configure a connection to use with Customer Journey Analytics

>[!NOTE]
> 
>Follow the steps on this page only after you complete all previous upgrade steps. You can follow the [recommended upgrade steps](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations), or you can follow the upgrade steps that were dynamically generated for your organization with the [Adobe Analytics to Customer Journey Analytics upgrade questionnaire](https://gigazelle.github.io/cja-ttv/). 
>
>After you complete the steps on this page, continue following the recommended or dynamically generated upgrade steps.

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/connections/create-connection.md -->

The following information explains how to create and configure a connection, as well as how to add Experience Platform datasets to the connection you create. For additional information about creating and configuring a connection, see [Create or edit a connection](/help/connections/create-connection.md).

## Create and configure the connection {#create-connection}

1. In Customer Journey Analytics, select the **[!UICONTROL Connections]** tab.
1. Select **[!UICONTROL Create new connection]**.

    ![Untitled connection settings](assets/create-conn1.png)

1. Configure the connection settings.

    | Setting | Description |
    | --- | --- |
    | **[!UICONTROL Connection name]** | Enter a unique name for the connection. |
    | **[!UICONTROL Connection description]** | Describe the purpose of this connection. |
    | **[!UICONTROL Sandbox]** | Choose a sandbox in Experience Platform that contains the dataset/s to which you want to create a connection.<p>Adobe Experience Platform provides [sandboxes](https://experienceleague.adobe.com/en/docs/experience-platform/sandbox/home) which partition a single Platform instance into separate virtual environments to help develop and evolve digital experience applications. You can think of sandboxes as "data silos" that contain datasets. Sandboxes are used to control access to datasets.<p>Once you have selected the sandbox, the left rail shows all the datasets in that sandbox that you can pull from.  |
    | **[!UICONTROL Enable rolling data window]** | This checkbox, if checked, lets you define Customer Journey Analytics data retention as a rolling window in months (1 month, 3 months, 6 months, and so on), at the connection level.<p>Data retention is based on event dataset timestamps and applies to event datasets only. No rolling data window setting exists for profile or lookup datasets, since there are no applicable timestamps. However, if your connection includes any profile or lookup datasets (besides one or more event datasets), that data is retained for the same time period.<p> The main benefit is that you store or report only on data that is applicable and useful and delete older data that is no longer useful. It helps you stay under your contract limits and reduces the risk of overage cost.<p>If you leave the default (unchecked), the Adobe Experience Platform data retention setting supersedes the retention period. If you have 25 months' worth of data in Experience Platform, Customer Journey Analytics gets 25 months of data through backfill. If you deleted 10 of those months in Platform, Customer Journey Analytics would retain the remaining 15 months. |
    | **[!UICONTROL Add datasets]** (see below) | Add datasets if no datasets appear in your dataset listing. |
    | **[!UICONTROL Dataset name]** | Select one or more datasets that you want to pull into Customer Journey Analytics and select **[!UICONTROL Add]**.<p>(If you have many datasets to choose from, you can search for the right one(s) using the Search datasets search bar above the list of datasets.) |
    | **[!UICONTROL Last updated]** | For event datasets only, this setting is automatically set to the default timestamp field from event-based schemas in Experience Platform. "N/A" means that this dataset contains no data. |
    | **[!UICONTROL Number of records]** | The total records in the previous month for the dataset in Experience Platform. |
    | **[!UICONTROL Schema]** | The [schema](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition) based on which the dataset was created in Adobe Experience Platform. |
    | **[!UICONTROL Dataset type]** | For each dataset that you added to this connection, Customer Journey Analytics automatically sets the dataset type based on the data coming in. There are 3 different dataset types: Event data, Profile data, and Lookup data. See the table below for an explanation of dataset types. |
    | **[!UICONTROL Granularity]** | The granularity of the data in the dataset; only applicable for summary datasets. | 
    | **[!UICONTROL Data source type]** | The data source type of the dataset. Not applicable for summary datasets. |
    | **[!UICONTROL Person ID]** | Select a Person ID from the drop-down list of available identities. These identities were defined in the dataset schema in the Experience Platform. See below for information on how to use Identity Map as a Person ID.<p>IMPORTANT: If there are no Person IDs to choose from, that means one or more Person IDs have not been defined in the schema. View [this video](https://www.youtube.com/watch?v=G_ttmGl_LRU) on how to define an identity in Experience Platform. |
    | **[!UICONTROL Key]** | For lookup datasets only (such as _id). |
    | **[!UICONTROL Matching Key]** | For lookup datasets only (such as _id). |
    | **[!UICONTROL Import new data]** | Set to On or Off. |
    | **[!UICONTROL Backfill data]** | You can request to backfill the data in a dataset. For example, you can request to backfill the last 7 days worth of data. Configure the dataset correctly and test your connection. If everything looks good, you can backfill all the remaining data with ease.<p>In addition, you can enable the import of new data by dataset.  |
    | **[!UICONTROL Backfill status]** | This status indicates whether any backfill data is processing. |

    {style="table-layout:auto"}

## Add and configure datasets {#add-dataset}

You can add an Experience Platform dataset when you create a connection. 

1. In the Connection settings dialog, select **[!UICONTROL Add datasets]**.

1. In the [!UICONTROL Select datasets] step, you see a list of the Experience Platform datasets. 

   ![Select datasets](assets/select-datasets.png)

   For each dataset, the list shows:
   
   | Column | Description |
   |---|---|
   | Dataset | Name of the dataset. Select the name to direct you to the dataset in Experience Platform. Select ![Info](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) to display a popup with more details for the dataset. You can select **[!UICONTROL Edit in Platform]** to edit the dataset directly in Experience Platform. |
   | Dataset type | The type of dataset: Event, Profile, Lookup, or Summary. | 
   | Number of records | The total records in the previous month for the dataset in Experience Platform. |
   | Schema | The schema for the dataset. Select the name to direct you to the schema in Experience Platform. |
   | Last batch | The state of the last batch ingested in Experience Platform. See [Batch states](https://experienceleague.adobe.com/en/docs/experience-platform/ingestion/batch/troubleshooting#batch-states) more information. |
   | Dataset ID | The id of the dataset. | 
   | Last updated | The last updated timestamp of the dataset. | 

   
1. Select one or more datasets and select **[!UICONTROL Next]**. At least one event dataset must be part of the connection.
   * To change the columns displayed for the list of datasets, select ![Column settings](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg) and select the columns to be displayed in the [!UICONTROL Customize table] dialog.
   * To search for a specific dataset, use the ![Search](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) search field.
   * To toggle between showing or hiding the selected datasets, select ![Select](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SelectBoxAll_18_N.svg) **[!UICONTROL Hide selected]** or **[!UICONTROL Show selected]**.
   * To remove a dataset from the list of selected datasets, use ![Close](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Close_18_N.svg). To remove all selected datasets, select **[!UICONTROL Clear all]**.

    


1. Now, configure the datasets one by one.

    ![Configure datasets](assets/add-dataset.png)

    | Setting | Description |
    | --- | --- |
    | **[!UICONTROL Person ID]** | Only available for event and profile datasets. Select a Person ID from the drop-down list of available identities. These identities were defined in the dataset schema in the Experience Platform. See below for information on how to use Identity Map as a Person ID.<p>If there are no Person IDs to choose from, that means one or more Person IDs have not been defined in the schema. See [Define identity fields in the UI](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/ui/fields/identity) for more information. <p>The value for the selected Person ID is considered to be case sensitive. For example, `abc123` and `ABC123` are two different values. |
    | **[!UICONTROL Timestamp]** | For event and summary datasets only, this setting is automatically set to the default timestamp field from event-based schemas in Experience Platform. |
    | **[!UICONTROL Key]** | Only available for lookup datasets. The key to use for a Lookup dataset. |
    | **[!UICONTROL Matching key]** | Only available for lookup datasets. The matching key to join on in one of the event datasets. If this list is empty, you probably haven't added or configured an event dataset. |
    | **[!UICONTROL Timezone]** | Only available for summary data. Select the appropriate timezone for the time-series summary data. |
    | **[!UICONTROL Data source type]** | Select a type of data source. <br/>Types of data sources include: <ul><li>[!UICONTROL Web data]</li><li>[!UICONTROL Mobile App data]</li><li>[!UICONTROL POS data]</li><li>[!UICONTROL CRM data]</li><li>[!UICONTROL Survey data]</li><li>[!UICONTROL Call Center data]</li><li>[!UICONTROL Product data]</li><li> [!UICONTROL Accounts data]</li><li> [!UICONTROL Transaction data]</li><li>[!UICONTROL Customer Feedback data]</li><li> [!UICONTROL Other]</li></ul>This field is used to survey the types of data sources in use. |
    | **[!UICONTROL Import new data]** | Enable this option if you want to establish an ongoing connection. With an ongoing connection new data batches that are added to the datasets are available automatically in Workspace. |
    | **[!UICONTROL Dataset backfill]** | Enable **[!UICONTROL Backfill all existing data]** to ensure that all existing data is backfilled.<br/><br/>Select **[!UICONTROL Request backfill]** to backfill historical data for a specific period. You can define up to 10 dataset backfill periods.<ol><li>Define the period by entering start and end data or selecting dates using ![Calendar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg).</li><li>Select **[!UICONTROL Queue backfill]** to add the backfill to the list, or **[!UICONTROL Cancel]** to cancel.</li></ol>For each entry, select ![Edit](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) to edit the period, or select ![Delete](https://spectrum.adobe.com/static/icons/ui_18/CrossSize500.svg) to delete the entry.<br/><br/>On backfills:<ul><li>You can backfill each dataset individually.</li><li>You prioritize new data added to a dataset in the connection, so this new data has the lowest latency.</li><li>Any backfill (historical) data is imported at a slower rate. The amount of historical data influences the latency.</li><li>The Analytics source connector imports up to 13 months of data (irrespective of size) for production sandboxes. The backfill in non-production sandboxes is limited to 3 months.</li></ul> |
    | **[!UICONTROL Transform dataset]** | For specific B2B lookup datasets, you can enable the transformation of a dataset for proper B2B person-based reporting scenarios. |
    | **[!UICONTROL Backfill status]** | Possible status indicators are:<ul><li>Success</li><li>X backfill(s) processing</li><li>Off</li></ul> |
    | **[!UICONTROL Dataset ID]** | This ID is automatically generated. |
    | **[!UICONTROL Description]** | The description given to this dataset when it was created. |
    | **[!UICONTROL Dataset size]** | The dataset's size. |
    | **[!UICONTROL Schema]** | The schema based on which the dataset was created in Adobe Experience Platform. |
    | **[!UICONTROL Dataset]** | The name of the dataset. |
    | **[!UICONTROL Preview: *dataset name*]** | Previews the dataset with date, my ID, and Identifier columns. |
    | **[!UICONTROL Remove]** | You can delete or remove the dataset and change the Person ID without deleting the whole connection. Deleting or removing reduces the costs involved in data ingestion and the cumbersome process of recreating the whole connection and associated data views. |

    {style="table-layout:auto"}

1. Continue following the upgrade steps that were dynamically generated for your organization from the [Adobe Analytics to Customer Journey Analytics upgrade questionnaire](https://gigazelle.github.io/cja-ttv/).

