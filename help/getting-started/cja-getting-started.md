---
title: Customer Journey Analytics Getting Started
description: Customer Journey Analytics Getting Started.
---

# Customer Journey Analytics Getting Started

To implement Customer Journey Analytics, you need to follow this workflow. Some tasks are performed in Adobe Experience Platform, and some in Customer Journey Analytics.

## Prerequisites

* Make sure you are an Adobe Analytics Select, Prime, or Ultimate customers.
* Make sure you are provisioned for the Adobe Experience Platform.
* Make sure you have the Customer Journey Analytics SKU.

## Workflow

|Task|Where performed|Details|
|---|---|---|
|**Step 1: Prepare your data schema**|Adobe Experience Platform|Use [Adobe Experience Data Model (XDM)](https://www.adobe.io/apis/experienceplatform/home/xdm.html) to standardize customer experience data and define schemas for customer experience management.|
|**Step 2: Create a dataset based on the schema**|Adobe Experience Platform|Data in Platform consists of data sets, such as email data sets, CRM datasets, POS data sets, the Adobe Analytics dataset, etc.. Each data sets consists of a schema and batches of data. You can create a data set [in Experience Platform](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/creating_a_dataset_tutorial/creating_a_dataset_tutorial.md).<br>Although the schema for datasets that can be imported into Customer Journey Analytics is flexible, it must conform to some basic rules. It is best to make sure your data meets these requirements before uploading them into Platform. (Note that schema includes both metrics and dimensions.)<br>There are three types of data that are compatible with Customer Journey Analytics:<ul><li>**Event data**: Data that represents events in time (e.g., web visits, interactions, transactions, POS data, survey data, ad impression data, etc.). This is typical clickstream data, with a customer ID or a cookie ID, and a timestamp. With Event data, we allow you to use whatever ID you want.</li><li>**Lookup data**: This data is used to lookup values or keys found in your Event or Profile data. For example, you might upload lookup data that maps numeric IDs in your event data to product names.</li><li>**Profile data**: Data that is applied to your visitors, users, or customers in the Event data. For example, allows you to upload CRM data about your customers.</li></ul>|
|**Step 3:Create connections between platform datasets and Customer Journey Analytics**|Customer Journey Analytics|See [Create a connection](/help/connections/create-connection.md).|
|**Step 4: Create data views**|Customer Journey Analytics|See [Create a data view](/help/data-views/create-dataview.md).|
|**Step 5: Report on your cross-channel data in Workspace**|Customer Journey Analytics|See [Perform basic analysis](/help/projects/perform-basic-analysis.md) and [Perform advanced analysis](/help/projects/perform-adv-analysis.md).|

