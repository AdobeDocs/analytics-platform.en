---
title: Ingest Paid Media Data In Customer Journey Analytics
description: Learn how to ingest paid media data through Adobe Experience Platform source connectors and prepare connections, data views, and metrics in Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Use Cases
hold: true
role: Admin
---

# Ingest and use paid media data

Paid media data includes advertising performance and metadata from platforms such as [!DNL Meta Ads], [!DNL Google Ads], [!DNL TikTok], and [!DNL LinkedIn]. This guide explains how to ingest that data into Adobe Experience Platform and make it available in Customer Journey Analytics for reporting and analysis.

Paid media data typically moves through three stages:

1. Advertising platforms provide campaign, ad, asset, and performance data.
1. Adobe Experience Platform ingests that data through a source connector and stores it in the standard paid media datasets.
1. Customer Journey Analytics exposes the datasets through a connection and a data view so that you can analyze the data in Workspace.

Paid media data is ingested through Experience Platform source connectors. For example, you can use the [!DNL Meta Ads] connector in the Advertising category. When you connect a supported source, Adobe provisions the standard paid media datasets based on the global paid media schema and field groups.

## Prerequisites

Make sure that you have the following access in Experience Platform:

* Permission to view and manage sources.
* Permission to create schemas, datasets, and dataflows.
* A sandbox selected to work in. You must choose the sandbox before proceeding with the setup steps.

If you use [!DNL Meta Ads] as the source, make sure that you also have the following prerequisites:

* A [!DNL Meta Business Manager] account with at least one active ads account that contains campaigns, ad sets, ads, and assets.
* A [!DNL Meta] app that is authorized for the [!DNL Graph API] and [!DNL Marketing API], configured in the [!DNL Meta] developer console, and linked to [!DNL Business Manager].
* Approved `ads_read` and `ads_management` scopes for the app.
* Advertiser-level or higher access for the user who authorizes the connection.
* Verified access to the intended ad accounts in the [!DNL Meta] user interface.

Authentication to the connector uses [!DNL OAuth 2.0]. During setup, you sign in and grant access to the connector. Because access tokens expire, be prepared to reauthorize the connection if the grant is revoked.

## Paid media data model

