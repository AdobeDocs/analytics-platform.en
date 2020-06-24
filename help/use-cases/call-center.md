---
title: Call center use case
description: Learn how to create a dashboard that links call center and website data.
---

# Import call center and web data into CJA

Introduction

## Prerequisites

- Must have a common ID between both platforms. Could be a customer ID, or hashed email address or something. Bottom line is they need to be shared between platforms.
- need CJA and platform
- Might need to do some data cleansing. call center data might be messy. expose the points of interest before getting it into platform.
- Excellent columns to have: date/time when call occurred, call reason, call center id, call center agent id, duration of call, outcome of call, (if possible) cost of call
- For any event, it must be a numeric value. You can't currently create an event based on the presence of a value in a column. might be fixed later, talk to trevor.

## Import web and call center data into Platform

Link to platfrom docs on importing data into platform

Make sure they understand schema and XDM. Make sure both have person ID columns declared.

## Re-key customer ID's (or use field-based stitching when it comes out)

Use query service to load the data, query the two person ID columns, and spit out a new version of both datasets with a stitched ID. Create a new combined dataset with the stitched column. Talk to Trevor about the specific query that is used.

Ooooooorrrrr use field based stitching when it comes out

## Create a connection

Link to CJA docs on creating a connection. Make sure that they both use the same person ID.

## Create a data view

Link to docs on creating a data view.

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