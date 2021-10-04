---
title: Customer Journey Analytics feature support
description: Customer Journey Analytics features compared with Adobe Analytics features set.
exl-id: be19aa27-58aa-438d-806c-e27c9a289797
---
# Customer Journey Analytics feature support

The following tables list which features in Adobe Analytics are supported, partially supported or not supported in Customer Journey Analytics (CJA). These lists will change over time as features are added to CJA.

## Fully supported features/components

| Adobe Analytics Feature | Notes on support |
| --- | --- |
| Anomaly Detection | Full Support |
| Attribution IQ | Full Support |
| Calculated Metrics | Full Support; Note that any existing calculated metrics in the traditional Analysis Workspace will not be ported to CJA. |
| Cross-device/cross-channel stitching | Full Support; See [Cross-Channel Analytics](/help/connections/cca/overview.md). |
| Custom Calendars | Full Support |
| Date Comparisons | Full Support | 
| Date Ranges | All date range functionality is supported. |
| Daylight Savings Time | Full Support |
| Dimensions | Full Support; CJA leverages XDM and supports unlimited dimensions. CJA is not tied to the custom eVars or props of traditional Adobe Analytics. |
| Out-of-the-box Analysis Workspace dimensions (e.g. Browser Type, Referrer Type, Operating System etc.) | CJA provides these dimensions natively as long as the base XDM fields (such as user agent or device ID) are populated. For customers using the Analytics Data Connector (ADC), some of these dimensions are available, but not all. Please refer to our [documentation on which Analytics variables are supported via ADC](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/analytics_mapping_fields.md). |
| GDPR Deletion | Full Support; note that GDPR is now handled in coordination with [!UICONTROL Adobe Experience Platform]. CJA inherits whatever data changes [!UICONTROL Experience Platform] makes to underlying datasets. |
| List Variables/List Props | Full Support; CJA leverages XDM and supports unlimited string arrays which can be used similarly to listVars. |
| Metrics | Full Support; CJA leverages the Experience Data Model (XDM) and supports unlimited metrics and is not tied to the custom success events of traditional Analytics. Note that some standard metrics have been renamed from traditional Analytics: Visitors = People, Visits = Sessions, Hits = Events. |
| Metric deduplication | Full Support |
| PDF Export | Full Support |
| Project Curation | Full Support |
| Project Linking | Full Support |
| Report Time Processing | Full Support; CJA relies exclusively on Report Time Processing. |
| Reporting API Access | Full Support; Available through the [CJA API](https://www.adobe.io/cja-apis/docs/). |
| Scheduled Reports/Projects | Full Support |
| Segments | Full Support; Now called "Filters" - note that any existing segments in traditional Analysis Workspace will not be ported to CJA. |
| User Permissions/Data Access Controls | Full Support; CJA distinguishes between [Adobe Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/administration/admin-getting-started.html?lang=en) product admins and users. Only product admins can <ul><li>Create/update/delete Connections or Data Views</li><li>Update/delete projects, filters, or calc metrics that were created by other users, and</li><li>Share a Workspace project to all users.</li></ul> |
| Virtual Report Suites | Full Support; Now called [Data Views](/help/data-views/create-dataview.md). |
| VRS Component Curation | Full Support; Now part of Data Views. |

## Supported with caveats

| Feature | Notes |
| --- | --- |
| A4T | Support is provided through fields in the [Adobe Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=en). |
| Classifications | Now called "Lookup Datasets". Classifications used in Analytics can be imported to the Experience Platform and CJA using the Analytics Classifications Data Connector. Lookup datasets can also be uploaded to AEP directly and made available in CJA. |
| Custom Sessionization | Support for all custom sessionization features other than mobile background hits. |
| Customer Attributes | Now called "Profile Datasets", they do not get automatically imported from Experience Cloud, but will have to be uploaded to AEP before they are available in CJA. |
| Device, Browser, Technology dimensions | These dimensions are automatically included when an AEP dataset includes specific XDM schema fields and conforms to the XDM Experience Event class. |
| Entries, Exits, and Time spent dimensions and metrics | Supported (Entries and Exits are now called Session Starts and Session Ends) and are calculated in a slightly different way. |
| eVar persistence settings | eVars are no longer part of CJA. However, persistence settings are now part of Data Views and are available for all dimensions. Keep in mind that persistence is based on report time processing, not data collection processing. Dimensions set within Data Views are limited to a 90 day max persistence and do not support unlimited persistence. |
| GeoSegmentation dimensions | All GeoSegmentation/geography collected into Adobe Analytics flows into CJA through the Analytics Data Connector. Implementations that do not use the Analytics Data Connector, such as those that rely on AEP Web SDK for digital data collection, will not have the full slate of geographical lookups performed automatically (country and state are supported, city and zip are not). |
| Marketing Channels | Marketing Channels data flows into CJA through the Analytics Data Connector. Marketing Channel rules must still be configured in traditional Adobe Analytics. Some rules are not supported. For more details, please see [CJA Marketing Channels documentation](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=en#cja-usecases). |
| Product Variable | Within the Experience Platform, users can use array of Object type fields within a dataset schema to satisfy this use case. Within CJA, customers have the ability to use any number of product variables and are not restricted to a single variables as in Adobe Analytics. |
| Project Sharing | Project sharing is only supported between users of CJA - there is not project sharing between CJA and the traditional Analysis Workspace. |
| Visualizations | All visualizations are supported except for the Map visualization. |

## Partial Support

| Feature | Notes |
| --- | --- |
| Bot Filtering | For Analytics Data Connector (ADC)-based datasets, bot filtering is applied. General bot filtering logic for other datasets is not performed by the [!UICONTROL Experience Platform] or CJA. |
| Media Analytics | Media data is available as part of the Analytics Data Connector. |
| Merchandising eVars | The behavior of Merchandising eVars can be achieved using dimensions within an Object Array given a merchandising eVar is not set to use persistence. Currently, merchandising dimension persistence is not available. |
| Panels | Blank Panel, Attribution Panel, Freeform Panel, and Quick Insights are fully supported. The Segment Comparison, Analytics for Target (A4T), and Media Concurrent Viewers panels are not supported. |
| Processing Rules | For Analytics Data Connector-based datasets, processing rules are still applied. [Data prep capabilities in Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=en) can also be used as a replacement for processing rules for data that is going directly to Platform. |

## Not currently supported, but planned

| Feature | Notes |
| --- | --- |
| Alerts | Support is planned. |
| Contribution Analysis | Support is planned. |
| CSV download | Support is planned. |
| Data Warehouse Reporting (100% row export) | Support is planned from the Analysis Workspace interface. [!UICONTROL Experience Platform Query Service] also provides an interface for these use cases in CJA. |
| ID Stitching via Device Graph | Support is planned. |
| Merchandising variable persistence | Support is planned. |
| Real-Time Reporting | Support is planned. |
| Report Builder (Excel plugin) | Support is planned. |
| Segment IQ | Support is planned. |
| Segment Publishing (sending segments from Workspace to the Experience Cloud) | Support is planned. |

## Support not yet planned

| Feature | Notes |
| --- | --- |
| Activity Map | Support is not yet planned. |
| Advertising Cloud | Support is not yet planned. |
| Classification Rule Builder | Support is not yet planned. |
| Data Feeds | Support is not yet planned. |
| Summary Data Sources | Support is not yet planned. |

## Will never be supported

* People metric using Cross-Device Coop
* Reports & Analytics Dashboards
* Reports & Analytics Bookmarks
* Reports & Analytics Targets
* Reports & Analytics Calendar Events
* Mobile Services
