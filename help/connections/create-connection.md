---
title: Create or edit a connection
description: Describes how to create or edit a connection to an Experience Platform dataset in Customer Journey Analytics.
exl-id: b4ac37ca-213b-4118-85e1-8e8f98553c6c
solution: Customer Journey Analytics
feature: Connections
role: Admin
---
# Create or edit a connection {#create-or-edit-a-connection}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_recordsadded"
>title="Records added"
>abstract="The number of records (rows) added to a Connection during the selected time interval for the selected datasets."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_recordsskipped"
>title="Records skipped"
>abstract="The number of records (rows) skipped during data transfer for a Connection during the selected time interval for the selected datasets."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_recordsdeleted"
>title="Records deleted"
>abstract="The number of records (rows) removed from a Connection during the selected time interval for the selected datasets"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_lastadded"
>title="Last added"
>abstract="The timestamp of the latest batch from any dataset transferred to a Connection."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_enablerollingdatawindow"
>title="Enable rolling data window"
>abstract="Define data retention as a rolling window in months at a connection level."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_averagenumberofdailyuses"
>title="Average number of daily uses"
>abstract="Select a range for the number of expected daily events for the entire connection."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_recordsadded"
>title="Records added"
>abstract="The number of records (rows) added to a Connection during the selected time interval for the selected datasets."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_recordsskipped"
>title="Records skipped"
>abstract="The number of records (rows) skipped during data transfer for a Connection during the selected time interval for the selected datasets."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_recordsdeleted"
>title="Records deleted"
>abstract="The number of records (rows) removed from a Connection during the selected time interval for the selected datasets"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_lastadded"
>title="Last added"
>abstract="The timestamp of the latest batch from any dataset transferred to a Connection."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_enablerollingdatawindow"
>title="Enable rolling data window"
>abstract="Define data retention as a rolling window in months at a connection level."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_averagenumberofdailyuses"
>title="Average number of daily uses"
>abstract="Select a range for the number of expected daily events for the entire connection."

<!-- markdownlint-enable MD034 -->


The connection creation and edit workflow experience brings all the dataset and connection configuration settings to the center of the screen with an assistive workflow. It provides detailed dataset selection, configuration, and review experience. And allows you to specify critical information like dataset type, size, schema, dataset id, batch status, backfill status, Person IDs, and much more, to reduce the risk of wrong connection configuration. Here is an overview of the capabilities:

