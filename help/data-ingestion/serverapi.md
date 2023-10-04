---
title: Ingest data via the Adobe Experience Platform Edge Network Server API
description: Explain how to ingest data into Customer Journey Analytics via the Adobe Experience Platform Edge Network Server API and the Edge Network
solution: Customer Journey Analytics
feature: Basics
exl-id: 6bfb7254-5bb7-45c6-86a2-0651a0d222fa
---
# Ingest data via the Adobe Experience Platform Edge Network Server API

This quick start guide explains how you can ingest tracking data from devices like IoT devices, set-top boxes, gaming consoles, desktop applications directly into Adobe Experience Platform using the Adobe Experience Platform Edge Network Server API and Edge Network. Then use that data in Customer Journey Analytics.

To accomplish this, you must:

- **Set up a schema and dataset** in Adobe Experience Platform to define the model (schema) of the data that you want to collect and where to actually collect the data (dataset).

- **Set up a datastream** to configure the Adobe Experience Platform Edge Network to route your collected data to the dataset you configured in Adobe Experience Platform.

- **Use Server API** to send data directly from your application or game running on a desktop, gaming console, IoT device, or set-top box to your datastream.

- **Deploy and validate**. Have an environment where you can iterate on your development and once everything is validated, publish it live on your production environment.

- **Set up a connection** in Customer Journey Analytics. This connection should (at least) include your Adobe Experience Platform dataset.

- **Set up a data view** in Customer Journey Analytics to define metrics and dimension that you want to use in Analysis Workspace.

- **Set up a project** in Customer Journey Analytics to build your reports and visualizations.

>[!NOTE]
>
>This quick start guide is a simplified guide on how to ingest data collected from an application or game running on an IoT device, set-top box, gaming console, or desktop into Adobe Experience Platform and use in Customer Journey Analytics. It is highly recommended to study the additional information when referred to.


## Set up a schema and dataset

To ingest data into Adobe Experience Platform, you first must define which data you want to collect. All data ingested into Adobe Experience Platform must conform to a standard, denormalized structure for it be recognized and acted upon by downstream capabilities and features. Experience Data Model (XDM) is the standard framework that provides a structure in the form of schemas. 

Once you have defined a schema, you use one or more datasets to store and manage the collection of data. A dataset is a storage and management construct for a collection of data (typically a table) that contains a schema (columns) and fields (rows). 

All data that is ingested into Adobe Experience Platform must conform to a pre-defined schema before it can be persisted as a dataset.

### Set up a schema

You want to track some minimal data from profiles playing your game on a console, for example identification, scores, progress, and other information.
You first must define a schema that models this data.

To set up your schema:

1. In the Adobe Experience Platform UI, in the left rail, select **[!UICONTROL Schemas]** within [!UICONTROL DATA MANAGEMENT].

2. Select **[!UICONTROL Create schema]**. Select **[!UICONTROL XDM ExperienceEvent]** from the list of options.

    ![Create a schema](./assets/create-ee-schema.png)

    >[!INFO]
    >
    >    An Experience Event schema is used to model the _behavior_ of a profile (like reach a level in the game for example). An Individual Profile schema is used to model the profile _attributes_ (like name, email, gender).


3. In the [!UICONTROL Untitled schema] screen:

   1. Enter a display name for your schema and (optional) a description.

      ![Name your schema](./assets/name-schema.png)
    
   2. Select **[!UICONTROL + Add]** in [!UICONTROL Field groups].

      ![Add field group](./assets/add-field-group-button.png)

      Field groups are reusable collections of objects and attributes that allow you to easily extend your schema.

   3. In the [!UICONTROL Add fields groups] dialog, select the **[!UICONTROL Blinding Light]** field group from the list. This fieldgroup is created to track user progress playing a fictitious game titled Blinding Light on a console.

      ![Blinding Light fieldgroup](assets/schema-fieldgroup-blindinglight.png)
    
      You can select the preview button, to see a preview of the fields that are part of this field group, like `scores > afterMatch`. 

      ![Blinding Light fieldgroup preview](assets/schema-fieldgroup-blindinglight-preview.png)

      Select **[!UICONTROL Back]** to close the preview.      

   4. Select **[!UICONTROL Add field groups]**.

