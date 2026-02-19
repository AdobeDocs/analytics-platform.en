---
title: Configure Content Analytics (Standalone)
description: Step-by-step guide to configure Adobe Content Analytics as a standalone solution. Learn how to set up schemas, datasets, datastreams, and reporting for comprehensive content performance insights without a full Customer Journey Analytics implementation.
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: yes
hidefromtoc: yes
---
# Standalone configuration

>[!IMPORTANT]
>
>This configuration guide is for customers that have licensed the standalone Adobe Content Analytics package. The guide assumes you have not used or planned to use Customer Journey Analytics or any other Experience Platform application beyond the Content Analytics capabilities and features. See [Configure Content Analytics](configuration.md) if you want to configure and use Content Analytics as part of an existing Customer Journey Analytics implementation.
>

Content Analytics is licensed as a standalone product, but the configuration happens within Experience Platform and Customer Journey Analytics. These platforms provide the data collection and analysis infrastructure that Content Analytics requires and uses. This guide provides all the specific instructions that you need, even if you're new to Experience Platform and Customer Journey Analytics.

Before you begin the setup of standalone Content Analytics, you should:

* Have a basic understanding of web analytics concepts, familiarity with tag management systems, and basic JavaScript knowledge.
* Plan 4-6 hours for the initial setup, plus additional time to test and validate the setup.

## Terminology

This guide uses several technical terms, from Experience Platform and Customer Journey Analytics, which you might not be familiar with. Below is an explanation of these terms (with reference links) in the context of Content Analytics:

