---
title: Customer Journey Analytics overview
description: Customer Journey Analytics introduction
---

# Customer Journey Analytics overview

Imagine your favorite Analytics tool, Analysis Workspace, taking advantage of the power of [!UICONTROL Adobe Experience Platform] and the myriad cross-channel datasets in it! 

![](assets/cja-multi-flow.png)
 
Customer Journey Analytics (Customer Journey Analytics) is a new Analytics capability that lets you use the power of Analysis Workspace for rapid insights to analyze the customer journey across channels, using any data available to you in Adobe Experience Platform (Platform). By now, you are familiar with Workspace, which allows reporting and exploration at the "speed of thought." Its ability to break down, filter, query, and visualize years' worth of data, often in seconds, is now being combined with Platform's ability to hold all of your data with all kinds of schemas and types, coming from unique channels and sources. Using the **Experience Data Model (XDM)** (link) allows data to be uniformly represented and organized, ready for combination and exploration. **Experience Query Services** allows you to use SQL-compatible tools and frameworks to query and manipulate all your data.

## What's new and different about Customer Journey Analytics?

Compared with what you are used to in Adobe Analytics, a number of things are going to be different and new in CJA:

* New concepts and terminology
* New domain (analytics.adobe.com)
* New features (see below)
* Some features that are not supported yet (see below)

Customer Journey Analytics expands the scope of Analytics not just by offering easy-to-use cross-channel capabilities. It also removes some of the traditional limitations. The biggest practical improvements you will notice in CJA are:

* Unlimited variables and events: the concepts of eVars, props, and events no longer exist. You are dealing with dimensions and metrics. As a result, you are no longer constrained by a maximum number of eVars, props, or events.
* Unlimited uniques: The Adobe Analytics limit of x uniques is no longer relevant.
* You can merge report suites without changes to re-implementation.
* You can report on out-of-order data.
* You can restate and fix historical data.
* You can leverage the power of segmentation, fallout, flow, attribution, etc., on non-web datasets.
* Some of the powerful capabilities found in Data Workbench are now available in Workspace, such as ...

### Adobe Analytics features supported by Customer Journey Analytics

The initial release of Customer Journey Analytics includes many, but not all, of the features that you are used to using in Adobe Analytics today. 

* Attribution IQ
* Segments (now called "Filters")
* All Workspace visualizations except Map
* Calculated Metrics
* Workspace project sharing to other Customer Journey Analytics users
* Virtual Report Suites (now called "Views")
* Creating new dataset connections from Platform UI and Customer Journey Analytics UI
* Classifications (now called "Lookup datasets")
* Customer attributes, now called "Profile datasets". They allow on-boarding of audiences from [Real-time Customer Profile](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/unified_profile_architectural_overview/unified_profile_architectural_overview.md)

### Current limitations

Customer Journey Analytics currently does not provide support for the following Analytics features. However, we are actively working on bringing these features to you in the near future.

* Segment/audience sharing to Profile or other Experience Cloud solutions
* PDF export, CSV export, scheduled reports, emailed reports
* Marketing Channels dimensions
* API access
* Alerts and Intelligent Alerts
* Report Builder
* Anomaly Detection, Contribution Analysis
* Segment Comparison (Segment IQ)
* Segments, calc. metrics, date ranges, or projects that were created in the current Adobe Analytics tools

## Key use cases

Customer Journey Analytics lets you:

* **See the customer in a journey context.** You can view and analyze data sequentially, spanning multiple channels such as call center, POS systems, and online properties and combine them into a single reporting view (Data Group).
* **Make insights available to everyone.** Democratize data access and let more people make business decisions with data-derived insights. Anyone in the organization with responsibility for any aspect of the customer experience can make real decisions faster, based on more complete data.
* **Harness the power of data science for your analysts.** Customer Journey Analytics lets normal humans use data science to unlock deep insights and analysis.
* **Visualize and interact with your datasets using ad-hoc reporting.** Workspace can import any datasets in AEP that conform to some basic rules.
* **View non-web data.** Because dataset schemas can be customized, Workspace is no longer limited to a rigid definition of what a "hit" or event must be. Evars, props, uniques exceeded, and other Adobe Analytics limitations no longer apply.
* **Exert greater control over your data manipulation.** Because AEP provides basic querying and ETL (Extract, Transform, Load) tools via Experience Cloud Query Service (EQS), you can now change data you've uploaded, create new datasets, and then import them into Workspace. Not needing to wait for new SQL queries to run means faster decision making and more immediate impact on your customers.

