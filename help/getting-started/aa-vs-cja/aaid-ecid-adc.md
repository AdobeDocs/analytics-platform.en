# AAID, ECID, and the Analytics Source Connector

Adobe Analytics data contains multiple identity fields. Three important identity fields are given special treatment by the [Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en):

* **AAID**. AAID is the primary device identifier in Adobe Analytics and is guaranteed to exist on every event passed through the Analytics Source Connector. AAID is sometimes referred to as the "Legacy Analytics ID" or "s\_vi cookie id", although an AAID is created even if the s\_vi cookie is not present. AAID is represented by the **_post\_visid\_high/post\_visid\_low_** columns in [Adobe Analytics data feeds](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=en#columns%2C-descriptions%2C-and-data-types). The AAID field on a given event contains a single identity which may be one of several different types as described in [Order of Operations for Analytics IDs](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/analytics-order-of-operations.html?lang=en%5B%5D). (Within an entire report suite, AAID may contain a mix of types across events. The type for each hit is indicated in the **_[post\_]visid\_type_** column in Analytics data feeds.) See also: [Data column reference](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=en).
* **ECID**. ECID (Experience Cloud ID), also sometimes referred to as MCID (Marketing Cloud ID), is a separate device identifier field which is populated in Adobe Analytics when Adobe Analytics is implemented using the [Experience Cloud Identity Service](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-analytics.html?lang=en). ECID is represented by the mcvisid column in Adobe Analytics data feeds. If an ECID exists on an event, AAID may be based on ECID depending on whether the Analytics [grace period](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/grace-period.html?lang=en) is configured. See also: [Analytics and Experience Cloud ID Requests](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/legacy-analytics.html?lang=en).
* **AACUSTOMID**. AACUSTOMID is a separate identifier field which is populated in Adobe Analytics based on use of the s.VisitorID variable in the Analytics implementation. AACUSTOMID is represented by the **_cust_visid_** column in Adobe Analytics data feeds. If AACUSTOMID is present, AAID will be based on AACUSTOMID. (AACUSTOMID trumps all other identifiers as defined by the order of operations mentioned above.) 

The Analytics Source Connector passes through all three of these identities to AEP as:

* endUserIDs.\_experience.aaid.id
* endUserIDs.\_experience.mcid.id
* endUserIDs.\_experience.aacustomid.id

These fields are not marked as identities. Rather, the same identities are copied into XDM's identityMap as key value pairs as follows:

* { “key”: “AAID”, “value”: [ { “id”: “_\<identity\>_”, “primary”: _\<true or false\>_} ] }
* { “key”: “ECID”, “value”: [ { “id”: “_\<identity\>_”, “primary”: _\<true or false\>_ } ] }
* { “key”: “AACUSTOMID”, “value”: [ { “id”: “_\<identity\>_”, “primary”: **false** } ] }

Within identityMap:

* If ECID is present it is marked as the primary identity for the event. Note that in this case AAID may be based on ECID per the discussion above.
Otherwise, AAID is marked as the primary identity for the event.
* AACUSTOMID is never marked as the Primary ID for the event. However, if AACUSTOMID is present then AAID is based on AACUSTOMID as per the discussion above.

As far as CJA is concerned, the definition of Primary ID is only important if the end user decides to use the Primary ID as the Person ID. Doing so is not mandatory, however. The user can choose some other identity column as the Person ID.

