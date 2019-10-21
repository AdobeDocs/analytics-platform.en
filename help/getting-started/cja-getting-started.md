---
title: [!UICONTROL Customer Journey Analytics] Getting Started
seo-title: [!UICONTROL Customer Journey Analytics] Getting Started
description: [!UICONTROL Customer Journey Analytics] Getting Started.
seo-description: [!UICONTROL Customer Journey Analytics] Getting Started.
---

# [!UICONTROL Customer Journey Analytics] Getting Started

To implement Customer Journey Analytics, you need to follow this workflow:

1. Enable [!UICONTROL Adobe Experience Platform] (Platform).
1. Enable CJA (is this step still needed?)
1. Prepare your data.
1. Create connections between platform datasets and Workspace.
1. Create data views.
1. Report on your cross-channel data in Workspace.

## Step 1: Enable Adobe Experience Platform

Your Experience Cloud organization must be first provisioned to work with the [!UICONTROL Adobe Experience Platform] (Platform). (Add details here.) The Platform is the centralized place where Adobe customers can put all of *their* customer data for analysis.

## Step 2: Enable CJA

Not sure if this is still needed.

## Step 3: Prepare your data 

Data in Platform consists of data sets, such as email data sets, CRM datasets, POS data sets, the Adobe Analytics dataset, etc.. Each data sets consists of a schema and batches of data. You can prepare your data in Platform or in CJA.

Although the schema for datasets that can be imported into CJA is flexible, it must conform to some basic rules. It is best to make sure your data meets these requirements before uploading them into Platform. (Note that schema includes both metrics and dimensions.)

There are three types of data that are compatible with [!UICONTROL Customer Journey Analytics]:

* **Event data**: Data that represents events in time (e.g., web visits, interactions, transactions, POS data, survey data, ad impression data, etc.). This is typical clickstream data, with a customer ID or a cookie ID, and a timestamp. With Event data, we allow you to use whatever ID you want.
* **Lookup data**: This data is used to lookup values or keys found in your Event or Profile data. For example, you might upload lookup data that maps numeric IDs in your event data to product names.
* **Profile data**: Data that is applied to your visitors, users, or customers in the Event data. For example, allows you to upload CRM data about your customers.

### General data requirements

The following requirements apply to all data types:

* Data must be in CSV or Parquet format
* If using CSV, must conform to the RFC 4180 standard.
* Column names must only contain letters, numbers, and underscores.

### Event data requirements

Event Data represents events in time. Each event is represented by a row in your CSV or Parquet file. Columns in each row contain the information about each event.

The following requirements apply to Event Data:

* Each row must have a column for visitor or customer ID.
* Each row must have a timestamp that occurs after 1973.
* The timestamp must be in one of the following formats:
    * ISO 8601 string (e.g. "2019-02-01T19:42:19")
    * UNIX epoch time in seconds (e.g. 1549050556)
    * Epoch time in milliseconds (e.g. 1549050556000)

### Lookup data requirements

The following requirements apply to Lookup Data:

* Each row must have a column that corresponds with a column in an Event Dataset. This will be the "join" column for the lookup. This column can be either a string or a number.

### Profile data requirements

The following requirements apply to Profile data:

* Each row must have a column that corresponds with the visitor or customer ID column present in one of the Event Datasets. This will be the "join" column for the profile data.

## Step 4: Create connections between platform datasets and Workspace

See [Create a connection](/help/connections/create-connection.md).

## Step 5: Create data views

See [Create a data view](/help/data-views/create-dataview.md).

## Step 6: Report on your cross-channel data in Workspace

To follow.
