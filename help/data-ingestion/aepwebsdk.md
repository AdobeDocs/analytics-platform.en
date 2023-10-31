---
title: Ingest data via the Adobe Experience Platform Web SDK
description: Explain how to ingest data into Customer Journey Analytics via the Adobe Experience Platform Web SDK and the Edge Network
solution: Customer Journey Analytics
feature: Basics
exl-id: 0b595e9e-0dcf-4c70-ac6d-5a2322824328
---
# Ingest data via the Adobe Experience Platform Web SDK

This quick start guide explains how you can ingest website tracking data directly into Adobe Experience Platform using the Adobe Experience Platform Web SDK and Edge Network and then use that data in Customer Journey Analytics.

To accomplish this, you need to:

- **Set up a schema and dataset** in Adobe Experience Platform to define the model (schema) of the data that you want to collect and where to actually collect the data (dataset).

- **Set up a datastream** to configure the Adobe Experience Platform Edge Network to route your collected data to the dataset you configured in Adobe Experience Platform.

- **Use Tags** to easily configure rules and data elements against the data in your data layer on your website. Then ensure that the data is sent to the datastream configured on the Adobe Experience Platform Edge Network.

- **Deploy and validate**. Have an environment where you can iterate on the development of tags and once everything is validated, publish it live on your production environment.

- **Set up a connection** in Customer Journey Analytics. This connection should (at least) include your Adobe Experience Platform dataset.

- **Set up a data view** in Customer Journey Analytics to define metrics and dimension that you want to use in Analysis Workspace.

- **Set up a project** in Customer Journey Analytics to build your reports and visualizations.

>[!NOTE]
>
> This quick start guide is a simplified guide on how to ingest data collected from your site into Adobe Experience Platform and use in Customer Journey Analytics. It is highly recommended to study the additional information when referred to. 


## Set up a schema and dataset

To ingest data into Adobe Experience Platform, you first must define which data you want to collect. All data ingested into Adobe Experience Platform must conform to a standard, denormalized structure for it be recognized and acted upon by downstream capabilities and features. Experience Data Model (XDM) is the standard framework that provides this structure in the form of schemas. 

Once you have defined a schema, you use one or more datasets to store and manage the collection of data. A dataset is a storage and management construct for a collection of data (typically a table) that contains a schema (columns) and fields (rows). 

All data that is ingested into Adobe Experience Platform must conform to a pre-defined schema before it can be persisted as a dataset.

### Set up a schema

You want to track some minimal data from profiles visiting your website, for example page name, identification. 
You first must define a schema that models this data.

To set up your schema:

1. In the Adobe Experience Platform UI, in the left rail, select **[!UICONTROL Schemas]** within [!UICONTROL DATA MANAGEMENT].

1. Select **[!UICONTROL Create schema]**. 
. 
1. In the Select a class step of the Create schema wizard: 

   1. Select **[!UICONTROL Experience Event]**.

      ![Create a schema](./assets/create-ee-schema-wizard-step-1.png)

      >[!INFO]
      >
      >    An Experience Event schema is used to model the _behavior_ of a profile (like scene name, push button to add to cart). An Individual Profile schema is used to model the profile _attributes_ (like name, email, gender).

   1. Select **[!UICONTROL Next]**.


1. In the [!UICONTROL Name and review step] of the [!UICONTROL Create schema] wizard:

   1. Enter a **[!UICONTROL Schema display name]** for your schema and (optional) a **[!UICONTROL Description]**.

      ![Name your schema](./assets/create-ee-schema-wizard-step-2.png)

   1. Select **[!UICONTROL Finish]**.

1. In the Structure tab of Example Schema:
    
   1. Select **[!UICONTROL + Add]** in [!UICONTROL Field groups].

      ![Add field group](./assets/add-field-group-button.png)

      Field groups are reusable collections of objects and attributes that allow you to easily extend your schema.

   1. In the [!UICONTROL Add fields groups] dialog, select the **[!UICONTROL AEP Web SDK ExperienceEvent]** field group from the list. 

      ![AEP Web SDK ExperienceEvent fieldgroup](./assets/select-aepwebsdk-experienceevent.png)
    
      You can select the preview button, to see a preview of the fields that are part of this field group, like `web > webPageDetails > name`. 

      ![AEP Web SDK ExperienceEvent fieldgroup preview](./assets/aepwebsdk-experiencevent-preview.png)

      Select **[!UICONTROL Back]** to close the preview.      

   1. Select **[!UICONTROL Add field groups]**.

