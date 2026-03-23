---
title: Map Adobe Analytics data feed columns to Customer Journey Analytics
description: Determine how to take a given Adobe Analytics data feed column and determine its rough equivalent in your Customer Journey Analytics implementation.
feature: Components
hide: yes
hidefromtoc: yes
exl-id: 81d6e79e-8324-4726-9a48-10177b0a91b1
---
# Map Adobe Analytics data feed columns to Customer Journey Analytics

A true 1:1 mapping between Adobe Analytics and Customer Journey Analytics data feed columns is not possible. The two products differ fundamentally, and each organization's implementation can vary significantly.

This reference helps data engineers evaluate Adobe Analytics data feed columns and identify the closest Customer Journey Analytics equivalents for their workflows.

>[!NOTE]
>
>This reference only includes columns that are considered current by Adobe, based on the [Analytics data feed column reference](https://experienceleague.adobe.com/en/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference). If you have an Analytics data feed column not listed on this table that you actively use, consult your organization's solution design document to determine its best equivalent in Customer Journey Analytics.

+++**`accept_language`**

Lists all accepted languages, as indicated in the Accept-Language HTTP header in an image request.

+++

+++**`adload`**

Media ad loads

{{cja-df-post}}

+++

+++**`aemassetid`**

A multi-value variable corresponding to Asset IDs (GUIDs) of a set of Adobe Experience Manager Assets. Increments Impression Events.

{{cja-df-post}}

+++

+++**`aemassetsource`**

Identifies the source of the asset event. Used in Adobe Experience Manager.

{{cja-df-post}}
+++

+++**`aemclickedassetid`**

Asset ID of an Adobe Experience Manager asset. Increments Click Events.

{{cja-df-post}}

+++

+++**`amo_cid`**

The AMO ID dimension, used in Adobe Advertising integrations.

{{cja-df-post}}

+++

+++**`amo_ef_id`**

The AMO EF ID dimension, used in Adobe Advertising integrations.

{{cja-df-post}}

+++

+++**`browser`**

A numeric ID that represents the browser.

{{cja-df-lookup}}

+++

+++**`browser_height`**

The Browser Height dimension.

{{cja-df-post}}

+++

+++**`browser_width`**

The Browser Width

{{cja-df-post}}

+++

+++**`campaign`**

The Tracking Code dimension.

{{cja-df-post}}

+++

+++**`carrier`**

Adobe Advertising integration variable. Specifies the mobile carrier.

{{cja-df-lookup}}

+++

+++**`channel`**

The Site sections dimension.

{{cja-df-post}}

+++

+++**`ch_hdr`**

Client hints collected through the HTTP request header.

+++

+++**`ch_js`**

Client hints collected through the User-Agent Client Hints JavaScript API.

+++

+++**`clickmaplink`**

The Activity Map link dimension.

{{cja-df-post}}

{{cja-df-na}}

This column does not apply because Customer Journey Analytics does not yet support Activity Map.

+++

+++**`clickmaplinkbyregion`**

The Activity Map link by region dimension.

{{cja-df-post}}

{{cja-df-na}}

This column does not apply because Customer Journey Analytics does not yet support Activity Map.

+++

+++**`clickmappage`**

The Activity Map page dimension.

{{cja-df-post}}

{{cja-df-na}}

This column does not apply because Customer Journey Analytics does not yet support Activity Map.

+++

+++**`clickmapregion`**

The Activity Map region dimension.

{{cja-df-post}}

{{cja-df-na}}

This column does not apply because Customer Journey Analytics does not yet support Activity Map.

+++

+++**`code_ver`**

API or client SDK version used to compile and send the image request.

+++

+++**`color`**

Color depth ID based on the value of the `c_color` column.

{{cja-df-lookup}}

+++

+++**`connection_type`**

Numeric ID representing the Connection type dimension.

{{cja-df-lookup}}

+++

+++**`cookies`**

The Cookie support dimension.<br>Y: Enabled<br>N: Disabled<br>U: Unknown

{{cja-df-post}}

+++

+++**`country`**

A numeric ID that represents the country of the visitor. References the `country.tsv` lookup table.

{{cja-df-lookup}}

+++

+++**`currency`**

The currency code that was used during the transaction. Set using `currencyCode`.

`xdm.commerce.order.currencyCode`

{{cja-df-post}}

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

Determines if the hit is a mobile background hit.

{{cja-df-post}}

+++

+++**`cust_hit_time_gmt`**

Timestamp-enabled report suites only. The timestamp sent with the hit, based in UNIX&reg; time.

{{cja-df-post}}

+++

+++**`cust_visid`**

The custom visitor ID, if set using `visitorID`.

{{cja-df-post}}

+++

+++**`c_color`**

Bit depth of the color palette. Used as part of calculating the Color depth dimension. AppMeasurement uses the JavaScript function `screen.colorDepth()`.

+++

+++**`daily_visitor`**

A flag that determines if the hit is a new daily visitor.

+++

+++**`dataprivacyconsentoptin`**

The Consent management opt-in dimension. Multiple values can be present per hit, separated by a pipe (`\|`). Valid values include `DMP` and `SELL`.

{{cja-df-na}}

This column does not apply because Customer Journey Analytics does not ???.

+++

+++**`dataprivacyconsentoptout`**

The Consent management opt-out dimension. Multiple values can be present per hit, separated by a pipe (`\|`). Valid values include `SSF`, `DMP`, and `SELL`.

+++

+++**`date_time`**

The time of the hit in readable format, based on the report suite's time zone.

+++

+++**`domain`**

The Domain dimension. Based on the visitor's Internet access point.

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

{{cja-df-post}}

+++

+++**`evar1 - evar250`**

Custom variables 1-250. Used in eVar dimensions. Each organization uses eVars differently. The best place for more information on how your organization populates respective eVars would be a solution design document specific to your organization.

{{cja-df-post}}

+++

+++**`event_list`**

Comma-separated list of numeric IDs that represent events triggered on the hit. Includes both commerce events and custom events 1-1000. Uses `event.tsv` lookup.

This column likely maps to dozens of separate metrics, depending on your implementation. Adobe recommends the following process to map each respective metric in Customer Journey Analytics to its numeric value represented in this Analytics data feed column:

1. Use the `event.tsv` lookup to map each numeric value to its metric name.
1. Use your solution design document to map each Analytics event name to its corresponding metric name in Customer Journey Analytics.
1. Select the mapped component in the Data Views UI and note its component ID. If the component ID is too unwieldy, you can populate the data feed alias ID field and use that instead.
1. Repeat for every metric that your organization uses.

{{cja-df-post}}

If your schema uses the [[!UICONTROL Commerce Details]](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/field-groups/event/commerce-details) field group, some metrics might directly map to the following XDM fields:

* **Checkouts**: `xdm.commerce.checkouts.value`
* **Cart adds**: `xdm.commerce.productListAdds.value`
* **Cart opens**: `xdm.commerce.productListOpens.value`
* **Cart removals**: `xdm.commerce.productListRemovals.value`
* **Cart views**: `xdm.commerce.productListViews.value`
* **Product views**: `xdm.commerce.productViews.value`
* **Orders**: `xdm.commerce.purchases.value`

Some metrics might use event serialization, which is how Adobe Analytics allows full control over deduplication. You can use the [Metric deduplication](/help/data-views/component-settings/metric-deduplication.md) component setting to achieve deduplication parity.

* If your metric deduplicates by visit in Adobe Analytics, you can set the deduplication scope to session in that metric's component settings.
* If your metric deduplicates by event ID in Adobe Analytics, it is likely that the XDM object for that metric contains both a `value` and `id` field. If your schema uses the [[!UICONTROL Commerce Details]](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/field-groups/event/commerce-details) field group, those metrics likely reside in these XDM fields, which you can set the **[!UICONTROL Deduplication ID]** field in the metric's component settings:

  * **Checkouts**: `xdm.commerce.checkouts.id`
  * **Cart adds**: `xdm.commerce.productListAdds.id`
  * **Cart opens**: `xdm.commerce.productListOpens.id`
  * **Cart removals**: `xdm.commerce.productListRemovals.id`
  * **Cart views**: `xdm.commerce.productListViews.id`
  * **Product views**: `xdm.commerce.productViews.id`
  * **Orders**: `xdm.commerce.purchases.id`

+++

+++**`exclude_hit`**

A flag that determines if the hit is excluded from reporting. The `visit_num` column is not incremented for excluded hits.<br>1: Not used. Part of a scrapped feature.<br>2: Not used. Part of a scrapped feature.<br>3: No longer used. User agent exclusion<br>4: Exclusion based on IP address<br>5: Vital hit info missing, such as `page_url`, `pagename`, `page_event`, or `event_list`<br>6: JavaScript did not correctly process hit<br>7: Account-specific exclusion, such as in a VISTA rules<br>8: Not used. Alternate account-specific exclusion.<br>9: Not used. Part of a scrapped feature.<br>10: Invalid currency code<br>11: Hit missing a timestamp on a timestamp-only report suite, or a hit contained a timestamp on a non-timestamp report suite<br>12: Not used. Part of a scrapped feature.<br>13: Not used. Part of a scrapped feature.<br>14: Target hit that did not match up with an Analytics hit<br>15: Not currently used.<br>16: Advertising Cloud hit that did not match up to an Analytics hit

+++

+++**`first_hit_pagename`**

The Entry page original dimension. The original entry page name of the visitor.

+++

+++**`first_hit_page_url`**

The very first URL of the visitor.

+++

+++**`first_hit_referrer`**

The very first referring URL of the visitor.

+++

+++**`first_hit_ref_domain`**

The Original referring domain dimension. Based on `first_hit_referrer`. The very first referring domain of the visitor.

+++

+++**`first_hit_ref_type`**

A numeric ID that represents the referrer type of the very first referrer of the visitor.

{{cja-df-lookup}}

+++

+++**`first_hit_time_gmt`**

Timestamp of the very first hit of the visitor in UNIX&reg; time.

+++

+++**`geo_city`**

The name of the city that the hit came from, based on IP. Used in the Cities dimension.

+++

+++**`geo_country`**

The abbreviation of the country that the hit came from, based on IP. Used in the Countries dimension.

+++

+++**`geo_dma`**

A numeric ID of the demographic area that the hit came from, based on IP. Used in the US DMA dimension.

+++

+++**`geo_region`**

The name of the state or region that the hit came from, based on IP. Used in the Regions dimension.

+++

+++**`geo_zip`**

The zip code that the hit came from, based on IP. Helps populate the Zip code dimension. See also `zip`.

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

A lookup ID of JavaScript version, based on `j_jscript`.

{{cja-df-lookup}}

+++

+++**`java_enabled`**

The Java enabled dimension. <br>Y: Enabled <br>N: Disabled <br>U: Unknown

{{cja-df-post}}

+++

+++**`j_jscript`**

Version of JavaScript supported by the browser.

+++

+++**`language`**

A numeric ID that represents the visitor's language.

{{cja-df-lookup}}

+++

+++**`last_hit_time_gmt`**

Timestamp (in UNIX&reg; time) of the prior hit. Used to calculate the Days since last visit dimension.

+++

+++**`last_purchase_num`**

The Customer loyalty dimension. The number of previous purchases the visitor has made. <br>0: No prior purchases (not a customer) <br>1: 1 prior purchase (new customer) <br>2: 2 prior purchases (return customer) <br>3: 3 or more prior purchases (loyal customer)

+++

+++**`last_purchase_time_gmt`**

Used in the Days since last purchase dimension. Timestamp (in UNIX&reg; time) of the last purchase made. For first-time purchases and visitors that have not made a purchase before, this value is `0`.

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

{{cja-df-post}}

+++

+++**`mobileaction`**

Mobile action. Automatically collected when `trackAction` is called in mobile implementations. Allows for automatic action pathing in the app.

{{cja-df-post}}

+++

+++**`mobileappid`**

Mobile app ID. Stores the application name and version in the following format: `[AppName] [BundleVersion]`

`xdm.application.name` + `xdm.application.version`

{{cja-df-post}}

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

{{cja-df-post}}

+++

+++**`mobilecampaignmedium`**

Marketing medium, such as banner or email. Populated by Mobile App Acquisition.

{{cja-df-post}}

+++

+++**`mobilecampaignname`**

The name of the campaign, also stored in the campaign variable. Populated by Mobile App Acquisition.

{{cja-df-post}}

+++

+++**`mobilecampaignsource`**

Original referrer, such as newsletter or social media network. Populated by Mobile App Acquisition.

{{cja-df-post}}

+++

+++**`mobilecampaignterm`**

Paid keywords or other terms you want to track with this acquisition. Populated by Mobile App Acquisition.

{{cja-df-post}}

+++

+++**`mobiledayofweek`**

Number of the weekday that the app was launched on.

{{cja-df-post}}

+++

+++**`mobiledayssincefirstuse`**

Number of days since the app was run for the first time.

{{cja-df-post}}

+++

+++**`mobiledayssincelastuse`**

Number of days since the app was last run.

{{cja-df-post}}

+++

+++**`mobiledeeplinkid`**

Collected from the context data variable `a.deeplink.id`. Used in acquisition reports as an identifier for mobile acquisition link.

+++

+++**`mobiledevice`**

Mobile device name. On iOS, it is stored as a comma-separated 2-digit string. The first number represents the device generation, and the second number represents the device family.

{{cja-df-post}}

+++

+++**`mobilehourofday`**

Defines the hour of the day that the app was launched. Follows 24-hour numerical format.

{{cja-df-post}}

+++

+++**`mobileinstalldate`**

Mobile install date. Provides the date of the first time that a user opens the mobile app.

{{cja-df-lookback}}

{{cja-df-post}}

+++

+++**`mobilelaunchnumber`**

Increments by one each time the mobile app is launched.

{{cja-df-lookback}}

{{cja-df-post}}

+++

+++**`mobilemessagebuttonname`**

Collected from the context data variable `a.message.button.id`. Used for in-app messaging to identify the button that closed the message.

{{cja-df-post}}

+++

+++**`mobilemessageid`**

In-app Message ID

{{cja-df-post}}

+++

+++**`mobilemessageonline`**

In-app Message Online

{{cja-df-post}}

+++

+++**`mobilemessagepushoptin`**

Collected from the context data variable `a.push.optin`. Set to "true" when the user opts in to push messaging; otherwise the value is "false".

{{cja-df-post}}

+++

+++**`mobilemessagepushpayloadid`**

Collected from the context data variable `a.push.payloadid`. Used in push messaging as the payload identifier.

{{cja-df-post}}

+++

+++**`mobileosversion`**

Mobile Services operating system version

{{cja-df-post}}

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

{{cja-df-post}}

+++

+++**`mobilepushpayloadid`**

Mobile Services Push payload ID

{{cja-df-post}}

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

{{cja-df-post}}

+++

+++**`mobile_id`**
If the user is using a mobile device, the numeric ID of the device.

{{cja-df-lookup}}

+++

+++**`monthly_visitor`**

A flag that determines if the visitor is unique to the current month.

+++

+++**`mvvar1`** - **`mvvar3`**

List variable values. Contains a delimited list of custom values depending on implementation. The `post_mvvar1` - `post_mvvar3` columns replace the original delimiter with `--**--`.

{{cja-df-post}}

+++

+++**`mvvar1_instances`** - **`mvvar3_instances`**

The list variable values that were set on the current hit. Replaces the original delimiter with `--**--`. The `post` columns typically do not contain data.

{{cja-df-post}}

+++

+++**`new_visit`**

A flag that determines if the current hit is a new visit. Set by Adobe after 30 minutes of visit inactivity.

+++

+++**`os`**

A numeric ID that represents the operating system of the visitor. Based on the `user_agent` column.

{{cja-df-lookup}}

+++

+++**`pagename`**

The Page dimension. If the `pagename` variable is empty, Analytics uses `page_url` instead.

{{cja-df-post}}

+++

+++**`pagename_no_url`**

Similar to `pagename`, except it does not fall back to `page_url`. Only the `post` column is available.

{{cja-df-post}}

+++

+++**`page_event`**

The type of hit that is sent in the image request (standard hit, download link, custom link, exit link).

{{cja-df-post}}

{{cja-df-lookup}}

+++

+++**`page_event_var1`**

Only used in link tracking image requests. The URL of the download link, exit link, or custom link clicked.

{{cja-df-post}}

+++

+++**`page_event_var2`**

Only used in link tracking image requests. The custom name (if specified) of the link. Sets the Custom link, Download link, or Exit link depending on the value in `page_event`.

{{cja-df-post}}

+++

+++**`page_type`**

The Pages not found dimension, which is typically used for 404 pages.

{{cja-df-post}}

+++

+++**`page_url`**

**`page_url`**: The URL of the hit. Uses a data type of text.<br>**`post_page_url`**: Stripped for link tracking image requests (`tl()`).

{{cja-df-post}}

+++

+++**`paid_search`**

A flag that determines if the hit matches paid search detection.

+++

+++**`persistent_cookie`**

Used in the Persistent cookie support dimension. Indicates if the visitor supports cookies that are not discarded after each hit.

{{cja-df-post}}

+++

+++**`pointofinterest`**

Mobile Services point of interest name

{{cja-df-post}}

+++

+++**`pointofinterestdistance`**

Mobile Services distance to point of interest center

{{cja-df-post}}

+++

+++**`product_list`**

The `products` page variable. Helps populate several dimensions and metrics, including Category, Product, Units, and Revenue.

{{cja-df-post}}

+++

+++**`prop1`** - **`prop75`**

Custom traffic variables 1-75. Used in Prop dimensions.

{{cja-df-post}}

+++

+++**`purchaseid`**

Unique identifier for a purchase, as set using the `purchaseID` variable. Used by the `duplicate_purchase` column.

`xdm.commerce.order.purchaseID`

{{cja-df-post}}

+++

+++**`quarterly_visitor`**

A flag that determines if the hit is a new quarterly visitor.

+++

+++**`referrer`**

The Referrer dimension. Note that while `referrer` uses a data type of varchar(255), `post_referrer` uses a data type of varchar(244).

{{cja-df-post}}

+++

+++**`ref_domain`**

The Referring domain dimension. Based on the `referrer` column.

+++

+++**`ref_type`**


A numeric ID that represents the type of referral for the hit. Used in the Referrer type dimension.<br>1: Inside your site<br>2: Other web sites<br>3: Search engines<br>4: Hard drive<br>5: USENET<br>6: Typed/Bookmarked (no referrer)<br>7: Email<br>8: No JavaScript<br>9: Social Networks<br>10: Conversational AI tools

+++

+++**`resolution`**

A numeric ID that represents the resolution of the monitor. Used in the Monitor resolution dimension.

{{cja-df-lookup}}

+++

+++**`search_engine`**

A numeric ID that represents the search engine that referred the visitor to your site. Used in Search Engine dimensions.

{{cja-df-post}}

{{cja-df-lookup}}

+++

+++**`search_page_num`**

Used by the All Search Page Rank dimension. Indicates which page of search results that your site appeared on before the user clicked through to your site.

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

{{cja-df-post}}

+++

+++**`s_resolution`**

Raw screen resolution value. Gathered using the JavaScript function `screen.width x screen.height`.

+++

+++**`tnt`**

Used in Adobe Target integrations. Represents all tests currently qualified for. Format is: `TargetCampaignID:TargetRecipeID:TargetType\|Event/Action`.

{{cja-df-post}}

+++

+++**`tnt_action`**

Used in Adobe Target integrations. Represents all tests the hit qualified for.

{{cja-df-post}}

+++

+++**`tnt_instances`**

Used in Adobe Target integrations. Target instances variable.

+++

+++**`transactionid`**

A unique identifier where various data points can be uploaded later through data sources. Collected using the `transactionID` variable.

`xdm.commerce.order.payments[0].transactionID`

{{cja-df-post}}

+++

+++**`truncated_hit`**

A flag indicating that the image request was truncated (a partial hit was received). <br>Y: Hit was truncated; partial hit received <br>N: Hit was not truncated; full hit received

+++

+++**`t_time_info`**

Local time for the visitor. Format is: `M/D/YYYY HH:MM:SS Month (0-11, 0=January) Timezone offset (in minutes)`

{{cja-df-post}}

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

Used in the Server dimension.

{{cja-df-post}}

+++

+++**`va_closer_detail`**

The Last touch detail dimension.

+++

+++**`va_closer_id`**

A numeric ID that identifies the Last touch channel dimension.

{{cja-df-lookup}}

+++

+++**`va_finder_detail`**

The First touch detail dimension.

+++

+++**`va_finder_id`**

A numeric ID that identifies the First touch channel dimension.

{{cja-df-lookup}}

+++

+++**`va_instance_event`**

A flag that identifies Marketing Channel Instances.

+++

+++**`va_new_engagement`**

A flag that identifies Marketing Channel New engagements.

+++

+++**`video`**

The Content streaming media services dimension.

{{cja-df-post}}

+++

+++**`videoad`**

The Ad streaming media services dimension.

{{cja-df-post}}

+++

+++**`videoadinpod`**

The Ad in pod position streaming media services dimension.

{{cja-df-post}}

+++

+++**`videoadlength`**

The Ad length (variable) streaming media services dimension.

{{cja-df-post}}

+++

+++**`videoadname`**

The Ad name (variable) streaming media services dimension.

{{cja-df-post}}

+++

+++**`videoadplayername`**

The Ad player name streaming media services dimension.

{{cja-df-post}}

+++

+++**`videoadpod`**

The Ad pod streaming media services dimension.

{{cja-df-post}}

+++

+++**`videoadvertiser`**

The Advertiser streaming media services dimension.

{{cja-df-post}}

+++

+++**`videoaudioalbum`**

The Album streaming media services dimension.

+++

+++**`videoaudioartist`**

The Artist streaming media services dimension.

+++

+++**`videoaudioauthor`**

The Author streaming media services dimension.

+++

+++**`videoaudiolabel`**

The Label streaming media services dimension.

+++

+++**`videoaudiopublisher`**

The Publisher streaming media services dimension.

+++

+++**`videoaudiostation`**

The Station streaming media services dimension.

+++

+++**`videocampaign`**

The Campaign ID streaming media services dimension.

{{cja-df-post}}

+++

+++**`videochannel`**

The Content channel streaming media services dimension.

{{cja-df-post}}

+++

+++**`videochapter`**

The Chapter streaming media services dimension.

{{cja-df-post}}

+++

+++**`videocontenttype`**

The Content type streaming media services dimension.

{{cja-df-post}}

+++

+++**`videodaypart`**

The Day part streaming media services dimension.

{{cja-df-post}}

+++

+++**`videoepisode`**

The Episode streaming media services dimension.

{{cja-df-post}}

+++

+++**`videofeedtype`**

The Media feed type streaming media services dimension.

{{cja-df-post}}

+++

+++**`videogenre`**

The Genre streaming media services dimension. This dimension allows multiple values in the same hit, delimited by a comma.

{{cja-df-post}}

+++

+++**`videolength`**

The Content length (variable) streaming media services dimension.

{{cja-df-post}}

+++

+++**`videomvpd`**

The MVPD streaming media services dimension.

{{cja-df-post}}

+++

+++**`videoname`**

The Content name (variable) streaming media services dimension.

{{cja-df-post}}

+++

+++**`videonetwork`**

The Network streaming media services dimension.

{{cja-df-post}}

+++

+++**`videopath`**

The Media path streaming media services dimension.

{{cja-df-post}}

+++

+++**`videoplayername`**

The Content player name streaming media services dimension.

{{cja-df-post}}

+++

+++**`videoqoebitrateaverageevar`**

The Average bitrate streaming media services dimension.

{{cja-df-post}}

+++

+++**`videoqoebitratechangecountevar`**

The Bitrate changes streaming media services dimension.

{{cja-df-post}}

+++

+++**`videoqoebuffercountevar`**

The Buffer events streaming media services dimension.

{{cja-df-post}}

+++

+++**`videoqoebuffertimeevar`**

The Total buffer duration streaming media services dimension.

{{cja-df-post}}

+++

+++**`videoqoedroppedframecountevar`**

The Dropped frames streaming media services dimension.

{{cja-df-post}}

+++

+++**`videoqoeerrorcountevar`**

The Errors streaming media services dimension.

+++
{{cja-df-post}}


+++**`videoqoeextneralerrors`**

The External error IDs streaming media services dimension. This dimension allows multiple values in the same hit.

+++

+++**`videoqoeplayersdkerrors`**

The Player SDK error IDs streaming media services dimension. This dimension allows multiple values in the same hit.

{{cja-df-post}}

+++

+++**`videoqoetimetostartevar`**

The Time to start streaming media services dimension.

{{cja-df-post}}

+++

+++**`videoseason`**

The Season streaming media services dimension.

{{cja-df-post}}

+++

+++**`videosegment`**

The Content segment streaming media services imension.

{{cja-df-post}}

+++

+++**`videosessionid`**

The Media session ID streaming media services dimension.

{{cja-df-post}}

+++

+++**`videoshow`**

The Show streaming media services dimension.

{{cja-df-post}}

+++

+++**`videoshowtype`**

The Show type streaming media services dimension.

{{cja-df-post}}

+++

+++**`videostreamtype`**

The Stream type streaming media services dimension.

+++

+++**`visid_high`**

Used with `visid_low` to uniquely identify a visitor.

{{cja-df-post}}

+++

+++**`visid_low`**

Used with `visid_high` to uniquely identify a visitor.

{{cja-df-post}}

+++

+++**`visid_new`**

A flag that determines if the hit contains a newly generated visitor ID.

+++

+++**`visid_timestamp`**

If a visitor ID is newly generated, provides the timestamp in UNIX&reg; time of when the visitor ID was generated.

+++

+++**`visid_type`**

Not for external use; internally used by Adobe for processing optimizations. A numeric ID that represents the method used to identify the visitor.<br>`0`: Custom visitor ID or Unknown/not applicable<br>`1`: IP and user agent fallback <br>`2`: HTTP Mobile Subscriber Header <br>`3`: Legacy cookie value (`s_vi`) <br>`4`: Fallback cookie value (`s_fid`) <br>`5`: Identity Service

{{cja-df-post}}

+++

+++**`visit_keywords`**

The Search keyword dimension. This column uses a non-standard character limit of varchar(244) to accommodate back-end logic used by Adobe. The post-processed column is `**post_keywords**`, not `**post_visit_keywords**`.

{{cja-df-post}}

+++

+++**`visit_num`**

The Visit number dimension. Starts at 1, and increments each time a new visit starts per visitor.

+++

+++**`visit_page_num`**

The Hit depth dimension. Increases by 1 for each hit that the visitor generates. Resets each visit.

+++

+++**`visit_referrer`**

The first referrer of the visit.

+++

+++**`visit_ref_domain`**

Based on the `visit_referrer` column. The first referring domain of the visit.

+++

+++**`visit_ref_type`**

A numeric ID that represents the referrer type of the first referrer of the visit.

{{cja-df-lookup}}

+++

+++**`visit_search_engine`**

A numeric ID that represents the first search engine of the visit.

{{cja-df-lookup}}

+++

+++**`visit_start_pagename`**

Page of the first hit of the visit.

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

Helps populate the Zip code dimension. See also `geo_zip`.

{{cja-df-post}}

+++
