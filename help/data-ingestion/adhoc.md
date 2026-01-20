---
title: Ingest and use ad hoc data
description: Explain how to ingest and use ad hoc in Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
role: Admin
exl-id: 17b5842f-dc81-481f-8b21-dc90a133adcf
---
# Ingest and use ad hoc data

This quick start guide explains how you can ingest ad hoc data into Experience Platform and then use that data in Customer Journey Analytics.

To accomplish this, you need to:

- **Create a dataset with a CSV file** in Experience Platform. This workflow defines the model (schema) of the data that you want to collect and where to collect the data (dataset).

- **Set up a connection** in Customer Journey Analytics. This connection should (at least) include your Experience Platform ad hoc dataset.

- **Set up a data view** in Customer Journey Analytics to define metrics and dimension from the fields in your ad hoc data that you want to use in Analysis Workspace.

- **Set up a project** in Customer Journey Analytics to build your reports and visualizations.



>[!NOTE]
>
>This quick start guide is a simplified guide on how to ingest ad hoc data using into Experience Platform and use that ad hoc data in Customer Journey Analytics. It is highly recommended to study the additional information when referred to.


## Create a dataset with a CSV file

For this quick start, you want to use a CSV file that represents lookup data and contains information similar to the one shown below.

|  _id | tracking_code | ad_group    | campaign_name |
| ---: | :---          | :---        | :---          |
|    1 | abc123        | abc-adgroup | 123 Campaign  |
|    2 | def123        | def-adgroup | 123 Campaign  |
|    3 | ghi123        | ghi-adgroup | 123 Campaign  |
|    4 | abc456        | abc-adgroup | 456 Campaign  |
|    5 | def456        | def-adgroup | 456 Campaign  |

>[!NOTE]
>
>Use ad hoc datasets and schemas for record based (lookup, profile) data. Ad hoc datasets and schemas are less suited and should not be considered for time-series (event, summary) data.

You do not need to create an XDM schema for ad hoc data. Experience Platform supports a workflow that, based on the data in the CSV file:

1. Creates an ad hoc schema automatically. That schema conforms to the columns of the CSV file.
1. Creates a dataset that contains the data from the CSV file.

To start the workflow:

1. In the Experience Platform interface, in the left rail, select **[!UICONTROL Workflows]**.
1. Select ![DataAdd](/help/assets/icons/DataAdd.svg) **[!UICONTROL Create dataset from CSV file]**.
1. Select **[!UICONTROL Launch]** from the right pane.
1. In the **[!UICONTROL Workflows]** > **[!UICONTROL Create dataset from CSV file]** wizard:
   1. In the **[!UICONTROL Configure dataset]** step:
      1. Enter a **[!UICONTROL Name]** for the dataset. For example: `Sample Data From CSV`. 
      1. Add an optional **[!UICONTROL Description]**. For example: `Sample data from a CSV file`.
      1. Add one or more optional **[!UICONTROL Tags]**, or select one or more existing **[!UICONTROL Tags]**.
         
         ![Configure ad hoc dataset configure](assets/adhoc-dataset-configure.png)

      1. Select **[!UICONTROL Next]**.
   1. In the **[!UICONTROL Add data]** step:
      1. Select **[!UICONTROL Choose Files]** to select your CSV file from your computer or network. Alternatively, drag and drop the file from its location on your computer or network onto **[!UICONTROL Drag and drop files]**. The file is uploaded and **[!UICONTROL Sample data]** is displayed.
      1. Enable or disable **[!UICONTROL Error diagnostics]** and **[!UICONTROL Enable partial ingestion]** in line with your preferences. When you **[!UICONTROL Enable Partial ingestion]**, you can define an **[!UICONTROL Error threshold %]**.
         
         ![Add data to an ad hoc dataset](assets/adhoc-dataset-adddata.png)

      1. Select **[!UICONTROL Finish]**.

After the data is successfully prepared and uploaded, you are redirected to **[!UICONTROL Datasets]** in the Experience Platform interface.<br/> You see the **[!UICONTROL Dataset activity]** for your **[!UICONTROL Sample Data from CSV]** dataset with the status ![StatusOrange](/help/assets/icons/StatusOrange.svg) **[!UICONTROL Processing]**.

![Dataset activity for ad hoc data](assets/datasets-dataset-activity.png)

