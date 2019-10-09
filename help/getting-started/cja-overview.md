---
title: [!UICONTROL Customer Journey Analytics] overview
seo-title: Overview of [!UICONTROL Customer Journey Analytics]
description: [!UICONTROL Customer Journey Analytics] overview.
seo-description: [!UICONTROL Customer Journey Analytics] overview.
---

# [!UICONTROL Customer Journey Analytics] overview

Imagine your favorite Analytics tool, Analysis Workspace, taking advantage of the power of [!UICONTROL Adobe Experience Platform] (AEP) and the myriad cross-channel datasets in it! 

![](assets/cja-multi-flow.png)
 
[!UICONTROL Customer Journey Analytics] (CJA) is a new Analytics capability that lets you use the power of Analysis Workspace for rapid insights to analyze the customer journey across channels, using any data available to you in Adobe Experience Platform (AEP). By now, you are familiar with Workspace, which allows reporting and exploration at the "speed of thought." Its ability to break down, filter, query, and visualize years' worth of data, often in seconds, is now being combined with the AEP's ability to hold all of your data with all kinds of schemas and types, coming from unique channels and sources. Using the **Experience Data Model (XDM)** (link) allows data to be uniformly represented and organized, ready for combination and exploration. **Experience Query Services (EQS)** allows you to use SQL-compatible tools and frameworks to query and manipulate all your data.

## Key use cases

[!UICONTROL Customer Journey Analytics] lets you:

* **See the customer in a journey context.** You can view and analyze data sequentially, spanning multiple channels such as call center, POS systems, and online properties and combine them into a single reporting view (Data Group).
* **Make insights available to everyone.** Democratize data access and let more people make business decisions with data-derived insights. Anyone in the organization with responsibility for any aspect of the customer experience can make real decisions faster, based on more complete data.
* **Harness the power of data science for your analysts.** [!UICONTROL Customer Journey Analytics] lets normal humans use data science to unlock deep insights and analysis.
* **Visualize and interact with your datasets using ad-hoc reporting.** Workspace can import any datasets in AEP that conform to some basic rules.
* **View non-web data.** Because dataset schemas can be customized, Workspace is no longer limited to a rigid definition of what a "hit" or event must be. Evars, props, uniques exceeded, and other Adobe Analytics limitations no longer apply.
* **Exert greater control over your data manipulation.** Because AEP provides basic querying and ETL (Extract, Transform, Load) tools via Experience Cloud Query Service (EQS), you can now change data you've uploaded, create new datasets, and then import them into Workspace. Not needing to wait for new SQL queries to run means faster decision making and more immediate impact on your customers.

See also slide 10 in Trevor's deck.

## Adobe Experience Platform and CJA

Adobe Experience Platform (AEP) enables organizations to centralize and standardize customer data and content from any system and apply data science and machine learning to improve the design and delivery of rich, personalized experiences. For more detail on the platform, see [Adobe Experience Platform Architecture Overview](https://www.adobe.io/apis/experienceplatform/home/overview.html).

![](assets/cja-capabilities.png)

From Data Ingestion to direct SQL access, several components of the Experience Platform are central to CJA and act in conjunction with it:

* Data Lake: (This doesn't appear to be an official AEP term). [AEP Glossary](https://www.adobe.io/apis/experienceplatform/home/services/acp-glossary.html)

* [Query Service](https://www.adobe.io/apis/experienceplatform/home/services/query-service/query-service.html#!end-user/markdown/query-service/qs-intro.md): Query Service lets you use standard SQL to retrieve data from Adobe Experience Platform, such as Adobe solution data, customer 1st-party data, or any other Platform data. It is a serverless tool that allows you to join any datasets in Experience Data Lake and capture the query results as a new dataset for use in reporting, Data Science Workspace, or for ingestion into Profile Service. You can use Query Service to build data analysis ecosystems, creating a picture of consumers across their various interaction channels. These channels might include Point-of-Sale systems, Web, Mobile, CRM systems, etc.

* [Real-time Customer Profile](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/unified_profile_architectural_overview/unified_profile_architectural_overview.md):

* [Identity Service](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/identity_services_architectural_overview/identity_services_architectural_overview.md):

* [Data Science Workspace](https://www.adobe.io/apis/experienceplatform/home/data-science-workspace.html) in "developer" option: 

## How does CJA differ from our traditional Adobe Analytics product?

CJA expands the scope of Analytics not just by offering easy-to-use cross-channel capabilities. It also removes some of the traditional limitations. The biggest practical improvements you will notice in CJA are:

* Unlimited variables and events: you are no longer constrained by a maximum number of eVars, props, or events.
* Unlimited uniques: The Adobe Analytics limit of x uniques is no longer relevant.
* You can merge report suites without changes to re-implementation.
* You can report on out-of-order data.
* You can restate and fix historical data.
* You can leverage the power of segmentation, fallout, flow, attribution, etc., on non-web datasets.
* Some of the powerful capabilities found in Data Workbench are now available in Workspace, such as ...

## Data Workbench functionality mapping

Do we want to include this?

## Prerequisites

Before you can start using [!UICONTROL Customer Journey Analytics], you need to complete the following steps for your organization:

* Available to Adobe Analytics Select, Prime, and Ultimate customers.
* You need to enable Adobe Experience Platform (what do we link to?)

## Adobe Analytics features supported by [!UICONTROL Customer Journey Analytics]

The initial release of CJA includes many, but not all, of the features that you are used to using in Adobe Analytics today. 

* Attribution IQ
* Segmentation (now called "Filters")
* All Workspace visualizations except Map
* Calculated Metrics
* Workspace project sharing to other CJA users
* Virtual Report Suites (now called "Views")
* Creating new dataset connections from Platform UI and CJA UI
* Classifications (now called "Lookup datasets")
* Customer attributes (now called "Profile datasets") - allow onboarding of audiences from United Profile

## Current limitations

[!UICONTROL Customer Journey Analytics] currently does not provide support for the following features. However, we are actively working on bringing these features to you in the near future.

* Segment/audience sharing to Profile or other EC solutions
* PDF export, CSV export, scheduled reports, emailed reports
* Marketing Channels dimensions
* API access
* Alerts and Intelligent Alerts
* Report Builder
* Anomaly Detection, Contribution Analysis
* Segment Comparison (Segment IQ)
* Segments, calc. metrics, date ranges, or projects that were created in the current Adobe Analytics tools

## User Access Permissions

As a CJA user, you will have access to your organization's Platform datasets in AEP and CJA:

* No additional permission levels are currently needed
* Once introduced, CJA permissions will be independent of existing Adobe Analytics permissions
* Enabled users will be able to create or modify a connection, or add a dataset to AEP
* Auto-enabling or enabled by Engineering and Customer Care?
