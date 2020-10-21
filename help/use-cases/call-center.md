---
title: Import call center and web data
description: Learn how to create a dataset that links call center and website data.
---

# Import call center and web data

Customer Journey Analytics provides the valuable and robust capability to combine datasets from different sources into a single Workspace project. One challenge frequently encountered is the ability to reliably match up visitor data that use different identifiers. Use this guide to understand how your organization can stitch data from your website to data that originates from your call center.

## Prerequisites

* The most important component to combining these two sets of data is a common identifier between each source of data. Examples include a customer ID, a hashed email, login username, or phone number.
* Access to both Adobe Experience Platform and Customer Journey Analytics
* Adobe recommends performing some basic data cleansing on your call center data prior to importing it into Platform.
* Recommended call center columns include:
  * The date/time when the call started
  * Call reason
  * Call center ID
  * Call center agent ID
  * Duration of call
  * Outcome of call
  * Cost of call (if available)

## Import web and call center data into Platform

Begin importing data into Adobe Experience Platform. See [Create a schema](https://docs.adobe.com/content/help/en/experience-platform/xdm/tutorials/create-schema-ui.html) and [Ingest data](https://docs.adobe.com/content/help/en/experience-platform/ingestion/home.html) in the Adobe Experience Platform documentation. Make sure that the person ID for both web and call center data are similarly formatted.

## Stitch the person ID's together

Once you have successfully imported your web and call center data into Platform, you can stitch the identifiers together using Cross-channel Analytics. See [Cross-channel Analytics overview](/help/connections/cca/overview.md) for steps to enable CCA for these two datasets.

## Create a connection in CJA

If CCA is set up correctly, a new stitched dataset is available for you to use. [Create a connection](/help/connections/create-connection.md) using this stitched dataset.

## Create a data view

After creating a connection, you can [Create a data view](/help/data-views/create-dataview.md) for use in Analysis Workspace.

## Create visualizations




1. import web data
2. import call center data
3. see how many visits are in both datasets (how do you determine when they're in both datasets?)
4. attribute pages to calls when they happen in the same visit
5. use target (AB testing) to test new versions of these pages so they reduce calls (using an eVar to determine A/B?)
6. filter by specific call reason using workspace dropdowns
7. visualize flow of pages > call reason 


talk with trevor about including an out-of-the-box dimension that includes the data set the hit originated from





1. submit request for loan
2. goes into salesforce
3. buncha backend events, did loan officer review it, did they approve, did the user accept, etc.
4. create fallout to see where loans that make it through the whole process, and where it broke down