To inspect the ad hoc data:

1. In the Experience Platform interface, in the left rail, select **[!UICONTROL Datasets]**.
1. Select the **[!UICONTROL Browse]** tab in **[!UICONTROL Datasets]**. You should see your dataset listed. 
1. Select the name of the schema from the **[!UICONTROL Schema]** column. For example: **[!UICONTROL Sample Data From CSV…]**

   ![Select schema for ad hoc dataset](assets/adhoc-schema-selection.png)

1. In the popup, select the **[!UICONTROL Schema name]**. For example: **[!UICONTROL Sample Data From CSV - adhoc schema - XXXXXXXXXXX]**. You are redirected to the **[!UICONTROL Schemas]** > **[!UICONTROL Sample Data From CSV - adhoc schema - XXXXXXXXXXX]** interface.
   
In the **[!UICONTROL Schemas]** > **[!UICONTROL Sample Data From CSV - adhoc schema - XXXXXXXXXXX]** interface:

- Select the topmost tenant name object underneath **[!UICONTROL Schemas]** > **[!UICONTROL Sample Data From CSV - adhoc schema - XXXXXXXXXXX]** to reveal the fields within the object. The fields within the object represent the structure of the CSV file. The schema is created automatically based on the upload of the ad hoc data.

  ![Ad hoc schema](dataset/../assets/adhoc-schema.png) 

   >[!NOTE]
   >
   >The workflow defines all fields in the schema to be of type String. You can not change this type at a later stage. If you need more flexibility in the definition of an ad hoc schema, consider [using the API to create an ad hoc schema](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/tutorials/ad-hoc) and then use the [Create dataset from schema](https://experienceleague.adobe.com/en/docs/experience-platform/catalog/datasets/user-guide#schema) workflow.
   > 




## Set up a connection

To use the Experience Platform dataset in Customer Journey Analytics, you create a connection that includes the ad hoc dataset resulting from the [workflow](#create-a-dataset-with-a-csv-file) 

A connection lets you integrate datasets from Experience Platform into Workspace. To report on these datasets, you first have to establish a connection between datasets in Experience Platform and Workspace.

To create your connection:

1. In the Customer Journey Analytics UI, select **[!UICONTROL Connections]**, optionally from **[!UICONTROL Data management]**, in the top menu.

1. Select **[!UICONTROL Create new connection]**.

1. In the **[!UICONTROL Untitled connection]** screen:

   1. Name and describe your connection in **[!UICONTROL Connection Settings]**.

   1. Select the correct sandbox from the **[!UICONTROL Sandbox]** list in **[!UICONTROL Data settings]** and select the number of daily events from the **[!UICONTROL Average number of daily events]** list.

      ![Connection Settings](./assets/cja-connections-1.png)
    
   1. Select **[!UICONTROL Add datasets]**. 
    
1. In the **[!UICONTROL Select datasets]** step in **[!UICONTROL Add datasets]**:
    
   1. Select the dataset that you created earlier, for example **[!UICONTROL Sample Data From CSV]**, and any other dataset you want to include in your connection. The ad hoc datasets do have the **[!UICONTROL Adhoc]** [!UICONTROL Dataset type].

      ![Add datasets](./assets/cja-connections-adhoc-2.png)

   1. Select **[!UICONTROL Next]**.

1. In the **[!UICONTROL Datasets settings]** step in **[!UICONTROL Add datasets]**:

   For your ad hoc dataset:

   1. Select the type of ad hoc dataset. For example: **[!UICONTROL Lookup]**. 
   1. Select a **[!UICONTROL Key]** from the available keys defined in the ad hoc schema.
   1. Select a **[!UICONTROL Matching key]** from an event dataset that you have added as part of your connection.
   1. Select the correct data source from the **[!UICONTROL Data source type]** list. If you specify **[!UICONTROL Other]**, then add a description for your data source.

   1. Set **[!UICONTROL Import all new data]** and **[!UICONTROL Dataset backfill existing data]** according to your preferences.

      ![Configure datasets](./assets/cja-connections-3-adhoc.png)

   1. Select **[!UICONTROL Add datasets]**.

   1. Select **[!UICONTROL Save]**.

See [Ad hoc dataset settings](/help/connections/create-connection.md#adhoc-dataset) for more details on the settings available for ad hoc datasets.

>[!IMPORTANT]
>
>On top of the general recommendation not to use ad hoc datasets and schemas for time-series data, you cannot use the **[!UICONTROL Create dataset from CSV]** workflow for time-series data. This workflow defines all fields to be of type String which you cannot modify afterwards. When you add a time-series based dataset (event or summary) to a connection, this type of dataset requires the definition of at least one field of type DateTime.<br/>If you do require to use ad hoc time-series data, consider [using the API to create an ad hoc schema](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/tutorials/ad-hoc#token_type=bearer&expires_in=43197438) and then use the [Create dataset from schema](https://experienceleague.adobe.com/en/docs/experience-platform/catalog/datasets/user-guide#schema) workflow. 


After you create a [connection](/help/connections/overview.md), you can perform various management tasks, such as [selecting and combining datasets](/help/connections/combined-dataset.md), [checking the status of a connection's datasets and the status of data ingestion](/help/connections/manage-connections.md), and more.

## Set up a data view

A data view is a container specific to Customer Journey Analytics that lets you determine how to interpret data from a connection. It specifies all dimensions and metrics available in Analysis Workspace and which columns those dimensions and metrics obtain their data from. Data views are defined in preparation for reporting in Analysis Workspace.

To create your data view:

1. In the Customer Journey Analytics UI, select **[!UICONTROL Data views]**, optionally from **[!UICONTROL Data management]**, in the top menu.

1. Select **[!UICONTROL Create new data view]**.

1. In the **[!UICONTROL Configure]** step:

    1. Select your [connection](#set-up-a-connection) from the **[!UICONTROL Connection]** list.

    1. Name and (optionally) describe your connection.

       ![Data view configure](./assets/cja-dataview-1.png)

    1. Select **[!UICONTROL Save and continue]**.

1. In the **[!UICONTROL Components]** step:

   1. Add any schema field and/or standard component that you want to include to the **[!UICONTROL METRICS]** or **[!UICONTROL DIMENSIONS]** component boxes. Ensure you add relevant fields from the dataset that contains the ad hoc data. To access those fields:

      1. Select **[!UICONTROL Event datasets]**.
      1. Select **[!UICONTROL Adhoc & Relational fields]**.

         ![Data view - adhoc components](assets/cja-dataview-components-adhoc.png)

      1. Drag and drop fields from the ad hoc schemas onto **[!UICONTROL METRICS]** or **[!UICONTROL DIMENSIONS]**.

         
   
   1. Optionally, use [derived fields](/help/data-views/derived-fields/derived-fields.md) to modify any of the ad hoc fields from their default String type and format to another type or format.

   1. Select **[!UICONTROL Save and continue]**.

1. In the **[!UICONTROL Settings]** step:

    Leave the settings as they are and select **[!UICONTROL Save and finish]**.

See [Data views overview](../data-views/data-views.md) for more information on how to create and edit a data view. And what components are available for you to use in your data view and how to use segment and sessions settings.


## Set up a project

Analysis Workspace is a flexible browser tool that allows you to build analyses quickly and share insights based on your data. You use Workspace projects to combine data components, tables, and visualizations to craft your analysis and share with anyone in your organization.

To create your project:

1. In the Customer Journey Analytics UI, select **[!UICONTROL Projects]** in the top menu.

1. Select **[!UICONTROL Projects]** in the left navigation.

1. Select **[!UICONTROL Create project]**.

1. Select **[!UICONTROL Blank project]**.

1. Select your [data view](#set-up-a-data-view) from the list.

1. To create your first report, start dragging and dropping dimensions and metrics on the [!UICONTROL Freeform table] in the [!UICONTROL Panel]. Including those metrics or dimension that are based on your ad hoc data.

See [Analysis Workspace overview](../analysis-workspace/home.md) for more information on how to create projects and build your analysis using components, visualizations, and panels.

>[!SUCCESS]
>
>You have completed all the steps. You started by defining what ad hoc data that you wanted to collect (CSV file). You used the workflow to create an ad hoc dataset and schema from that CSV file. You defined a connection in Customer Journey Analytics to use the ingested ad hoc data and other data. Your data view definition allowed you to specify which dimension and metrics to use and finally you created your first project visualizing and analyzing your data.
