---
title: Ingest and use data using source connectors
description: Explain how to ingest and use data using source connectors in Customer Journey Analytics 
solution: Customer Journey Analytics
feature: CJA Basics
---

# Ingest and use data using source connectors.

This quick start guide explains how you can ingest data into Adobe Experience Platform using a source connector to a data provider and then use that data in Customer Journey Analytics.

To accomplish this, you need to:

-   **Set up a schema and dataset** in Adobe Experience Platform to define the model (schema) of the data that you want to collect and where to actually collect the data (dataset).

-   **Use a source connector** in Adobe Experience Platform to get your data into the dataset configured.

-   **Set up a connection** in Customer Journey Analytics. This connection should (at least) include your Adobe Experience Platform dataset.

-   **Set up a data view** in Customer Journey Analytics to define metrics and dimension that you want to use in Analysis Workspace.

-   **Set up a project** in Customer Journey Analytics to build your reports and visualizations.



>[!NOTE]
>
>This is a simplified guide on how to ingest data using a source connector into Adobe Experience Platform and use it in Customer Journey Analytics. It is highly recommended to study the additional information when referred to.


## Set up a schema and dataset

To ingest data into Adobe Experience Platform, you first need to define which data you want to collect. All data ingested into Adobe Experience Platform must conform to a standard, denormalized structure for it be recognized and acted upon by downstream capabilities and features. Experience Data Model (XDM) is the standard framework that provides this structure in the form of schemas. 

Once you have defined a schema, you use one or more datasets to store and manage the collection of data. A dataset is a storage and management construct for a collection of data, typically a table, that contains a schema (columns) and fields (rows). 

All data that is ingested into Adobe Experience Platform must conform to a pre-defined schema before it can be persisted as a dataset.

### Set up a schema

For this quick start, you want to collect some loyalty data, for example loyalty id, loyalty points, and loyalty status.
For this, you first need to define a schema that models this data.

To set up your schema:

1.  In the Adobe Experience Platform UI, in the left rail, select **[!UICONTROL Schemas]** within [!UICONTROL DATA MANAGEMENT].

2.  Select **[!UICONTROL Create schema]**. Select **[!UICONTROL XDM Individual Profile]** from the list of options.

    ![Create a schema](./assets/create-schema.png)

    >[!INFO]
    >
    >    An Individual Profile schema is used to model the profile _attributes_ (like name, email, gender). An Experience Event schema is used to model the _behavior_ of a profile (like page view, add to cart). 


3.  In the [!UICONTROL Untitled schema] screen:

    1.  Enter a display name for your schema and (optional) a description.

        ![Name your schema](./assets/name-loyalty-schema.png)
    
    2.  Select **[!UICONTROL + Add]** in [!UICONTROL Field groups].

        ![Add field group](./assets/add-field-group-button.png)

        Field groups are reusable collection of objects and attributes that allow you to easily extend your schemas.

    3.  In the [!UICONTROL Add fields groups] dialog, select the **[!UICONTROL Loyalty Details]** field group from the list. 

        ![AEP Web SDK ExperienceEvent fieldgroup](./assets/loyalty-fieldgroup.png)
    
        You can select the preview button, to see a preview of the fields that are part of this field group. 

        ![AEP Web SDK ExperienceEvent fieldgroup preview](./assets/loyalty-fieldgroup-preview.png)

        Select **[!UICONTROL Back]** to close the preview.      

    4.  Select **[!UICONTROL Add field groups]**.

4.  Select **[!UICONTROL +]** next to your schema name in the [!UICONTROL Structure] panel.

    ![Example Schema Add Field button](./assets/example-loalty-schema-plus.png)

5.  In the [!UICONTROL Field Properties] panel, enter `Identification` as the name, **[!UICONTROL Identification]** as the [!UICONTROL Display name], select **[!UICONTROL Object]** as the [!UICONTROL Type] and select **[!UICONTROL Profile Core v2]** as the [!UICONTROL Field Group].

    ![Identification Object](./assets/identifcation-loyalty-field.png)

    This adds identification capabilities to your schema. In your case, you want to identify loyalty information using the email address in your batch data.

    Select **[!UICONTROL Apply]** to add this object to your schema.

