---
title: Customer Journey Analytics Getting Started
description: Customer Journey Analytics Getting Started.
---

# Customer Journey Analytics Getting Started

To implement Customer Journey Analytics, you need to follow this workflow:

1. Enable [!UICONTROL Adobe Experience Platform] (Platform).
1. Prepare your data schema in Adobe Experience Platform.
1. Create a dataset based on the schema
1. Create connections between platform datasets and Workspace.
1. Create data views.
1. Report on your cross-channel data in Workspace.

## Step 1: Enable Adobe Experience Platform

Your Experience Cloud organization must be first provisioned to work with the [!UICONTROL Adobe Experience Platform] (Platform). (Add details here.) The Platform is the centralized place where Adobe customers can put all of *their* customer data for analysis.

## Step 2: Prepare your data

Use [Adobe Experience Data Model (XDM)](https://www.adobe.io/apis/experienceplatform/home/xdm.html) to standardize customer experience data and define schemas for customer experience management.

You can 

## Step 3: Create a dataset based on the schema

Data in Platform consists of data sets, such as email data sets, CRM datasets, POS data sets, the Adobe Analytics dataset, etc.. Each data sets consists of a schema and batches of data. You can create a data set [in Experience Platform](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/creating_a_dataset_tutorial/creating_a_dataset_tutorial.md).

Although the schema for datasets that can be imported into CJA is flexible, it must conform to some basic rules. It is best to make sure your data meets these requirements before uploading them into Platform. (Note that schema includes both metrics and dimensions.)

There are three types of data that are compatible with Customer Journey Analytics:

* **Event data**: Data that represents events in time (e.g., web visits, interactions, transactions, POS data, survey data, ad impression data, etc.). This is typical clickstream data, with a customer ID or a cookie ID, and a timestamp. With Event data, we allow you to use whatever ID you want.
* **Lookup data**: This data is used to lookup values or keys found in your Event or Profile data. For example, you might upload lookup data that maps numeric IDs in your event data to product names.
* **Profile data**: Data that is applied to your visitors, users, or customers in the Event data. For example, allows you to upload CRM data about your customers.


## Step 4: Create connections between platform datasets and Customer Journey Analytics

See [Create a connection](/help/connections/create-connection.md).

## Step 5: Create data views

See [Create a data view](/help/data-views/create-dataview.md).

## Step 6: Report on your cross-channel data in Workspace

See [Perform basic analysis](/help/projects/perform-basic-analysis.md) and [Perform advanced analysis](/help/projects/perform-adv-analysis.md).
