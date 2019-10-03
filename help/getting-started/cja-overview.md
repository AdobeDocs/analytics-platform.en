---
title: [!UICONTROL Customer Journey Analytics] overview
seo-title: Overview of [!UICONTROL Customer Journey Analytics]
description: [!UICONTROL Customer Journey Analytics] overview.
seo-description: [!UICONTROL Customer Journey Analytics] overview.
---

# [!UICONTROL Customer Journey Analytics] overview
 
[!UICONTROL Customer Journey Analytics] is a groundbreaking new Analytics capability that lets you use the power of Analysis Workspace for rapid insights to analyze the customer journey across channels, using any data available to you in Adobe Experience Platform (AEP). By now, you are familiar with Workspace, which allows reporting and exploration at the "speed of thought." Its ability to break down, filter, query, and visualize years' worth of data, often in seconds, is now being combined with the AEP's ability to hold all of your data with all kinds of schemas and types, coming from unique channels and sources. Using the **Experience Data Format (XDM)** (link) allows data to be uniformly represented and organized, ready for combination and exploration. **Experience Query Services (EQS)** allows you to use SQL-compatible tools and frameworks to query and manipulate all your data.

[!UICONTROL Customer Journey Analytics] lets you:

* **See the customer in a journey context.** You can view and analyze data sequentially, spanning multiple channels such as call center, POS systems, and online properties and combine them into a single reporting view (Data Group).
* **Make insights available to everyone.** Democratize data access and let more people make business decisions with data-derived insights. Anyone in the organization with repsonsibility for any aspect of the customer experience can make real decisions faster, based on more complete data.
* **Harness the power of data science for your analysts.** [!UICONTROL Customer Journey Analytics] lets normal humans use data science to unlock deep insights and analysis.
* **Visualize and interact with your datasets using ad-hoc reporting.** Workspace can import any Datasets in Platform that conform to some basic rules.
* **View non-web data.** Because Dataset schemas can be customized, Workspace is no longer limited to a rigid definition of what a "hit" or event must be. Evars, props, uniques exceeded, and other Adobe Analytics limitations no longer apply.
* **Exert greater control over your data manipulation.** Because ECP provides basic querying and ETL (Extract, Transform, Load) tools via Experience Cloud Query Service (EQS), you can now change data you've uploaded, create new Datasets, and then import them into Workspace. Not needing to wait for new SQL queries to run means faster decision making and more immediate impact on your customers.

![](assets/cja-capabalities.png)

## How does CJA differ from our traditional Adobe Analytics product?

|Functionality|Adobe Analytics|Customer Journey Analytics|
|eVars, props|These variables are ...|blablabla|

## Prerequisites

Before you can start using [!UICONTROL Customer Journey Analytics], you need to complete the following steps for your organization:

* You have to be an Analytics Ultimate customers to take advantage of this new Analytics capability.
* You need to enable Experience Cloud Platform (what do we link to?)
* ?Enable [!UICONTROL Customer Journey Analytics] (temporary requirement)?

## Adobe Analytics features supported by [!UICONTROL Customer Journey Analytics]

* Attribution IQ
* Segmentation (now called "Filters")
* All Workspace visualizations except Map
* Calculated Metrics
* Project Sharing to other CJA users
* Virtual Report Suites (now called "Views")
* Classifications (now called "Lookup datasets")
* Customer attributes (now called "Profile datasets") - allows onboarding of audiences from United Profile

## Current limitations

[!UICONTROL Customer Journey Analytics] currently does not provide support for the following features:

* Anomaly Detection and Contribution Analysis
* Segment Comparison (Segment IQ)
* Segment/audience sharing to Profile or other EC solutions
* PDF export, CSV export, scheduled reports, emailed reports
* Alerts and Intelligent Alerts
* API access
* Report Builder
* Marketing Channels dimensions
* Segments, calc. metrics, date ranges, or projects that were created in the current Analytics tools
