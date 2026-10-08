---
title: Content Analytics Paid Media Automatic Configuration
description: Learn about the automatic configuration of datasets, connection, data views, and more.
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
---
# Paid media automatic configuration

When you enable the Paid media channel in Content Analytics and save the configuration, Adobe updates the selected connection and data views with reporting configuration for the paid media datasets. You do not need to recreate the default dimensions, metrics, lookup logic, or summary-data groups yourself.

Three layers of objects are created:

| Objects | Contains | Purpose |
| --- | --- | --- |
| Summary datasets | Advertising-network performance data at ad, experience-placement, or asset level, with separate demographic/geographic breakdowns where supported. | Allow you to measure delivery, clicks, spend, and advertising-network-reported outcomes |
| Metadata and attribute lookup datasets | Account, campaign, ad group, ad, experience, and asset details; Content Analytics creative attributes. | Allow you to report using recognizable names, creative details, thumbnails, and content attributes rather than using identifiers. |
| Data-view components and configuration | Dimensions, metrics, calculated metrics, derived fields, and summary-data groups. | Allow you to build Workspace analyses without you manually rebuilding the relationships between these datasets. |

Enabling paid media does not automatically connect the paid media data to your site's orders, bookings, or revenue. The correlation between your experience event  data and paid media data requires customer-specific tracking-key mapping and reporting configuration.

## Summary datasets

The illustration below shows how ummary datasets are generated when you enable the paid media channel in Content Analytics for one or more of your ad networks. The relevant APIs from the available ad networks are used to download and transform experience, asset and ad data into potentially six summary datasets.

![Paid media generation of summary datasets](/help/content-analytics/assets/paid-media-generation-of-datasets.svg)

Which summary datasets are created is determined by the specific ad network. Not every ad network, for which you have configured a source connector, generates all six possible summary datasets. See the table below for an overview of the summary datasets with the following information:

* Summary dataset name, event type, and component suffix
* Entity
* Breakdowns 
* Which datasets are populated ![Checkmark](/help/assets/icons2/Checkmark.svg) for the following networks:
  * ![MetaSolid](/help/assets/icons2/MetaSolid.svg) Meta
  * ![GoogleAdsMulti](/help/assets/icons2/GoogleAdsMulti.svg) Google
  * ![PinterestMulti](/help/assets/icons2/PinterestMulti.svg) Pinterest
  * ![Snapchat](/help/assets/icons2/Snapchat.svg) Snapchat
  * ![TikTok](/help/assets/icons2/TikTok.svg) TikTok

    >[!AVAILABILITY]
    >
    >Pinterest, Snapchat, and TikTok are in the Limited Testing phase of release and might not be available yet in your environment. This note will be removed when the functionality is generally available. For information about the Customer Journey Analytics release process, see [Customer Journey Analytics feature releases](/help/release-notes/releases.md)
    >


* what each row in a summary dataset represents. 

