---
title: How to manage connections in Customer Journey Analytics
description: Describes how to manage connections to Experience Platform datasets in Customer Journey Analytics (Customer Journey Analytics).
mini-toc-levels: 3
exl-id: 0a87518c-3608-44ad-b5e3-976f97560433
solution: Customer Journey Analytics
feature: Connections
role: Admin
---
# Manage connections

Once you have [created or edited one or more connections](/help/connections/create-connection.md), you can manage them in **[!UICONTROL Connections]**. Connections let you:

* View all your connections at a glance, including the owner, the sandbox, and when the connections were created and modified.
* Edit a connection.
* Delete a connection.
* Create a data view from a connection.
* View all datasets in a connection.
* Check the status of your connection's datasets and the status of the ingestion process. For example, when is your data available so that you can start with reporting and analysis in Analysis Workspace.
* Identify any data discrepancies due to misconfiguration. Are you missing any rows? If so, what rows are missing and why? Did you misconfigure connections and cause missing data in Customer Journey Analytics?
* Get insights on the usage of ingested and reportable rows across all your connections.

[!UICONTROL Connections] has two interfaces: [[!UICONTROL List]](#list) and [[!UICONTROL Usage]](#usage).


## List

The [!UICONTROL List] interface is the default interface for Connections. If not selected, select the **[!UICONTROL List]** tab to access the interface.

![list view](assets/list-view.png)

The [!UICONTROL List] interface shows a table of all connections available. You can quickly search for a connection using the Search ![Search](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) box.

The following columns or icons are available in the table.

| Column or Icon | Description |
| --- | --- |
| [!UICONTROL Name] | The connection's friendly name. To see the details of the connection, select the hyperlinked name. See [Connection details](#connection-details). |
| ![Information](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) | To view information about [!UICONTROL Datasets included], [!UICONTROL Sandbox], [!UICONTROL Owner], and more, select ![Information](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) next to the connection name.<p>A popup window displays details. <p><img src="./assets/conn-info.png" alt="View connection info" width="400"/> |
| ![Data view](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) | To [create a data view](#create-a-data-view) for the connection, select ![Data view](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg). This icon only shows when no data view is already associated with the connection. |
| ![More](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) | Select ![More](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) to: <p>![Edit](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) [Edit](#edit-a-connection) a connection.<p>![Delete](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) [Delete](#delete-a-connection) a connection.<p>![Data view](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) [Create new data view](#create-a-data-view). To create additional data views for the connection. |
| [!UICONTROL Datasets] | Shows one or more links to the datasets that are part of the connection. You can select the dataset hyperlink to view the dataset in the connection. If more datasets are part of the selected connection, select **[!UICONTROL +*x* more]** to show a **[!UICONTROL Datasets included]** panel. This panel shows links to all datasets and an option to search for a specific dataset that is part of the connection.<p><img src="./assets/datasets-included.png" alt="Datassets included" width="400"/><p>Selecting a dataset name opens the dataset in the Experience Platform UI in a new tab. |
| [!UICONTROL Sandbox] | Shows the [Experience Platform sandbox](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html) from which this connection draws its datasets. This sandbox was selected when you first created the connection. It cannot be changed.|
| [!UICONTROL Owner] | The person who created the connection. |
| [!UICONTROL Import new data] | Shows the status of importing new data for datasets: <p>![Status green](assets/status-green.svg)) &nbsp;&nbsp;&nbsp;**[!UICONTROL _x_ On]** for datasets configured to import new data, and<p>![Status gray](assets/status-gray.svg)&nbsp;&nbsp;&nbsp;**[!UICONTROL _x Off_]** for datasets not configured to import new data. |
| [!UICONTROL Date created] | The timestamp when the connection was created. |
| [!UICONTROL Last modified] | The timestamp when the connection is last updated. |
| [!UICONTROL Backfill data] | Shows the status for backfill data across datasets.<p>![Status red](assets/status-red.svg)&nbsp;&nbsp;&nbsp;**[!UICONTROL _x_ backfills failed]** for number of failed backfills across datasets,<p>![Status orange](assets/status-orange.svg)&nbsp;&nbsp;&nbsp;**[!UICONTROL _x_ backfills processing]** for number of processing backfills across datasets,<p>![Status green](assets/status-green.svg)&nbsp;&nbsp;&nbsp;**[!UICONTROL _x_ backfills completed]** for number of completed backfills for datasets, and<p>![Status gray](assets/status-gray.svg)&nbsp;&nbsp;&nbsp;**[!UICONTROL _Off_]** in case no backfills are defined for the datasets in the connection. |

To configure which columns to display select ![Column settings](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg), which shows the **Customize table** dialog allowing you turn columns on or off in the table.

### Edit a connection

1. Select ![More](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) next to the connection name
1. Select ![Edit](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Edit]** from the context menu.

Alternatively, you can:

1. Select the connection row.

1. Select ![Edit](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Edit]** from the blue bar.

When editing a connection, you can:

* Start and stop importing new data.
* Rename a connection.
* Refresh the dataset/s.
* Remove dataset/s from the connections.

See [Create or edit a connection](create-connection.md) for more information.


### Delete a connection {#connections-delete}

1. Select ![More](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) next to the connection name.
1. Select ![Delete](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Delete]**.

Alternatively, you can:

1. Select the connection row.

1. Select ![Delete](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Delete]** from the blue bar.

When you delete a connection, a **[!UICONTROL Delete connection]** panel indicates which data views are deleted and which workspace projects are affected.

![Delete connection](assets/delete-connection.png)

Select **[!UICONTROL Continue]** to delete the connection.

See [Deletion implications](/help/technotes/deletion.md) for more information about deleting a connection.


### Create a data view for a connection

* If no data view is associated with the connection:

    1. Select ![Add data view](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) next to the connection name.

* If one or more data views are already created for the connection:

  1. Select ![More](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) next to the connection name.
  1. Select ![Add data view](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Create new data view]**.

Alternatively, you can:

1. Select the connection row.

1. Select ![Add data view](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Create data view]** from the blue button bar.

See [Create or edit a data view](/help/data-views/create-dataview.md) for more information.

### Connection details {#connection-detail}

To go to the details for a connection, select a connection name in the connections table.

![All datasets window showing the widgets and settings](assets/conn-details.png)

The Connections details interface provides a detailed view of the status of a connection. You can:

* Check the status of your connection's datasets and of the ingestion process.
* Identify configuration problems that can cause skipped or deleted records.
* See when the data is available for reporting.

| User Interface | Description |
| --- | --- |
| ![Edit](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) [!UICONTROL Edit Connection] | To edit the details of a connection, select ![Edit](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Edit Connection]**. See [Create or edit a connection](create-connection.md) for more information. |
| Dataset selector | Lets you pick one or all datasets in the connection. You cannot multi-select datasets. Defaults to [!UICONTROL All datasets]. |
| Date range selector | Edit start date, end date, or select ![Calendar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) to open the data range selector. In the date range selector, select a date range by using one of the predefined periods (for example **[!UICONTROL Last 6 months]**) or use the calendar to select start and end date. Select **[!UICONTROL Apply]** to apply the new data range.|
| [!UICONTROL Records of event data available] | The total number of event dataset rows available for reporting, **for the entire connection**. This count is independent of any calendar settings. The count changes if you select a dataset from the dataset selector or by selecting a dataset in the table. Once data is added, there is a latency of 1-2 hours to get the data to appear in reporting. |
| [!UICONTROL Metrics] | Summarizes the event, lookup, profile and summary dataset records that are added, skipped, and deleted, and the number of batches added, **for the dataset and date range you have selected**.<p>Select **[!UICONTROL Check detail]** to show the **[!UICONTROL Check skipped detail]** popup. The popup lists the number of skipped records and the reason for all event datasets or selected dataset.<p><img src="./assets/skipped-records.png" width="500"/><p>Select ![Info](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) popup with more information. For some skipped reasons, like [!UICONTROL Empty visitor ID], the popup displays Sample PSQL for EQS (Experience Platform for Query Service) you can use in [Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/home.html) to query for the skipped records in the dataset. Select ![Copy](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) **[!UICONTROL Copy sample PSQL for EQS]** to copy the SQL. |
| [!UICONTROL Records added] | Indicates how many rows were added in the selected time period, **for the dataset and date range you have selected**. Updated every 10 minutes. |
| [!UICONTROL Records skipped] | Indicates how many rows were skipped in the selected time period, **for the dataset and date range you have selected**. Reasons for skipping records include: missing timestamps, missing or invalid person ID, and so forth. Updated every 10 minutes. <p>Invalid person IDs (such as `undefined`, or `00000000`, or any combination of numbers and letters in a [!UICONTROL Person ID] that appears in an event more than 1 million times in a given month) are IDs that cannot be attributed to any specific user or person. These rows cannot be ingested into the system and result in error-prone ingestion and reporting. To fix invalid person IDs, you have 3 options:<ul><li>Use [Stitching](/help/stitching/overview.md) to populate the undefined or all-zero user IDs with valid user IDs.</li><li>Blank out the user ID, which are then kipped during ingestion (preferable to invalid or all-zero user IDs).</li><li>Fix any invalid user IDs in your system before ingesting the data.</li></ul> |
| [!UICONTROL Records] deleted | Indicates how many rows were deleted in the selected time period, **for the dataset and date range you have selected**. Someone might have deleted a dataset in [!DNL Experience Platform], for example. Updated every 10 minutes.<p>In some scenarios, this value can also include records replaced, as with stitching or some lookup dataset updates. Consider this example:</p><ul><li>You upload one record to an XDM Individual Profile dataset, which Customer Journey Analytics is configured to ingest as profile lookup data. In the connection details, this dataset would display 1 record added.</li><li>You upload a duplicate of the original record into the same AEP dataset, which now contains two records. Customer Journey Analytics ingests the additional record from the profile lookup dataset. Seeing that it has already ingested a profile record in the connection for that person ID, Customer Journey Analytics deletes its earlier version and adds the new profile data. In the connection details, this action would represent 1 record added and 1 record deleted, because Customer Journey Analytics only retains the most recent profile lookup data for any ingested person ID.</li><li>In total, the AEP dataset contains two records that happen to be identical. Separately, the Customer Journey Analytics connection details display the status of its ingested data: 2 records added and 1 record deleted for this profile dataset. </li></ul> |
| ![Search](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) _Search dataset name or ID_ | Dataset search field. You can search the datasets table by dataset name or [!UICONTROL Dataset ID]. |
| [!UICONTROL Datasets table] | Shows the datasets that are part of the connection. |
| [!UICONTROL Datasets] | Shows the name of the dataset that is part of the connection. You can select the hyperlink to open the dataset in the Experience Platform UI in a new tab. You can select the row or the checkbox to show details for the selected dataset only. |
| [!UICONTROL Dataset ID] | Automatically generated by Experience Platform. |
| [!UICONTROL Records added] | The number of dataset records (rows) added to a connection during the selected time interval. |
| [!UICONTROL Records skipped] | The number of dataset records (rows) skipped during data transfer for a connection during the selected time interval. |
| [!UICONTROL Records deleted] | The number of dataset records (rows) removed from a connection during the selected time interval. |
| [!UICONTROL Batches added] | The number of dataset batches have been added to a connection. |
| [!UICONTROL Last added] | The timestamp of the latest batch from the dataset that has been added to a connection.  |
| [!UICONTROL Data source type] | The source type of the dataset. You define the source type when creating a connection. |
| [!UICONTROL Dataset type] | The dataset type for this dataset. Type can be [!UICONTROL Event], [!UICONTROL Profile], [!UICONTROL Lookup], or [!UICONTROL Summary]. [Learn more](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html#configure-dataset)  |
| Schema | The Experience Platform schema that the dataset is based on.  |
| [!UICONTROL Import new data] | Shows the status of importing new data for the dataset: <p>![Status green](assets/status-green.svg)&nbsp;&nbsp;&nbsp;**[!UICONTROL _x_ On]** if dataset is configured to import new data, and<p>![Status gray](assets/status-gray.svg)&nbsp;&nbsp;&nbsp;**[!UICONTROL _x Off_]** if dataset is configured to not import new data import. |
| [!UICONTROL Transform data] | Shows the transformation status of applicable B2B lookup datasets. See [Transform datasets for B2B lookups](transform-datasets-b2b-lookups.md) for more information.<p>![Status green](assets/status-green.svg)&nbsp;&nbsp;&nbsp;**[!UICONTROL _x_ On]** for applicable datasets enabled for transformation, <p>![Status gray](assets/status-gray.svg)&nbsp;&nbsp;&nbsp;**[!UICONTROL _x Off_]** for applicable datasets not enabled for transformation, and<p>**[!UICONTROL N/A]** for all other datasets, not applicable for transformation.| 
| [!UICONTROL Backfill data] | Shows the status of backfill data for the dataset.<p>![Status red](assets/status-red.svg)&nbsp;&nbsp;&nbsp;**[!UICONTROL _x_ backfills failed]** for number of failed backfills,<p>![Status red](assets/status-orange.svg)&nbsp;&nbsp;&nbsp;**[!UICONTROL _x_ backfills processing]** for number of backfills processing,<p>![Status green](assets/status-green.svg)&nbsp;&nbsp;&nbsp;**[!UICONTROL _x_ backfills completed]** for number of backfills completed, and<p>![Status gray](assets/status-gray.svg)&nbsp;&nbsp;&nbsp;**[!UICONTROL _Off_]** in case no  backfills are configured. |
| [!UICONTROL Import new data] | Shows the status of importing new data for the dataset: <p>![Status green](assets/status-green.svg)&nbsp;&nbsp;&nbsp;**[!UICONTROL _x_ On]** if the dataset is configured to import new data, and<p>![Status gray](assets/status-gray.svg)&nbsp;&nbsp;&nbsp;**[!UICONTROL _x Off_]** if the dataset is configured not to import new data. |
| [!UICONTROL Backfill data] | Shows the status of backfill data for the dataset.<p>![Status red](assets/status-red.svg)&nbsp;&nbsp;&nbsp;**[!UICONTROL _x_ backfills failed]** for number of failed backfills,<p>![Status red](assets/status-orange.svg)&nbsp;&nbsp;&nbsp;**[!UICONTROL _x_ backfills processing]** for number of backfills processing,<p>![Status green](assets/status-green.svg)&nbsp;&nbsp;&nbsp;**[!UICONTROL _x_ backfills completed]** for number of backfills completed, and<p>![Status gray](assets/status-gray.svg)&nbsp;&nbsp;&nbsp;**[!UICONTROL _Off_]** in case no backfills are configured. |

>[!IMPORTANT]
>
>Any data ingested before August 13, 2021 is not reflected in the [!UICONTROL Connections] interface.

#### Connection panel

When no dataset is selected in the datasets table, a panel on the right side of the Connections interface shows connection options and details.

| Options / Details | Description |
| --- | --- |
| ![Refresh](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) [!UICONTROL Refresh] |To refresh the connection and allow recently added records to be reflected, select ![Refresh](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) **[!UICONTROL Refresh]**.  |
| ![Delete](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Delete]** | [Delete](#delete-a-connection) this connection.  |
| ![Add data view](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Create data view]** | [Create a data view](#create-a-data-view) based on this connection. See [Data views](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html) for more information.|
| [!UICONTROL Connection name] | Shows the friendly name of the connection. |
| [!UICONTROL Connection description] | Shows a more detailed description that describes the purpose of this connection. |
| [!UICONTROL Sandbox] | The [Experience Platform sandbox](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html) from which this connection draws its dataset/s. This sandbox was selected when you first created the connection. It cannot be changed. |
| [!UICONTROL Connection ID] | This ID is generated in Experience Platform. You can use ![Copy](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) to copy the ID.  |
| [!UICONTROL Data views using connection] | Lists all the data views that use this connection. |
| [!UICONTROL Import new data] | Shows the status of importing new data for datasets: <p>![Status green](assets/status-green.svg)&nbsp;&nbsp;&nbsp;**[!UICONTROL _x_ On]** for how many datasets are configured to import new data, and<p>![Status gray](assets/status-gray.svg)&nbsp;&nbsp;&nbsp;**[!UICONTROL _x Off_]** for how many datasets new data import is turned off. |
| [!UICONTROL Backfill data] | Shows the status of backfill data for datasets.<p>![Status red](assets/status-red.svg)&nbsp;&nbsp;&nbsp;**[!UICONTROL _x_ backfills failed]** for number of failed backfills across datasets,<p>![Status red](assets/status-orange.svg)&nbsp;&nbsp;&nbsp;**[!UICONTROL _x_ backfills processing]** for number of processing backfills across datasets,<p>![Status green](assets/status-green.svg)&nbsp;&nbsp;&nbsp;**[!UICONTROL _x_ backfills completed]** for number of completed backfills for datasets, and<p>![Status gray](assets/status-gray.svg)&nbsp;&nbsp;&nbsp;**[!UICONTROL _Off_]** in case no backfills are defined for the datasets in the connection. |
| Transform data | Shows the transformation status of applicable B2B lookup datasets. See [Transform datasets for B2B lookups](transform-datasets-b2b-lookups.md) for more information.<p>![Status green](assets/status-green.svg)&nbsp;&nbsp;&nbsp;**[!UICONTROL _x_ On]** for number of datasets enabled for transformation.| 
| [!UICONTROL Created by] | Shows the name of the person who created the connection. |
| [!UICONTROL Last modified] | Shows the timestamp of the last change to the connection. |
| [!UICONTROL Last modified by] | Shows the person who last modified the connection. |

#### Dataset panel

When a dataset is selected in the datasets table, a panel on the right side of the Connections interface show details for the selected dataset.

| Details | Description |
| --- | --- |
| [!UICONTROL Person ID] | Shows an identity that was defined in the dataset schema in the Experience Platform. This identity is the Person ID that you selected during the creation of the connection. If you create a connection that includes datasets with different IDs, the reporting reflects that. To merge datasets, you need to use the same Person ID across datasets. |
| [!UICONTROL Key] | Shows the key that you have specified for a lookup dataset. |
| [!UICONTROL Matching Key] | Shows the matching key that you have specified for a lookup dataset. |
| [!UICONTROL Timestamp] | Shows the timestamp defined for an event dataset. |
| [!UICONTROL Records available] | Shows the total number of rows ingested for this dataset, for the particular time period selected through the calendar. There is no latency in terms of getting the data to appear in reporting, once it is added. However, when you create a brand new connection, there is [latency](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html#3.-getting-data-into-customer-journey-analytics). |
| [!UICONTROL Records added] | Shows how many rows were added in the selected time period. |
| [!UICONTROL Records deleted] | Shows how many records were deleted during the selected time period. |
| [!UICONTROL Batches added] | Shows how many data batches were added into this dataset.  |
| [!UICONTROL Records skipped] | Shows how many rows were skipped during ingestion in the selected time period.<p>Reasons for skipping records include: Missing timestamps, missing or invalid person ID, and so forth. Updated every 10 minutes.<p>Invalid person IDs (such as `undefined`, or `00000000`, or any combination of numbers and letters in a [!UICONTROL Person ID] that appears in an event more than 1 million times in a given month) are IDs that cannot be attributed to any specific user or person. These rows cannot be ingested into the system and result in error-prone ingestion and reporting. To fix invalid person IDs, you have 3 options:<ul><li>Use [Stitching](/help/stitching/overview.md) to populate the undefined or all-zero user IDs with valid user IDs.</li><li>Blank out the user ID, which is then skipped during ingestion (preferable to invalid or all-zero user IDs).</li><li>Fix any invalid user IDs in your system before ingesting the data.</li></ul> |
| [!UICONTROL Last added] | Shows when the last batch was added. |
| [!UICONTROL Import new data] | Shows the status of importing new data for the dataset: <p>![Status green](assets/status-green.svg)&nbsp;&nbsp;&nbsp;**[!UICONTROL _x_ On]** if the dataset is configured to import new data, and<p>![Status gray](assets/status-gray.svg)&nbsp;&nbsp;&nbsp;**[!UICONTROL _x Off_]** if the dataset is configured not to import new data.  |
| [!UICONTROL Backfill data] | Shows the status of backfill data for the dataset.<p>![Status red](assets/status-red.svg)&nbsp;&nbsp;&nbsp;**[!UICONTROL _x_ backfills failed]** for number of failed backfills,<p>![Status red](assets/status-orange.svg)&nbsp;&nbsp;&nbsp;**[!UICONTROL _x_ backfills processing]** for number of backfills processing,<p>![Status green](assets/status-green.svg)&nbsp;&nbsp;&nbsp;**[!UICONTROL _x_ backfills completed]** for number of backfills completed, and<p>![Status gray](assets/status-gray.svg)&nbsp;&nbsp;&nbsp;**[!UICONTROL _Off_]** in case no backfills are configured.<p>To show a dialog with an overview of the past backfills for the dataset, select <img src="./assets/pastbackfill.svg" alt="Past backfills" width="15"/> **[!UICONTROL Past backfills]**. |
| [!UICONTROL Data source type] | Data source type as defined when adding the dataset to the connection. |
| [!UICONTROL Dataset type] | Either [!UICONTROL Event], [!UICONTROL Profile], [!UICONTROL Lookup], or [!UICONTROL Summary]. [Learn more](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html#configure-dataset)  |
| [!UICONTROL Schema] | Shows the Experience Platform schema that this dataset is based on. |
| [!UICONTROL Dataset ID] | This dataset ID is generated in Experience Platform. |


## Usage

The [!UICONTROL Usage] interface shows the usage of ingested and reportable rows across all connections. This interface supports you to determine whether your Customer Journey Analytics usage complies with what is contractually agreed upon. In addition to monitoring purposes, you can use the Usage UI to better plan your Customer Journey Analytics license renewal.

You can select a time range (between last 6 months, year to date, or last 2 Years) and an interval (between monthly or quarterly) to monitor Customer Journey Analytics usage. The interface is divided into two sections:

* Ingested rows: total rows ingested/sent from event datasets across all Customer Journey Analytics Connections, including records skipped during ingestion
* Reportable rows: total reportable rows that include all events data across all Customer Journey Analytics Connections

![usage-view](assets/usage-view.png)

Select the **[!UICONTROL Usage]** tab to access the interface.

### Report on usage

1. Select a **[!UICONTROL Time range]**. You can select between **[!UICONTROL Last 6 months]**, **[!UICONTROL Year to date]**, or **[!UICONTROL Last 2 Years]**.
1. Select an **[!UICONTROL Interval]**. You can select between **[!UICONTROL Monthly]** or **[!UICONTROL Quarterly]**.

For [!UICONTROL Ingested rows]:

* A panel displays the total ingested rows that include all the events data across all the connections updated on every 2nd day of a month. Within the panel: 
  * a box displays the number of ingested rows for the last month and the change in % (indicated by ▲ or ▼) from the previous month.
  * a line graph displays the ◼︎ [!UICONTROL Monthly ingested rows].<br/>To see a popup that displays the number of monthly ingested rows for a month, hover over any data point in the line graph.


For [!UICONTROL Reportable rows]:

* A panel displays total reportable rows that include all the events data across all the connections updated on every 2nd day of a month. Within the panel:
  * a box displays the cumulative total number of reportable rows.
  * a box displays the total number of reportable rows for the last month and the change in % (indicated by ▲ or ▼) from the previous month.
  * a line graph displays the ◼︎ [!UICONTROL Monthly reportable rows].<br/>To see a popup that displays the number of cumulative reportable rows for a specific month, hover over any data point in the line graph.
  * a line graph displays the ◼︎ [!UICONTROL Cumulative reportable rows].<br/>To see a popup that displays the number of monthly reportable rows for a month, hover over any data point in the line graph.


>[!MORELIKETHIS]
>
>[View, troubleshoot, and modify connection settings](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/connections/connections-details-experience-in-cja.html) tutorial.
