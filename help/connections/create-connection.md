---
title: Create a connection
description: Describes how to create a connection to a Platform dataset in Customer Journey Analytics.
---

# Create a connection

A connection lets you integrate datasets from [!DNL Adobe Experience Platform] into [!UICONTROL Workspace]. In order to report on [!DNL Experience Platform] datasets, you first have to establish a connection between datasets in [!DNL Experience Platform] and [!UICONTROL Workspace].

Click [here](https://docs.adobe.com/content/help/en/platform-learn/tutorials/cja/connecting-customer-journey-analytics-to-data-sources-in-platform.html) for a video overview.

>[!IMPORTANT] You can combine multiple [!DNL Experience Platform] datasets into a single connection.

1. Go to [https://analytics.adobe.com](https://analytics.adobe.com).

1. Click the **[!UICONTROL Connections]** tab.

1. Click **[!UICONTROL Create new connection]** on the top right.

  ![Create connection](assets/create-connection.png)

1. The left rail shows all the datasets in [!DNL Experience Platform] that you can pull from. Select one or more dataset(s) you want to pull into [!UICONTROL Customer Journey Analytics] and click **[!UICONTROL Add]**. (If you have a lot of datasets to choose from, you can search for the right one(s) using the search bar above the list of datasets.)

1. Next, for each dataset that you added to this connection, [!UICONTROL Customer Journey Analytics] automatically sets the dataset type based on the data coming in. There are 3 different dataset types: [!UICONTROL Event] data, [!UICONTROL Profile] data, and [!UICONTROL Lookup] data.

    |Dataset Type|Description|Timestamp|Schema|Person ID|
    |---|---|---|---|---|
    |[!UICONTROL Event]|Data that represents events in time (e.g., web visits, interactions, transactions, POS data, survey data, ad impression data, etc.). This is typical clickstream data, with a customer ID or a cookie ID, and a timestamp. With Event data, we allow you to use whatever ID you want. |Will be set to Timestamp.|The [!DNL Experience Platform] schema that this dataset type is based on.|N/A|
    |[!UICONTROL Lookup]|Analogous to a Classifications file. This data is used to look up values or keys found in your Event or Profile data. For example, you might upload lookup data that maps numeric IDs in your event data to product names.|N/A|The [!DNL Experience Platform] schema that this dataset type is based on.|N/A|
    |[!UICONTROL Profile]|Analogous to [!UICONTROL Customer Attributes] - for non-changing and non-temporal attributes. Data that is applied to your visitors, users, or customers in the [!UICONTROL Event] data. For example, allows you to upload CRM data about your customers. |N/A|The [!DNL Experience Platform] schema that this dataset type is based on.|You can pick which Person ID you want to include. Each dataset defined in the [!DNL Experience Platform] has its own set of one or more Person IDs defined, such as Cookie ID, Stitched ID, User ID, Tracking Code, etc.<br>![Person ID](assets/person-id.png)**Note**: If you create a connection that includes datasets with different IDs, the reporting will reflect that. To really merge datasets, you need to be using the same Person ID.|

1. Clicking **[!UICONTROL Next]** takes you to the [!UICONTROL Create Connection] dialog.

    ![Create connection](assets/create-connection2.png)

1. In the [!UICONTROL Create Connection] dialog, define these settings:

    |Field|Description|
    |---|---|
    |[!UICONTROL Name Connection]|Give the connection a descriptive name. The connection cannot be saved without a name.|
    |[!UICONTROL Description]|Add more detail to distinguish this connection from others.|
    |[!UICONTROL Datasets]|The datasets that are included in this connection.|
    |[!UICONTROL Automatically import all new datasets in this connection, beginning today.]| Select this option if you want to establish an ongoing connection, so that any new data batches that get added to the datasets in this connection automatically flow into [!UICONTROL Workspace].|
    |[!UICONTROL Import all existing data]|When you select this option and save the connection, all of the existing (historical) data from [!DNL Experience Platform] for all datasets that are in this connection will be imported. In the future, all existing historical data for any new dataset(s) added to this saved connection will also be automatically imported. <br>**Note that, once this connection is saved, this setting cannot be changed.**|

    **Keep in mind that:**

    * If the cumulative size of the historical data for all datasets in the connection exceeds 1.5 Billion rows, an error message will indicate that you cannot import this amount of  historical data. However, if you were to add a dataset with 1 Billion rows of historical data, and import that data, and a week later, add another dataset of the same size and import its historical data, this would work.
    * We prioritize new data added to a dataset in the connection, so this data has the lowest latency.
    * Any backfill (historical) data is imported at a slower rate.

1. Click **[!UICONTROL Save]**. 

The next step in the workflow is to [create a data view](/help/data-views/create-dataview.md).
