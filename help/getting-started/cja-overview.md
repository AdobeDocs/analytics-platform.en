---
title: Customer Journey Analytics overview
description: Customer Journey Analytics introduction
---

# Customer Journey Analytics overview

Customer Journey Analytics is an Analytics capability that lets you use the power of Analysis Workspace with data from Adobe Experience Platform. It can break down, filter, query, and visualize years' worth of data, and is combined with Platform's ability to hold all kinds of data schemas and types. Using the **Experience Data Model (XDM)**, data can be uniformly represented and organized, ready for combination and exploration. **Experience Query Services** allows you to use SQL-compatible tools and frameworks to query and manipulate all your data.

## Comparing CJA to Traditional Adobe Analytics

Customer Journey Analytics expands the scope of Analytics by offering easy-to-use cross-channel capabilities and removing limitations in previous versions of Adobe Analytics. Some notable improvements are:

* **Unlimited variables and events**: The concepts of eVars, props, and events no longer exist. Data is primarily focused on dimensions and metrics. Data sets can have an unlimited amount of unique dimensions and metrics.
* **Unlimited unique values**: Adobe Experience Platform is not constrained to any unique limitations, such as the 500k unique values in traditional report suites.
* **Alter historical data**: Using Adobe Experience Platform, data can be removed or corrected.
* **Cross-report-suite data**: Existing implementations from multiple data sets can be combined in Platform.

The initial release of Customer Journey Analytics includes many of the features included in Analysis Workspace. For a complete list, see [Customer Journey Analytics feature support](cja-aa.md).

## Comparing CJA to Cross-Device Analytics

[Cross-Device Analytics](https://docs.adobe.com/content/help/en/analytics/components/cda/cda-home.html) integrates with Adobe Experience Platform Identity Service, utilizing either the Co-op Graph or Private Graph, to identify how digital devices map to people. It is available for Adobe Analytics Ultimate customers.

CJA, on the other hand, integrates with Adobe Experience Platform datasets and enables cross-channel analysis in Analysis Workspace. Although CJA does not yet integrate with the Co-op or Private identity graphs, you can "bring your own ID" to join datasets together, and those datasets can go beyond digital data to include both online and offline touchpoints. CJA prerequisites are covered in more detail below.

## Key use cases

Customer Journey Analytics lets you:

* **See the customer in a journey context**: You can view and analyze data sequentially, spanning multiple channels. Data from your call center, POS systems, and online properties can be combined into a single reporting view.
* **Make insights available to everyone**: Democratize data access and let more people make business decisions with data-derived insights. Anyone in the organization with responsibility for any aspect of the customer experience can make real decisions faster, based on more complete data.
* **Harness the power of data science for your analysts**: Customer Journey Analytics lets normal humans use data science to unlock deep insights and analysis.
* **Visualize and interact with your datasets using ad-hoc reporting**: Workspace can use any dataset from Adobe Experience Platform that conform to some basic rules.
* **View non-web data**: Workspace is no longer limited to a rigid definition of a 'hit' or 'event'. Custom schemas allow complete control over data and definitions.
* **Exert greater control over your data manipulation**: Change data you've uploaded, create new datasets, and import them into Workspace. Adobe Experience Platform provides querying, extracting, transforming, and loading tools through the Experience Cloud Query Service.

## Prerequisites

Before you can start using Customer Journey Analytics, the following prerequisites must be met:

* Your organization has an active contract with Adobe Analytics for Select, Prime, or Ultimate with the Customer Journey Analytics add-on. If you are not sure what type of contract you have, or are not sure if you have the CJA add-on, contact your organization's Account Manager.
* Your organization has been provisioned for Adobe Experience Platform.

## Admin Access Permissions

To create connections, add datasets, etc., you need the following permissions in the [Admin Console](https://adminconsole.adobe.com/enterprise/):

* As of Sept. 9, 2020, to access Customer Journey Analytics or make a connection, you will need to be added as an Admin to a **Customer Journey Analytics Product Profile** in the [Admin Console](https://adminconsole.adobe.com/enterprise/). Admins need the following permissions:
  * Create/update/delete Connections or Data Views
  * Update/delete projects, filters, calc metrics, or segments created by other users
  * Share a Workspace project to all users
* Becoming a product admin within Customer Journey Analytics is not enough to create create, update, or delete a Connection. To create a connection to an Experience Platform dataset, you also need Experience Platform permissions. Specifically, you must be part of an **Experience Platform Product Profile** that gives you the following permissions:
  * View Schemas
  * Manage Schemas
  * View Identity Namespaces
  * View Datasets
  
For more information on Experience Platform permissions, see [Access control in Adobe Experience Platform](https://www.adobe.io/apis/experienceplatform/home/permissions-and-sandboxes/permissions-and-sandboxes.html#!api-specification/markdown/narrative/technical_overview/access-control/access-control-overview.md).

### User access

Non-admins (users) in Customer Journey Analytics cannot view Data Views or Connections, but can create filters, projects, and calculated metrics.

## Terminology updates

Several features in CJA have been renamed, when compared to traditional Adobe Analytics, to align with industry standards. Some updated terminology includes:

* Segments are now known as 'Filters'.
* Virtual Report Suites are now known as 'Views'.
* Classifications are now known as 'Lookup datasets'.
* Customer attributes are now known as 'Profile datasets'.
* Hit containers are now known as 'Event' containers.
* Visit containers are now known as 'Session' containers.
* Visitor containers are now known as 'Person' containers.

## Other capabilities built on Adobe Experience Platform

Customer Journey Analytics is one capability among many that rely on the Adobe Experience Platform. Several other capabilities, also built on Experience Platform, let you get the most out of your data.

Adobe Experience Platform lets you centralize and standardize customer data and content from any system and apply data science and machine learning to improve the design and delivery of personalized experiences. Customer data in the platform is stored as datasets,which consist of a schema and batches of data. For more detail on the platform, see [Adobe Experience Platform Architecture Overview](https://www.adobe.io/apis/experienceplatform/home/overview.html).

From Data Ingestion to direct SQL access, several components of the Experience Platform are central to Customer Journey Analytics and act in conjunction with it:

* [Query Service](https://www.adobe.io/apis/experienceplatform/home/query-service/sql-reference.html): Use standard SQL to retrieve data from Adobe Experience Platform, such as Adobe solution data, customer 1st-party data, or any other Platform data. It is a serverless tool that allows you to join any datasets and capture the query results as a new dataset for use in reporting, Data Science Workspace, or for ingestion into Profile Service. You can use Query Service to build data analysis ecosystems, creating a picture of consumers across their various interaction channels. These channels might include Point-of-Sale systems, Web, Mobile, CRM systems, etc.
* [Real-time Customer Profile](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/unified_profile_architectural_overview/unified_profile_architectural_overview.md):
* [Identity Service](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/identity_services_architectural_overview/identity_services_architectural_overview.md):
* [Data Science Workspace](https://www.adobe.io/apis/experienceplatform/home/data-science-workspace.html) in "developer" option: you can use prebuilt artificial intelligence (AI) and machine-learning models in Adobe Experience Platform to influence various points of the customer journey. By unearthing hidden insights, you can make better predictions across the customer journey, suggest recommended best next steps, or automate cumbersome processes.