4. Select **[!UICONTROL +]** next to your schema name.

   ![Example Schema Add Field button](./assets/example-gamingschema-plus.png)

5. In the [!UICONTROL Field Properties] panel, enter `identification` as the [!UICONTROL Field name], **[!UICONTROL Identification]** as the [!UICONTROL Display name], select **[!UICONTROL Object]** as the [!UICONTROL Type] and select **[!UICONTROL ExperienceEvent Core v2.1]** as the [!UICONTROL Field Group].

    ![Identification Object](./assets/identification-field-gaming.png)

    The identification object adds identification capabilities to your schema. In your case, you want to identify profiles playing your game using the Experience Cloud Id and email address they use to log in to their gaming console. There are many other attributes available to track your person's identification.

    Select **[!UICONTROL Apply]** to add this object to your schema.

6. Select the **[!UICONTROL ecid]** field in the identification object you just added, and select **[!UICONTROL Identity]** and **[!UICONTROL Primary Identity]** and **[!UICONTROL ECID]** from the [!UICONTROL Identity namespace] list in the right panel.

   ![Specifiy ECID as identity](./assets/specify-identity-gaming.png)

   You are specifying the Experience Cloud Identity as the primary identity the Adobe Experience Platform Identity service can use to combine (stitch) the behavior of profiles with the same ECID.

   Select **[!UICONTROL Apply]**. You see that a fingerprint icon appears in the ecid attribute.

7. Select the **[!UICONTROL email]** field in the identification object you just added, and select **[!UICONTROL Identity]** and **[!UICONTROL Email]** from the [!UICONTROL Identity namespace] list in the [!UICONTROL Field Properties] panel. 

   ![Specifiy email as identity](./assets/specify-email-identity-gaming.png)

   You are specifying the email address as another identity the Adobe Experience Platform Identity service can use to combine (stitch) the behavior of profiles.

   Select **[!UICONTROL Apply]**. You see that a fingerprint icon appears in the email attribute.

    Select **[!UICONTROL Save]**.