| Summary dataset<br/>Event type<br/>Component suffix |  Entity | Breakdown | ![MetaMulti](/help/assets/icons2/MetaSolid.svg)| ![GoogleAdsMulti](/help/assets/icons2/GoogleAdsMulti.svg)| ![PinterestMulti](/help/assets/icons2/PinterestMulti.svg)| ![Snapchat](/help/assets/icons2/Snapchat.svg) | ![TikTok](/help/assets/icons2/TikTok.svg)| Each row represents |
|---|---|---|:---:|:---:|:---:|:---:|:---:|---|
| `paidmedia_ad_summary` <br/> `ad.summary`<br/>`\| Ad Summary` | Ad | none | ![Checkmark](/help/assets/icons2/Checkmark.svg) | ![Checkmark](/help/assets/icons2/Checkmark.svg) | ![Checkmark](/help/assets/icons2/Checkmark.svg)| ![Checkmark](/help/assets/icons2/Checkmark.svg) | ![Checkmark](/help/assets/icons2/Checkmark.svg) | An ad's daily performance without demographic or geographic breakdowns. |
| `paidmedia_ad_demographics` <br/> `ad.demographics`<br/>`\| Ad Demo` | Ad | age, gender | ![Checkmark](/help/assets/icons2/Checkmark.svg) | | ![Checkmark](/help/assets/icons2/Checkmark.svg) | ![Checkmark](/help/assets/icons2/Checkmark.svg) | ![Checkmark](/help/assets/icons2/Checkmark.svg) | An ad's daily performance broken down by age and gender. |
| `paidmedia_ad_geography` <br/> `ad.geography`<br/>`\| Ad Geo` | Ad | country, region | ![Checkmark](/help/assets/icons2/Checkmark.svg) | | ![Checkmark](/help/assets/icons2/Checkmark.svg) | ![Checkmark](/help/assets/icons2/Checkmark.svg) | ![Checkmark](/help/assets/icons2/Checkmark.svg) | An ad's daily performance broken down by country and region. |
| `paidmedia_experience_placement` <br/> `ad.experience.placement`<br>`\| Experience Placement` | Experience | platform, position | ![Checkmark](/help/assets/icons2/Checkmark.svg) | ![Checkmark](/help/assets/icons2/Checkmark.svg) | ![Checkmark](/help/assets/icons2/Checkmark.svg) | ![Checkmark](/help/assets/icons2/Checkmark.svg) | ![Checkmark](/help/assets/icons2/Checkmark.svg) | Daily performance associated with an ad's creative experience, broken down by platform and position. |
| `paidmedia_asset_summary` <br/>`ad.asset.summary`<br/>`\| Asset Summary` | Asset | none | ![Checkmark](/help/assets/icons2/Checkmark.svg) | ![Checkmark](/help/assets/icons2/Checkmark.svg) | | | ![Checkmark](/help/assets/icons2/Checkmark.svg) | Daily asset-level performance in its ad/campaign context, without demographic or geographic breakdown. |
| `paidmedia_assets_demographics` <br/> `ad.asset.demographics`<br/>`\| Asset Demo` | Asset | age, gender | ![Checkmark](/help/assets/icons2/Checkmark.svg) | | | | | Daily asset-level performance in its ad/campaign context, broken down by age and gender. |


This table describes dataset coverage, not a guarantee that every metric or metadata field is populated by a particular network. Check the fields needed for your analysis. An unavailable field or unsupported breakdown is not the same as a measured zero value for a field.

Separate lookup datasets describe Account, Campaign, Ad Group, Ad, Experience, and Asset. They provide names and metadata using entity GUIDs. No one-to-one pairing exists between the summary datasets and the six lookup datasets. 

Summary data grouping brings equivalent dimensions together; the grouping does not total the six performance metric totals. 

## Components

The Content Analytics Paid media channel, once enabled, also generates a number of data view components. These components are provided with a component suffix to distinct similar named components from each other.

### Metrics

Different ad networks return different performance breakdowns. Content Analytics preserves those distinctions instead of treating every version of a metric as interchangeable.

For example:

| Component | Meaning | Appropriate starting analysis |
| --- | --- | --- |
| Clicks \| Ad Summary | Clicks reported at the ad's no-breakdown level | Campaign or ad performance |
| Clicks \| Asset Summary | Clicks reported at the asset level | Creative-asset performance |
| Clicks \| Ad Geo | Clicks from the ad-geography report | Performance by country or region |
| Clicks \| Experience Placement | Clicks from the experience-placement report | Creative performance by placement |

Each clicks metric component serves a different reporting context. You cannot simply total these metric comnponents into a grand total. The same underlying advertising activity can be represented in more than one summary dataset.

### Dimensions

Each summary dataset contains IDs and GUIDs. The ID is the identity (for account, campaign, ad group, ad,  experience, and asset) provided by the ad network and is unique **within** the ad network data. The GUID is an Adobe provided identity (for account, campaign, ad group, ad,  experienc, and asset) and is unique **across** ad networks. IDs and GUIDs are used to lookup the corresponding names and metadata. 

### Derived fields

