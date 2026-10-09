---
title: Content Analytics Paid Media Automatic Configuration
description: Learn about the automatic configuration of datasets, connection, data views, and more.
solution: Customer Journey Analytics
feature: Content Analytics
hold: true
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

The illustration below shows how summary datasets are generated when you enable the paid media channel in Content Analytics for one or more of your ad networks. The relevant APIs from the available ad networks are used to download and transform experience, asset and ad data into potentially six summary datasets.

![Paid media generation of summary datasets](/help/content-analytics/assets/paid-media-generation-of-datasets.png)

The specific ad network determines which summary datasets are created. Not every ad network, for which you have configured a source connector, generates all six possible summary datasets. See the table below for an overview of the summary datasets with the following information:

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


* What each row in a summary dataset represents. 

| Summary dataset<br/>Event type<br/>Component suffix |  Entity<br/>Breakdown | ![MetaMulti](/help/assets/icons2/MetaSolid.svg)| ![GoogleAdsMulti](/help/assets/icons2/GoogleAdsMulti.svg)| ![PinterestMulti](/help/assets/icons2/PinterestMulti.svg)| ![Snapchat](/help/assets/icons2/Snapchat.svg) | ![TikTok](/help/assets/icons2/TikTok.svg)| Each row represents |
|---|---|:---:|:---:|:---:|:---:|:---:|---|
| `paidmedia_ad_summary` <br/> `ad.summary`<br/>`\| Ad Summary` | Ad<br/>none | ![Checkmark](/help/assets/icons2/Checkmark.svg) | ![Checkmark](/help/assets/icons2/Checkmark.svg) | ![Checkmark](/help/assets/icons2/Checkmark.svg)| ![Checkmark](/help/assets/icons2/Checkmark.svg) | ![Checkmark](/help/assets/icons2/Checkmark.svg) | An ad's daily performance without demographic or geographic breakdowns. |
| `paidmedia_ad_demographics` <br/> `ad.demographics`<br/>`\| Ad Demo` | Ad<br/>age, gender | ![Checkmark](/help/assets/icons2/Checkmark.svg) | | ![Checkmark](/help/assets/icons2/Checkmark.svg) | ![Checkmark](/help/assets/icons2/Checkmark.svg) | ![Checkmark](/help/assets/icons2/Checkmark.svg) | An ad's daily performance<br/>broken down by age and gender. |
| `paidmedia_ad_geography` <br/> `ad.geography`<br/>`\| Ad Geo` | Ad<br/>country, region | ![Checkmark](/help/assets/icons2/Checkmark.svg) | | ![Checkmark](/help/assets/icons2/Checkmark.svg) | ![Checkmark](/help/assets/icons2/Checkmark.svg) | ![Checkmark](/help/assets/icons2/Checkmark.svg) | An ad's daily performance<br/>broken down by country and region. |
| `paidmedia_experience_placement` <br/> `ad.experience.placement`<br>`\| Experience Placement` | Experience<br>platform, position | ![Checkmark](/help/assets/icons2/Checkmark.svg) | ![Checkmark](/help/assets/icons2/Checkmark.svg) | ![Checkmark](/help/assets/icons2/Checkmark.svg) | ![Checkmark](/help/assets/icons2/Checkmark.svg) | ![Checkmark](/help/assets/icons2/Checkmark.svg) | Daily performance associated<br/>with an ad's creative experience,<br/>broken down by platform and position. |
| `paidmedia_asset_summary` <br/>`ad.asset.summary`<br/>`\| Asset Summary` | Asset<br/>none | ![Checkmark](/help/assets/icons2/Checkmark.svg) | ![Checkmark](/help/assets/icons2/Checkmark.svg) | | | ![Checkmark](/help/assets/icons2/Checkmark.svg) | Daily asset-level performance<br/>in its ad/campaign context<br/>without demographic or geographic breakdown. |
| `paidmedia_assets_demographics` <br/> `ad.asset.demographics`<br/>`\| Asset Demo` | Asset<br/>age, gender | ![Checkmark](/help/assets/icons2/Checkmark.svg) | | | | | Daily asset-level performance<br/>in its ad/campaign context<br/>broken down by age and gender. |


