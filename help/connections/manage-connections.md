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

The [!UICONTROL List] interface shows a table of all connections available. 

### Search for a connection

You can quickly search for a connection using the Search ![Search](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) box.

### Apply a filter to the list of connections

To apply a filter to the list of connections, select the filter icon, then select from the following filter options:

| Filter option | Description | 
|---------|----------|
| **[!UICONTROL Datasets]** | Only connections that are associated with the datasets you select are displayed. |
| **[!UICONTROL Owner]** | Only connections owned by the people you select are displayed. |
| **[!UICONTROL Sandbox]** | Only connections available in the sandboxes you select are displayed. |
| **[!UICONTROL Use in CJA]** | Select **[!UICONTROL On]** to show only connections that are enabled for use with Customer Journey Analytics. Select **[!UICONTROL Off]** to show only connections that are not yet enabled for use with Customer Journey Analytics. |

### Available columns

The following columns or icons are available in the table.

| Column or Icon | Description |
| --- | --- |
| [!UICONTROL Name] | The connection's friendly name. To see the details of the connection, select the hyperlinked name. See [Connection details](#connection-details). |
| ![Information](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) | To view information about [!UICONTROL Datasets included], [!UICONTROL Sandbox], [!UICONTROL Owner], and more, select ![Information](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) next to the connection name.<p>A popup window displays details. <p><img src="./assets/conn-info.png" alt="View connection info" width="400"/> |
| ![Data view](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) | To [create a data view](#create-a-data-view) for the connection, select ![Data view](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg). This icon only shows when no data view is already associated with the connection. |
| ![More](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) | Select ![More](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) to: <p>![Edit](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) [Edit](#edit-a-connection) a connection.<p>![Delete](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) [Delete](#delete-a-connection) a connection.<p>![Data view](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) [Create new data view](#create-a-data-view). To create additional data views for the connection. |
| [!UICONTROL Datasets] | One or more links to the datasets that are part of the connection. You can select the dataset hyperlink to view the dataset in the connection. If more datasets are part of the selected connection, select **[!UICONTROL +*x* more]** to show a **[!UICONTROL Datasets included]** panel. This panel shows links to all datasets and an option to search for a specific dataset that is part of the connection.<p><img src="./assets/datasets-included.png" alt="Datassets included" width="400"/><p>Selecting a dataset name opens the dataset in the Experience Platform UI in a new tab. |
| [!UICONTROL Sandbox] | The [Experience Platform sandbox](https://experienceleague.adobe.com/en/docs/experience-platform/sandbox/home) from which this connection draws its datasets. This sandbox was selected when you first created the connection. It cannot be changed.|
| [!UICONTROL Owner] | The person who created the connection. |
| [!UICONTROL Import new data] | The status of importing new data for datasets: <p>![Status green](assets/status-green.svg)) &nbsp;&nbsp;&nbsp;**[!UICONTROL _x_ On]** for datasets configured to import new data, and<p>![Status gray](assets/status-gray.svg)&nbsp;&nbsp;&nbsp;**[!UICONTROL _x Off_]** for datasets not configured to import new data. |
| [!UICONTROL Date created] | The timestamp when the connection was created. |
| [!UICONTROL Last modified] | The timestamp when the connection is last updated. |
| [!UICONTROL Backfill data] | The status for backfill data across datasets.<p>![Status red](assets/status-red.svg)&nbsp;&nbsp;&nbsp;**[!UICONTROL _x_ backfills failed]** for number of failed backfills across datasets,<p>![Status orange](assets/status-orange.svg)&nbsp;&nbsp;&nbsp;**[!UICONTROL _x_ backfills processing]** for number of processing backfills across datasets,<p>![Status green](assets/status-green.svg)&nbsp;&nbsp;&nbsp;**[!UICONTROL _x_ backfills completed]** for number of completed backfills for datasets, and<p>![Status gray](assets/status-gray.svg)&nbsp;&nbsp;&nbsp;**[!UICONTROL _Off_]** in case no backfills are defined for the datasets in the connection. |
| [!UICONTROL Integrations] | Shows any Experience Platform applications that are enabled with the connection.  |
| [!UICONTROL Use in CJA] | Shows whether the connection has been enabled for use with Customer Journey Analytics. |

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

### Use a Journey Optimizer connection in Customer Journey Analytics {#use-connection-in-cja}

>[!IMPORTANT]
>When you enable a Journey Optimizer connection for use with Customer Journey Analytics as described in this section, each row of data within the connection counts toward your billable data allotment each month for Customer Journey Analytics and appears within the Connections Usage UI. Select the **[!UICONTROL Use in CJA]** option on the connection only if you are comfortable with these additional costs. 
>

You can use a Journey Optimizer connection in Customer Journey Analytics to bring the following additional value to your connection:

* Perform in-depth analysis of Journey Optimizer data within Customer Journey Analytics (by using the **[!UICONTROL Analyze in CJA]** option within Journey Optimizer).

  For more information, see [Analyze in Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/reporting/channel-report/report-cja-manage#cja-template) in the Journey Optimizer documentation. 

* Edit the Journey Optimizer connection and associated data views.

  For more information about editing options, see [Edit a connection](#edit-a-connection).

To enable this functionality, your organization needs access to Customer Journey Analytics. If you don't have access, contact your Adobe sales representative. 

After you have access to Customer Journey Analytics, you must allow the Journey Optimizer connection to be used in Customer Journey Analytics:

1. Locate the Journey Optimizer connection that you want to use with Customer Journey Analytics. 

   1. Select the Filter icon on the **[!UICONTROL Connections]** tab.

   1. In the **[!UICONTROL Use in CJA]** section, select **[!UICONTROL Off]**.

      This displays all connections that are not currently configured for use in Customer Journey Analytics.

   1. Select the Journey Optimizer connection that you want to use in Customer Journey Analytics. 

1. In the Journey Optimizer connection, select **[!UICONTROL Use in CJA]**.

   The following **[!UICONTROL Use this connection in Customer Journey Analytics]** dialog displays:

   <!-- add screenshot -->

1. After you understand the costs associated with enabling this connection in Customer Journey Analytics, enable the toggle, **[!UICONTROL Use connection in CJA]**.

1. Select **[!UICONTROL Use connection]**. <!-- double-check these dialog button names -->

#### Remove the connection from Customer Journey Analytics

You can remove the connection from Customer Journey Analytics at any time. However, removing the Journey Optimizer connection from Customer Journey Analytics after it is being used results in the following:

* The connection and any associated data views are reset to their default state. 

* You can no longer perform in-depth analysis of Journey Optimizer data within Customer Journey Analytics

* You can no longer edit the Journey Optimizer connection and associated data views.

To remove the connection from Customer Journey Analytics:

1. When editing a Journey Optimizer connection, select **[!UICONTROL Remove from CJA]**.

   The following **[!UICONTROL Remove this connection from Customer Journey Analytics]** dialog displays:

   <!-- add screenshot -->

1. Disable the option, **[!UICONTROL Remove connection from CJA]**.

1. Select **[!UICONTROL Remove connection]**.

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
| Date range selector | Edit start date, end date, or select ![Calendar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) to open the date range selector. In the date range selector, select a date range by using one of the predefined periods (for example **[!UICONTROL Last 6 months]**) or use the calendar to select start and end date. Select **[!UICONTROL Apply]** to apply the new date range.|
| [!UICONTROL Records of event data available] | The total number of event dataset rows available for reporting, **for the entire connection**. This count is independent of any calendar settings. The count changes if you select a dataset from the dataset selector or by selecting a dataset in the table. Once data is added, there is a latency of 1-2 hours to get the data to appear in reporting. |
| [!UICONTROL Metrics] | Summarize the event, lookup, profile and summary dataset records that are added, skipped, and deleted, and the number of batches added. These metrics are based on **the dataset and date range you have selected**.<p>Select **[!UICONTROL Check detail]** to show the **[!UICONTROL Check skipped detail]** popup. The popup lists the number of skipped records and the reason for all event datasets or selected dataset.<p><img src="./assets/skipped-records.png" width="500"/><p>Select ![Info](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) popup with more information. For some skipped reasons, like [!UICONTROL Empty visitor ID], the popup displays Sample PSQL for EQS (Experience Platform for Query Service) you can use in [Query Service](https://experienceleague.adobe.com/en/docs/experience-platform/query/home) to query for the skipped records in the dataset. Select ![Copy](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) **[!UICONTROL Copy sample PSQL for EQS]** to copy the SQL. |
| [!UICONTROL Records added] | Indicates how many rows were added in the selected time period, **for the dataset and date range you have selected**. Updated every 10 minutes. |
| [!UICONTROL Records skipped] | Indicates how many rows were skipped in the selected time period, **for the dataset and date range you have selected**. Reasons for skipping records include: missing timestamps, missing or invalid person ID, and so forth. Updated every 10 minutes. <p>Invalid person IDs (such as `undefined`, or `00000000`, or any combination of numbers and letters in a [!UICONTROL Person ID] that appear in an event more than 1 million times in a given month) are IDs that cannot be attributed to any specific user or person. These rows cannot be ingested into the system and result in error-prone ingestion and reporting. To fix invalid person IDs, you have 3 options:<ul><li>Use [Stitching](/help/stitching/overview.md) to populate the undefined or all-zero user IDs with valid user IDs.</li><li>Blank out the user ID, which are then kipped during ingestion (preferable to invalid or all-zero user IDs).</li><li>Fix any invalid user IDs in your system before ingesting the data.</li></ul> |
| [!UICONTROL Records] deleted | Indicates how many rows were deleted in the selected time period, **for the dataset and date range you have selected**. Someone might have deleted a dataset in [!DNL Experience Platform], for example. Updated every 10 minutes.<p>In some scenarios, this value can also include records replaced, as with stitching or some lookup dataset updates. Consider this example:</p><ul><li>You upload one record to an XDM Individual Profile dataset, which Customer Journey Analytics is configured to ingest as profile lookup data. In the connection details, this dataset would display 1 record added.</li><li>You upload a duplicate of the original record into the same AEP dataset, which now contains two records. Customer Journey Analytics ingests the additional record from the profile lookup dataset. Seeing that it has already ingested a profile record in the connection for that person ID, Customer Journey Analytics deletes its earlier version and adds the new profile data. In the connection details, this action would represent 1 record added and 1 record deleted, because Customer Journey Analytics only retains the most recent profile lookup data for any ingested person ID.</li><li>In total, the AEP dataset contains two records that happen to be identical. Separately, the Customer Journey Analytics connection details display the status of its ingested data: 2 records added and 1 record deleted for this profile dataset. </li></ul> |
| ![Search](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) _Search dataset name or ID_ | Dataset search field. You can search the datasets table by dataset name or [!UICONTROL Dataset ID]. |
| [!UICONTROL Datasets table] | The datasets that are part of the connection. |
| [!UICONTROL Datasets] | The name of the dataset that is part of the connection. You can select the hyperlink to open the dataset in the Experience Platform UI in a new tab. You can select the row or the checkbox to show details for the selected dataset only. |
| [!UICONTROL Dataset ID] | Automatically generated by Experience Platform. |
| [!UICONTROL Records added] | The number of dataset records (rows) added to a connection during the selected time interval. |
| [!UICONTROL Records skipped] | The number of dataset records (rows) skipped during data transfer for a connection during the selected time interval. |
| [!UICONTROL Records deleted] | The number of dataset records (rows) removed from a connection during the selected time interval. |
| [!UICONTROL Batches added] | The number of dataset batches have been added to a connection. |
| [!UICONTROL Last added] | The timestamp of the latest batch from the dataset that has been added to a connection.  |
| [!UICONTROL Data source type] | The source type of the dataset. You define the source type when creating a connection. |
| [!UICONTROL Dataset type] | The dataset type for this dataset. Type can be [!UICONTROL Event], [!UICONTROL Profile], [!UICONTROL Lookup], or [!UICONTROL Summary]. [Learn more](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-connections/create-connection)  |
| Schema | The Experience Platform schema that the dataset is based on.  |
| [!UICONTROL Import new data] | The status of importing new data for the dataset: <p>![Status green](assets/status-green.svg)&nbsp;&nbsp;&nbsp;**[!UICONTROL _x_ On]** if dataset is configured to import new data, and<p>![Status gray](assets/status-gray.svg)&nbsp;&nbsp;&nbsp;**[!UICONTROL _x Off_]** if dataset is configured not to import new data import. |
| [!UICONTROL Transform data] | The transformation status of applicable B2B lookup datasets. See [Transform datasets for B2B lookups](transform-datasets-b2b-lookups.md) for more information.<p>![Status green](assets/status-green.svg)&nbsp;&nbsp;&nbsp;**[!UICONTROL _x_ On]** for applicable datasets enabled for transformation, <p>![Status gray](assets/status-gray.svg)&nbsp;&nbsp;&nbsp;**[!UICONTROL _x Off_]** for applicable datasets not enabled for transformation, and<p>**[!UICONTROL N/A]** for all other datasets, not applicable for transformation.| 
| [!UICONTROL Backfill data] | The status of backfill data for the dataset.<p>![Status red](assets/status-red.svg)&nbsp;&nbsp;&nbsp;**[!UICONTROL _x_ backfills failed]** for number of failed backfills,<p>![Status red](assets/status-orange.svg)&nbsp;&nbsp;&nbsp;**[!UICONTROL _x_ backfills processing]** for number of processing backfills,<p>![Status green](assets/status-green.svg)&nbsp;&nbsp;&nbsp;**[!UICONTROL _x_ backfills completed]** for number of backfills completed, and<p>![Status gray](assets/status-gray.svg)&nbsp;&nbsp;&nbsp;**[!UICONTROL _Off_]** in case backfills are not configured. |
| [!UICONTROL Import new data] | The status of importing new data for the dataset: <p>![Status green](assets/status-green.svg)&nbsp;&nbsp;&nbsp;**[!UICONTROL _x_ On]** if the dataset is configured to import new data, and<p>![Status gray](assets/status-gray.svg)&nbsp;&nbsp;&nbsp;**[!UICONTROL _x Off_]** if the dataset is configured not to import new data. |
| [!UICONTROL Backfill data] | The status of backfill data for the dataset.<p>![Status red](assets/status-red.svg)&nbsp;&nbsp;&nbsp;**[!UICONTROL _x_ backfills failed]** for number of failed backfills,<p>![Status red](assets/status-orange.svg)&nbsp;&nbsp;&nbsp;**[!UICONTROL _x_ backfills processing]** for number of processing backfills,<p>![Status green](assets/status-green.svg)&nbsp;&nbsp;&nbsp;**[!UICONTROL _x_ backfills completed]** for number of backfills completed, and<p>![Status gray](assets/status-gray.svg)&nbsp;&nbsp;&nbsp;**[!UICONTROL _Off_]** in case no backfills are configured. |

>[!IMPORTANT]
>
>Any data ingested before August 13, 2021 is not reflected in the [!UICONTROL Connections] interface.

#### Connection panel

When no dataset is selected in the datasets table, a panel on the right side of the Connections interface shows connection options and details.

| Options | Description |
| --- | --- |
| ![Refresh](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) [!UICONTROL Refresh] |To refresh the connection and allow recently added records to be reflected, select ![Refresh](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) **[!UICONTROL Refresh]**.  |
| ![Delete](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Delete]** | [Delete](#delete-a-connection) this connection.  |
| ![Add data view](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Create data view]** | [Create a data view](#create-a-data-view) based on this connection. See [Data views](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/data-views) for more information.|
| **[!UICONTROL Use in CJA]** | Use a Journey Optimizer connection in Customer Journey Analytics to bring additional value to your Journey Optimizer connection. For more information, see [Use a Journey Optimizer connection in Customer Journey Analytics](#use-a-journey-optimizer-connection-in-customer-journey-analytics).|
| [!UICONTROL Connection name] | The friendly name of the connection. |
| [!UICONTROL Connection description] | A more detailed description that describes the purpose of this connection. |
| [!UICONTROL Sandbox] | The [Experience Platform sandbox](https://experienceleague.adobe.com/en/docs/experience-platform/sandbox/home) from which this connection draws its dataset/s. This sandbox was selected when you first created the connection. It cannot be changed. |
| [!UICONTROL Connection ID] | This ID is generated in Experience Platform. You can use ![Copy](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) to copy the ID.  |
| [!UICONTROL Data views using connection] | Lists all the data views that use this connection. |
| [!UICONTROL Import new data] | The status of importing new data for datasets: <p>![Status green](assets/status-green.svg)&nbsp;&nbsp;&nbsp;**[!UICONTROL _x_ On]** for how many datasets are configured to import new data, and<p>![Status gray](assets/status-gray.svg)&nbsp;&nbsp;&nbsp;**[!UICONTROL _x Off_]** for how many datasets new data import is turned off. |
| [!UICONTROL Backfill data] | The status of backfill data for datasets.<p>![Status red](assets/status-red.svg)&nbsp;&nbsp;&nbsp;**[!UICONTROL _x_ backfills failed]** for number of failed backfills across datasets,<p>![Status red](assets/status-orange.svg)&nbsp;&nbsp;&nbsp;**[!UICONTROL _x_ backfills processing]** for number of processing backfills across datasets,<p>![Status green](assets/status-green.svg)&nbsp;&nbsp;&nbsp;**[!UICONTROL _x_ backfills completed]** for number of completed backfills for datasets, and<p>![Status gray](assets/status-gray.svg)&nbsp;&nbsp;&nbsp;**[!UICONTROL _Off_]** in case no backfills are defined for the datasets in the connection. |
| Transform data | The transformation status of applicable B2B lookup datasets. See [Transform datasets for B2B lookups](transform-datasets-b2b-lookups.md) for more information.<p>![Status green](assets/status-green.svg)&nbsp;&nbsp;&nbsp;**[!UICONTROL _x_ On]** for number of datasets enabled for transformation.| 
| [!UICONTROL Created by] | The name of the person who created the connection. |
| [!UICONTROL Last modified] | The timestamp of the last change to the connection. |
| [!UICONTROL Last modified by] | The person who last modified the connection. |

#### Dataset panel

When a dataset is selected in the datasets table, a panel on the right side of the Connections interface show details for the selected dataset.

| Details | Description |
| --- | --- |
| [!UICONTROL Person ID] | An identity that was defined in the dataset schema in the Experience Platform. This identity is the Person ID that you selected during the creation of the connection. If you create a connection that includes datasets with different IDs, the reporting reflects that. To merge datasets, you need to use the same Person ID across datasets. |
| [!UICONTROL Key] | The key that you have specified for a lookup dataset. |
| [!UICONTROL Matching Key] | The matching key that you have specified for a lookup dataset. |
| [!UICONTROL Timestamp] | The timestamp defined for an event dataset. |
| [!UICONTROL Records available] | The total number of rows ingested for this dataset, for the particular time period selected through the calendar. There is no latency in terms of getting the data to appear in reporting, once it is added. However, when you create a brand new connection, there is [latency](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-faq). |
| [!UICONTROL Records added] | How many rows were added in the selected time period. |
| [!UICONTROL Records deleted] | How many records were deleted during the selected time period. |
| [!UICONTROL Batches added] | How many data batches were added into this dataset.  |
| [!UICONTROL Records skipped] | How many rows were skipped during ingestion in the selected time period.<p>Reasons for skipping records include: Missing timestamps, missing or invalid person ID, and so forth. Updated every 10 minutes.<p>Invalid person IDs (such as `undefined`, or `00000000`, or any combination of numbers and letters in a [!UICONTROL Person ID] that appears in an event more than 1 million times in a given month) are IDs that cannot be attributed to any specific user or person. These rows cannot be ingested into the system and result in error-prone ingestion and reporting. To fix invalid person IDs, you have 3 options:<ul><li>Use [Stitching](/help/stitching/overview.md) to populate the undefined or all-zero user IDs with valid user IDs.</li><li>Blank out the user ID, which is then skipped during ingestion (preferable to invalid or all-zero user IDs).</li><li>Fix any invalid user IDs in your system before ingesting the data.</li></ul> |
| [!UICONTROL Last added] | The timestamp the last batch was added. |
| [!UICONTROL Import new data] | The status of importing new data for the dataset: <p>![Status green](assets/status-green.svg)&nbsp;&nbsp;&nbsp;**[!UICONTROL _x_ On]** if the dataset is configured to import new data, and<p>![Status gray](assets/status-gray.svg)&nbsp;&nbsp;&nbsp;**[!UICONTROL _x Off_]** if the dataset is configured not to import new data.  |
| [!UICONTROL Backfill data] | The status of backfill data for the dataset.<p>![Status red](assets/status-red.svg)&nbsp;&nbsp;&nbsp;**[!UICONTROL _x_ backfills failed]** for number of failed backfills,<p>![Status red](assets/status-orange.svg)&nbsp;&nbsp;&nbsp;**[!UICONTROL _x_ backfills processing]** for number of processing backfills,<p>![Status green](assets/status-green.svg)&nbsp;&nbsp;&nbsp;**[!UICONTROL _x_ backfills completed]** for number of backfills completed, and<p>![Status gray](assets/status-gray.svg)&nbsp;&nbsp;&nbsp;**[!UICONTROL _Off_]** in case no backfills are configured.<p>To show a dialog with an overview of the past backfills for the dataset, select <img src="./assets/pastbackfill.svg" alt="Past backfills" width="15"/> **[!UICONTROL Past backfills]**. |
| [!UICONTROL Data source type] | Data source type as defined when adding the dataset to the connection. |
| [!UICONTROL Dataset type] | Either [!UICONTROL Event], [!UICONTROL Profile], [!UICONTROL Lookup], or [!UICONTROL Summary]. [Learn more](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-connections/create-connection)  |
| [!UICONTROL Schema] | The Experience Platform schema that this dataset is based on. |
| [!UICONTROL Dataset ID] | This dataset ID is generated in Experience Platform. |


## Usage {#connections-usage}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_keyusagemetrics"
>title="Key usage metrics" 
>abstract="Provide monthly and total data for core and historical reportable rows."
<!-- markdownlint-enable MD034 -->


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_monthlyingestedrows"
>title="Monthly ingested rows"
>abstract="Measures the total number of records added to the system each month to provide insights into data growth and ingestion rates."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_monthlyreportablerows"
>title="Monthly reportable rows"
>abstract="Tracks the number of rows available for reporting. Reportable rows are the ingested rows minus the  rows that are skipped and deleted during ingestion. Reportable rows serve as a key metric for billing and data usage."
<!-- markdownlint-enable MD034 -->


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_detailbreakdown"
>title="Detail breakdown."
>abstract="You can view detailed metrics by connection, dataset, sandbox, and tags, with the option to download a CSV file of the data."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_otherdatasets"
>title="Other datasets"
>abstract="For the months before September 2024, data was collected at the dataset level and is displayed as *Other datasets* for clarity. Starting from September 2024, data is gathered at a granular dataset level, and *Other datasets* will no longer appear."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_unknowndatasetsorconnections"
>title="Unknown datasets or connections"
>abstract="Unknown datasets or connections are displayed using their IDs."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_datanotavailable"
>title="Data not available"
>abstract="Historical data prior to September 2024 is not available due to system limitations. Metrics are collected and displayed starting from September 2024 onwards. The chart shows the last 18 months on the timeline, and future data will appear as the data becomes available."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_corereportablerows"
>title="Core reportable rows"
>abstract="Displays the total number of rows available for the past 13 months. For example, on February 1, 2024, the number shows the total rows available with an event timestamp from January 2023 to January 2024."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_historicalreportablerows"
>title="Historical reportable rows"
>abstract="Displays the total number of rows available for the period older than 13 months. For example, on February 1, 2024, the number shows the total rows available with an event timestamp older than January 2023."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_keyusagemetrics"
>title="Key usage metrics" 
>abstract="Provide monthly and total data for core and historical reportable rows."
<!-- markdownlint-enable MD034 -->


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_monthlyingestedrows"
>title="Monthly ingested rows"
>abstract="Measures the total number of records added to the system each month to provide insights into data growth and ingestion rates."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_monthlyreportablerows"
>title="Monthly reportable rows"
>abstract="Tracks the number of rows available for reporting. Reportable rows are the ingested rows minus the  rows that are skipped and deleted during ingestion. Reportable rows serve as a key metric for billing and data usage."
<!-- markdownlint-enable MD034 -->


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_detailbreakdown"
>title="Detail breakdown."
>abstract="You can view detailed metrics by connection, dataset, sandbox, and tags, with the option to download a CSV file of the data."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_otherdatasets"
>title="Other datasets"
>abstract="For the months before September 2024, data was collected at the dataset level and is displayed as *Other datasets* for clarity. Starting from September 2024, data is gathered at a granular dataset level, and *Other datasets* will no longer appear."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_unknowndatasetsorconnections"
>title="Unknown datasets or connections"
>abstract="Unknown datasets or connections are displayed using their IDs."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_datanotavailable"
>title="Data not available"
>abstract="Historical data prior to September 2024 is not available due to system limitations. Metrics are collected and displayed starting from September 2024 onwards. The chart shows the last 18 months on the timeline, and future data will appear as the data becomes available."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_corereportablerows"
>title="Core reportable rows"
>abstract="Displays the total number of rows available for the past 13 months. For example, on February 1, 2024, the number shows the total rows available with an event timestamp from January 2023 to January 2024."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_historicalreportablerows"
>title="Historical reportable rows"
>abstract="Displays the total number of rows available for the period older than 13 months. For example, on February 1, 2024, the number shows the total rows available with an event timestamp older than January 2023."

<!-- markdownlint-enable MD034 -->


The [!UICONTROL Usage] interface shows the usage of ingested and reportable rows across all connections. If not selected, select the **[!UICONTROL Usage]** tab to access the interface.

This interface supports you to determine whether your Customer Journey Analytics usage complies with what is contractually agreed upon. In addition to monitoring purposes, you can use the Usage interface to plan your Customer Journey Analytics license renewal.

The Usage interface uses the folowing metrics

| Metric name | Description |
|---|---|
| Historical reportable rows | Count of rows for the period older than 13 months. |
| Core reportable rows | Count of rows over the last 13 months. | 
| Ingested rows | How many rows are ingested for the specific period. |
| Reportable rows | How many rows of data do you have as part of the connection for the specific period. |
| Cumulative rows | How many rows are ingested up until the specific month. |

>[!NOTE]
>
>Data is collected, starting from July 2024 for the core, historical, and total records. Reach out to your account manager for earlier historical data.
>



The Usage interface consists of two panels:

* The **[!UICONTROL Key usage metrics]** panel: provides core and historical data reportable rows. The panel also tracks percentage changes compared to the previous month for both core and historical data rows.
  
  The panel displays in a visualization: 
  
  * **[!UICONTROL Core data reportable rows]**.

    How many reportable rows do you have over the last 13 months. The summary number is the number of core reportable rows (for example, 741M) for the last month (for example, December 2024).
    
  * **[!UICONTROL Historical data reportable rows]**.

    How many reportable rows do you have for the period older than 13 months. The summary number is the number of historical reportable rows (for example, 127M) for the last month (for example, December 2024). 
    
  When you hover over any stacked bar in the visualization, a popup shows the number of rows for that specific part of the bar (for example).


  ![Key Usage Metrics](assets/usage-key-usage-metrics.png)

* A combined panel, showing three subpanels for:

  +++ Ingested rows

  The **[!UICONTROL Ingested rows]** subpanel measures the total number of records added to the system each month, providing insight into data growth and ingestion rates. The subpanel provides a summary of this month's total ingested rows and the change from the previous month.

  ![Ingested rows](assets/usage-ingested-rows.png)

  You can hover over data points in the visualization to display a popup with more details.

  +++

  +++ Reportable rows

  The **[!UICONTROL Reportable rows]** visualization tracks the number of rows available for reporting by subtracting skipped and deleted rows from ingested rows, serving as a key metric for billing and data usage. The subpanel provides two summaries:
  
  * **[!UICONTROL Last month total]**: A summary of total reportable rows up until this month.
  * **[!UICONTROL This month]**: A summary of this month's total reportable rows and the change from the previous month.

  ![Reportable rows](assets/usage-reportable-rows.png)

  You can hover over data points in the visualizations to display a popup with more details.

  +++

  +++ Detail breakdown

  You can use the **[!UICONTROL Detail breakdown]** table to view detailed metrics by connection, dataset, sandbox, and tags. Datasets are reported using ids instead of names, as dataset names can be modified during a reporting period. Unknown datasets or connections are reported using ids.

  For the months before September 2024, data was collected at the dataset level and is displayed as [!UICONTROL Other datasets] for clarity. Starting from September 2024, data is gathered at a granular dataset level, and [!UICONTROL Other datasets] does no longer appear.

  * To change the breakdown, select a combination for **[!UICONTROL View by]** and **[!UICONTROL Breakdown by]**.

    | **[!UICONTROL View by]** options | **[!UICONTROL Breakdown by]** options |
    |---|---|
    | **[!UICONTROL Connection]** | **[!UICONTROL -]** and **[!UICONTROL Dataset]** |
    | **[!UICONTROL Dataset]** | **[!UICONTROL -]** |
    | **[!UICONTROL Sandbox]** | **[!UICONTROL Connection]** | 
    | **[!UICONTROL Tag]** | **[!UICONTROL Connection]** | 

  ![Detail breakdown](assets/usage-detail-breakdown.png)

  +++

  You can define a **[!UICONTROL Time range]** in months to report on. Use ![Calendar](/help/assets/icons/Calendar.svg) to select the time range. 

>[!MORELIKETHIS]
>
>[View, troubleshoot, and modify connection settings](https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/connections/connections-details-experience-in-cja) tutorial.
