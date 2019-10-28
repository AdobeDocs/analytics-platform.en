---
title: Create a connection
seo-title: Create a connection in [!UICONTROL Customer Journey Analytics] (CJA).
description: Describes how to create a connection to a Platform dataset.
seo-description: Describes how to create a connection to a Platform dataset in [!UICONTROL Customer Journey Analytics].
---

# Create a connection

In order to report on Platform datasets, you first have to establish a connection between Workspace and datasets in Platform. A connection lets you integrate datasets from your platform into Analysis Workspace. 

>[!IMPORTANT]
>You can combine multiple Platform datasets into a single connection.

1. Go to [https://www.analytics.adobe.com](https://www.analytics.adobe.com).

1. Click the **[!UICONTROL Connections]** tab.

1. Click **[!UICONTROL Create new connection]** on the top right.

    ![](assets/create-connection.png)

1. The left rail shows all the datasets in Platform that you can pull from. Select the dataset(s) you want to pull into Customer Journey Analytics and click **[!UICONTROL Add]**.

1. Next, for each dataset that you added to this connection, you have to let CJA know how it should be interpreting this data. There are 3 different dataset types that you can connect: [Event data, Profile data, and Lookup data](/help/getting-started/cja-getting-started.md).

    |Dataset Type|Person ID|Timestamp|Key|Matching Key (from Event dataset)|
    |---|---|---|---|---|
    |Event|You can use any ID you want from the dropdown, and you are not restricted to the Analytics cookie ID or the ECID. If you specify your own ID on every hit, feel free to use that ID. |Will be set to Timestamp.|N/A|N/A|
    |Lookup|Analogous to a Classifications file.|N/A|For example, tracking code.|The matching key in the Event dataset, e.g. tracking code.|
    |Profile|Analogous to Customer Attributes - for non-changing and non-temporal attributes. You can pick which Person ID you want to include. |N/A|N/A|N/A|

1. Click **[!UICONTROL Next]**.

1. In the Create Connection dialog, define these settings:

    |Field|Description|
    |---|---|
    |Name|Give the connection a descriptive name. The connection cannot be saved without a name.|
    |Description|Add more detail to distinguish this connection from others.|
    |Size|The collective size of the datasets in the data connection.|
    |Datasets|The datasets that are included in this connection.|
    |Data Streaming|To begin streaming data for this connection, enable data streaming. When data streaming is enabled for this connection, your account is billed for the amount of data that this connection is streaming. (You can also enable data streaming in the Connections Manager.)|
    
1. Click **[!UICONTROL Save]**. When you save this connection, two things happen:

    * You pull in all of the historical data from Platform for all datasets that are in this connection.
    * If you enabled streaming, you establish an ongoing connection, so that any new data that gets added to the datasets in this connection automatically flows into Workspace.

The next step in the workflow is to [create a data view](/help/data-views/create-dataview.md).
