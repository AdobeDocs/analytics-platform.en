---
title: Customer Journey Analytics feature support
description: Customer Journey Analytics features compared with Adobe Analytics features set.
---

# Customer Journey Analytics feature support

The following tables list which features in Adobe Analytics are supported, partially supported or not supported in Customer Journey Analytics (CJA). These lists will change over time as features are added to CJA.

## Fully supported features/components

|Feature|Notes|
|---|---|
|Metrics|CJA leverages the Experience Data Model (XDM) and supports unlimited metrics and is not tied to the custom success events of traditional Analytics. Note that some standard metrics have been renamed: Visitors = People, Visits = Sessions, Hits = Events.|
|Dimensions|CJA leverages XDM and supports unlimited dimensions and is not tied to the custom success events of traditional Analytics.|
|List Variables/List Props|CJA leverages XDM and supports unlimited list variables|
|Date Ranges|Custom Calendar support is planned.|
|Calculated Metrics|Note that any existing calc metrics in the traditional Analysis Workspace will not be ported to CJA.|
|Segments|Now called "Filters" - note that any existing segments in traditional Analysis Workspace will not be ported to CJA.|
|Attribution IQ|Full Support|
|Project Curation|Full Support|
|Project Linking|Full Support|
|Date Comparisons|Full Support|
|Virtual Report Suites|Now called "Data Views".|
|VRS Component Curation|Now part of Data Views.|
|Report Time Processing|CJA relies on Report Time Processing exclusively.|
|GDPR Deletion|Note that GDPR is now handled via AEP - CJA inherits whatever data changes AEP makes to underlying datasets.|


## Supported with caveats

|Feature|Notes|
|---|---|
|Product Variable|The product variable is available only for ADC (Analytics Data Connector) datasets. For non-ADC datasets, the product variable (or its functionality) is not available unless customers put the product information in the identical schema location as ADC.|
|Visualizations|All visualizations are supported except for the Map visualization.|
|AAM Audiences|If customers are using Analytics Data Connector datasets, this data will be part of the ADC data.|
|Project Sharing|Project sharing is only supported between users of CJA - there is not project sharing between CJA and the traditional Analysis Workspace.|
|Custom Sessionization|Support for all custom sessionization features except mobile background hits.|
|eVar persistence settings|eVars are no longer part of CJA. However, persistence settings are now part of Data Views and are available for all dimensions. Keep in mind that persistence is based on report time processing, not data collection processing. This means all persistence will be based on the reporting date range rather than the entirety of the data.|
|Classifications|Now called "Lookup Datasets", they do not get automatically imported from traditional Analytics. They will have to be uploaded to AEP before they're available in CJA.|
|Customer Attributes|Now called "Profile Datasets", they do not get automatically imported from Experience Cloud, but will have to be uploaded to AEP before they're available in CJA.|

## Partial Support

|Feature|Notes|
|---|---|
|Out-of-the-box Analysis Workspace dimensions (e.g. Browser Type, Referrer Type, Marketing Channels, Visit Number etc.)|CJA does not provide these dimensions natively. For customers using the Analytics Data Connector (ADC), some of these dimensions are available, but not all. Please refer to our [documentation on which Analytics variables are supported via ADC](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/analytics_mapping_fields.md).|
|Panels|Blank Panel, Attribution Panel, and Freeform Panel are fully supported. Segment Comparison is not supported.|
|Merchandising eVars|Merchandising eVars will only work with ADC-based datasets unless they strictly conform to the same XDM schema (similar to the product list limitations above).|
|Bot Filtering|Needs to be planned by AEP for more general support - for ADC-based datasets, bot filtering is still applied.|
|Processing Rules|Needs to be planned by AEP for more general support - for ADC-based datasets, processing rules are still applied.|
|ID Stitching via Query Service|Currently, there is no way to automate this. Customers are limited to "one-time" stitches of the data.|

## Not currently supported, but planned

|Feature|Notes|
|---|---|
|Anomaly Detection|Support is planned.|
|Contribution Analysis|Support is planned.|
|Segment IQ|Support is planned.|
|Segment Publishing (sending segments from Workspace to the Experience Cloud)|Support is planned.|
|User Permissions/Data Access Controls|All users in CJA have the same access controls - this means all users have access to all connections, data views, etc. Basically all users are admin level users in CJA. Support is planned for 2020.|
|CSV download|Support is planned.|
|Scheduled Reports/Projects|Support is planned.|
|Alerts|Support is planned.|
|Custom Calendars|Support is planned.|
|Marketing Channels|Needs to be planned by AEP for more general support - even for datasets from ADC this is not supported.|
|PDF Export|Support is planned.|
|Reporting API Access|Support is planned - will only be available with API 2.0.|
|ID Stitching via Device Graph|Support is planned.|

## Support not yet planned

|Feature|Notes|
|---|---|
|A4T|Support is not yet planned.|
|Video Analytics|Support is not yet planned.|
|Advertising Cloud|Support is not yet planned.|
|Report Builder (Excel plugin)|Support is not yet planned.|
|Activity Map|Support is not yet planned.|
|Classification Rule Builder|Support is not currently planned.|
|Summary Data Sources|Support is not yet planned.|
|Real-Time Reporting|Support is not yet planned.|

## Will never be supported

|Feature|Notes|
|---|---|
|People metric||
|Reports & Analytics Dashboards||
|Reports & Analytics Bookmarks||
|Reports & Analytics Targets||
|Reports & Analytics Calendar Events||
|Ad Hoc Analysis||
|Data Warehouse Reporting|Adobe Experience Platform Query Service will be the new interface for these use cases in CJA.|
|Mobile Services||
|Data Feeds||

