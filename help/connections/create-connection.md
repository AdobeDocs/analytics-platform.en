---
title: Create a connection
description: Describes how to create a connection to a Platform dataset in Customer Journey Analytics.
---

# Create a connection

A connection lets you integrate datasets from Adobe Experience Platform into Workspace. In order to report on Platform datasets, you first have to establish a connection between Workspace and datasets in Platform.

Click [here](https://docs.adobe.com/content/help/en/platform-learn/tutorials/cja/connecting-customer-journey-analytics-to-data-sources-in-platform.html) for a video overview.

>[!IMPORTANT] You can combine multiple Platform datasets into a single connection.

1. Go to [https://www.analytics.adobe.com](https://www.analytics.adobe.com).

1. Click the **[!UICONTROL Connections]** tab.

1. Click **[!UICONTROL Create new connection]** on the top right.

  ![Create connection](assets/create-connection.png)

1. The left rail shows all the datasets in Platform that you can pull from. Select one or more dataset(s) you want to pull into Customer Journey Analytics and click **[!UICONTROL Add]**. (If you have a lot of datasets to choose from, you can search for the right one(s) using the search bar above the list of datasets.)

1. Next, for each dataset that you added to this connection, Customer Journey Analytics automatically sets the dataset type based on the data coming in. There are 3 different dataset types: Event data, Profile data, and Lookup data.

    |Dataset Type|Description|Timestamp|Schema|Person ID|
    |---|---|---|---|---|
    |Event|Data that represents events in time (e.g., web visits, interactions, transactions, POS data, survey data, ad impression data, etc.). This is typical clickstream data, with a customer ID or a cookie ID, and a timestamp. With Event data, we allow you to use whatever ID you want. |Will be set to Timestamp.|The Platform schema that this dataset type is based on.|N/A|
    |Lookup|Analogous to a Classifications file. This data is used to lookup values or keys found in your Event or Profile data. For example, you might upload lookup data that maps numeric IDs in your event data to product names.|N/A|The Platform schema that this dataset type is based on.|N/A|
    |Profile|Analogous to Customer Attributes - for non-changing and non-temporal attributes. Data that is applied to your visitors, users, or customers in the Event data. For example, allows you to upload CRM data about your customers. |N/A|The Platform schema that this dataset type is based on.|You can pick which Person ID you want to include. Each dataset defined in the Adobe Experience Platform has its own set of one or more Person IDs defined, such as Cookie ID, Stitched ID, User ID, Tracking Code, etc.<br>![Person ID](assets/person-id.png)**Note**: If you create a connection that includes datasets with different IDs, the reporting will reflect that. To really merge datasets, you need to be using the same Person ID.|

1. Click **[!UICONTROL Next]**.

1. In the Create Connection dialog, define these settings:

    |Field|Description|
    |---|---|
    |Name|Give the connection a descriptive name. The connection cannot be saved without a name.|
    |Description|Add more detail to distinguish this connection from others.|
    |Size|The collective size of the datasets in the data connection.|
    |Datasets|The datasets that are included in this connection.|
    |Data Streaming|To begin streaming data for this connection, enable data streaming. When data streaming is enabled for this connection, your account is billed for the amount of data that this connection is streaming. (Note that you can also enable data streaming in the Connections Manager.)|

1. Click **[!UICONTROL Save]**. When you save this connection, two things happen:

    * You pull in all of the historical data from Platform for all datasets that are in this connection.
    * If you enabled streaming, you establish an ongoing connection, so that any new data that gets added to the datasets in this connection automatically flows into Workspace.

The next step in the workflow is to [create a data view](/help/data-views/create-dataview.md).
