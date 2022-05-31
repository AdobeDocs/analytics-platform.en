---
title: Customer Journey Analytics feature support
description: Customer Journey Analytics features compared with Adobe Analytics features set.
exl-id: be19aa27-58aa-438d-806c-e27c9a289797
solution: Customer Journey Analytics
feature: CJA Basics
---
# Customer Journey Analytics feature support

The following tables list which features in Adobe Analytics are supported, partially supported or not supported in Customer Journey Analytics (CJA). These lists will change over time as features are added to CJA.

## Fully supported features/components

| Adobe Analytics Feature | Notes on support |
| --- | --- |
| Anomaly Detection | Full Support |
| Attribution IQ | Full Support |
| Calculated Metrics | Full Support; Note that any existing calculated metrics in the traditional Analysis Workspace will not be ported to CJA. |
| Calendar events | Full Support. Calendar events have been implemented as [Annotations](/help/components/annotations/overview.md) in Workspace. |
| Classification Rule Builder | Full support. Called [substrings](/help/data-views/component-settings/substring.md) in CJA. Uses string manipulations at report time rather than lookup datasets. |
| Cross-device/cross-channel stitching | Full Support; See [Cross-Channel Analytics](/help/connections/cca/overview.md). |
| CSV download | Full Support |
| Custom Calendars | Full Support |
| Date Comparisons | Full Support | 
| Date Ranges | All date range functionality is supported. |
| Daylight Savings Time | Full Support |
| Dimensions | Full Support; CJA leverages XDM and supports unlimited dimensions. CJA is not tied to the custom eVars or props of traditional Adobe Analytics. |
| GDPR Deletion | Full Support; note that GDPR is now handled in coordination with [!UICONTROL Adobe Experience Platform]. CJA inherits whatever data changes [!UICONTROL Experience Platform] makes to underlying datasets. |
| List Variables/List Props | Full Support; CJA leverages XDM and supports unlimited string arrays which can be used similarly to listVars. |
| Merchandising variable persistence | Full Support via [binding dimensions and binding metrics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html#binding-dimension) (January 2022) |
| Merchandising eVars | Full Support via [binding dimensions and binding metrics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html#binding-dimension) (January 2022) |
| Metrics | Full Support; CJA leverages the Experience Data Model (XDM) and supports unlimited metrics and is not tied to the custom success events of traditional Analytics. Note that some standard metrics have been renamed from traditional Analytics: Visitors = People, Visits = Sessions, Hits = Events. |
| Metric deduplication | Full Support |
| Mobile Scorecard/Dashboards | Full Support |
| Panels | Blank Panel, Attribution Panel, Freeform Panel, and Quick Insights are fully supported. |
| PDF Export | Full Support |
| Project Curation | Full Support |
| Project Linking | Full Support |
| Report Builder (Excel plugin) | Full Support |
| Report Time Processing | Full Support; CJA relies exclusively on Report Time Processing. |
| Reporting API Access | Full Support; Available through the [CJA API](https://www.adobe.io/cja-apis/docs/). |
| Scheduled Reports/Projects | Full Support |
| Segments | Full Support; Now called "Filters" - note that any existing segments in traditional Analysis Workspace will not be ported to CJA. |
| User Permissions/Data Access Controls | Full Support; CJA distinguishes between [Adobe Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/administration/admin-getting-started.html) product admins and users. Only product admins can <ul><li>Create/update/delete Connections or Data Views</li><li>Update/delete projects, filters, or calc metrics that were created by other users, and</li><li>Share a Workspace project to all users.</li></ul> |
| Virtual Report Suites | Full Support; Now called [Data Views](/help/data-views/create-dataview.md). |
| VRS Component Curation | Full Support; Now part of Data Views. |

## Supported with caveats

| Feature | Notes |
| --- | --- |
| A4T | Support is provided through fields in the [Adobe Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html). |
| Classifications | Now called "Lookup Datasets". Classifications used in Analytics can be imported to the Experience Platform and CJA using the Analytics Classifications Data Connector. Lookup datasets can also be uploaded to AEP directly and made available in CJA. |
| Custom Sessionization | Support for all custom sessionization features other than mobile background hits. |
| Customer Attributes | Now called "Profile Datasets", they do not get automatically imported from Experience Cloud, but will have to be uploaded to AEP before they are available in CJA. |
| [!UICONTROL Device], [!UICONTROL Browser], [!UICONTROL Referrer], [!UICONTROL Technology] dimensions | These dimensions are automatically included when an AEP dataset includes specific XDM schema fields and conforms to the XDM Experience Event class. Please refer to our [documentation on which Analytics variables are supported via Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html). For CJA customers who are not using the Source Connector to populate data from Adobe Analytics into CJA, but are instead using AEP Web SDK data collection, [!UICONTROL Device] and dimensions based on the Device lookup are not currently supported, but will be in the near future. |
| Entries, Exits, and Time spent dimensions and metrics | Supported (Entries and Exits are now called Session Starts and Session Ends) and are calculated in a slightly different way. |
| eVar persistence settings | eVars are no longer part of CJA. However, persistence settings are now part of Data Views and are available for all dimensions. Keep in mind that persistence is based on report time processing, not data collection processing. Dimensions set within Data Views are limited to a 90 day max persistence and do not support unlimited persistence. |
| GeoSegmentation dimensions | All GeoSegmentation/geography collected into Adobe Analytics flows into CJA through the [Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html). Implementations that do not use the Analytics Source Connector, such as those that rely on AEP Web SDK for digital data collection, will not have the full slate of geographical lookups performed automatically: Country and U.S. state are supported, city and zip are not. There is limited or no support currently for states/regions outside the U.S.. |
| Marketing Channels | Marketing Channels data flows into CJA through the Analytics Data Connector. Marketing Channel rules must still be configured in traditional Adobe Analytics. Some rules are not supported. For more details, please see [CJA Marketing Channels documentation](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html#cja-usecases). |
| Product Variable | Within the Experience Platform, users can use array of Object type fields within a dataset schema to satisfy this use case. Within CJA, customers have the ability to use any number of product variables and are not restricted to a single variable as in Adobe Analytics. |
| Project Sharing | Project sharing is only supported between users of CJA - there is not project sharing between CJA and the traditional Analysis Workspace. |
| Visualizations | All visualizations are supported except for the Map visualization. |

## Partial Support

| Feature | Notes |
| --- | --- |
| Bot Filtering | For [Adobe Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html)-based datasets, bot filtering is applied. General bot filtering logic for other datasets is not performed by the [!UICONTROL Experience Platform] or CJA. |
| Media Analytics | Media data is available as part of the Analytics Source Connector. |
| Panels | Blank Panel, Attribution Panel, Freeform Panel, and Quick Insights are fully supported. The Segment Comparison, Analytics for Target (A4T), and Media Concurrent Viewers panels are not supported. |
| Processing Rules | For Analytics Data Connector-based datasets, processing rules are still applied. [Data prep capabilities in Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html) can also be used as a replacement for processing rules for data that is going directly to Platform. |

## Not currently supported, but planned

| Feature | Notes |
| --- | --- |
| Alerts | Support is planned. |
| Contribution Analysis | Support is planned. |
| Data Warehouse Reporting (100% row export) | Support is planned from the Analysis Workspace interface. Adobe Experience Platform [[!UICONTROL Query Service]](https://experienceleague.adobe.com/docs/experience-platform/query/home.html) also provides an interface for these use cases in CJA. |
| ID Stitching via Device Graph | Support is planned. |
| Lift and Confidence Reporting | Support is planned. |
| Processing Rules, VISTA Rules, Marketing Channels Processing Rules | Support planned, but will work at query-time rather than during data collection for more flexible and retroactive and non-destructive data manipulations. |
| Project Templates | Support is planned. |
| Real-Time Reporting | Support is planned. |
| Segment IQ | Support is planned. |
| Segment Publishing (sending segments from Workspace to the Experience Cloud) | Support is planned. Will be called "Audience Publishing" in CJA. |
| New vs. Repeat Session Reporting | Support is planned with some caveats. |

## Support not yet planned

| Feature | Notes |
| --- | --- |
| Activity Map | Support is not yet planned. |
| Advertising Cloud | Support is not yet planned. |
| Currency Conversion | Support is not yet planned. |
| Data Feeds | Support is not yet planned. |
| Summary Data Sources | Support is not yet planned. |
| Transaction ID Data Sources | Support is not yet planned. |

## Will never be supported

* People metric using Cross-Device Coop
* Reports & Analytics Dashboards
* Reports & Analytics Bookmarks
* Reports & Analytics Targets
* Mobile Services