| Term | Explanation |
|---|---|
| **Schema** | A [schema](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition) is a set of rules that represent and validate the structure and format of data. At a high level, schemas provide an abstract definition of a real-world object, such as an event that happens on a website, like a click. And outline what data should be included in each instance of that object. |
| **Dataset** | A [dataset](https://experienceleague.adobe.com/en/docs/experience-platform/catalog/datasets/overview) is a storage and management construct for a collection of data, typically a table, that contains a schema (columns) and fields (rows). A dataset is like a database table where each row is an event from your website.  |
| **Datastream** | A [datastream](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/overview) represents the server-side configuration that routes data from your website to the correct dataset in Adobe Experience Platform. A datastream acts as a data highway connecting your site to your storage. |
| **Tags** | [Tags](https://experienceleague.adobe.com/en/docs/experience-platform/tags/home) in Experience Platform are the next generation of tag management capabilities from Adobe. Tags give customers a simple way to deploy and manage analytics, marketing, and advertising tags necessary to power relevant customer experiences. In Content Analytics, Adobe's tag management system lets you deploy tracking code on your website without you having to edit every page similarly. The Tags functionality is similar to functionality that you might know from Google Tag Manager. |
| **Sandbox** | Experience Platform provides [sandboxes](https://experienceleague.adobe.com/en/docs/experience-platform/sandbox/home) which partition a single Experience Platform instance into separate virtual environments to help develop and evolve digital experience applications. Content Analytics typically uses the *Production* sandbox. |
| **Connection** | [Connections](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-connections/overview) define what Experience Platform datasets are ingested. A connection defines the link between your dataset (where data is stored in AEP) and Customer Journey Analytics (where you analyze it). A connection makes your collected data available for reporting. |
| **Data View** | A [data view](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/data-views) is a container that lets you determine how to interpret data from a connection. A data view specifies all dimensions and metrics that are available for you to report on. A data view is like a configuration that determines the rows and columns available for you to use in your analysis. |
| **Analysis Workspace** | [Analysis Workspace](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/home) is a drag-and-drop browser interface that you use to build your Content Analytics reports and analyses. |
| **Experience** | In Content Analytics, an [experience](https://experienceleague.adobe.com/en/docs/analytics-platform/using/content-analytics/content-analytics#terminology) refers to all the text content on a web page that can be captured and analyzed based on the page URL. |
| **Asset**| In Content Analytics, an [asset](https://experienceleague.adobe.com/en/docs/analytics-platform/using/content-analytics/content-analytics#terminology) is an individual and unique piece of content, like an image. |


## Setup overview

This configuration guides you in the setup of all applications that are required to have a working **standalone** Content Analytics implementation. You can divide the setup in three phases, where each phase builds upon the previous one:

**Phase 1** - [Prepare your environment](#prepare-your-environment). In this phase, you set up user permissions and verify your data infrastructure. Without these proper permissions and data structure, you are not able to complete the remaining steps. The steps involved are:

1. **Configure access control and permissions** to support the Content Analytics configuration and implementation.
1. **Set up a schema and dataset** to define the model (schema) of the data you want to collect content analytics insights from and where to collect that data (dataset).

**Phase 2** - [Configure data collection](#configure-data-collection). In this phase, you create the pipeline that captures content data from your website. So, Content Analytics knows what content visitors engage with your content.

1. **Set up a datastream** to configure how your collected data is routed to the dataset.
1. **Use website tags** to configure rules and data elements against the data in your data layer on your website and to ensure that data is sent to the configured datastream. 
1. **Deploy** to a test environment **and validate** the data collection before you publish to a production environment.

**Phase 3** - [Set up reporting](#set-up-reporting). In this phase, make your collected data available for analysis in reports. So, you can actually get the content performance insights you want to get out of Content Analytics.

1. **Set up a connection** to your dataset.
1. **Set up a data view** to define metrics and dimensions.
1. **Configure and implement Content Analytics**.
1. **Set up a project** to build your Content Analytics reports and visualizations.


## Prepare your environment

In this phase, you set up user permissions and verify your data infrastructure.

### Configure access control and permissions

This section documents what access you require to product, product profiles and which permissions are required to configure and set up standalone Content Analytics. Although you are only interested in the functionality of Content Analytics, for that functionality to work properly, you still require access and permissions for other Experience Platform products.

#### Access control

Access control determines whether you are allowed access to an Experience Platform product.

You need either a system administrator or a product administrator to add you as an administrator for a product or a product profile. A product administrator can only add you as an administrator for the administered product (profile), a system administrator can add product administrators to any product (profile).

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Manage users for a product profile](https://video.tv.adobe.com/v/333860/?quality=12&learn=on){target="_blank"} for a demo video.


>[!ENDSHADEBOX]

You need to be a product admin to the following products and product profiles for standalone Content Analytics:

* Adobe Experience Platform
  * AEP-Default-All-Users (the default profile for access to the production sandbox)

* Adobe Experience Platform Data Collection
  * Default Data Collection All Access

* Adobe Experience Platform Privacy Service
  
* Customer Journey Analytics (Custom)
  * Customer Journey Analytics (or any other default provisioned product profile)

You define product administrator access through the Admin Console:

1. Access [Admin Console](https://adminconsole.adobe.com).
1. Select **[!UICONTROL Products]**.
1. Select the specific product.
1. Select the **[!UICONTROL Admins]** tab.
1. Select **[!UICONTROL Add admin]** to add an administrator to the product.
1. Enter one or more email or user names in the **[!UICONTROL Add product administrators]** dialog. Select **[!UICONTROL Save]** to save.


You define product profile administrator access through the Admin Console:

1. Access [Admin Console](https://adminconsole.adobe.com).
1. Select **[!UICONTROL Products]**.
1. Select the specific product. Ensure you already have product administrator access.
1. Select **[!UICONTROL Product profiles]**.
1. Select the specific product profile.
1. Select the **[!UICONTROL Admins]** tab.
1. Select **[!UICONTROL Add admin]** to add an administrator to the product profile.
1. Enter one or more email or user names in the **[!UICONTROL Add product profile administrators]** dialog. Select **[!UICONTROL Save]** to save.
   

#### Permissions

Permissions define what you can do within a product once you do have access to the product.

You define permissions for Experience Platform in the [!UICONTROL Permissions] interface and you use attribute based access control. For Customer Journey Analytics, you define permissions through the [!UICONTROL Admin Console].

##### Experience Platform

The [!UICONTROL Permissions] interface in Experience Platform is based on the definition of a role. A role is a collection of resource based permissions. In a new provisioned environment, two default roles are available: **[!UICONTROL Default Production All Access]** and **[!UICONTROL Sandbox Administrators]**.

For Content Analytics, you need to verify whether the following resources and associated permissions are added to these roles:

* Default Production All Access role

  * Data Collection
    * View Datastreams
    * Manage Datastreams

  * Data Management
    * View Datasets
    * Manage Datasets

  * Data Modeling
    * View Schemas
    * Manage Schemas
    * Manage Identity Metadata


* Sandbox Administrators role
  
  * Sandboxes
    * Prod
    * (any other sandbox you want to use for Content Analytics)

  * Sandbox Administration
    * Manage Packages
    * Manage Sandboxes
    * Reset Sandbox
    * View Sandbox


Within the Permissions interface you can verify both roles and associated permissions. And which users belong to the role.

1. Access Experience Platform for your organization.
1. In the welcome screen, in **[!UICONTROL Quick access]**, select **[!UICONTROL View all]**.
1. Enable the pin ![PinOn](/help/assets/icons/PinOn.svg) for **[!UICONTROL Permissions]**, so **[!UICONTROL Permissions]** becomes available within **[!UICONTROL Quick Access]** for future use.
1. Select **[!UICONTROL Permissions]**.
1. Select ![User](/help/assets/icons/User.svg) **[!UICONTROL Roles]**.
1. Select the specific role that you want to verify (for example, **[!UICONTROL Default Production All Access]**). Select **[!UICONTROL View all]** to see all permissions.
1. In the **[!UICONTROL Details]** screen: 
   1. Verify the **[!UICONTROL Resources]** listed in **[!UICONTROL Permissions]**.
   1. Verify the sandbox names in **[!UICONTROL Sandboxes]**.
   
   To make any updates, select ![Edit](/help/assets/icons/Edit.svg) **[!UICONTROL Edit]**.
   1. To add a missing resource, select **[!UICONTROL Resource name]** ![Add](/help/assets/icons/Add.svg) from the **[!UICONTROL Resources]** > **[!UICONTROL Adobe Experience Platform]** left rail.
   1. To add a missing permission, select ![ChevronDown](/help/assets/icons/ChevronDown.svg) within the resource that is missing the permission in the main panel, and select the missing permission.

      ![Permissions interface](/help/content-analytics/assets/aep-permissions-ui.png)

   Select **[!UICONTROL Save]** to save any update.

1. In the Users or Users groups screen:
   1. Verify the right individual users or group of users are part of this role.
      1. Select ![UserAdd](/help/assets/icons/UserAdd.svg) Add Users in Users to add individual users you have defined in Admin Console.
      1. Select ![Add](/help/assets/icons/Add.svg) Add Groups in Users groups to add user groups you have defined in Admin Console.


##### Customer Journey Analytics

Customer Journey Analytics does not support attribute based access control. To specify permissions, you use the Admin Console.

For Content Analytics, you need to verify whether the following Customer Journey Analytics product profile permissions are included:

* Data views
  * All available data views.

* Reporting Tools
  * Guided Analysis Access?
  * Calculated Metrics Creation
  * Segment Creation
  * Labs Access?
  * Annotation Creation
  * Audience Creation?
  * Audience View?
  * Audit Logs Access
  * Share Project Links With Anyone
  * Forecasting
  * AI Assistant: Product Knowledge
  * Data Insights Agent
  * Intelligent Captions
  * Data Storytelling?

* Data View Tools
  * Full Table Export?
  * CJA BI Extension?

To verify and update these permissions for Customer Journey Analytics:

1. Access [Admin Console](https://adminconsole.adobe.com).
1. Select **[!UICONTROL Products]**.
1. Select the **[!UICONTROL Customer Journey Analytics]** product.
1. Select **[!UICONTROL Product profiles]**.
1. Select the default provisioned product profile that is available for Customer Journey Analytics. For example: **[!UICONTROL Customer Journey Analytics]**.
1. In the product profile screen, select **[!UICONTROL Permissions]**.
1. Select any of the ![Edit](/help/assets/icons/Edit.svg) buttons to edit the permissions. In the **[!UICONTROL Edit permissions for Customer Journey Analytics]** dialog:

   ![CJA Permissions UI](../assets/cja-permissions-ui.png)

   1. Select **[!UICONTROL Data Views]** and enable **[!UICONTROL Auto-include: On]**. This toggle ensures that all data views are automatically part of the **[!UICONTROL Included permission items]**.
   1. Select **[!UICONTROL Reporting Tools]** and ensure all permissions listed above are part of the **[!UICONTROL Included permission items]**.
   1. Select **[!UICONTROL Data View Tools]** and ensure all permissions listed above are part of the **[!UICONTROL Included permission items]**.

   Select **[!UICONTROL Save]**.


### Set up schema and dataset

To collect data from your website, subject to Content Analytics insights, you first need to define what kind of data you want to collect. And also how that data is stored. Both concepts are explained in [Setup a schema and dataset](/help/data-ingestion/aepwebsdk.md#set-up-a-schema-and-dataset) in the [Ingest data via the Adobe Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) quick start guide.


## Configure data collection

In this phase you create the pipeline that captures content data from your website.

### Set up a datastream 

You have defined what data to collect and how to store that data. The next step is to ensure that the data collected from your website is routed to the dataset. You need to set up and configure a datastream, which is explained in [Setup a datastream](/help/data-ingestion/aepwebsdk.md#set-up-a-datastream) in the [Ingest data via the Adobe Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) quick start guide.


### Use Tags

You have defined what data to collect (schema), how to store that data (dataset) and how collected data from your website is routed to the dataset (datastream). As a next step, you need to tag your website to configure rules and data elements against the data in your data layer on your website. Tagging your website ensures that data is sent to the configured datastream. The tagging of your website with the help of Tags is explained in [Use Tags](/help/data-ingestion/aepwebsdk.md#use-tags) in the [Ingest data via the Adobe Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) quick start guide.


### Deploy and validate

You can now deploy the code on the development version of your website inside the `<head>` tag. When deployed, your website starts collecting data into Adobe Experience Platform. That data is then subject to Content Analytics.

Validate your implementation, correct it where necessary, and once correct, deploy it to your staging and production environment using the publishing workflow feature of Tags


## Set up reporting

In this phase you make the collected data available for analysis in reports.

### Set up a connection to your dataset

To report on the collected data and to configure that data for Content Analytics, you need to set up a connection in Customer Journey Analytics. The connection connects to the dataset that contains the collected data. How to set up a connection is explained in [Set up a connection](../../data-ingestion/aepwebsdk.md#set-up-a-connection) in the [Ingest data via the Adobe Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) quick start guide.


### Set up a data view

The final step before you can configure Content Analytics, is to define a data view. A data view is a container specific to Customer Journey Analytics that lets you determine how to interpret data from a connection. A data view allows you to define metrics and dimensions from the data from one or more datasets to which Customer Journey Analytics is connected. How to set up a data view is explained in [Set up a data view](/help/data-ingestion/aepwebsdk.md#set-up-a-data-view) in the [Ingest data via the Adobe Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) quick start guide.


### Configure Content Analytics

You now have everything in place to configure Content Analytics. 

#### Guided configuration

Use the [guided configuration wizard](guided.md) and select the data view you created as part of the [Setup a data view](#set-up-a-data-view) step. That selection ensures that Content Analytics is configured and implemented on top of the data you collect from your website.

Be aware that the guided configuration wizard configures the following additional specific Content Analytics objects: 

* **Dataset**, which is set up automatically for Content Analytics events. This dataset uses a specific Content Analytics schema that is already created and available.
* **Datastream**, which is set up automatically to stream Content Analytics events into the Content Analytics dataset.
* **Tags property**, which is set up automatically and configured with the Content Analytics extension. This Tags property ensures that your website sends Content Analytics data to the Content Analytics datastream and the Content Analytics dataset. 
  
  >[!IMPORTANT]
  >
  >Ensure you select the option to create a New Tags property as part of the [Data collection](guided.md#new-configuration-1) step in the wizard.
  >


#### Manual configuration

To implement Content Analytics for your website, you need to publish the Content Analytics Tags property [manually](manual.md). 


### Set up a project

Set up a project in Customer Journey Analytics to build your [Content Analytics reports and visualizations](/help/content-analytics/report/report.md). Alternatively, you can use a [Content Analytics template](/help/content-analytics/report/report.md#template) to get started.
