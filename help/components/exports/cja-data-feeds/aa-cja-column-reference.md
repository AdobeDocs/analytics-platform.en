---
title: Map Adobe Analytics data feed columns to Customer Journey Analytics
description: Determine how to take a given Adobe Analytics data feed column and determine its rough equivalent in your Customer Journey Analytics implementation.
---
# Map Adobe Analytics data feed columns to Customer Journey Analytics

Since Adobe Analytics and Customer Journey Analytics operate fundamental differently, a 1:1 column mapping is not possible. These differences are further exacerbated by the fact that every Adobe Analytics and Customer Journey Analytics implementation wildy differs.

This reference is designed to help data engineers adjust their Adobe Analytics-focused data feed workflows column-by-column to a workflow based on Customer Journey Analytics data feeds.

>[!NOTE]
>
>This reference only includes columns that are considered current by Adobe, based on the [Analytics data feed column reference](https://experienceleague.adobe.com/en/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference). If you have an Analytics data feed column not listed on this table that you actively use, consult your organization's solution design document to determine its best equivalent in Customer Journey Analytics.

+++**`accept_language`**

Lists all accepted languages, as indicated in the Accept-Language HTTP header in an image request.

+++

+++**`adload`**

Media ad loads

+++

+++**`aemassetid`**

A multi-value variable corresponding to Asset IDs (GUIDs) of a set of Adobe Experience Manager Assets. Increments Impression Events.

+++

+++**`aemassetsource`**

Identifies the source of the asset event. Used in Adobe Experience Manager.

+++

+++**`aemclickedassetid`**

Asset ID of an Adobe Experience Manager asset. Increments Click Events.

+++

+++**`amo_cid`**

The [AMO ID](/help/components/dimensions/amo-id.md) dimension, used in Adobe Advertising integrations.

+++

+++**`amo_ef_id`**

The [AMO EF ID](/help/components/dimensions/amo-ef-id.md) dimension, used in Adobe Advertising integrations.

+++

+++**`browser`**

A numeric ID that represents the browser. References the `browser.tsv` lookup table.

+++

+++**`browser_height`**

The [Browser Height](/help/components/dimensions/browser-height.md) dimension.

+++

+++**`browser_width`**

The [Browser Width](/help/components/dimensions/browser-width.md)

+++

+++**`campaign`**

The [Tracking Code](/help/components/dimensions/tracking-code.md) dimension.

+++

+++**`carrier`**

Adobe Advertising integration variable. Specifies the mobile carrier. The key value for `carrier.tsv` [Dynamic lookup](dynamic-lookups.md).

+++

+++**`channel`**

The [Site sections](/help/components/dimensions/site-section.md) dimension.

+++

+++**`ch_hdr`**

Client hints collected through the HTTP request header.

+++

+++**`ch_js`**

Client hints collected through the User-Agent Client Hints JavaScript API.

+++

+++**`clickmaplink`**

The [Activity Map link](/help/components/dimensions/activity-map-link.md) dimension.

+++

+++**`clickmaplinkbyregion`**

The [Activity Map link by region](/help/components/dimensions/activity-map-link-by-region.md) dimension.

+++

+++**`clickmappage`**

The [Activity Map page](/help/components/dimensions/activity-map-page.md) dimension.

+++

+++**`clickmapregion`**

The [Activity Map region](/help/components/dimensions/activity-map-region.md) dimension.

+++

+++**`code_ver`**

API or client SDK version used to compile and send the image request.

+++

+++**`color`**

Color depth ID based on the value of the `c_color` column. References the `color_depth.tsv` lookup table.

+++

+++**`connection_type`**

Numeric ID representing the [Connection type](/help/components/dimensions/connection-type.md) dimension. References the `connection_type.tsv` lookup table.

+++

+++**`cookies`**

The [Cookie support](/help/components/dimensions/cookie-support.md) dimension.<br>Y: Enabled<br>N: Disabled<br>U: Unknown

+++

+++**`country`**

A numeric ID that represents the country of the visitor. References the `country.tsv` lookup table.

+++

+++**`currency`**

The currency code that was used during the transaction. Set using [`currencyCode`](/help/implement/vars/config-vars/currencycode.md).

+++

+++**`ct_connect_type`**

Related to the `connection_type` column. The most common values are LAN/Wifi, Mobile Carrier, and Modem.

+++

+++**`curr_factor`**

Determines the currency decimal place. Used for currency conversion. For example, USD uses two decimal places, so this column value would be `2`.

+++

+++**`curr_rate`**

The exchange rate when the transaction occurred. Adobe partners with XE to determine the current day's exchange rate.

+++

+++**`customer_perspective`**

Determines if the hit is a mobile background hit. See [Context-aware sessions](/help/components/vrs/vrs-mobile-visit-processing.md) for more information.

+++

+++**`cust_hit_time_gmt`**

Timestamp-enabled report suites only. The timestamp sent with the hit, based in UNIX&reg; time.

+++

+++**`cust_visid`**

The custom visitor ID, if set using [`visitorID`](/help/implement/vars/config-vars/visitorid.md).

+++

+++**`c_color`**

Bit depth of the color palette. Used as part of calculating the [Color depth](/help/components/dimensions/color-depth.md) dimension. AppMeasurement uses the JavaScript function `screen.colorDepth()`.

+++

+++**`daily_visitor`**

A flag that determines if the hit is a new daily visitor.

+++

+++**`dataprivacyconsentoptin`**

The [Consent management opt-in](/help/components/dimensions/cm-opt-in.md) dimension. Multiple values can be present per hit, separated by a pipe (`\|`). Valid values include `DMP` and `SELL`.

+++

+++**`dataprivacyconsentoptout`**

The [Consent management opt-out](/help/components/dimensions/cm-opt-out.md) dimension. Multiple values can be present per hit, separated by a pipe (`\|`). Valid values include `SSF`, `DMP`, and `SELL`.

+++

+++**`date_time`**

The time of the hit in readable format, based on the report suite's time zone.

+++

+++**`domain`**

The [Domain](/help/components/dimensions/domain.md) dimension. Based on the visitor's Internet access point.

+++

+++**`duplicated_from`**

Only used in report suites containing hit copy VISTA rules. Indicates which report suite that the hit was copied from.

+++

+++**`duplicate_events`**

Lists each event that was counted as a duplicate.

+++

+++**`duplicate_purchase`**

A flag that determines if the purchase event for this hit is ignored because it is a duplicate.

+++

+++**`ef_id`**

The EF ID, used in Adobe Advertising integrations.

+++

+++**`evar1 - evar250`**

Custom variables 1-250. Used in [eVar](/help/components/dimensions/evar.md) dimensions. Each organization uses eVars differently. The best place for more information on how your organization populates respective eVars would be a [solution design document](/help/implement/prepare/solution-design.md) specific to your organization.

+++

+++**`event_list`**

Comma-separated list of numeric IDs that represent events triggered on the hit. Includes both commerce events and [custom events 1-1000](/help/components/metrics/custom-events.md). Uses `event.tsv` lookup.

+++

+++**`exclude_hit`**

A flag that determines if the hit is excluded from reporting. The `visit_num` column is not incremented for excluded hits.<br>1: Not used. Part of a scrapped feature.<br>2: Not used. Part of a scrapped feature.<br>3: No longer used. User agent exclusion<br>4: Exclusion based on IP address<br>5: Vital hit info missing, such as `page_url`, `pagename`, `page_event`, or `event_list`<br>6: JavaScript did not correctly process hit<br>7: Account-specific exclusion, such as in a VISTA rules<br>8: Not used. Alternate account-specific exclusion.<br>9: Not used. Part of a scrapped feature.<br>10: Invalid currency code<br>11: Hit missing a timestamp on a timestamp-only report suite, or a hit contained a timestamp on a non-timestamp report suite<br>12: Not used. Part of a scrapped feature.<br>13: Not used. Part of a scrapped feature.<br>14: Target hit that did not match up with an Analytics hit<br>15: Not currently used.<br>16: Advertising Cloud hit that did not match up to an Analytics hit

+++

+++**`first_hit_pagename`**

The [Entry page original](/help/components/dimensions/entry-dimensions.md) dimension. The original entry page name of the visitor.

+++

+++**`first_hit_page_url`**

The very first URL of the visitor.

+++

+++**`first_hit_referrer`**

The very first referring URL of the visitor.

+++

+++**`first_hit_ref_domain`**

The [Original referring domain](/help/components/dimensions/original-referring-domain.md) dimension. Based on `first_hit_referrer`. The very first referring domain of the visitor.

+++

+++**`first_hit_ref_type`**

A numeric ID that represents the referrer type of the very first referrer of the visitor. References the `referrer_type.tsv` lookup table.

+++

+++**`first_hit_time_gmt`**

Timestamp of the very first hit of the visitor in UNIX&reg; time.

+++

+++**`geo_city`**

The name of the city that the hit came from, based on IP. Used in the [Cities](/help/components/dimensions/cities.md) dimension.

+++

+++**`geo_country`**

The abbreviation of the country that the hit came from, based on IP. Used in the [Countries](/help/components/dimensions/countries.md) dimension.

+++

+++**`geo_dma`**

A numeric ID of the demographic area that the hit came from, based on IP. Used in the [US DMA](/help/components/dimensions/us-dma.md) dimension.

+++

+++**`geo_region`**

The name of the state or region that the hit came from, based on IP. Used in the [Regions](/help/components/dimensions/regions.md) dimension.

+++

+++**`geo_zip`**

The zip code that the hit came from, based on IP. Helps populate the [Zip code](/help/components/dimensions/zip-code.md) dimension. See also `zip`.

+++

+++**`hitid_high`**

Used with `hitid_low` to identify a hit.

+++

+++**`hitid_low`**

Used with `hitid_high` to identify a hit.

+++

+++**`hit_source`**

The source that the hit came from. Hit sources 1 and 2 are billed. <br>1: Standard image request without timestamp <br>2: Standard image request with timestamp <br>3: Live data source upload with timestamps <br>4: Not used <br>5: Generic data source upload <br>6: No longer used; full processing data source upload <br>7: TransactionID data source upload <br>8: No longer used; Previous versions of Adobe Advertising data sources <br>9: No longer used; Adobe Social summary metrics <br>10: Audience Manager server-side forwarding used

+++

+++**`hit_time_gmt`**

The timestamp of the hit Adobe data collection servers received the hit, based in UNIX&reg; time.

+++

+++**`hourly_visitor`**

A flag that determines if the hit is a new hourly visitor.

+++

+++**`ip`**

The IPv4 address, based on the HTTP header of the image request. Mutually exclusive to `ipv6`; if this column contains a non-obfuscated IP address, `ipv6` is blank.

+++

+++**`ipv6`**

The compressed IPv6 address, if available. Mutually exclusive to `ip`; if this column contains a non-obfuscated IP address, `ip` is blank.

+++

+++**`javascript`**

A lookup ID of JavaScript version, based on `j_jscript`. References the `javascript_version` lookup table.

+++

+++**`java_enabled`**

The [[!UICONTROL Java enabled]](/help/components/dimensions/java-enabled.md). <br>Y: Enabled <br>N: Disabled <br>U: Unknown

+++

+++**`j_jscript`**

Version of JavaScript supported by the browser.

+++

+++**`language`**

A numeric ID that represents the visitor's language. References the `languages.tsv` lookup table.

+++

+++**`last_hit_time_gmt`**

Timestamp (in UNIX&reg; time) of the prior hit. Used to calculate the [[!UICONTROL Days since last visit]](/help/components/dimensions/days-since-last-visit.md) dimension.

+++

+++**`last_purchase_num`**

The [Customer loyalty](/help/components/dimensions/customer-loyalty.md) dimension. The number of previous purchases the visitor has made. <br>0: No prior purchases (not a customer) <br>1: 1 prior purchase (new customer) <br>2: 2 prior purchases (return customer) <br>3: 3 or more prior purchases (loyal customer)

+++

+++**`last_purchase_time_gmt`**

Used in the [[!UICONTROL Days since last purchase]](/help/components/dimensions/days-since-last-purchase.md) dimension. Timestamp (in UNIX&reg; time) of the last purchase made. For first-time purchases and visitors that have not made a purchase before, this value is `0`.

+++

+++**`latlon1`**

Location (down to 10 km)

+++

+++**`latlon23`**

Location (down to 100 m)

+++

+++**`latlon45`**

Location (down to 1 m)

+++

+++**`mcvisid`**

Experience Cloud Visitor ID. 128-bit number consisting of two concatenated 64-bit numbers padded to 19 digits.

+++

+++**`mc_audiences`**

List of Audience Manager segment IDs that the visitor belongs to. The `post_mc_audiences` column changes the delimiter to `--**--`.

+++

+++**`mobileaction`**

Mobile action. Automatically collected when `trackAction` is called in mobile implementations. Allows for automatic action pathing in the app.

+++

+++**`mobileappid`**

Mobile app ID. Stores the application name and version in the following format: `[AppName] [BundleVersion]`

+++

+++**`mobileappperformanceappid`**

Used in the Apteligent data connector. The App ID used in Apteligent.

+++

+++**`mobileappperformancecrashid`**

Used in the Apteligent data connector. The crash ID used in Apteligent.

+++

+++**`mobileappstoreobjectid`**

Used in the [!DNL Appfigures] data connector. App store object ID.

+++

+++**`mobilebeaconmajor`**

Mobile Services beacon major

+++

+++**`mobilebeaconminor`**

Mobile Services beacon minor

+++

+++**`mobilebeaconproximity`**

Mobile Services beacon proximity

+++

+++**`mobilebeaconuuid`**

Mobile Services beacon UUID

+++

+++**`mobilecampaigncontent`**

The name or ID of the content that displayed the link. Populated by Mobile App Acquisition.

+++

+++**`mobilecampaignmedium`**

Marketing medium, such as banner or email. Populated by Mobile App Acquisition.

+++

+++**`mobilecampaignname`**

The name of the campaign, also stored in the campaign variable. Populated by Mobile App Acquisition.

+++

+++**`mobilecampaignsource`**

Original referrer, such as newsletter or social media network. Populated by Mobile App Acquisition.

+++

+++**`mobilecampaignterm`**

Paid keywords or other terms you want to track with this acquisition. Populated by Mobile App Acquisition.

+++

+++**`mobiledayofweek`**

Number of the weekday that the app was launched on.

+++

+++**`mobiledayssincefirstuse`**

Number of days since the app was run for the first time.

+++

+++**`mobiledayssincelastuse`**

Number of days since the app was last run.

+++

+++**`mobiledeeplinkid`**

Collected from the context data variable `a.deeplink.id`. Used in acquisition reports as an identifier for mobile acquisition link.

+++

+++**`mobiledevice`**

Mobile device name. On iOS, it is stored as a comma-separated 2-digit string. The first number represents the device generation, and the second number represents the device family.

+++

+++**`mobilehourofday`**

Defines the hour of the day that the app was launched. Follows 24-hour numerical format.

+++

+++**`mobileinstalldate`**

Mobile install date. Provides the date of the first time that a user opens the mobile app.

+++

+++**`mobilelaunchnumber`**

Increments by one each time the mobile app is launched.

+++

+++**`mobilemessagebuttonname`**

Collected from the context data variable `a.message.button.id`. Used for in-app messaging to identify the button that closed the message.

+++

+++**`mobilemessageid`**

In-app Message ID

+++

+++**`mobilemessageonline`**

In-app Message Online

+++

+++**`mobilemessagepushoptin`**

Collected from the context data variable `a.push.optin`. Set to "true" when the user opts in to push messaging; otherwise the value is "false".

+++

+++**`mobilemessagepushpayloadid`**

Collected from the context data variable `a.push.payloadid`. Used in push messaging as the payload identifier.

+++

+++**`mobileosversion`**

Mobile Services operating system version

+++

+++**`mobileplaceaccuracy`**

Collected from the context data variable `a.loc.acc`. Indicates the accuracy of the GPS in meters at time of collection.

+++

+++**`mobileplacecategory`**

Collected from the context data variable `a.loc.category`. Describes the category of a specific place.

+++

+++**`mobileplaceid`**

Collected from the context data variable `a.loc.id`. Identifier for a given point of interest.

+++

+++**`mobilepushoptin`**

Mobile Services Push opt-in

+++

+++**`mobilepushpayloadid`**

Mobile Services Push payload ID

+++

+++**`mobilerelaunchcampaigncontent`**

Mobile Services launch content

+++

+++**`mobilerelaunchcampaignmedium`**

Mobile Services launch medium

+++

+++**`mobilerelaunchcampaignsource`**

Mobile Services launch source

+++

+++**`mobilerelaunchcampaignterm`**

Mobile Services launch term

+++

+++**`mobilerelaunchcampaigntrackingcode`**

Collected from the context data variable `a.launch.campaign.trackingcode`. Used in acquisition as the tracking code for launch campaign.

+++

+++**`mobileresolution`**

Resolution of the mobile device. `[Width] x [Height]` in pixels.

+++

+++**`mobile_id`**
If the user is using a mobile device, the numeric ID of the device. The key value for `mobile_attributes.tsv` [Dynamic lookup](dynamic-lookups.md).

+++

+++**`monthly_visitor`**

A flag that determines if the visitor is unique to the current month.

+++

+++**`mvvar1`** - **`mvvar3`**

[List variable](/help/implement/vars/page-vars/list.md) values. Contains a delimited list of custom values depending on implementation. The `post_mvvar1` - `post_mvvar3` columns replace the original delimiter with `--**--`.

+++

+++**`mvvar1_instances`** - **`mvvar3_instances`**

The list variable values that were set on the current hit. Replaces the original delimiter with `--**--`. The `post` columns typically do not contain data.

+++

+++**`new_visit`**

A flag that determines if the current hit is a new visit. Set by Adobe after 30 minutes of visit inactivity.

+++

+++**`os`**

A numeric ID that represents the operating system of the visitor. Based on the `user_agent` column. The key value for `operating_system.tsv` standard lookup and `operating_system_type.tsv` [Dynamic lookup](dynamic-lookups.md).

+++

+++**`pagename`**

The [Page](/help/components/dimensions/page.md) dimension. If the [`pagename`](/help/implement/vars/page-vars/pagename.md) variable is empty, Analytics uses `page_url` instead.

+++

+++**`pagename_no_url`**

Similar to `pagename`, except it does not fall back to `page_url`. Only the `post` column is available.

+++

+++**`page_event`**

The type of hit that is sent in the image request (standard hit, download link, custom link, exit link). See [Page event lookup](datafeeds-page-event.md).

+++

+++**`page_event_var1`**

Only used in link tracking image requests. The URL of the download link, exit link, or custom link clicked.

+++

+++**`page_event_var2`**

Only used in link tracking image requests. The custom name (if specified) of the link. Sets the [Custom link](/help/components/dimensions/custom-link.md), [Download link](/help/components/dimensions/download-link.md), or [Exit link](/help/components/dimensions/exit-link.md) depending on the value in `page_event`.

+++

+++**`page_type`**

The [Pages not found](/help/components/dimensions/pages-not-found.md) dimension, which is typically used for 404 pages.

+++

+++**`page_url`**

**`page_url`**: The URL of the hit. Uses a data type of text.<br>**`post_page_url`**: Stripped for link tracking image requests ([`tl()`](/help/implement/vars/functions/tl-method.md)). Uses a data type of varchar(255).

+++

+++**`paid_search`**

A flag that determines if the hit matches paid search detection.

+++

+++**`persistent_cookie`**

Used in the [Persistent cookie support](/help/components/dimensions/persistent-cookie-support.md) dimension. Indicates if the visitor supports cookies that are not discarded after each hit.

+++

+++**`pointofinterest`**

Mobile Services point of interest name

+++

+++**`pointofinterestdistance`**

Mobile Services distance to point of interest center

+++

+++**`product_list`**

The [`products`](/help/implement/vars/page-vars/products.md) page variable. Helps populate several dimensions and metrics, including [Category](/help/components/dimensions/category.md), [Product](/help/components/dimensions/product.md), [Units](/help/components/metrics/units.md), and [Revenue](/help/components/metrics/revenue.md).

+++

+++**`prop1`** - **`prop75`**

Custom traffic variables 1-75. Used in [Prop](/help/components/dimensions/prop.md) dimensions.

+++

+++**`purchaseid`**

Unique identifier for a purchase, as set using the [`purchaseID`](/help/implement/vars/page-vars/purchaseid.md) variable. Used by the `duplicate_purchase` column.

+++

+++**`quarterly_visitor`**

A flag that determines if the hit is a new quarterly visitor.

+++

+++**`referrer`**

The [Referrer](/help/components/dimensions/referrer.md) dimension. Note that while `referrer` uses a data type of varchar(255), `post_referrer` uses a data type of varchar(244).

+++

+++**`ref_domain`**

The [Referring domain](/help/components/dimensions/referring-domain.md) dimension. Based on the `referrer` column.

+++

+++**`ref_type`**


A numeric ID that represents the type of referral for the hit. Used in the [Referrer type](/help/components/dimensions/referrer-type.md) dimension.<br>1: Inside your site<br>2: Other web sites<br>3: Search engines<br>4: Hard drive<br>5: USENET<br>6: Typed/Bookmarked (no referrer)<br>7: Email<br>8: No JavaScript<br>9: Social Networks<br>10: Conversational AI tools

+++

+++**`resolution`**

A numeric ID that represents the resolution of the monitor. Used in the [Monitor resolution](/help/components/dimensions/monitor-resolution.md) dimension. Uses `resolution.tsv` lookup table.

+++

+++**`search_engine`**

A numeric ID that represents the search engine that referred the visitor to your site. Used in [Search Engine](/help/components/dimensions/search-engine.md) dimensions. References the `search_engines.tsv` lookup table.

+++

+++**`search_page_num`**

Used by the [All Search Page Rank](/help/components/dimensions/all-search-page-rank.md) dimension. Indicates which page of search results that your site appeared on before the user clicked through to your site.

+++

+++**`secondary_hit`**

A flag that determines if the hit is a secondary hit. This flag typically originates from multi-suite tagging and VISTA rules that copy hits.

+++

+++**`sourceid`**

Source ID

+++

+++**`stats_server`**

Not of use. Adobe internal server that processed the hit.

+++

+++**`s_kwcid`**

Keyword ID used in Adobe Advertising integrations.

+++

+++**`s_resolution`**

Raw screen resolution value. Gathered using the JavaScript function `screen.width x screen.height`.

+++

+++**`tnt`**

Used in Adobe Target integrations. Represents all tests currently qualified for. Format is: `TargetCampaignID:TargetRecipeID:TargetType\|Event/Action`.

+++

+++**`tnt_action`**

Used in Adobe Target integrations. Represents all tests the hit qualified for.

+++

+++**`tnt_instances`**

Used in Adobe Target integrations. Target instances variable.

+++

+++**`transactionid`**

A unique identifier where various data points can be uploaded later through data sources. Collected using the [`transactionID`](/help/implement/vars/page-vars/transactionid.md) variable.

+++

+++**`truncated_hit`**

A flag indicating that the image request was truncated (a partial hit was received). <br>Y: Hit was truncated; partial hit received <br>N: Hit was not truncated; full hit received

+++

+++**`t_time_info`**

Local time for the visitor. Format is: `M/D/YYYY HH:MM:SS Month (0-11, 0=January) Timezone offset (in minutes)`

+++

+++**`userid`**

Not of use. The numeric ID for the report suite ID. Use `username` instead.

+++

+++**`username`**

The report suite ID for the hit.

+++

+++**`user_agent`**

The user agent string sent in the HTTP header of the image request.

+++

+++**`user_hash`**

Not of use. Hash on the report suite ID. Use `username` instead.

+++

+++**`user_server`**

Used in the [Server](/help/components/dimensions/server.md) dimension.

+++

+++**`va_closer_detail`**

The [Last touch detail](/help/components/dimensions/last-touch-detail.md) dimension.

+++

+++**`va_closer_id`**

A numeric ID that identifies the [Last touch channel](/help/components/dimensions/last-touch-channel.md) dimension. The lookup for this ID can be found in the Marketing Channel Manager.

+++

+++**`va_finder_detail`**

The [First touch detail](/help/components/dimensions/first-touch-detail.md) dimension.

+++

+++**`va_finder_id`**

A numeric ID that identifies the [First touch channel](/help/components/dimensions/first-touch-channel.md) dimension. The lookup for this ID can be found in the Marketing Channel Manager.

+++

+++**`va_instance_event`**

A flag that identifies Marketing Channel [Instances](/help/components/metrics/instances.md).

+++

+++**`va_new_engagement`**

A flag that identifies Marketing Channel [New engagements](/help/components/metrics/new-engagements.md).

+++

+++**`video`**

The [Content](/help/components/dimensions/sm-core.md) streaming media services dimension.

+++

+++**`videoad`**

The [Ad](/help/components/dimensions/sm-ads.md) streaming media services dimension.

+++

+++**`videoadinpod`**

The [Ad in pod position](/help/components/dimensions/sm-ads.md) streaming media services dimension.

+++

+++**`videoadlength`**

The [Ad length (variable)](/help/components/dimensions/sm-ads.md) streaming media services dimension.

+++

+++**`videoadname`**

The [Ad name (variable)](/help/components/dimensions/sm-ads.md) streaming media services dimension.

+++

+++**`videoadplayername`**

The [Ad player name](/help/components/dimensions/sm-ads.md) streaming media services dimension.

+++

+++**`videoadpod`**

The [Ad pod](/help/components/dimensions/sm-ads.md) streaming media services dimension.

+++

+++**`videoadvertiser`**

The [Advertiser](/help/components/dimensions/sm-ads.md) streaming media services dimension.

+++

+++**`videoaudioalbum`**

The [Album](/help/components/dimensions/sm-audio-metadata.md) streaming media services dimension.

+++

+++**`videoaudioartist`**

The [Artist](/help/components/dimensions/sm-audio-metadata.md) streaming media services dimension.

+++

+++**`videoaudioauthor`**

The [Author](/help/components/dimensions/sm-audio-metadata.md) streaming media services dimension.

+++

+++**`videoaudiolabel`**

The [Label](/help/components/dimensions/sm-audio-metadata.md) streaming media services dimension.

+++

+++**`videoaudiopublisher`**

The [Publisher](/help/components/dimensions/sm-audio-metadata.md) streaming media services dimension.

+++

+++**`videoaudiostation`**

The [Station](/help/components/dimensions/sm-audio-metadata.md) streaming media services dimension.

+++

+++**`videocampaign`**

The [Campaign ID](/help/components/dimensions/sm-ads.md) streaming media services dimension.

+++

+++**`videochannel`**

The [Content channel](/help/components/dimensions/sm-core.md) streaming media services dimension.

+++

+++**`videochapter`**

The [Chapter](/help/components/dimensions/sm-chapters.md) streaming media services dimension.

+++

+++**`videocontenttype`**

The [Content type](/help/components/dimensions/sm-core.md) streaming media services dimension.

+++

+++**`videodaypart`**

The [Day part](/help/components/dimensions/sm-video-metadata.md) streaming media services dimension.

+++

+++**`videoepisode`**

The [Episode](/help/components/dimensions/sm-video-metadata.md) streaming media services dimension.

+++

+++**`videofeedtype`**

The [Media feed type](/help/components/dimensions/sm-video-metadata.md) streaming media services dimension.

+++

+++**`videogenre`**

The [Genre](/help/components/dimensions/sm-video-metadata.md) streaming media services dimension. This dimension allows multiple values in the same hit, delimited by a comma.

+++

+++**`videolength`**

The [Content length (variable)](/help/components/dimensions/sm-core.md) streaming media services dimension.

+++

+++**`videomvpd`**

The [MVPD](/help/components/dimensions/sm-video-metadata.md) streaming media services dimension.

+++

+++**`videoname`**

The [Content name (variable)](/help/components/dimensions/sm-core.md) streaming media services dimension.

+++

+++**`videonetwork`**

The [Network](/help/components/dimensions/sm-video-metadata.md) streaming media services dimension.

+++

+++**`videopath`**

The [Media path](/help/components/dimensions/sm-core.md) streaming media services dimension.

+++

+++**`videoplayername`**

The [Content player name](/help/components/dimensions/sm-core.md) streaming media services dimension.

+++

+++**`videoqoebitrateaverageevar`**

The [Average bitrate](/help/components/dimensions/sm-quality.md) streaming media services dimension.

+++

+++**`videoqoebitratechangecountevar`**

The [Bitrate changes](/help/components/dimensions/sm-quality.md) streaming media services dimension.

+++

+++**`videoqoebuffercountevar`**

The [Buffer events](/help/components/dimensions/sm-quality.md) streaming media services dimension.

+++

+++**`videoqoebuffertimeevar`**

The [Total buffer duration](/help/components/dimensions/sm-quality.md) streaming media services dimension.

+++

+++**`videoqoedroppedframecountevar`**

The [Dropped frames](/help/components/dimensions/sm-quality.md) streaming media services dimension.

+++

+++**`videoqoeerrorcountevar`**

The [Errors](/help/components/dimensions/sm-quality.md) streaming media services dimension.

+++

+++**`videoqoeextneralerrors`**

The [External error IDs](/help/components/dimensions/sm-quality.md) streaming media services dimension. This dimension allows multiple values in the same hit.

+++

+++**`videoqoeplayersdkerrors`**

The [Player SDK error IDs](/help/components/dimensions/sm-quality.md) streaming media services dimension. This dimension allows multiple values in the same hit.

+++

+++**`videoqoetimetostartevar`**

The [Time to start](/help/components/dimensions/sm-quality.md) streaming media services dimension.

+++

+++**`videoseason`**

The [Season](/help/components/dimensions/sm-video-metadata.md) streaming media services dimension.

+++

+++**`videosegment`**

The [Content segment](/help/components/dimensions/sm-core.md) streaming media services imension.

+++

+++**`videosessionid`**

The [Media session ID](/help/components/dimensions/sm-core.md) streaming media services dimension.

+++

+++**`videoshow`**

The [Show](/help/components/dimensions/sm-video-metadata.md) streaming media services dimension.

+++

+++**`videoshowtype`**

The [Show type](/help/components/dimensions/sm-video-metadata.md) streaming media services dimension.

+++

+++**`videostreamtype`**

The [Stream type](/help/components/dimensions/sm-core.md) streaming media services dimension.

+++

+++**`visid_high`**

Used with `visid_low` to uniquely identify a visitor.

+++

+++**`visid_low`**

Used with `visid_high` to uniquely identify a visitor.

+++

+++**`visid_new`**

A flag that determines if the hit contains a newly generated visitor ID.

+++

+++**`visid_timestamp`**

If a visitor ID is newly generated, provides the timestamp in UNIX&reg; time of when the visitor ID was generated.

+++

+++**`visid_type`**

Not for external use; internally used by Adobe for processing optimizations. A numeric ID that represents the method used to identify the visitor.<br>`0`: Custom visitor ID or Unknown/not applicable<br>`1`: IP and user agent fallback <br>`2`: HTTP Mobile Subscriber Header <br>`3`: Legacy cookie value (`s_vi`) <br>`4`: Fallback cookie value (`s_fid`) <br>`5`: Identity Service

+++

+++**`visit_keywords`**

The [Search keyword](/help/components/dimensions/search-keyword.md) dimension. This column uses a non-standard character limit of varchar(244) to accommodate back-end logic used by Adobe. The post-processed column is `**post_keywords**`, not `**post_visit_keywords**`.

+++

+++**`visit_num`**

The [Visit number](/help/components/dimensions/visit-number.md) dimension. Starts at 1, and increments each time a new visit starts per visitor.

+++

+++**`visit_page_num`**

The [Hit depth](/help/components/dimensions/hit-depth.md) dimension. Increases by 1 for each hit that the visitor generates. Resets each visit.

+++

+++**`visit_referrer`**

The first referrer of the visit.

+++

+++**`visit_ref_domain`**

Based on the `visit_referrer` column. The first referring domain of the visit.

+++

+++**`visit_ref_type`**

A numeric ID that represents the referrer type of the first referrer of the visit. References the `referrer_type.tsv` lookup table.

+++

+++**`visit_search_engine`**

A numeric ID that represents the first search engine of the visit. References the `search_engines.tsv` lookup table.

+++

+++**`visit_start_pagename`**

[Page](/help/components/dimensions/page.md) of the first hit of the visit.

+++

+++**`visit_start_page_url`**

URL of the first hit of the visit.

+++

+++**`visit_start_time_gmt`**

Timestamp (in UNIX&reg; time) of the first hit of the visit.

+++

+++**`weekly_visitor`**

A flag that determines if the hit is a new weekly visitor.

+++

+++**`yearly_visitor`**

A flag that determines if the hit is a new yearly visitor.

+++

+++**`zip`**

Helps populate the [Zip code](/help/components/dimensions/zip-code.md) dimension. See also `geo_zip`.

+++
