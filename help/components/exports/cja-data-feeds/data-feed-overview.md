---
description: Learn how to use data feeds to get raw data out of Customer Journey Analytics. Find out the prerequisites for using data feeds what to do next.
keywords: clickstream;data feed;datafeed;Data Feed
title: Analytics Data Feed Overview
feature: Components
hide: true
exl-id: 991a7861-cbde-4d55-935c-d56c8031853e
---
# Data feeds overview

Data feeds are a powerful way to get raw data out of Customer Journey Analytics. You can use this raw data in other platforms outside of Adobe at your organization's discretion. Data is delivered in hourly batches at the conclusion of each hour, or in daily batches at the conclusion of each day.

## Prerequisites

Make sure that you meet all the following requirements before using data feeds:

* A working implementation with data being ingested into Adobe Customer Journey Analytics <!-- For more information, see Data ingestion overview - add link -->
* Your account is an Analytics product admin, or your account belongs to a product profile with access to data feeds <!--???-->
* A bucket configured on {DNL Amazon S3}, {DNL Google Cloud Platform}, {DNL Azure RBAC}, or {DNL Azure SAS}

## Get started

To get started using data feeds in Customer Journey Analytics, first understand how data feeds in Customer Journey Analytics differ from data feeds in Adobe Analytics. After you understand the differences, you can map Adobe Analytics data feeds to Customer Journey Analytics, then begin creating a data feed.

1. [Understand the differences between data feeds in Customer Journey Analytics and Adobe Analytics](/help/components/exports/cja-data-feeds/df-comparison.md).

1. [Map Adobe Analytics data feed columns to Customer Journey Analytics](/help/components/exports/cja-data-feeds/aa-cja-column-reference.md).

1. [Create a data feed](/help/components/exports/cja-data-feeds/create-feed.md).
