---
title: Ingest and use data from traditional Adobe Analytics
description: Explain how to ingest data from traditional Adobe Analytics
solution: Customer Journey Analytics
feature: Data Ingestion
---

# Ingest and use data from traditional Adobe Analytics

This quick start guide explains how you can use the data collected by Adobe Analytics in Customer Journey Analytics.

>[!PREREQUISITES]
>
>You do have Adobe Analytics licensed and deployed on one or more of your websites, using any of the documented implementation methods:
>
>-   [Implement Analytics using Experience Platform Edge](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/overview.html?lang=en)
>
>-   [Implement Analytics using Adobe Analytics extension](https://experienceleague.adobe.com/docs/analytics/implementation/launch/overview.html?lang=en)
>
>-   [Implement Analytics using Javascript](https://experienceleague.adobe.com/docs/analytics/implementation/js/overview.html?lang=en)

To accomplish this, you need to:

-   **Set up an Adobe Analytics source connector** in Adobe Experience Platform. This will take care of ingesting your current Adobe Analytics data into a dataset in Adobe Experience Platform.

-   **Set up a connection** in Customer Journey Analytics. This connection should (at least) include your Adobe Experience Platform dataset.

-   **Set up a data view** in Customer Journey Analytics to define metrics and dimension you want to use in Analysis Workspace.

-   **Set up a project** in Customer Journey Analytics to build your reports and visualisations.


>[!NOTE]
>
>This is a simplified guide on how to ingest data, using the Adobe Analytics source connector, and use that data in Customer Journey Analytics.  It is higly recommended to study the additional information when referred to.


## Set up an Adobe Analytics source connector

The Adobe Analytics source connector allows you to bring Adobe Analytics report suite data into Adobe Experience Platform.

To create an Adobe Analytics source connector:

1.  In the Platform UI, select **[!UICONTROL Sources]** from the left rail.

2.  Select **[!UICONTROL Adobe applications]** from the list of [!UICONTROL CATEGORIES].

3.  Select **[!UICONTROL Set up]** or **[!UICONTROL Add data]** in the Adobe Analytics tile.

    ![Sources](./assets/sources-overview.png)

4.  Select **[!UICONTROL Report suite]**. From the list of report suites select the one you want to use. 

    ![Report suites](./assets/report-suites.png)

    Select **[!UICONTROL Next]**.

5.  Select **[!UICONTROL Default schema]** as the [!UICONTROL Target schema]. Adobe Experience Platform will automatically create the schema and the corresponding dataset to map all standard fields from the selected Adobe Analytics report suite.

    ![Default schema](./assets/default-schema.png)

    Select **[!UICONTROL Next]**.

6.  Name the data flow and (optionally) provide a description.

    ![Dataflow details](./assets/dataflow-detail.png)

    Select **[!UICONTROL Next]**.

7.  Review the connection and select **[!UICONTROL Finish]**.

    ![Review](./assets/review.png)


Once the connection is created, the dataflow is automatically created to populate a dataset with the Adobe Analytics data from your report suite, including the ingestion of up to 13 months of historical data.

When the initial ingestion completes, your Adobe Analytics report suite data is ready to be used by Customer Journey Analytics.

See [Create an Adobe Analytics source connection in the UI](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en) for a much more comprehensive tutorial.


## Setup a connection

To use the Adobe Experience Platform data in Customer Journey Analytics, you create a connection that includes the data resulting from setting up your schema, dataset and workflow. 

A connection lets you integrate datasets from Adobe Experience Platform into Workspace. In order to report on  these datasets, you first have to establish a connection between datasets in Adobe Experience Platform and Workspace.

To create your connection:

1.  In the Customer Journey Analytics UI, select **[!UICONTROL Connections]** in the top navigation.

2.  Select **[!UICONTROL Create new connection]**.

3.  In the [!UICONTROL Untitled connection] screen:

    Name and describe your connection in [!UICONTROL Connection Settings].

    Select the correct sandbox from the [!UICONTROL Sandbox] list in [!UICONTROL Data settings] and select the number of daily events from the [!UICONTROL Avergage number of daily events] list.

    ![Connection Settings](./assets/cja-connections-1.png)
    
    Select **[!UICONTROL Add datsets]**. 
    
    In the [!UICONTROL Select datasets] step in [!UICONTROL Add datasets]:
    
    -   Select the dataset automatically created by the Adobe Analytics source connector and any other dataset you want to include in your connection.

        ![Add datasets](./assets/cja-connections-2a.png)

    -   Select **[!UICONTROL Next]**.

    In the [!UICONTROL Datasets settings] step in [!UICONTROL Add datasets]:

    -   For each dataset:

        -   Select a [!UICONTROL Person ID] from the available identities defined in the dataset schemas in Adobe Experience Platform.
    
        -   Select the correct data source from the [!UICONTROL Data source type] list. If you specify **[!UICONTROL Other]** then add a description for your data source.

        -   Set **[!UICONTROL Import all new data]** and **[!UICONTROL Dataset backfill existing data]** according to your preferences.

        ![Configure datasets](./assets/cja-connections-3.png)

    -   Select **[!UICONTROL Add datasets]**.

    Select **[!UICONTROL Save]**.

See [Connections overview](../connections/overview.md) for more information on how to create and manage a connection and how to select and combine datasets.

## Setup a data view

A data view is a container specific to Customer Journey Analytics that lets you determine how to interpret data from a connection. It specifies all dimensions and metrics available in Analysis Workspace and which columns those dimensions and metrics obtain their data from. Data views are defined in preparation for reporting in Analysis Workspace.

To create your data view:

1.  In the Customer Journey Analytics UI, select **[!UICONTROL Data views]** in the top navigation.

2.  Select **[!UICONTROL Create new data view]**.

3.  In the [!UICONTROL Configure] step:

    Select your connection from the [!UICONTROL Connection] list.

    Name and (optionally) describe your connection.

    ![Data view configure](./assets/cja-dataview-1.png)

    Select **[!UICONTROL Save and continue]**.

4.  In the [!UICONTROL Components] step:

    Add any schema field and/or standard component you want to include to the [!UICONTROL METRICS] or [!UICONTROL DIMENSIONS] component boxes.

    ![Data view components](./assets/cja-dataview-2.png)

    Select **[!UICONTROL Save and continue]**.

5.  In the [!UICONTROL Settings] step:

    ![Data view settings](./assets/cja-dataview-3.png)

    Leave the settings as they are and select **[!UICONTROL Save and finish]**.

See [Data views overview](../data-views/data-views.md) for more information on how to create and edit a data view, what components are available for you to use in your data view and how to use filter and sessions settings.


## Setup a project

Analysis Workspace is a flexible browser tool that allows you to quickly build analyses and share insights based on your data. You use Workspace projects to combine data components, tables and visualizations to craft your analysis and share with anyone in your organization.

To create your project:

1.  In the Customer Journey Analytics UI, select **[!UICONTROL Projects]** in the top navigation.

2.  Select **[!UICONTROL Projects]** in the left navigation.

3.  Select **[!UICONTROL Create project]**.

    ![Workspace Project](./assets/cja-projects-1.png)

    Select **[!UICONTROL Blank project]**.

    ![Workspace - Blank Project](./assets/cja-projects-2.png)

4.  Select your data view from the list.

    ![Workspace Select Data view](./assets/cja-projects-3.png).

5.  Start dragging and dropping dimensions and metrics on the [!UICONTROL Freeform table] in the [!UICONTROL Panel] to create your first report. As an example, drag `Program Points Balance` and `Page View` as metrics and `email` as dimension to get a quick overview of profiles that have visited your website and also are part of the loyalty program collecting loyalty points.

    ![Workspace - First Report](./assets/cja-projects-5.png)

See [Analysis Workspace overview](../analysis-workspace/home.md) for more information on how to create projects and build your analysis using components, visualization and panels.


>[!SUCCESS]
>
>You have completed all the steps. Starting by setting up the Adobe Analytics data source connector and configuring that connector for your report suite, your Adobe Analytics data is automatically uploaded into Adobe Experience Platform. You defined a connection in Customer Journey Analytics to make use of the ingested Adobe Analytics data and other data. Your data view definition allowed you to specify which dimension and metrics to use and finally you created your first project visualizing and analyzing your data.







