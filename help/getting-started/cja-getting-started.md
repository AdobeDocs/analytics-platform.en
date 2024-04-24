---
title: Customer Journey Analytics Getting Started
description: Understand the prerequisites and workflow required to implement Customer Journey Analytics.
exl-id: cab218c0-009c-4669-9dfb-f8872a7f066b
solution: Customer Journey Analytics
feature: Basics
role: User
---
# Customer Journey Analytics Getting Started

To implement Customer Journey Analytics, you need to follow this workflow. Some initial tasks are performed in Adobe Experience Platform, and some in Customer Journey Analytics.

## Prerequisites

Customer Journey Analytics is available for customers who 

* Are provisioned for the [Adobe Experience Platform](https://www.adobe.com/experience-platform.html), and 
* Have purchased the Customer Journey Analytics SKU

## Workflow

| Task | Details |
| --- | --- |
| **Step 1: If you are migrating from Adobe Analytics to Customer Journey Analytics: Choose a migration path and send data to Adobe Experience Platform** | There are various paths available when migrating from Adobe Analytics to Customer Journey Analytics. Each possible migration path has its own advantages and disadvantages, and a path that is right for one organization might not make sense for another. <p>To begin migrating from Adobe Analytics to Customer Journey Analytics, see [Get started with the migration to Customer Journey Analytics](/help/getting-started/cja-migration/cja-migration-getstarted.md). <!-- [Utilizing Adobe Analytics report suite data in Customer Journey Analytics](/help/getting-started/aa-vs-cja/aa-data-in-cja.md) --> </p> |
| **Step 2: Get other data into Adobe Experience Platform** | This step, performed in Adobe Experience Platform, involves several sub steps:<ul><li>**Step 2a: Prepare your data schema**: Use [Adobe Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) to standardize customer experience data and [define schemas](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html) for customer experience management.</li><li>**Step 2b: Create a dataset based on the schema**: Data in Platform consists of datasets, such as email datasets, CRM datasets, POS datasets, the Adobe Analytics dataset, etc.. Each dataset consists of a schema and batches of data. You can [create a dataset in Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/create-datasets.html).</li><li>**Step 2c: Ingest data into Experience Platform**: Here, you have several options.</li></ul> |
| **Step 3: Create connections between platform datasets and Customer Journey Analytics** | A connection lets you integrate datasets from Adobe Experience Platform into Workspace. In order to report on Experience Platform datasets, you first have to establish a connection between datasets in Experience Platform and Workspace.<br>See [Create or edit a connection](/help/connections/create-connection.md). |
| **Step 4: Create data views** | A data view is a "filtered" view of the data. You can create different data views for the same connection, with different settings for visit timeout, attribution, etc.. You can create multiple data views for a single dataset.<br>See [Create a data view](/help/data-views/create-dataview.md). |
| **Step 5: Port the reporting API usage**</br>Applies only when migrating from Adobe Analytics | The Customer Journey Analytics reporting API is in the same format, but uses a different endpoint. Port the reporting API usage from the Adobe Analytics reporting API to the Customer Journey Analytics reporting API. | 
| **Step 6: Account for Data Feeds and Data Warehouse use cases**</br>Applies only when migrating from Adobe Analytics | Decide how you will use the export options that are available in Customer Journey Analytics in order to best replicate the Data Feeds and Data Warehouse features you were using in Adobe Analytics. <!-- link to docs Rob is creating --> |
| **Step 7: Migrate projects and components**</br>Applies only when migrating from Adobe Analytics | The Component migration area in Adobe Analytics allows you to migrate projects and their associated components from Adobe Analytics to Customer Journey Analytics.<p>For information about replicating your Adobe Analytics projects in Customer Journey Analytics, as well as mapping project components from an Adobe Analytics report suite to a Customer Journey Analytics data view, see [Migrate components and projects from Adobe Analytics to Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration.html).</p>  |
| **Step 8: Plan user onboarding** | Like in Adobe Analytics, Analysis Workspace is the main user-facing tool in Customer Journey Analytics. However, there are some key differences when using Analysis Workspace in Customer Journey Analytics that users need to be aware of.<p>You should give your users ample time (3 - 6 months) to become familiar with the key differences of Analysis Workspace in Customer Journey Analytics.</p><p>For information about some of the key differences between Adobe Analytics and Customer Journey Analytics, see [User Guide for Adobe Analytics users](/help/getting-started/aa-to-cja-user.md).</p> | 
| **Step 9: Report on your cross-channel data in Workspace** | After you have created connections and data views, analyze the data you have brought in using the power and flexibility of Analysis Workspace.<br>See [Perform basic analysis](/help/analysis-workspace/perform-basic-analysis.md) and [Perform advanced analysis](/help/analysis-workspace/perform-adv-analysis.md). |

## Quick start guides

The [Data ingestion](../data-ingestion/data-ingestion.md) section provides quick start guides on the workflow above. These quick start guides illustrate how to ingest data from a variety of sources (including Adobe Analytics) in Adobe Experience Platform and then use that data in Customer Journey Analytics.