1. Select **[!UICONTROL +]** next to your schema name in the [!UICONTROL Structure] panel.

   ![Example Schema Add Field button](./assets/example-schema-plus.png)

1. In the [!UICONTROL Field Properties] panel, enter `Identification` as the name, **[!UICONTROL Identification]** as the [!UICONTROL Display name], select **[!UICONTROL Object]** as the [!UICONTROL Type] and select **[!UICONTROL ExperienceEvent Core v2.1]** as the [!UICONTROL Field Group].

    ![Identification Object](./assets/identification-field.png)

    The identification object adds identification capabilities to your schema. In your case, you want to identify profiles visiting your site using the Experience Cloud Id and email address. There are many other attributes available to track your person's identification (for example customer id, loyalty id).

    Select **[!UICONTROL Apply]** to add this object to your schema.

1. Select the **[!UICONTROL ecid]** field in the identification object you just added, and select **[!UICONTROL Identity]** and **[!UICONTROL Primary Identity]** and **[!UICONTROL ECID]** from the [!UICONTROL Identity namespace] list in the right panel.

   ![Specifiy ECID as identity](./assets/specify-identity.png)

   You are specifying the Experience Cloud Identity as the primary identity the Adobe Experience Platform Identity service can use to combine (stitch) the behavior of profiles with the same ECID.

   Select **[!UICONTROL Apply]**. You see that a fingerprint icon appears in the ecid attribute.

1. Select the **[!UICONTROL email]** field in the identification object you just added, and select **[!UICONTROL Identity]** and **[!UICONTROL Email]** from the [!UICONTROL Identity namespace] list in the [!UICONTROL Field Properties] panel. 

   ![Specifiy email as identity](./assets/specify-email-identity.png)

   You are specifying the email address as another identity the Adobe Experience Platform Identity service can use to combine (stitch) the behavior of profiles.

   Select **[!UICONTROL Apply]**. You see that a fingerprint icon appears in the email attribute.

    Select **[!UICONTROL Save]**.

