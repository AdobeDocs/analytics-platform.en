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

1. Click **[!UICONTROL Create a New Connection]** on the top right.

    ![](assets/create-connection.png)

    |Field|Description|
    |---|---|
    |Name|Give the connection a descriptive name. This is a mandatory field.|
    |Description|(Not mandatory.) Add more detail to distinguish this connection from others.|
    |Tags|(Not mandatory.) This is a good way to organize connections into categories.|

1. Click **[!UICONTROL Next]**.

1. The next dialog shows all the datasets in Platform that you can pull from. Select the dataset(s) you want to pull into Customer Journey Analytics.

    ![](assets/create-connection2.png)

1. Next, you have to let CJA know how it should be interpreting this data. There are 3 different types of data that you can connect: [Event data, Profile data, and Lookup data](/help/getting-started/cja-getting-started.md).

    (This section is still a bit fuzzy... and I know we are now auto-detectin which type of dataset they are pulling in...)

    |Dataset Type|Person ID|Timestamp|Key|Matching Key (from Event dataset)|
    |---|---|---|---|---|
    |Event|You can use any ID you want, and you are not restricted to the Analytics cookie ID or the ECID. If you specify your own ID on every hit, feel free to use that ID. |Choose among the timestamps.|N/A|N/A|
    |Lookup|Analogous to a Classifications file.|N/A|For example, tracking code.|The matching key in the Event dataset, e.g. tracking code.|
    |Profile|Analogous to Customer Attributes - for non-changing and non-temporal attributes. You can pick which Person ID you want to include. |N/A|N/A|N/A|

    Notice that a **[!UICONTROL Connection Preview]** is generated that shows a summary of the fields that will be brought in.

    ![](assets/connection-preview.png)

    If you pull in more than one dataset, the preview shows which schema fields are shared between datasets. Each dataset is color coded, so it's easy to see:

    ![](assets/shared-dataset.png)
    
1. Click **[!UICONTROL Save]**. When you save this connection, two things happen:

    * You pull in all of the historical data from Platform for all datasets that are in this connection.
    * You establish an ongoing connection, so that any new data that gets added to the datasets in this connection automatically flows into Workspace.

The next step in the workflow is to [create a data view](/help/data-views/create-dataview.md).