Paid media data uses a star schema. One [summary metrics dataset](#summary-metrics-dataset) acts as the fact table, and six lookup datasets provide the related dimensions. The lookup datasets join to the summary metrics dataset by entity `GUID` and native ID values for accounts, campaigns, ad groups, ads, assets, and experiences.

The lookup datasets share two common building blocks:

* **Entity IDs object**: Stores account, ad, ad group, asset, campaign, and experience objects. Each object contains an Adobe-generated global key and a platform-native ID.
* **Paid media core metadata**: Stores common descriptive fields such as name, status, objective, optimization goal, bidding strategy, budget type, budget values, currency, time zone, serving status, dates, ad network, channel, hierarchy path, network, and portfolio identifiers.

The following table summarizes the six lookup datasets.

| Lookup dataset | Key contents |
|---|---|
| Account Lookup | Account-level metadata such as name, currency, time zone, status, spending limit, and creation dates |
| Campaign Lookup | Campaign settings for budget, scheduling, targeting, conversion tracking, attribution, placements, promoted objects, objective, and catalog or store IDs |
| Ad Group Lookup | Ad group metadata such as campaign linkage, status, budget, optimization goals, and targeting |
| Ad Lookup | Ad creative details such as assets, variants, dimensions, tracking URLs, call to action, body text, titles, destination URL, delivery status, and review status |
| Asset Lookup | Asset properties such as dimensions, file details, image properties, media URLs, usage metadata, video metadata, description, subtype, title, and type |
| Experience Lookup | Experience-level creative groupings such as experience ID, assets, title, description, and call to action |

### Summary metrics dataset

The Paid Media Summary Metrics dataset is the central summary dataset. Each row typically represents one entity for one day and includes a timestamp, an identifier, an event type, entity IDs, and denormalized names for reporting.

The summary metrics dataset can include the following metric groups:

* **Core performance**: impressions, clicks, click-through rate, engagements, engagement rate, conversions, conversion rate, conversion value, leads, link clicks, downloads, and app installs or opens.
* **Cost and budget**: daily spend, allocated and remaining budget, pacing, overrun or underrun, average cost metrics, and bid amounts.
* **Video**: video views, view-rate milestones, and average watch time.
* **Impression share**: impression share, top impression share, and lost impression share metrics.
* **Conversion detail**: conversion types, add-to-cart actions, checkouts, calls, directions requests, lead form activity, and other conversion-related events.
* **Social engagement**: likes, comments, and follows.
* **Attribution and path**: attribution model details, confidence, weights, path metrics, and channel contribution.
* **Quality and fraud**: quality scores, fraud indicators, invalid traffic rates, and brand safety metrics.
* **Dimensional breakdowns**: Data can be broken down by channel, ad network, device type, age group, gender, country, city, language, day of week, audience category, creative format, and other dimensions depending on the source platform.

### Standard datasets

When you connect a paid media source, Adobe provisions 12 standard paid media datasets based on the global paid media schema classes and field groups. These datasets include six summary metrics datasets, the six lookup datasets, and supporting datasets. All 12 summary and lookup datasets must be present so that paid media data resolves correctly downstream.

Required datasets:

* Paid Media Account Summary
* Paid Media Campaign Summary
* Paid Media Ad Group Summary
* Paid Media Ad Summary
* Paid Media Experience Summary
* Paid Media Asset Summary
* Paid Media Account Lookup
* Paid Media Campaign Lookup
* Paid Media Ad Group Lookup
* Paid Media Ad Lookup
* Paid Media Experience Lookup
* Paid Media Asset Lookup

Supporting datasets, for example:

* Paid Media Ad Demographic Lookup
* Paid Media Experience Placement Summary
* Paid Media Ad Geographic Summary
* Paid Media Ad Summary (summary metrics)
* Paid Media Asset Demographic Summary

## Ingest paid media data in Adobe Experience Platform

Use the following process to connect a source and ingest paid media data into Experience Platform:

1. Verify that you have the required Experience Platform source permissions and ad-platform access.
1. In Experience Platform, go to **[!UICONTROL Sources]** > **[!UICONTROL Catalog]** > **[!UICONTROL Advertising]**.
1. 1. Ensure you are in the sandbox that contains the paid media datasets.
1. Select the connector that you want to use, such as **[!DNL Meta Ads]**. Select **[!UICONTROL Set up]** to create a new connection, or select **[!UICONTROL Add data]** to add more data to an existing connection.
1. Authenticate with [!DNL OAuth 2.0] by signing in with a user who has the required advertiser-level access.
1. Select the ad accounts, entities, and insight data that you want to ingest.
1. Verify that the lookup datasets and summary metrics dataset are provisioned correctly.
1. Enter dataflow settings, confirm the target datasets, and configure the ingestion schedule.
1. Save the dataflow and monitor the runs in **[!UICONTROL Sources]** > **[!UICONTROL Dataflows]**.
1. Validate that the standard paid media datasets exist and contain data.

Before you move to Customer Journey Analytics, validate the ingested data:

* Confirm that entity `GUID` and native ID values are populated consistently across the summary metrics and lookup datasets.
* Confirm that every summary metrics row includes a timestamp.
* Confirm that key reporting fields such as  dimensions (for example: `channel`, `adNetwork`) and metrics (for example: `impressions`, `clicks`, `spend`) contain values. Note that some fields like `region` may not be populated by all source platforms.
* Confirm that currency and time zone values are consistent across the relevant accounts.

## Bring paid media data into Customer Journey Analytics

Customer Journey Analytics does not report directly on Experience Platform datasets. Instead, you expose the datasets through a connection and then build a data view that defines the dimensions, metrics, and logic used in reporting.

### Create or update a connection

Use the following process to create or update a connection:

1. In Customer Journey Analytics, [create or edit an existing connection](/help/connections/create-connection.md).
1. Ensure you select the sandbox that contains the paid media datasets as part of the connection configuration.
1. Add the summary metrics datasets as summary data. If multiple summary metrics datasets are available, use [search](/help/connections/create-connection.md#add-datasets) to filter by the `Paid Media` classes to identify the correct datasets.
1. Add each lookup dataset as a lookup dataset. Join the lookup dataset to the summary data using the corresponding entity GUID identifiers (the Adobe-generated global keys) for account, campaign, ad group, ad, asset, and experience. Some source platforms may also support joins on native ID values.
1. Optionally, add clickstream event data if you want to relate aggregate paid media data to shared metadata such as IDs, tracking codes, or `UTM` parameters.
1. Review the [dataset-specific settings](/help/connections/create-connection.md#dataset-settings) for each dataset.
1. Save the connection and confirm that the connection starts to backfill data.

Paid media data is aggregate data and does not rely on person-level identity stitching. The entity identifiers in the summary table are used to join on similar identities in the lookup tables.

### Create a data view

After the connection is ready, you need to create or edit one or more data views for the connection:


1. In Customer Journey Analytics, [create or edit one or more data views](/help/data-views/create-dataview.md):
1. Define the default settings such as time zone and currency.
1. Add the components that you need for paid media analysis.

Include components, such as the following:

* **Dimensions**: campaign, channel, ad network, ad group, ad, asset, account, region, and device type.
* **Metrics**: impressions, clicks, click-through rate, spend, conversions, conversion value, engagements, and relevant video or impression-share metrics.
* **Derived fields**: normalize or classify dimensions by using [parsing](/help/data-views/derived-fields/derived-fields.md#url-parse), [regular expressions](/help/data-views/derived-fields/derived-fields.md#regex-replace), or [lookup](/help/data-views/derived-fields/derived-fields.md#lookup) logic to produce consistent channel and campaign values across ad networks.
* **Summary grouping**: [combine related values from multiple datasets into a single reporting dimension](/help/data-views/component-settings/summary-data-group.md), such as a unified paid channel dimension.
* **Calculated metrics**: define reusable efficiency metrics such as CPC, CPM, CPA, CTR, and conversion rate.

## Validate

Use the following checklist to validate the implementation.

### Adobe Experience Platform checks

* Confirm that source permissions and ad-platform access are in place.
* Confirm that the connector is authenticated and the dataflow is running on schedule.
* Confirm that all 12 standard datasets are present and populated.
* Confirm that the schemas use the global paid media classes and field groups.
* Confirm that join keys, timestamps, and key reporting fields are populated.

### Customer Journey Analytics checks

* Confirm that the connection includes the summary metrics dataset and the six lookup datasets.
* Confirm that the data view includes the required advertising dimensions and paid media metrics.
* Confirm that derived fields normalize channel and campaign values as expected.
* Confirm that summary grouping consolidates multi-network data where needed.
* Confirm that calculated metrics are defined for the ratios that your organization uses.
* Confirm that Workspace reporting aligns with the source ad-platform reporting.


>[!MORELIKETHIS]
>
>[Meta Ads source connector](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/advertising/meta-ads)
>