8. Select the root element of your schema displaying the name of the schema, then select the **[!UICONTROL Profile]** switch.

   You are prompted to enable the schema for profile. Once enabled, when data is ingested into datasets based on this schema, that data is merged into the Real-Time Customer Profile. 
    
   See [Enable the schema for use in Real-Time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=en#profile) for more information.

   >[!IMPORTANT]
   >
   >    Once you save a schema enabled for profile, it can no longer be disabled for profile.

   ![Enable schema for profile](./assets/enable-for-profile.png)

9. Select **[!UICONTROL Save]** to save your schema.

You have created a minimal schema that models the data you can capture from your game. The schema allows profiles to be identified using the Experience Cloud Identity and email address. By enabling the schema for profile, you ensure data captured from your console game is added to the Real-Time Customer Profile.

Next to behavior data, you can also capture profile attribute data from your console (for example details of profiles signed into the console). 

To capture profile data, you would:

- Create a schema based on the XDM Individual Profile class.

- Add the Profile Core v2 field group to the schema.

- Add an identification object based on the Profile Core v2 field group.

- Define Experience Cloud ID as primary identifier and email as identifier.

- Enable the schema for profile

See [Create and edit schemas in the UI](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html) for more information on adding and removing field groups and individual fields to a schema.

### Set up a dataset

With your schema, you have defined your data model. You now have to define the construct to store and manage that data by using datasets.

To set up your dataset:

1. In the Adobe Experience Platform UI, in the left rail, select **[!UICONTROL Datasets]** within [!UICONTROL DATA MANAGEMENT].

2. Select **[!UICONTROL Create dataset]**.

   ![Create dataset](./assets/create-dataset.png)

3. Select **[!UICONTROL Create dataset from schema]**.

   ![Create dataset from schema](./assets/create-dataset-from-schema.png)

4. Select the schema that you created earlier and select **[!UICONTROL Next]**.

5. Name your dataset and (optional) provide a description.

   ![Name dataset](./assets/name-your-datatest.png)

6. Select **[!UICONTROL Finish]**.

7. Select the **[!UICONTROL Profile]** switch.

   You are prompted to enable the dataset for profile. Once enabled, the dataset enriches real-time customer profiles with its ingested data.

   >[!IMPORTANT]
   >
   >    You can only enable a dataset for profile when the schema, to which the dataset adheres, is also enabled for profile.

   ![Enable schema for profile](./assets/aepwebsdk-dataset-profile.png)

See [Datasets UI guide](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html) for much more information on how to view, preview, create, delete a dataset. And how to enable a dataset for Real-Time Customer Profile.

## Set up a datastream

A datastream represents the server-side configuration when implementing the Adobe Experience Platform Web and Mobile SDKs and the Adobe Experience Platform Edge Network Server API. When collecting data with the Adobe Experience Platform SDKs and Edge Network Server APIs, data is sent to the Adobe Experience Platform Edge Network. It is the datastream that determines to which services that data is forwarded.

In your setup, you want the data you collect from the game to be sent to your dataset in Adobe Experience Platform.

To set up your datastream:

1. In the Adobe Experience Platform UI, select **[!UICONTROL Datastreams]** from [!UICONTROL DATA COLLECTION] in the left rail.

2. Select **[!UICONTROL New Datastream]**.

3. Name and describe your datastream. Select your schema from the [!UICONTROL Event Schema] list.

   ![New Datastream](./assets/new-datastream.png)

4. Select **[!UICONTROL Save]**.

5. Select **[!UICONTROL Add Service]**.

6. In the [!UICONTROL Add Service screen]:

   1. Select **[!UICONTROL Adobe Experience Platform]** from the [!UICONTROL Service] list.

   2. Ensure **[!UICONTROL Enabled]** is selected.

   3. Select your dataset from the [!UICONTROL Event Dataset] list.

      ![Datastream AEP service](./assets/datastream-aep-service.png)

   4. Leave the other settings and select **[!UICONTROL Save]** to save the datastream.

Your datastream is now configured to forward the data collected from your game to your dataset in Adobe Experience Platform.

See [Datastreams overview](https://experienceleague.adobe.com/docs/experience-platform/datastreams/overview.html?lang=en) for more information on how to configure a datastream and how to handle sensitive data.

## Use Edge Network Server API

In the development of your game, you can add relevant calls to the Adobe Experience Platform Edge Network Server API where appropriate. 

For example, to update the score of player, you would use:

```
curl -X POST "https://server.adobedc.net/ee/v2/interact?dataStreamId={DATASTREAM_ID}"
-H "Authorization: Bearer {TOKEN}"
-H "x-gw-ims-org-id: {ORG_ID}"
-H "x-api-key: {API_KEY}"
-H "Content-Type: application/json"
-d '{
   "event": {
      "xdm": {
         "identityMap": {
            "Email_LC_SHA256": [
               {
                  "id": "0c7e6a405862e402eb76a70f8a26fc732d07c32931e9fae9ab1582911d2e8a3b",
                  "primary": true
               }
            ]
         },
         "eventType": "game.scoreUpdate",
         "{sandbox}": {
            "scores": {
               "afterMatch": 132391",
            }
         },
         "timestamp": "2021-08-09T14:09:20.859Z"
      }
   }
}'
```

In the example POST request, `{DATASTREAM_ID}` points to the identifier of the example datastream you configured earlier. `{sandbox}` is the unique name of your sandbox identifying the path to the custom Blinding Light field group.

See [Interactive data collection](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/data-collection/interactive-data-collection.html?lang=en) and [Non-interactive data collection](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/data-collection/non-interactive-data-collection.html?lang=en) for more information on how to use the Edge Network Server API.

## Set up a connection

To use the Adobe Experience Platform data in Customer Journey Analytics, you create a connection that includes the data resulting from setting up your schema, dataset, and workflow. 

A connection lets you integrate datasets from Adobe Experience Platform into Workspace. To report on  these datasets, you first have to establish a connection between datasets in Adobe Experience Platform and Workspace.

To create your connection:

1. In the Customer Journey Analytics UI, select **[!UICONTROL Connections]** in the top navigation.

2. Select **[!UICONTROL Create new connection]**.

3. In the [!UICONTROL Untitled connection] screen:

    Name and describe your connection in [!UICONTROL Connection Settings].

    Select the correct sandbox from the [!UICONTROL Sandbox] list in [!UICONTROL Data settings] and select the number of daily events from the [!UICONTROL Average number of daily events] list.

    ![Connection Settings](./assets/cja-connections-1.png)
    
    Select **[!UICONTROL Add datasets]**. 
    
    In the [!UICONTROL Select datasets] step in [!UICONTROL Add datasets]:
    
    - Select datasets that you created earlier and/or other relevant datasets you want to include in your connection

    - Select **[!UICONTROL Next]**.

    In the [!UICONTROL Datasets settings] step in [!UICONTROL Add datasets]:

    - For each dataset:

        - Select a [!UICONTROL Person ID] from the available identities defined in the dataset schemas in Adobe Experience Platform.
    
        - Select the correct data source from the [!UICONTROL Data source type] list. If you specify **[!UICONTROL Other]**, then add a description for your data source.

        - Set **[!UICONTROL Import all new data]** and **[!UICONTROL Dataset backfill existing data]** according to your preferences.

    - Select **[!UICONTROL Add datasets]**.

    Select **[!UICONTROL Save]**.

See [Connections overview](../connections/overview.md) for more information on how to create and manage a connection and how to select and combine datasets.

## Set up a data view

A data view is a container specific to Customer Journey Analytics that lets you determine how to interpret data from a connection. It specifies all dimensions and metrics available in Analysis Workspace and which columns those dimensions and metrics obtain their data from. Data views are defined in preparation for reporting in Analysis Workspace.

To create your data view:

1. In the Customer Journey Analytics UI, select **[!UICONTROL Data views]** in the top navigation.

2. Select **[!UICONTROL Create new data view]**.

3. In the [!UICONTROL Configure] step:

    Select your connection from the [!UICONTROL Connection] list.

    Name and (optionally) describe your connection.

    ![Data view configure](./assets/cja-dataview-1.png)

    Select **[!UICONTROL Save and continue]**.

4. In the [!UICONTROL Components] step:

    Add any schema field and/or standard component that you want to include to the [!UICONTROL METRICS] or [!UICONTROL DIMENSIONS] component boxes.

    Select **[!UICONTROL Save and continue]**.

5. In the [!UICONTROL Settings] step:

    ![Data view settings](./assets/cja-dataview-3.png)

    Leave the settings as they are and select **[!UICONTROL Save and finish]**.

See [Data views overview](../data-views/data-views.md) for more information on how to create and edit a data view, what components are available for you to use in your data view and how to use filter and sessions settings.


## Set up a project

Analysis Workspace is a flexible browser tool that allows you to quickly build analyses and share insights based on your data. You use Workspace projects to combine data components, tables, and visualizations to craft your analysis and share with anyone in your organization.

To create your project:

1. In the Customer Journey Analytics UI, select **[!UICONTROL Projects]** in the top navigation.

2. Select **[!UICONTROL Projects]** in the left navigation.

3. Select **[!UICONTROL Create project]**.

    ![Workspace Project](./assets/cja-projects-1.png)

    Select **[!UICONTROL Blank project]**.

    ![Workspace - Blank Project](./assets/cja-projects-2.png)

4. Select your data view from the list.

    ![Workspace Select Data view](./assets/cja-projects-3.png).

5. To create your first report, start dragging and dropping dimensions and metrics on the [!UICONTROL Freeform table] in the [!UICONTROL Panel].

See [Analysis Workspace overview](../analysis-workspace/home.md) for more information on how to create projects and build your analysis using components, visualizations, and panels.

>[!SUCCESS]
>
>You have completed all the steps. Starting by defining what data you want to collect (schema) and where to store it (dataset) in Adobe Experience Platform. You configured a datastream on the Edge Network to ensure that data can be forwarded to that dataset. Then you used the Edge Network Server API to send that data to your datastream. You defined a connection in Customer Journey Analytics to use your game data and other data. Your data view definition allowed you to specify which dimension and metrics to use and finally you created your first project visualizing and analyzing your game data.