* You can enable a rolling data retention window when you create the connection.
* You can add to and remove datasets from a connection. (Removing a dataset removes it from the connection and impacts any associated data views and underlying Analysis Workspace projects.)
* You can enable and request backfill data per dataset.
* You can edit datasets, for example to request another backfill.
* You can import existing data per dataset.


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Create and edit a connection](https://video.tv.adobe.com/v/343044/?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]


## Prerequisites

The maximum number of datasets you can add to a connection is capped at 100. The mix depends on which Customer Journey Analytics package your company has purchased. 

Contact your administrator if you're unsure which Customer Journey Analytics package you have.

| **Select** package | **Foundation** package |
| --- | --- |
| Any combination of event/profile/lookup/summary datasets, adding up to 100  | One event dataset per connection | 
|  | Up to 99 profile, lookup, or summary datasets per connection  |

{style="table-layout:auto"}

## Create and configure the connection {#create-connection}

1. In Customer Journey Analytics, select **[!UICONTROL Connections]** from the main menu.
1. Select **[!UICONTROL Create new connection]**.

>[!BEGINTABS]

>[!TAB Standard] 

![Untitled connection settings](assets/create-conn1.png)

>[!TAB B2B Edition]

![Untitled connection settings](assets/create-conn1-b2b.png)

>[!ENDTABS]

In the **[!UICONTROL Connections]** > **[!UICONTROL Untitled connection]** screen:

1. Configure the connection settings.

    | Setting | Description |
    | --- | --- |
    | **[!UICONTROL Connection name]** | Enter a unique name for the connection. |
    | **[!UICONTROL Connection description]** | Describe the purpose of this connection. |
    | [!BADGE B2B Edition]{type=Informative} **[!UICONTROL Primary ID]** | Select the proper primary ID for your connection: <ul><li>![User](/help/assets/icons/User.svg) **[!UICONTROL Person]** for a B2C scenario</li><li> ![Building](/help/assets/icons/Building.svg) **[!UICONTROL Account]** for a B2B scenario.</li></ul> |
    | [!BADGE B2B Edition]{type=Informative} **[!UICONTROL Optional containers]** | Select additional containers.<ul><li>**[!UICONTROL Global account]**: enables configuration of global accounts in a connection.</li><li>**[!UICONTROL Opportunity]**: enables configuration of opportunities in a connection.</li><li>**[!UICONTROL Buying group]**: enables configuration of buying groups in a connection.</li><ul> |
    | **[!UICONTROL Sandbox]** | Choose a sandbox in Experience Platform that contains the dataset/s to which you want to create a connection.<p>Adobe Experience Platform provides [sandboxes](https://experienceleague.adobe.com/en/docs/experience-platform/sandbox/home) which partition a single Platform instance into separate virtual environments to help develop and evolve digital experience applications. You can think of sandboxes as "data silos" that contain datasets. Sandboxes are used to control access to datasets.<p>Once you have selected the sandbox, the left rail shows all the datasets in that sandbox that you can pull from.  |
    | **[!UICONTROL Enable rolling data window]** | This checkbox, if checked, lets you define Customer Journey Analytics data retention as a rolling window in months (1 month, 3 months, 6 months, and so on), at the connection level.<p>Data retention is based on event dataset timestamps and applies to event datasets only. No rolling data window setting exists for profile or lookup datasets, since there are no applicable timestamps. However, if your connection includes any profile or lookup datasets (besides one or more event datasets), that data is retained for the same time period.<p> The main benefit is that you store or report only on data that is applicable and useful and delete older data that is no longer useful. It helps you stay under your contract limits and reduces the risk of overage cost.<p>If you leave the default (unchecked), the Adobe Experience Platform data retention setting supersedes the retention period. If you have 25 months' worth of data in Experience Platform, Customer Journey Analytics gets 25 months of data through backfill. If you deleted 10 of those months in Platform, Customer Journey Analytics would retain the remaining 15 months. |
    | **[!UICONTROL Add datasets]** (see below) | Add datasets if no datasets appear in your dataset table. Otherwise you will see a list of the datasets you already added as part of the creation of the connection. |


    For the datasets you have configured, the table of datasets shows the following columns:

    | Column | Description |
    |---|---|
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

    You can search for a specific dataset using the ![Search](/help/assets/icons/Search.svg) field.


## Add and configure datasets {#add-dataset}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_primaryid"
>title="Primary ID"
>abstract="Select the proper primary ID for your connection: Person for a B2C scenario. Account for a B2B scenario."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_optionalcontainers"
>title="Optional containers"
>abstract="Select additional containers.<br/><br/>**[!UICONTROL Global account]**: enables configuration of global accounts in a connection.<br/>**[!UICONTROL Opportunity]**: enables configuration of opportunities in a connection.<br/>**[!UICONTROL Buying group]**: enables configuration of buying groups in a connection."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_personid"
>title="Person ID"
>abstract="Select a person ID from the available identities defined in the dataset schema in the Experience Platform."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_accountid"
>title="Account ID"
>abstract="Select an account ID (the unique identifier for an account) from the available identities defined in the dataset schema in the Experience Platform."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_accountfield"
>title="Account field"
>abstract="Select a field that represents the account ID (the unique identifier for an account)."

<!-- markdownlint-enable MD034 -->


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_globalaccountid"
>title="Global account ID"
>abstract="Select a global account ID (the unique identifier for a global account) from the available identities defined in the dataset schema in the Experience Platform."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_opportunityid"
>title="Opportunity ID"
>abstract="Select an opportunity ID (the unique identifier for an opportunity) from the available identities defined in the dataset schema in the Experience Platform."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_buyinggroupid"
>title="Buying group ID"
>abstract="Select a buying group ID (the unique identifier for a buying group) from the available identities defined in the dataset schema in the Experience Platform."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_matchingkey"
>title="Matching key"
>abstract="Select how to join: based on a matching key or a matching container.<br/><br/>**[!UICONTROL Matching key]**: Select a field to join on with one of the event datasets. If this list is empty you probably haven't added or configured an event dataset.<br/>**[!UICONTROL Matching container]**: Select a container to use to join with one of the event datasets. If this list is empty you probably haven't configured one or more containers."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_importnewdata"
>title="Import new data"
>abstract="Any new batches that get added in the Experience Platform dataset will automatically be added in this connection and made available for analysis."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_datasetbackfill"
>title="Dataset backfill"
>abstract="This option will backfill the existing (historical) data from Experience Platform for this dataset in the connection."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_transformdataset"
>title="Transform dataset"
>abstract="This option will transform the dataset so it can be used for person-based lookups in B2B scenarios. Once turned on, the transformation of the dataset is irreversible."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_connectionmap"
>title="Connection map"
>abstract="The Connection map visualizes the relationships between event, person, account and relevant lookup datasets (like opportunities, campaign members, and more)."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_primaryid"
>title="Primary ID"
>abstract="Select the proper primary ID for your connection: Person for a B2C scenario. Account for a B2B scenario."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_optionalcontainers"
>title="Optional containers"
>abstract="Select additional containers.<br/><br/>**[!UICONTROL Global account]**: enables configuration of global accounts in a connection.<br/>**[!UICONTROL Opportunity]**: enables configuration of opportunities in a connection.<br/>**[!UICONTROL Buying group]**: enables configuration of buying groups in a connection."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_personid"
>title="Person ID"
>abstract="Select a person ID from the available identities defined in the dataset schema in the Experience Platform."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_accountid"
>title="Account ID"
>abstract="Select an account ID (the unique identifier for an account) from the available identities defined in the dataset schema in the Experience Platform."

<!-- markdownlint-enable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_accountfield"
>title="Account field"
>abstract="Select a field that represents the account ID (the unique identifier for an account)."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_globalaccountid"
>title="Global account ID"
>abstract="Select a global account ID (the unique identifier for a global account) from the available identities defined in the dataset schema in the Experience Platform."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_opportunityid"
>title="Opportunity ID"
>abstract="Select an opportunity ID (the unique identifier for an opportunity) from the available identities defined in the dataset schema in the Experience Platform."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_buyinggroupid"
>title="Buying group ID"
>abstract="Select a buying group ID (the unique identifier for a buying group) from the available identities defined in the dataset schema in the Experience Platform."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_matchingkey"
>title="Matching key"
>abstract="Select how to join: based on a matching key or a matching container.<br/><br/>**[!UICONTROL Matching key]**: Select a field to join on with one of the event datasets. If this list is empty you probably haven't added or configured an event dataset.<br/>**[!UICONTROL Matching container]**: Select a container to use to join with one of the event datasets. If this list is empty you probably haven't configured one or more containers."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_importnewdata"
>title="Import new data"
>abstract="Any new batches that get added in the Experience Platform dataset will automatically be added in this connection and made available for analysis."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_datasetbackfill"
>title="Dataset backfill"
>abstract="This option will backfill the existing (historical) data from Experience Platform for this dataset in the connection."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_transformdataset"
>title="Transform dataset"
>abstract="This option will transform the dataset so it can be used for person-based lookups in B2B scenarios. Once turned on, the transformation of the dataset is irreversible."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_connectionmap"
>title="Connection map"
>abstract="The Connection map visualizes the relationships between event, person, account and relevant lookup datasets (like opportunities, campaign members, and more)."

<!-- markdownlint-enable MD034 -->


The new workflow lets you add an Experience Platform dataset when you create a connection. 

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

## Connection preview {#preview}

To preview the connection that you have created, select **[!UICONTROL Connection preview]** in the Connection settings dialog.

![Connection preview](assets/create-conn4.png)

This preview contains some columns listing the connection configuration. What column types are shown depends on your individual datasets.

## Dataset types {#dataset-types}

For each dataset that you add to this connection, [!UICONTROL Customer Journey Analytics] automatically sets the dataset type based on the data coming in. 

>[!IMPORTANT]
>
>Add at least one event or summary dataset as part of a connection.

There are different dataset types: [!UICONTROL Event] data, [!UICONTROL Profile] data, [!UICONTROL Lookup] data and [!UICONTROL Summary] data.

|Dataset Type|Description|Timestamp|Schema|Person ID|
|---|---|---|---|---|
| **[!UICONTROL Event]** | Data that represents events in time. For example, web visits, interactions, transactions, POS data, survey data, ad impression data, and so on. This data could be typical clickstream data, with a customer ID or a Cookie ID, and a timestamp. With event data, you have flexibility as to which ID is used as the Person ID. | Automatically set to the default timestamp field from event-based schemas in [!UICONTROL Experience Platform]. | Any built-in or custom schema that is based on an XDM class with the "Time Series" behavior. Examples include "XDM Experience Event" or "XDM Decision Event." | You can pick which Person ID you want to include. Each dataset schema defined in the Experience Platform can have its own set of one or more identities defined and associated with an Identity Namespace. Any of these identities can be used as the Person ID. Examples include Cookie ID, Stitched ID, User ID, Tracking Code, and so on. |
| **[!UICONTROL Lookup]** | You can add datasets as lookups of fields within all dataset types: Profile, Lookup, and Event datasets (the latter was always supported). This additional capability expands the capability of Customer Journey Analytics to support complex data models, including B2B. This data is used to look up values or keys found in your Event, Profile, or Lookup data. You can add up to two levels of lookups. (Note that [Derived Fields](/help/data-views/derived-fields/derived-fields.md) cannot be used as matching keys for lookups within Connections.) For example, you might upload lookup data that maps numeric IDs in your event data to product names. See the [B2B example](/help/use-cases/b2b/example.md) for an example. | N/A | Any built-in or custom schema that is based on an XDM class with the "Record" behavior, except for the "XDM Individual Profile" class. | N/A |
| **[!UICONTROL Profile]** | Data that is applied to your persons, users, or customers in the [!UICONTROL Event] data. For example, allows you to upload CRM data about your customers. | N/A | Any built-in or custom schema that is based on the "XDM Individual Profile" class. | You can pick which Person ID you want to include. Each dataset (except summary datasets), defined in [!DNL Experience Platform], has its own set of one or more Person IDs defined. For example, Cookie ID, Stitched ID, User ID, Tracking Code, and so on.<br>![Person ID](assets/person-id.png)**Note**: If you create a connection that includes datasets with different IDs, the reporting reflects that. To merge datasets, you need to use the same Person ID. |
| **Summary** | Time-series data that is not tied to an individual Person ID. Summary data represents aggregated data at a different level of aggregation, for example campaigns. You can use this data in Customer Journey Analytics to support various use cases. See [Summary data](/help/data-views/summary-data.md) for more information. | Automatically set to the default timestamp field from event-based summary metrics schemas in Experience Platform. Only hourly or daily granularity is supported. | Any built-in or custom schema that is based on the "XDM Summary Metrics" class. | N/A |

>[!MORELIKETHIS]
>
>Blog: [How to Leverage Event, Lookup, and Profile Datasets in Adobe Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/how-to-leverage-event-lookup-and-profile-datasets-in-adobe/ba-p/681478)

## Use numeric fields as lookup keys and lookup values {#numeric}

This lookup functionality is useful if you want to add a numeric field such as a cost or margin to a string-based key field. It allows numeric values to be part of lookups, either as keys or as values. In your lookup schema, you might have numeric values tied to, for example, your product names, COGS, campaign marketing cost, or margins. Here is an example lookup schema in Adobe Experience Platform:

![Lookup schema](assets/schema.png)

You now support bringing in these values as metrics or dimensions into Customer Journey Analytics reporting. When you set up your connection and pull in lookup datasets, you can edit the datasets to select the [!UICONTROL Key] and [!UICONTROL Matching Key]:

![Edit-dataset](assets/lookup-dataset.png)

When you set up a data view based on this connection, you add the numeric values as components to the data view. Any project based on this data view can then report on these numeric values.

## Use Identity Map as a Person ID {#id-map}

Customer Journey Analytics supports the ability to use the Identity Map for its Person ID. Identity Map is a map data structure that allows you to upload key -> value pairs. The keys are identity namespaces and the value is a structure that holds the identity value. The Identity Map exists on each row/event uploaded and is populated for each row accordingly.

The Identity Map is available for any dataset that uses a schema based on the [ExperienceEvent XDM](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home) class. When you select such a dataset to be included in a Customer Journey Analytics Connection, you have the option of selecting either a field as the primary ID or the Identity Map:

![](assets/idmap1.png)

If you select Identity Map, you get two additional configuration options:

|Option|Description|
|---|---|
| **[!UICONTROL Use Primary ID Namespace]** | This option instructs Customer Journey Analytics to find the identity in the Identity Map that is marked with a `primary=true` attribute and use that identity as the Person ID for that row. This identity is the primary key that is used in Experience Platform for partitioning. And this identity is also the prime candidate for usage as Customer Journey Analytics Person ID (depending on how the dataset is configured in a Customer Journey Analytics Connection).|
| **[!UICONTROL Namespace]**| (This option is only available if you do not use the Primary ID Namespace.) Identity namespaces are a component of the [Experience Platform Identity Service](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/namespaces). Namespaces serve as indicators of the context to which an identity relates. If you specify a namespace, Customer Journey Analytics searches each row's Identity Map for this namespace key and use the identity under that namespace as the Person ID for that row. Since Customer Journey Analytics cannot do a full dataset scan of all rows to determine which namespaces are present, all possible namespaces are displayed in the drop-down list. Know which namespaces are specified in the data; these namespaces are not auto-detected. |

{style="table-layout:auto"}

### Identity Map edge cases {#id-map-edge}

This table shows the two configuration options when edge cases are present and how they are handled:

| Option | No IDs are present in the Identity Map | Multiple IDs, none marked as primary | Multiple IDs are marked as primary | Single ID, marked as primary or not | Invalid namespace with an ID marked as primary |
|---|---|---|---|---|---|
| **[!UICONTROL Use Primary ID Namespace] checked** | Customer Journey Analytics drops the row. | Customer Journey Analytics drops the row, as no primary ID is specified. | All IDs marked as primary, under all namespaces, are extracted into a list. They are then alphabetically sorted; with the new sorting, the first namespace with its first ID is used as the Person ID. | The single ID is used as the Person ID. | Even though the namespace may be invalid (not present in Adobe Experience Platform), Customer Journey Analytics uses the primary ID under that namespace as the Person ID. |
| **[!UICONTROL Specific Identity Map namespace] selected** | Customer Journey Analytics drops the row. | All IDs under the selected namespace are extracted into a list and the first is used as the Person ID. | All IDs under the selected namespace are extracted into a list and the first is used as the Person ID. | All IDs under the selected namespace are extracted into a list and the first is used as the Person ID. | All IDs under the selected namespace are extracted into a list and the first is used as the Person ID. (Only a valid namespace can be selected at Connection creation time, so it is not possible for an invalid namespace/ID to be used as Person ID) |

{style="table-layout:auto"}

## Calculate the average number of daily events {#average-number}

This calculation is done for every dataset in the connection.

1. Go to [Adobe Experience Platform Query Services](https://experienceleague.adobe.com/en/docs/experience-platform/query/home) and create a query.

    The query would look like this:
    
    ```
    Select AVG(A.total_events) from (Select DISTINCT COUNT (*) as total_events, date(TIMESTAMP) from analytics_demo_data GROUP BY 2 Having total_events>0) A;
    ```

    In this example, "analytics_demo_data" is the name of the dataset.

2. To show all the datasets that exist in Adobe Experience Platform, perform the `Show Tables` query.


## Algorithmic pruning of large lookup datasets

When creating a connection, you can add large datasets for lookup purposes. For example, a dataset representing a product catalog so descriptive product information can be looked up when building reports and visualizations. Such a large lookup dataset can exceed the maximum of 10 million unique lookups currently implemented as a guardrail, resulting in additional data being skipped.

You can request an algorithmic pruning of a large lookup dataset. This algorithmic pruning only keeps data in the lookup dataset that matches the keys in your event dataset. This way, you don't need to load the entire unpruned lookup dataset. Old or less frequently used items are removed, which might slightly affect reports but brings significant benefits. The algorithm looks back 90 days and updates weekly.

Contact your Adobe support team for further information and to enable this capability.