Derived fields are part of the automatic reporting configuration. Derived fields translate identifiers into names and metadata, expose creative attributes, and support the equivalent dimensions used across reporting sources. They do not create additional advertising activity or automatically attribute a website conversion.

Use the same breakdown for the metrics within an analysis, and dimensions supported by that breakdown. Be aware that demographic and geographic totals do not necessarily equal the no-breakdown totals for an ad network and does not imply an ingestion failure.

## Reporting and analysis

Once you have finished Content Analytics Paid media setup and ingestion, you can start with reporting and analysis. See the table below for some examples. Use the canonical grouped dimensions where available, and choose metrics from the matching reporting level.

| Business question | Starting level | Rows and breakdowns | Starting metrics | Important boundary |
| --- | --- | --- | --- | --- |
| How are my campaigns and ads performing? | Ad Summary | Campaign Name, AdGroup Name, Ad Name; optionally Ad Network and Account Name | Impressions \| Ad Summary, Clicks \| Ad Summary, Spend \| Ad Summary, matching CTR and CPC | Use one level for delivery/spend totals; validate currency before combining accounts |
| Which creative assets get the strongest response? | Asset Summary | Asset Name (Paid Media), asset identity; optionally Ad Network | Impressions \| Asset Summary, Clicks \| Asset Summary, Click-Through Rate \| Asset Summary | This is asset performance reported by the network, not proof of a later on-site conversion |
| Which image characteristics are associated with performance? | Asset Summary | Asset Tags, Asset Objects, Asset People Categories, Asset Scenes, or other available asset attributes | Asset Summary impressions, clicks, and CTR | Attribute extraction must be available; multivalued attribute categories can overlap |
| Which messaging characteristics are associated with paid performance? | Experience Placement | Experience Keywords, Experience Tones, Experience Persuasion Strategies, or other available experience attributes; optionally Platform and Placement | Impressions \| Experience Placement, Clicks \| Experience Placement, matching CTR | Requires populated experience attributes; results are placement-specific and describe association, not causal impact |
| Which placements perform best? | Experience Placement | Experience Name, Platform, Placement | Impressions \| Experience Placement, Clicks \| Experience Placement, matching CTR | Placement definitions and available values vary by advertising network |
| How do Meta and Google ads/assets/experiences compare? | Ad Summary, Asset Summary, or Experience Placement, chosen for the question | Ad Network with the appropriate campaign, asset, or experience dimension | The same level and metric definition for both networks | Only compare fields populated by both networks; Google does not populate the three demographic/geographic summaries in this model |

These reports can reveal associations between creative attributes and performance, not prove that an attribute caused a result.

Avoid incompatible combinations: Asset Name (Paid Media) with Ad Summary metrics is not a substitute for an asset report. Use Asset Summary metrics for asset analysis and Ad Geography metrics for region analysis. Empty or zero cells from an incompatible pairing should not be interpreted as proof of no activity.

### Ad campaign performance example

You want to report on campaign performance on ad level. In Analysis Workspace, use Campaign Name as the dimension (rows) and use the metrics as outlined in the table below. Each metric has the same component suffix.

| Metrics | Reporting level |
| --- | --- |
| Impressions | Ad Summary |
| Clicks | Ad Summary |
| Spend | Ad Summary |
| Click-Through Rate | Ad Summary |
| Cost Per Click | Ad Summary |

Optionally break down Campaign Name by Ad Name but keep all five columns at Ad Summary level.

To investigate individual assets, use a separate table with Asset Name (Paid Media) and the matching Asset Summary columns. Do not add the two tables' totals together. 

### Networking best performing ads example

You want to understand where your Meta ads are performing best? 

To investigate, use additional breakdowns for geography and demographics. Use Campaign Name or Ad Name as the dimension and use the metrics as outlined in the table below. Each metric has the same component suffix.

| Metrics | Reporting level |
| --- | --- |
| Impressions | Ad Geo |
| Clicks | Ad Geo |
| Spend | Ad Summary |
| Click-Through Rate | Ad Geo |
| Cost Per Click | Ad Summary |


