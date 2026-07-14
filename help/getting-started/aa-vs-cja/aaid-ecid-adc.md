---
title: AAID, ECID, AACUSTOMID and the Analytics source connector
description: Learn how the Analytics source connector deals with Adobe Analytics identity fields.
exl-id: c983cf50-0b6c-4daf-86a8-bcd6c01628f7
feature: Basics
role: User
autotag-review: '2026-05-19T07:16:36.730Z'
TQID: 'https://experienceleague.adobe.com/8ijMa5NbkCx0H48qSZkYrgTDRaVCSBmO9twZvWFJ83o'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
    internal-label: Administration
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
    internal-label: Dimensions
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
---
# AAID, ECID, AACUSTOMID and the Analytics source connector

Adobe Analytics data contains multiple identity fields. Three important identity fields are given special treatment by the [Analytics source connector](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html): AAID, ECID, AACUSTOMID.

## AAID

Adobe Analytics ID (AAID) is the primary device identifier in Adobe Analytics and is guaranteed to exist on every event passed through the Analytics source connector. AAID is sometimes referred to as the "Legacy Analytics ID" or `s_vi` cookie id. However, an AAID is created even if the `s_vi` cookie is not present. AAID is represented by the `post_visid_high/post_visid_low` columns in [Adobe Analytics data feeds](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html#columns%2C-descriptions%2C-and-data-types). 

In the Analytics source connector, AAID is transformed to `HEX(post_visid_high) + "-" + HEX(post_visid_low)`. The AAID field on a given event contains a single identity which may be one of several different types as described in [Order of Operations for Analytics IDs](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/analytics-order-of-operations.html). (Within an entire report suite, AAID may contain a mix of types across events. The type for each event is indicated in the `post_visid_type` column in Analytics data feeds.) See also: [Data column reference](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html).

## ECID

ECID (Experience Cloud ID), also sometimes referred to as MCID (Marketing Cloud ID), is a separate device identifier field which is populated in Adobe Analytics when Analytics is implemented using the [Visitor ID Service](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-analytics.html) (AppMeasurement) or the Experience Platform Identity Service (Web SDK). ECID is represented by the `mcvisid` column in Adobe Analytics data feeds. 

If an ECID exists on an event, AAID may be based on ECID depending on whether the Analytics [grace period](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/grace-period.html) is configured. See also: [Analytics and Experience Cloud ID Requests](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/legacy-analytics.html).

## AACUSTOMID

AACUSTOMID is a separate identifier field which is populated in Adobe Analytics based on use of the `s.VisitorID` variable in the Analytics implementation. AACUSTOMID is represented by the `cust_visid` column in Adobe Analytics data feeds. If AACUSTOMID is present, AAID will be based on AACUSTOMID. (AACUSTOMID trumps all other identifiers as defined by the order of operations mentioned above.) 

## How the Analytics source connector treats these identities

The Analytics source connector passes these identities through to Adobe Experience Platform in XDM form as:

* `endUserIDs._experience.aaid.id`
* `endUserIDs._experience.mcid.id`
* `endUserIDs._experience.aacustomid.id`

These fields are not marked as identities. Rather, the same identities are copied into XDM's **_identityMap_** as key value pairs as follows:

* `{ "key": "AAID", "value": [ { "id": "<identity>", "primary": <true or false> } ] }`
* `{ "key": "ECID", "value": [ { "id": "<identity>", "primary": <true or false> } ] }`
* `{ "key": "AACUSTOMID", "value": [ { "id": "<identity>", "primary": false } ] }`

The items in <> brackets represent places where actual values would appear.

Within identityMap:

* If ECID is present it is marked as the primary identity for the event. Note that in this case AAID may be based on ECID per the discussion above.
Otherwise, AAID is marked as the primary identity for the event.
* AACUSTOMID is never marked as the Primary ID for the event. However, if AACUSTOMID is present, then AAID is based on AACUSTOMID as per the discussion above.

When the identity or identities are copied into `identityMap`, `endUserIDs._experience.mcid.namespace.code` is also set on the same event:

* If AAID is present, `endUserIDs._experience.aaid.namespace.code` is set to "AAID".
* If ECID is present, `endUserIDs._experience.mcid.namespace.code` is set to "ECID".
* If AACUSTOMID is present, `endUserIDs._experience.aacustomid.namespace.code` is set to "AACUSTOMID".

## Customer Journey Analytics and Primary ID

As far as Customer Journey Analytics is concerned, the definition of Primary ID is only important if you decide to use the Primary ID as the Person ID. Doing so is not mandatory, however. You may choose some other identity column as the Person ID.
