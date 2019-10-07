---
title: [!UICONTROL Customer Journey Analytics] Getting Started
seo-title: [!UICONTROL Customer Journey Analytics] Getting Started
description: [!UICONTROL Customer Journey Analytics] Getting Started.
seo-description: [!UICONTROL Customer Journey Analytics] Getting Started.
---

# [!UICONTROL Customer Journey Analytics] Getting Started

Workflow:

1. Enable [!UICONTROL Adobe Experience Platform] (AEP).
1. Enable CJA (is this step still needed?)
1. Prepare your data.
1. Create [!UICONTROL Analysis Workspace Data Group] (is this step still relevant?).
1. Upload your data into AEP datasets.
1. Link datasets into [!UICONTROL Customer Journey Analytics] data groups.

## Step 1: Enable Adobe Experience Platform

Your Experience Cloud organization must be first provisioned to work with AEP. (Add details here.)

## Step 2: Enable CJA

Not sure if this is still needed.

## Step 3: Prepare your data 

Although the schema for data that can be imported into CJA is flexible, it must conform to some basic rules. It is best to make sure your data meets these requirements before uploading them into Platform.

There are three types of data that are compatible with [!UICONTROL Customer Journey Analytics]:

* Event Data: Data that represents events in time (e.g., web visits, interactions, transactions, etc.).
* Lookup Data: This data is used to lookup values or keys found in your Event or Profile data. For example, you might upload lookup data that maps numeric IDs in your event data to product names.
* Profile Data: Data that is applied to your visitors, users, or customers in the Event Data. For example, allows you to upload CRM data about your customers.

Datasets in the ECP consist of 2 things: a schema (columns) and data fields (rows). 

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

### Profile rata requirements

The following requirements apply to Profile Data:

* Each row must have a column that corresponds with the visitor or customer ID column present in one of the Event Datasets. This will be the "join" column for the profile data.

## Step 4: Create Workspace data group

Is this still a step?

## Step 5: Upload data to the AEP

Steps here.

