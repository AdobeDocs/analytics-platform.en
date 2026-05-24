---
description: Learn how to use data feeds to get raw data out of Customer Journey Analytics. Find out the prerequisites for using data feeds what to do next.
keywords: clickstream;data feed;datafeed;Data Feed
title: Analytics Data Feed Overview
feature: Components
hide: true
exl-id: 991a7861-cbde-4d55-935c-d56c8031853e
autotag-review: '2026-05-19T08:45:11.428Z'
TQID: 'https://experienceleague.adobe.com/TO8lEW8-GE-sIGj3vmm0X1zCgpg-0VpS1wjs0-HQjg8'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
    internal-label: Exports
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
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