This table describes dataset coverage, not a guarantee that a particular network populates every metric or metadata field. Check the fields needed for your analysis. An unavailable field or unsupported breakdown is not the same as a measured zero value for a field.

Separate lookup datasets describe Account, Campaign, Ad Group, Ad, Experience, and Asset. They provide names and metadata using entity GUIDs. No one-to-one pairing exists between the summary datasets and the six lookup datasets. 

Summary data grouping brings equivalent dimensions together; the grouping does not total the six performance metric totals. 

## Components

The Content Analytics Paid media channel, once enabled, also generates a number of data view components. These components are provided with a component suffix to distinguish similar named components from each other.

### Metrics

Different ad networks return different performance breakdowns. Content Analytics preserves those distinctions instead of treating every version of a metric as interchangeable.

For example:

| Component | Meaning | Appropriate starting analysis |
| --- | --- | --- |
| Clicks \| Ad Summary | Clicks reported at the ad's no-breakdown level | Campaign or ad performance |
| Clicks \| Asset Summary | Clicks reported at the asset level | Creative-asset performance |
| Clicks \| Ad Geo | Clicks from the ad-geography report | Performance by country or region |
| Clicks \| Experience Placement | Clicks from the experience-placement report | Creative performance by placement |

Each clicks metric component serves a different reporting context. You cannot total these metric components into a grand total. The same underlying advertising activity can be represented in more than one summary dataset.

### Dimensions

Each summary dataset contains IDs and GUIDs. The ID is the identity (for account, campaign, ad group, ad,  experience, and asset) provided by the ad network and is unique **within** the ad network data. The GUID is an Adobe provided identity (for account, campaign, ad group, ad,  experience, and asset) and is unique **across** ad networks. IDs and GUIDs are used to lookup the corresponding names and metadata. 

### Derived fields

Derived fields are part of the automatic reporting configuration. Derived fields translate identifiers into names and metadata, expose creative attributes, and support the equivalent dimensions used across reporting sources. They do not create additional advertising activity or automatically attribute a website conversion.

Use the same breakdown for the metrics within an analysis, and dimensions supported by that breakdown. Be aware that demographic and geographic totals do not necessarily equal the no-breakdown totals for an ad network and do not imply an ingestion failure.

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

### Examples

Below are examples of how to report on and analyze paid media performance and how to combine Content Analytics experience and assets data with paid media data.

#### Ad campaign performance

You want to report on campaign performance at the ad level. In Analysis Workspace, use Campaign Name as the dimension (rows) and use the metrics as outlined in the table below. Each metric has the same component suffix.

| Metrics | Reporting level |
| --- | --- |
| Impressions | Ad Summary |
| Clicks | Ad Summary |
| Spend | Ad Summary |
| Click-Through Rate | Ad Summary |
| Cost Per Click | Ad Summary |

Optionally break down Campaign Name by Ad Name but keep all five columns at Ad Summary level.

To investigate individual assets, use a separate table with Asset Name (Paid Media) and the matching Asset Summary columns. Do not add the two tables' totals together. 

#### Identifying best performing ads

You want to understand where your Meta ads are performing best? 

To investigate, use additional breakdowns for geography and demographics. Use Campaign Name or Ad Name as the dimension and use the metrics as outlined in the table below. Each metric has the same component suffix.

| Metrics | Reporting level |
| --- | --- |
| Impressions | Ad Geo |
| Clicks | Ad Geo |
| Spend | Ad Summary |
| Click-Through Rate | Ad Geo |
| Cost Per Click | Ad Summary |


#### Join paid media data with experience event data

Join paid media performance with on-site behavioral data to understand how campaigns and ads are associated with website engagement, conversions, and revenue. For example, compare advertising-network clicks and spend with orders attributed to visits from the same campaign. 

 To configure this reporting, include the paid media summary datasets and your on-site event dataset in the same Customer Journey Analytics connection. Capture stable campaign, ad, or supported asset identifiers from landing-page URL parameters or existing event fields. Use derived fields as needed to parse and map those values to the corresponding paid media identifiers, preserving the required network and account context. Keep identifiers as strings. To associate the matching event and summary dimensions, configure a Summary Data Group in the data view. Enabling the Paid Media channel does not automatically configure this implementation-specific URL tracking and mapping. 