## Prerequisites

Before you can start using Customer Journey Analytics, you need to complete the following steps for your organization:

* Make sure you are an Adobe Analytics Select, Prime, or Ultimate customers.
* Make sure you are enabled for the Adobe Experience Platform.
* Make sure you have the Customer Journey Analytics SKU.

## User Access Permissions

To create connections, add datasets, etc., you need the following permissions in the [Admin Console](https://adminconsole.adobe.com/enterprise/):

* To manage datasets in the Experience Platform, you must be part of a Platform Product Profile that gives you the "Manage Datasets" permission. For more information, see [Access control in Adobe Experience Platform](https://www.adobe.io/apis/experienceplatform/home/permissions-and-sandboxes/permissions-and-sandboxes.html#!api-specification/markdown/narrative/technical_overview/access-control/access-control-overview.md).

* To create a connection to a Platform dataset, you must be part of a Platform Product Profile that gives you the following permissions:

    * View Schemas
    * View Datasets
    * Manage Identity Namespaces
    * View Sandboxes

* To access Customer Journey Analytics or make a connection, you will also need to be added to a Customer Journey Analytics Product Profile in the [Admin Console](https://adminconsole.adobe.com/enterprise/). (More detail to follow).

## Adobe Experience Platform and Customer Journey Analytics

Adobe Experience Platform lets you centralize and standardize customer data and content from any system and apply data science and machine learning to improve the design and delivery of personalized experiences. Customer data in the platform is stored as datasets,which consist of a schema and batches of data. For more detail on the platform, see [Adobe Experience Platform Architecture Overview](https://www.adobe.io/apis/experienceplatform/home/overview.html).

From Data Ingestion to direct SQL access, several components of the Experience Platform are central to Customer Journey Analytics and act in conjunction with it:

* Dataset: A platform dataset consists of a schema and rows of data that represent your customer data in the platform. For example, an email dataset schema might consist of a customer ID, email reason, validation timestamp, email opened, email sent, email delivered, validation data source, validation tracking code, etc. You can include the Adobe Analytics dataset and other Adobe solution datasets as part of your platform datasets. <!--how do they get the Adobe datasets into the platform?>

* Data Lake: (This doesn't appear to be an official AEP term). [AEP Glossary](https://www.adobe.io/apis/experienceplatform/home/services/acp-glossary.html)

* [Query Service](https://www.adobe.io/apis/experienceplatform/home/services/query-service/query-service.html#!end-user/markdown/query-service/qs-intro.md): Query Service lets you use standard SQL to retrieve data from Adobe Experience Platform, such as Adobe solution data, customer 1st-party data, or any other Platform data. It is a serverless tool that allows you to join any datasets in Experience Data Lake and capture the query results as a new dataset for use in reporting, Data Science Workspace, or for ingestion into Profile Service. You can use Query Service to build data analysis ecosystems, creating a picture of consumers across their various interaction channels. These channels might include Point-of-Sale systems, Web, Mobile, CRM systems, etc.

* [Real-time Customer Profile](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/unified_profile_architectural_overview/unified_profile_architectural_overview.md):

* [Identity Service](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/identity_services_architectural_overview/identity_services_architectural_overview.md):

* [Data Science Workspace](https://www.adobe.io/apis/experienceplatform/home/data-science-workspace.html) in "developer" option: you can use prebuilt artificial intelligence (AI) and machine-learning models in Adobe Experience Platform to influence various points of the customer journey. By unearthing hidden insights, you can make better predictions across the customer journey, suggest recommended best next steps, or automate cumbersome processes.