6.  Select the **[!UICONTROL email]** field in the identification object you just added, and select **[!UICONTROL Identity]** and **[!UICONTROL Email]** from the [!UICONTROL Identity namespace] in the [!UICONTROL Field Properties] panel. 

    ![Specifiy email as identity](./assets/specify-email-loyalty-id.png)

    You are specifying the email address as the identity the Adobe Experience Platform Identity service can use to combine (stitch) the behavior of profiles.

    Select **[!UICONTROL Apply]**. You see that a fingerprint icon appears in the email attribute.

7.  Select the root level of your schema (with the schema name), then select the **[!UICONTROL Profile]** switch.

    You are prompted to enable the schema for profile. Once enabled, when data is ingested into datasets based on this schema, that data is merged into the Real-Time Customer Profile. 
    
    See [Enable the schema for use in Real-Time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=en#profile) for more information.

    >[!IMPORTANT]
    >
    >    Once you save a schema enabled for profile, it can no longer be disabled for profile.

    ![Enable schema for profile](./assets/enable-for-profile.png)

8.  Select **[!UICONTROL Save]** to save your schema.

You have created a minimal schema that models the loyalty data you can ingest into Adobe Experience Platform. The schema allows profiles to be identified using the email address. By enabling the schema for profile, you ensure that data from your streaming source is added to the Real-Time Customer Profile.

See [Create and edit schemas in the UI](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html) for more information on adding and removing field groups and individual fields to a schema.

### Set up a dataset

With your schema, you have defined your data model. You now have to define the construct to store and manage that data. This is done through datasets.

To set up your dataset:

1.  In the Adobe Experience Platform UI, in the left rail, select **[!UICONTROL Datasets]** within [!UICONTROL DATA MANAGEMENT].

2.  Select **[!UICONTROL Create dataset]**.

    ![Create dataset](./assets/create-dataset.png)

3.  Select **[!UICONTROL Create dataset from schema]**.

    ![Create dataset from schema](./assets/create-dataset-from-schema.png)

4.  Select the schema that you created earlier and select **[!UICONTROL Next]**.

5.  Name your dataset and (optional) provide a description.

    ![Name dataset](./assets/name-your-datatest.png)

6.  Select **[!UICONTROL Finish]**.

7.  Select the **[!UICONTROL Profile]** switch.

    You are prompted to enable the dataset for profile. Once enabled, the dataset enriches real-time customer profiles with its ingested data.

    >[!IMPORTANT]
    >
    >    You can only enable a dataset for profile when the schema, to which the dataset adheres to, is also enabled for profile.

    ![Enable schema for profile](./assets/loyalty-dataset-profile.png)

See [Datasets UI guide](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html) for much more information on how to view, preview, create, delete a dataset. And how to enable a dataset for Real-Time Customer Profile.


## Use a source connector

Depending on where you receive the loyalty data from, you pick the relevant source connector available within Adobe Experience Platform.

To set up a source connector:

1.  In Adobe Experience Platform UI, select **[!UICONTROL Sources]** from [!UICONTROL CONNECTIONS] in the left rail.

2.  Select your source connector from the list of available source connectors. Each connector follows a similar workflow:

    -   **[!UICONTROL Authentication]**. You provide authentication details to access the source of data.

    -   **[!UICONTROL Select data]**: You select the source data that you want to ingest.

    -   **[!UICONTROL Dataflow detail]**: You provide additional details on the dataflow, i.e. name and which dataset to use.

    -   **[!UICONTROL Mapping]**: You map the incoming source data fields to attributes in the schema associated with the dataset that you selected.

    -   **[!UICONTROL Scheduling]**: If available, you can schedule the ingestion of data.

    -   **[!UICONTROL Review]**: You see a review of the definition of the source connector.

    Each connector provides detailed documentation.

    To access this documentation:

    -   On the connector tile, select the **[!UICONTROL ...]** next to [!UICONTROL Set up] or [!UICONTROL Add data].

        ![View documentation](./assets/sourceconnector-documentation.png)

    -   Select **[!UICONTROL View documentation]**.

See [Ingest and use data from traditional Adobe Analytics](./analytics.md) how to use the Adobe Analytics source connector.

See [Ingest and use streaming data](./streaming.md) how to use the HTTP API source connector.

See [Source Connectors overview](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=en#terms-and-conditions) for an overview of source connectors including links to more information for each connector.


## Set up a connection

To use the Adobe Experience Platform data in Customer Journey Analytics, you create a connection that includes the data resulting from setting up your schema, dataset, and workflow. 

A connection lets you integrate datasets from Adobe Experience Platform into Workspace. In order to report on  these datasets, you first have to establish a connection between datasets in Adobe Experience Platform and Workspace.

To create your connection:

1.  In the Customer Journey Analytics UI, select **[!UICONTROL Connections]** in the top navigation.

2.  Select **[!UICONTROL Create new connection]**.

3.  In the [!UICONTROL Untitled connection] screen:

    Name and describe your connection in [!UICONTROL Connection Settings].

    Select the correct sandbox from the [!UICONTROL Sandbox] list in [!UICONTROL Data settings] and select the number of daily events from the [!UICONTROL Average number of daily events] list.

    ![Connection Settings](./assets/cja-connections-1.png)
    
    Select **[!UICONTROL Add datasets]**. 
    
    In the [!UICONTROL Select datasets] step in [!UICONTROL Add datasets]:
    
    -   Select the dataset that you created earlier (`Example Loyalty Dataset`) and any other dataset you want to include in your connection.

        ![Add datasets](./assets/cja-connections-2.png)

    -   Select **[!UICONTROL Next]**.

    In the [!UICONTROL Datasets settings] step in [!UICONTROL Add datasets]:

    -   For each dataset:

        -   Select a [!UICONTROL Person ID] from the available identities defined in the dataset schemas in Adobe Experience Platform.
    
        -   Select the correct data source from the [!UICONTROL Data source type] list. If you specify **[!UICONTROL Other]**, then add a description for your data source.

        -   Set **[!UICONTROL Import all new data]** and **[!UICONTROL Dataset backfill existing data]** according to your preferences.

        ![Configure datasets](./assets/cja-connections-3.png)

    -   Select **[!UICONTROL Add datasets]**.

    Select **[!UICONTROL Save]**.

See [Connections overview](../connections/overview.md) for more information on how to create and manage a connection and how to select and combine datasets.

## Set up a data view

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

    Add any schema field and/or standard component that you want to include to the [!UICONTROL METRICS] or [!UICONTROL DIMENSIONS] component boxes.

    ![Data view components](./assets/cja-dataview-2.png)

    Select **[!UICONTROL Save and continue]**.

5.  In the [!UICONTROL Settings] step:

    ![Data view settings](./assets/cja-dataview-3.png)

    Leave the settings as they are and select **[!UICONTROL Save and finish]**.

See [Data views overview](../data-views/data-views.md) for more information on how to create and edit a data view, what components are available for you to use in your data view and how to use filter and sessions settings.


## Set up a project

Analysis Workspace is a flexible browser tool that allows you to quickly build analyses and share insights based on your data. You use Workspace projects to combine data components, tables, and visualizations to craft your analysis and share with anyone in your organization.

To create your project:

1.  In the Customer Journey Analytics UI, select **[!UICONTROL Projects]** in the top navigation.

2.  Select **[!UICONTROL Projects]** in the left navigation.

3.  Select **[!UICONTROL Create project]**.

    ![Workspace Project](./assets/cja-projects-1.png)

    Select **[!UICONTROL Blank project]**.

    ![Workspace - Blank Project](./assets/cja-projects-2.png)

4.  Select your data view from the list.

    ![Workspace Select Data view](./assets/cja-projects-3.png).

5.  Start dragging and dropping dimensions and metrics on the [!UICONTROL Freeform table] in the [!UICONTROL Panel] to create your first report. As an example, drag `Program Points Balance` and `Page View` as metrics and `email` as dimension to get a quick overview of profiles that have visited your website and are part of the loyalty program collecting loyalty points.

    ![Workspace - First Report](./assets/cja-projects-5.png)

See [Analysis Workspace overview](../analysis-workspace/home.md) for more information on how to create projects and build your analysis using components, visualizations, and panels.

>[!SUCCESS]
>
>You have completed all the steps. Starting by defining what loyalty data you want to collect (schema) and where to store it (dataset) in Adobe Experience Platform, you configured the appropriate source connector to provide you with the loyalty data. You defined a connection in Customer Journey Analytics to use the ingested loyalty data and other data. Your data view definition allowed you to specify which dimension and metrics to use and finally you created your first project visualizing and analyzing your data.