1. Select the root element of your schema displaying the name of the schema, then select the **[!UICONTROL Profile]** switch.

   You are prompted to enable the schema for profile. Once enabled, when data is ingested into datasets based on this schema, that data is merged into the Real-Time Customer Profile. 
    
   See [Enable the schema for use in Real-Time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=en#profile) for more information.

   >[!IMPORTANT]
   >
   >    Once you save a schema enabled for profile, it can no longer be disabled for profile.

   ![Enable schema for profile](./assets/enable-for-profile.png)

1. Select **[!UICONTROL Save]** to save your schema.

You have created a minimal schema that models the data you can capture from your website. The schema allows profiles to be identified using the Experience Cloud Identity and email address. By enabling the schema for profile, you ensure data captured from your website is added to the Real-Time Customer Profile.

Next to behavior data, you can also capture profile attribute data from your site (for example details of profiles subscribing to a newsletter). 

To capture this profile data, you would:

- Create a schema based on the XDM Individual Profile class.

- Add the Profile Core v2 field group to the schema.

- Add an identification object based on the Profile Core v2 field group.

- Define Experience Cloud ID as primary identifier and email as identifier.

- Enable the schema for profile

See [Create and edit schemas in the UI](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html) for more information on adding and removing field groups and individual fields to a schema.

### Set up a dataset

With your schema, you have defined your data model. You now have to define the construct to store and manage that data, which is done through datasets.

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

A datastream represents the server-side configuration when implementing the Adobe Experience Platform Web and Mobile SDKs. When collecting data with the Adobe Experience Platform SDKs, data is sent to the Adobe Experience Platform Edge Network. It is the datastream that determines to which services that data is forwarded.

In your setup, you want the data you collect from the website to be sent to your dataset in Adobe Experience Platform.

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

Your datastream is now configured to forward the data collected from your website to your dataset in Adobe Experience Platform.

See [Datastreams overview](https://experienceleague.adobe.com/docs/experience-platform/datastreams/overview.html?lang=en) for more information on how to configure a datastream and how to handle sensitive data.



## Use Tags

To implement code on your site to actually collect data, use the Tags feature within Adobe Experience Platform . This tag management solution lets you deploy code alongside other tagging requirements. Tags offer seamless integration with Adobe Experience Platform using the Adobe Experience Platform Web SDK extension.

### Create your tag

1. In the Adobe Experience Platform UI, in the left rail, select **[!UICONTROL Tags]** within [!UICONTROL DATA COLLECTION].

2. Select **[!UICONTROL New Property]**. 

    Name the tag, select **[!UICONTROL Web]** and enter a domain name. Select **[!UICONTROL Save]** to continue.

    ![Create a property](./assets/create-property.png)

### Configure your tag

After creating the tag, you must configure it with the correct extensions and configure data elements and rules according to how you want to track your site and send data to Adobe Experience Platform. 

Select your newly created tag from the list of [!UICONTROL Tag Properties] to open it.


#### **Extensions**

To ensure you can send data to Adobe Experience Platform (via your datastream), add the Adobe Platform Web SDK extension to your tag.

To create and configure the Adobe Experience Platform Web SDK extension:

1. Select **[!UICONTROL Extensions]** in the left rail.

2. Select **[!UICONTROL Catalog]** in the top bar.

3. Search for or scroll to the Adobe Experience Platform Web SDK extension, and Select **[!UICONTROL Install]** to install it.

   <img src="./assets/aepwebsdk-extension.png" width="35%"/>

4. Select your sandbox and your earlier created datastream for your [!UICONTROL Production Environment] and (optional) [!UICONTROL Staging Environment] and [!UICONTROL Development Environment].

   ![AEP Web SDK extension configuration](./assets/aepwebsk-extension-datastreams.png)

   Select **[!UICONTROL Save]**.

See [Configure the Adobe Experience Platform Web SDK extension](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration.html) for more information.

You also want to set up the Experience Cloud ID Service extension so you can easily use of the Experience Cloud ID. The Experience Cloud ID Service identifies persons across all Adobe Experience Cloud solutions.

To create and configure the Experience Cloud ID Service extension:

1. Select **[!UICONTROL Extensions]** in the left rail.

2. Select **[!UICONTROL Catalog]** in the top bar.

3. Search for or scroll to the Experience Cloud ID Service extension, and select **[!UICONTROL Install]** to install it.

   <img src="./assets/ecid-extension.png" width="35%"/>

4. Leave all configurations at their default.

5. Select **[!UICONTROL Save]**.

#### **Data Elements**

Data elements are the building blocks for your data dictionary (or data map). Use data elements to collect, organize, and deliver data across marketing and ad technology. You set up data elements in your tag that read from your data layer and can be used to deliver data into Adobe Experience Platform.

There are different types of data elements. You first set up a data element to capture the page name persons are viewing on your site.

To define a page name data element:

1. Select **[!UICONTROL Data Elements]** in the left rail.

2. Select **[!UICONTROL Add Data Element]**.

3. In the [!UICONTROL Create Data Element] dialog:

   - Name your data element, for example `Page Name`.

   - Select **[!UICONTROL Core]** from the [!UICONTROL Extension] list.

   - Select **[!UICONTROL Page Info]** from the [!UICONTROL Data Element Type] list.

   - Select **[!UICONTROL Title]** from the [!UICONTROL Attribute] list.

     ![Create Date Element using Page Info](./assets/create-dataelement-1.png)

     Alternatively you could have used the value from a variable of your data layer, for example `pageName` and the [!UICONTROL JavaScript Variable] data element type to define the data element.

     ![Create Data Element using Javascript Variable](./assets/create-dataelement-2.png)

   - Select **[!UICONTROL Save]**.

You now want to set up a data element referencing the Experience Cloud ID that is automatically provided by the Adobe Experience Platform Web SDK and available through the Experience Cloud ID Service extension.

To define an ECID data element:

1. Select **[!UICONTROL Data Elements]** in the left rail.

2. Select **[!UICONTROL Add Data Element]**.

3. In the [!UICONTROL Create Data Element] dialog:

   - Name your data element, for example `ECID`.

   - Select **[!UICONTROL Experience Cloud ID Service]** from the [!UICONTROL Extension] list.

   - Select **[!UICONTROL ECID]** from the [!UICONTROL Data Element Type] list.

     ![ECID Data Element](./assets/ecid-dataelement.png)

   - Select **[!UICONTROL Save]**.

Finally, you now want to map any of your specific data elements to the schema you defined earlier. You define another data element which provides a representation of your XDM schema.

To define an XDM object data element:

1. Select **[!UICONTROL Data Elements]** in the left rail.

2. Select **[!UICONTROL Add Data Element]**.

3. In the [!UICONTROL Create Data Element] dialog:

   - Name your data element, for example `XDM - Page View`.

   - Select **[!UICONTROL Adobe Experience Platform Web SDK]** from the [!UICONTROL Extension] list.

   - Select **[!UICONTROL XDM Object]** from the [!UICONTROL Data Element Type] list.

   - Select your sandbox from the [!UICONTROL Sandbox] list.

   - Select your schema from the [!UICONTROL Schema] list.

   - Map the `identification > core > ecid` attribute, defined in your schema, to the ECID data element. Select the cylinder icon to easily pick the ECID data element from your list of data elements.

     ![Pick ECID Data Element](./assets/pick-ecid-dataelement.png)

        ![Map ECID Data Element](./assets/map-ecid.png)


   - Map the `web > webPageDetails > name` attribute, defined in your schema, to the Page Name data element.

        ![Map Page Name Data Element](./assets/map-pagename.png)

   - Select **[!UICONTROL Save]**.


#### **Rules**

Tags in Adobe Experience Platform follow a rule-based system. They look for user interaction and associated data. When the criteria outlined in your rules are met, the rule triggers the extension, script, or client-side code you identified. You can use rules to send data (like an XDM object) into Adobe Experience Platform using the Adobe Experience Platform Web SDK extension.

To define a rule:

1. Select **[!UICONTROL Rules]** in the left rail.

2. Select **[!UICONTROL Create New Rule]**.

3. In the [!UICONTROL Create Rule] dialog:

   - Name the rule, for example `Page View`.

   - Select **[!UICONTROL + Add]** underneath [!UICONTROL Events]. 
    
   - In the [!UICONTROL Event Configuration] dialog:

     - Select **[!UICONTROL Core]** from the [!UICONTROL Extension] list.

     - Select **[!UICONTROL Window Loaded]** from the [!UICONTROL Event Type] list.

       ![Rule - Event Configuration](./assets/event-windowloaded-pageview.png)

     - Select **[!UICONTROL Keep Changes]**.



   - Select **[!UICONTROL + Add]** underneath [!UICONTROL Actions]. 
    
   - In the [!UICONTROL Action Configuration] dialog:

     - Select **[!UICONTROL Adobe Experience Platform Web SDK]** from the [!UICONTROL Extension] list.

     - Select **[!UICONTROL Send Event]** from the [!UICONTROL Action Type] list.

     - Select **[!UICONTROL web.webpagedetails.pageViews]** from the [!UICONTROL Type] list.

     - Select the cylinder icon next to  [!UICONTROL XDM data] and Select **[!UICONTROL XDM - Page View]** from the list of data elements.

      ![Rule - Action Configuration](./assets/action-pageview-xdm.png)

     - Select **[!UICONTROL Keep Changes]**.

   - Your rule should look like:

     ![Create Rule](assets/rule-pageview.png)

   - Select **[!UICONTROL Save]**.

The above is just an example of defining a rule that sends XDM data, containing values from other data elements, to Adobe Experience Platform. 

You can use rules in various ways in your tag to manipulate variables (using your data elements). 

See [Rules](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/rules.html) for more information.

### Build and Publish your tag

After having defined data elements and rules, you must build and publish your tag. When you create a library build, you must assign it to an environment. The build's extensions, rules, and data elements are then compiled and placed into the assigned environment. Each environment provides a unique embed code that allows you to integrate its assigned build into your site.

To build and publish your tag:

1. Select **[!UICONTROL Publishing Flow]** from the left rail.

2. Select **[!UICONTROL Select a working library]**, followed by **[!UICONTROL Add Library…]**.

3. In the [!UICONTROL Create Library] dialog:

    - Name the library.

    - Select **[!UICONTROL Development (development)]** from the [!UICONTROL Environment] list.

    - Select **[!UICONTROL + Add All Changed Resources]**.

        ![Publish - Create Library](./assets/create-library-aep.png)

    - Select **[!UICONTROL Save & Build to Development]**.

    Your tag is saved and is build for your development environment. A green dot indicates a successful build of your tag on your development environment.

4. You can select **[!UICONTROL ...]** to rebuild the library or move the library to a staging or production environment.

    ![Publish - Build Library](./assets/build-library.png)

Adobe Experience Platform Tags support simple to complex publishing workflows that should accommodate your deployment of the Adobe Experience Platform Web SDK. 

See [Publishing overview](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html) for more information.


### Retrieve your tag code

Finally you must install your tag on the website you want to track, which implies placing code in the header tag of your website's template.

To get the code that references your tag:

1. Select **[!UICONTROL Environments]** in the left rail.

2. From the list of environments, select the correct install (box) button.

   In the [!UICONTROL Web Install Instructions] dialog, select the copy button next to the script code that should read like:

   ```
   <script src="https://assets.adobedtm.com/2a518741ab24/.../launch-...-development.min.js" async></script>>
         
   ```   

   ![Environment](./assets/environment.png)

3. Select **[!UICONTROL Close]**.

Instead of the code for the development environment, you could have selected another environment (staging, production) based on where you are in the process of deploying the Adobe Experience Platform Web SDK. 

See [Environments](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/environments/environments.html?) for more information.

## Deploy and validate

You can now deploy the code on the development version of your website inside the `<head>` tag. When deployed, your website starts collecting data into Adobe Experience Platform.

Validate your implementation, correct it where necessary, and once correct, deploy it to your staging and production environment using the publishing workflow feature of Tags.

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
    
    - Select the dataset that you created earlier (`Example dataset`) and any other dataset you want to include in your connection.

        ![Add datasets](./assets/cja-connections-2b.png)

    - Select **[!UICONTROL Next]**.

    In the [!UICONTROL Datasets settings] step in [!UICONTROL Add datasets]:

    - For each dataset:

        - Select a [!UICONTROL Person ID] from the available identities defined in the dataset schemas in Adobe Experience Platform.
    
        - Select the correct data source from the [!UICONTROL Data source type] list. If you specify **[!UICONTROL Other]**, then add a description for your data source.

        - Set **[!UICONTROL Import all new data]** and **[!UICONTROL Dataset backfill existing data]** according to your preferences.

        ![Configure datasets](./assets/cja-connections-3b.png)

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

    ![Data view components](./assets/cja-dataview-2.png)

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

5. To create your first report, start dragging and dropping dimensions and metrics on the [!UICONTROL Freeform table] in the [!UICONTROL Panel]. As an example, drag `Program Points Balance` and `Page View` as metrics and `email` as dimension to get a quick overview of profiles that have visited your website and are part of the loyalty program collecting loyalty points.

    ![Workspace - First Report](./assets/cja-projects-5.png)

See [Analysis Workspace overview](../analysis-workspace/home.md) for more information on how to create projects and build your analysis using components, visualizations, and panels.

>[!SUCCESS]
>
>You have completed all the steps. Starting by defining what data you want to collect (schema) and where to store it (dataset) in Adobe Experience Platform. You then configured a datastream on the Edge Network to ensure that data can be forwarded to that dataset. Then you defined and deployed your tag containing the extensions (Adobe Experience Platform Web SDK, Experience Cloud ID Service), data elements, and rules to capture data from your website and send that data to your datastream. You defined a connection in Customer Journey Analytics to use your website tracking data and other data. Your data view definition allowed you to specify which dimension and metrics to use and finally you created your first project visualizing and analyzing your data.
