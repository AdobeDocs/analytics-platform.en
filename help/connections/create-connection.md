---
title: Create a connection
description: Describes how to create a connection to a Platform dataset in Customer Journey Analytics.
exl-id: b4ac37ca-213b-4118-85e1-8e8f98553c6c
solution: Customer Journey Analytics
feature: Connections
---
# Create a connection

A new Connections workflow was recently launched in Customer Journey Analytics (CJA). The new connection creation and edit workflow experience brings all the dataset and connection configuration settings to the center of the screen with assistive workflow.  We provided detailed dataset selection, configuration, and review experience with critical information like dataset type, size, schema, dataset id, batch status, backfill status, Person IDs, and much more to reduce the risk of wrong connection configuration. Here is an overview of the new capabilities:

* You can enable a rolling data retention window when you create the connection.
* You can add to and remove datasets from a connection. (Removing a dataset removes it from the connection and impacts any associated data views and underlying Analysis Workspace projects.)
* You can enable and request backfill data per dataset.
* You can edit datasets, for example to request another backfill.
* You can import existing data per dataset.

>[!VIDEO](https://video.tv.adobe.com/v/343044/?quality=12&learn=on)

## Create and configure the connection {#create-connection}

1. In CJA, click the **[!UICONTROL Connections]** tab.
1. Click **[!UICONTROL Create new connection]**.

    ![Connection settings](assets/create-conn1.png)

1. Configure the connection settings.

    | Setting | Description |
    | --- | --- |
    | **[!UICONTROL Connection name]** | Enter a unique name for the connection. |
    | **[!UICONTROL Connection description]** | Describe the purpose of this connection. |
    | **[!UICONTROL Sandbox]** | Choose a sandbox in Experience Platform that contains the dataset/s to which you want to create a connection.<p>Adobe Experience Platform provides [sandboxes](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=en) which partition a single Platform instance into separate virtual environments to help develop and evolve digital experience applications. You can think of sandboxes as “data silos” that contain data sets. Sandboxes are used to control access to data sets.<p>Once you have selected the sandbox, the left rail shows all the datasets in that sandbox that you can pull from.  |
    | **[!UICONTROL Enable rolling data window]** | This checkbox, if checked, lets you define CJA data retention as a rolling window in months (1 month, 3 months, 6 months, etc.), at the connection level.<p>Data retention is based on event dataset timestamps and applies to event datasets only. No rolling data window setting exists for profile or lookup datasets, since there are no applicable timestamps. However, if your connection includes any profile or lookup datasets (besides one or more event datasets), that data will be retained for the same time period.<p> The main benefit is that you store or report only on data that is applicable and useful and delete older data that is no longer useful. It helps you stay under your contract limits and reduces the risk of overage cost.<p>If you leave the default (unchecked), the retention period will be superseded by the Adobe Experience Platform data retention setting. If you have 25 months' worth of data in Experience Platform, CJA will get 25 months of data through backfill. If you deleted 10 of those months in Platform, CJA would retain the remaining 15 months. |
    | **[!UICONTROL Add datasets]** (see below) | Add datasets if no datasets appear in your dataset listing. |
    | **[!UICONTROL Dataset name]** | Select one or more dataset(s) you want to pull into Customer Journey Analytics and click **[!UICONTROL Add]**.<p>(If you have a lot of datasets to choose from, you can search for the right one(s) using the Search datasets search bar above the list of datasets.) |
    | **[!UICONTROL Last updated]** | For event datasets only, this setting is automatically set to the default timestamp field from event-based schemas in Experience Platform. "N/A" means that this dataset contains no data. |
    | **[!UICONTROL Schema]** | This is the [schema](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html?lang=en) based on which the dataset was created in Adobe Experience Platform. |
    | **[!UICONTROL Dataset type]** | For each dataset that you added to this connection, Customer Journey Analytics automatically sets the dataset type based on the data coming in. There are 3 different dataset types: Event data, Profile data, and Lookup data. See the table below for an explanation of dataset types. |
    | **[!UICONTROL Person ID]** | Select a person ID from the dropdown list of available identities. These identities were defined in the dataset schema in the Experience Platform. See below for information on how to use Identity Map as a Person ID.<p>IMPORTANT: If there are no person IDs to choose from, that means one or more person IDs have not been defined in the schema. View [this video](https://www.youtube.com/watch?v=G_ttmGl_LRU) on how to define an identity in Experience Platform. |
    | **[!UICONTROL Key]** | For lookup datasets only (such as _id). |
    | **[!UICONTROL Matching Key]** | For lookup datasets only (such as _id). |
    | **[!UICONTROL Import new data]** | Set to On or Off. |
    | **[!UICONTROL Backfill data]** | You can request to backfill the data in a dataset based on event timestamps. For example, you can request to backfill the last 7 days worth of data, configure the right Person ID and test your connection for correct configuration. If everything looks good, you can backfill all the remaining data with ease.<p>In addition, you can enable the import of new data by dataset. For example, you can enable the import of new data for lookup data only.  |
    | **[!UICONTROL Backfill status]** | Indicates whether any backfill data is processing. |

    {style="table-layout:auto"}

## Add and configure datasets {#add-dataset}

The new workflow lets you add an Experience Platform dataset when you create a connection. 

1. In the Connection settings dialog, click **[!UICONTROL Add datasets]**.
1. Select one or more datasets and click **[!UICONTROL Next]**. 

    Note that at least one event dataset needs to be part of the connection.
1. Now configure the datasets one by one.

    ![Configure datasets](assets/add-dataset.png)

    | Setting | Description |
    | --- | --- |
    | **[!UICONTROL Person ID]** | Select a person ID from the dropdown list of available identities. These identities were defined in the dataset schema in the Experience Platform. See below for information on how to use Identity Map as a Person ID.<p>If there are no person IDs to choose from, that means one or more person IDs have not been defined in the schema. View this video on how to define an identity in Experience Platform. |
    | **[!UICONTROL Timestamp]** | For event datasets only, this setting is automatically set to the default timestamp field from event-based schemas in Experience Platform. |
    | **[!UICONTROL Import new data]** | Select this option if you want to establish an ongoing connection, so that any new data batches that get added to the datasets in this connection automatically flow into Workspace. Can be set to On or Off. |
    | **[!UICONTROL Dataset backfill]** | Click **[!UICONTROL Request backfill]** to backfill historical data.<ul><li>You can backfill each dataset individually.</li><li>We prioritize new data added to a dataset in the connection, so this new data has the lowest latency.</li><li>Any backfill (historical) data is imported at a slower rate. The latency is influenced by how much historical data you have.</li><li>The Adobe Analytics Source Connector imports up to 13 months of data, irrespective of size.</li></ul> |
    | **[!UICONTROL Backfill status]** | Possible status indicators are:<ul><li>Success</li><li>X backfill(s) processing</li><li>Off</li></ul> |
    | **[!UICONTROL Dataset ID]** | This ID is automatically generated. |
    | **[!UICONTROL Description]** | The description given to this dataset when it was created. |
    | **[!UICONTROL Dataset size]** | The dataset’s size. |
    | **[!UICONTROL Schema]** | This is the schema based on which the dataset was created in Adobe Experience Platform. |
    | **[!UICONTROL Dataset]** | The name of the dataset. |
    | **[!UICONTROL Preview]**: `<dataset name>` | Previews the dataset with date, my ID and Identifier columns. |
    | **[!UICONTROL Remove]** | You can delete or remove the dataset and change the Person ID without deleting the whole connection. This reduces the costs involved in data ingestion and the cumbersome process of recreating the whole connection and associated data views. |

    {style="table-layout:auto"}

## Connection preview {#preview}

To preview the connection that you have created, click **[!UICONTROL Connection preview]** in the Connection settings dialog.

![Connection preview](assets/create-conn4.png)

This preview contains a number of columns listing the connection configuration. What column types are shown depends on your individual datasets.

## Dataset types {#dataset-types}

For each dataset that you added to this connection, [!UICONTROL Customer Journey Analytics] automatically sets the dataset type based on the data coming in. 

>[!IMPORTANT]
>
>You need to add at least one event dataset as part of a connection.

There are 3 different dataset types: [!UICONTROL Event] data, [!UICONTROL Profile] data, and [!UICONTROL Lookup] data.

|Dataset Type|Description|Timestamp|Schema|Person ID|
|---|---|---|---|---|
| **[!UICONTROL Event]** | Data that represents events in time (e.g., web visits, interactions, transactions, POS data, survey data, ad impression data, etc.). For example, this could be typical clickstream data, with a customer ID or a cookie ID, and a timestamp. With Event data, you have flexibility as to which ID is used as the Person ID. |Is automatically set to the default timestamp field from event-based schemas in [!UICONTROL Experience Platform]. | Any built-in or custom schema that is based on an XDM class with the "Time Series" behavior. Examples include "XDM Experience Event" or "XDM Decision Event." | You can pick which Person ID you want to include. Each dataset schema defined in the Experience Platform can have its own set of one or more identities defined and associated with an Identity Namespace. Any of these can be used as the Person ID. Examples include Cookie ID, Stitched ID, User ID, Tracking Code, etc. |
| **[!UICONTROL Lookup]** | This data is used to look up values or keys found in your Event or Profile data. For example, you might upload lookup data that maps numeric IDs in your event data to product names. See [this use case](/help/use-cases/b2b.md) for an example. | N/A | Any built-in or custom schema that is based on an XDM class with the "Record" behavior, except for the "XDM Individual Profile" class. | N/A |
| **[!UICONTROL Profile]** | Data that is applied to your visitors, users, or customers in the [!UICONTROL Event] data. For example, allows you to upload CRM data about your customers. | N/A | Any built-in or custom schema that is based on the "XDM Individual Profile" class. | You can pick which Person ID you want to include. Each dataset defined in the [!DNL Experience Platform] has its own set of one or more Person IDs defined, such as Cookie ID, Stitched ID, User ID, Tracking Code, etc.<br>![Person ID](assets/person-id.png)**Note**: If you create a connection that includes datasets with different IDs, the reporting will reflect that. To really merge datasets, you need use the same Person ID. |

{style="table-layout:auto"}

## Use numeric fields as lookup keys and lookup values {#numeric}

This functionality is useful you want to classify string values with a numeric field, such as a COGS or margin, on a product SKU. It allows numeric values to be part of lookups, either as keys or as values. In your lookup schema, you might have numeric values tied to, for example, your product names, COGS, campaign marketing cost, or margins. Here is an example lookup schema in Adobe Experience Platform:

![Lookup schema](assets/schema.png)

We now support bringing in these values as metrics or dimensions into CJA reporting. When you set up your connection and pull in lookup datasets, you can edit the datasets to select the [!UICONTROL Key] and [!UICONTROL Matching Key]:

![Edit-dataset](assets/lookup-dataset.png)

When you set up a data view based on this connection, you add the numeric values as components to the data view. Any project based on this data view can then report on these numeric values.

## Use Identity Map as a Person ID {#id-map}

Customer Journey Analytics supports the ability to use the Identity Map for its Person ID. Identity Map is a map data structure that allows you to upload key -> value pairs. The keys are identity namespaces and the value is a structure that holds the identity value. The Identity Map exists on each row/event uploaded and is populated for each row accordingly.

The Identity Map is available for any dataset that uses a schema based on the [ExperienceEvent XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) class. When you select such a dataset to be included in a CJA Connection, you have the option of selecting either a field as the primary ID or the Identity Map:

![](assets/idmap1.png)

If you select Identity Map, you get two additional configuration options:

|Option|Description|
|---|---|
| **[!UICONTROL Use Primary ID Namespace]** | This instructs CJA, per row, to find the identity in the Identity Map that is marked with a primary=true attribute and use that as the Person ID for that row. This means that this is the primary key that will be used in Experience Platform for partitioning. It is also the prime candidate for usage as CJA's visitor ID (depending on how the dataset is configured in a CJA Connection).|
| **[!UICONTROL Namespace]**| (This option is only available if you do not use the Primary ID Namespace.) Identity namespaces are a component of [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html) that serve as indicators of the context to which an identity relates. If you specify a namespace, CJA will search each row's Identity Map for this namespace key and use the identity under that namespace as the person ID for that row. Note that since CJA cannot do a full dataset scan of all rows to determine which namespaces are actually present, all possible namespaces are listed in the dropdown. You need to know which namespaces are specified in the data; this cannot be auto-detected.|

{style="table-layout:auto"}

### Identity Map edge cases {#id-map-edge}

This table shows the two configuration options when edge cases are present and how they are handled:

| Option | No IDs are present in Identity Map | No IDs are marked as primary | Multiple IDs are marked as primary | Single ID is marked as primary | Invalid namespace with an ID marked as primary |
|---|---|---|---|---|---|
| **[!UICONTROL Use Primary ID Namespace] checked** | The row is dropped by CJA. | The row is dropped by CJA, as no primary ID is specified. | All IDs marked as primary, under all namespaces, are extracted into a list. They are then alphabetically sorted; with this new sorting, the first namespace with its first ID is used as the Person ID. | The single ID marked as primary is used as the Person ID. | Even though the namespace may be invalid (not present in AEP), CJA will use the primary ID under that namespace as the Person ID. |
| **[!UICONTROL Specific Identity Map namespace] selected** | The row is dropped by CJA. | All IDs under the selected namespace are extracted into a list and the first is used as the Person ID. | All IDs under the selected namespace are extracted into a list and the first is used as the Person ID. | All IDs under the selected namespace are extracted into a list and the first is used as the Person ID. | All IDs under the selected namespace are extracted into a list and the first is used as the Person ID. (Only a valid namespace can be selected at Connection creation time, so it is not possible for an invalid namespace/ID to be used as Person ID) |

{style="table-layout:auto"}

## Calculate the average number of daily events

This calculation has to be done for every dataset in the connection.

1. Go to [Adobe Experience Platform Query Services](https://experienceleague.adobe.com/docs/experience-platform/query/home.html) and create a new query.

    The query would look like this:
    
    ```
    Select AVG(A.total_events) from (Select DISTINCT COUNT (*) as total_events, date(TIMESTAMP) from analytics_demo_data GROUP BY 2 Having total_events>0) A;

    ```

    In this example, "analytics_demo_data" is the name of the dataset.

1. Perform the `Show Tables` query to show all the datasets that exist in AEP.