| Tracking option | Considerations |
|---|---|
| Meta Ads | Configure destination URL parameters using dynamic identifiers such as `campaign.id`, `adset.id`, and `ad.id` where supported. Capture the resolved values on your website. Enabling the connector does not automatically add these parameters to your ad URLs.  |
| Google Ads | |
| Individual assets | Asset-level reporting of downstream outcomes requires a captured identifier that maps to the specific asset associated with the click. A custom URL parameter can support this where the ad format permits asset-specific tracking. An ad identifier alone cannot distinguish multiple assets within an ad, and one static asset parameter applied to an entire multi-asset ad does not identify which asset was associated with the click. |

In Analysis Workspace, use **[!UICONTROL Ad Summary]** metrics for campaign or ad comparisons and **[!UICONTROL Asset Summary]** metrics for supported asset comparisons. Apply an attribution model and lookback window to the on-site conversion metrics that reflect your reporting question. 

Be aware of the following:

* Paid media data is aggregated summary data without a person ID. On-site behavior is event data. 
* Grouping matching dimensions supports reporting across these sources, but does not match individual ad network conversions to website conversions or perform person-level stitching. 
* The comparison shows an association, not causal lift. 
* Results can differ because of conversion definitions, attribution windows, view-through or modeled conversions, consent, and reporting dates or time zones. 
* Validate the source of campaign-tagged visits when tracking parameters are reused across channels. 

 
#### Compare campaign performance with on-site orders

A landing-page URL can contain several tracking parameters. In this example, the campaign ID in `utm_id` is used to compare campaign spend with website orders. 

https://www.example.com/offer?utm_source=facebook&utm_medium=paid_social&utm_campaign=autumn_offer&utm_id=120218706543980215 

The parameter used for this comparison: `utm_id=120218706543980215`. The other parameters describe the source, medium, and campaign label but are not used as a matching field used in this example. 

If the URL is captured in website event data and both website event dataset and paid media datasets are part of the same Customer Journey Analytics connection:

1. Identify the campaign. Use a derived field to read `utm_id` from the URL and map its value to the corresponding campaign identifier in the paid media data. 
1. Group the matching dimensions. In the data view, add the website campaign dimension to the paid campaign dimension's `Summary Data Group`, preserving any existing members. 
1. Compare spend and orders. In Analysis Workspace, use the grouped campaign dimension as the rows of a freeform table. Add `Ad Summary` spend and website `Orders` as columns. Set the attribution model and lookback window for `Orders`. 
 

The freeform table shows ad network spend alongside website orders attributed to each campaign. Two campaigns with similar ad spend have different numbers of attributed downstream website actions. Use this comparison to identify campaigns and landing-page experiences for further investigation or testing, rather than assessing performance from advertising metrics alone. 

The example uses a campaign ID, but the same approach can use ad group, ad, or asset identifiers when matching values can be captured. Content Analytics attributes, such as **[!UICONTROL Asset Foreground Colors]**, let you compare creative characteristics with paid media performance. With asset-specific tracking and matching attribute dimensions configured across both sources, you can extend that comparison to attributed website orders and use the results to guide creative testing.

#### Combine asset performance with web data

If you want to report and analyze on asset performance related to your paid media investments, consider adding a specific asset UTM parameter in your ad network paid media configuration. For example, besides standard dynamic parameters like s`ite_source_name`, `campaign.id`, `adset.id`, or `placement`, add static custom parameters, like `aca_asset_id=999999`.

This custom parameter is added to your landing page URL. For example: https://www.example.com/home.html?utm_content=120241705099850539%2Caca_asset_id%3D9999999%2Caca_placement%3DFacebook_Desktop_Feed&aca_id_2=8888888&utm_medium=paid&utm_source=fb&utm_id=120241705099830539&utm_term=120241705099840539&utm_campaign=120241705099830539

You now have a relation between an asset on a page and your paid media data. Use that relation in Analysis Workspace to see how Content Analytics asset metadata (for example **[!UICONTROL Asset Foreground Colors]**) contribute to paid media campaign success.
