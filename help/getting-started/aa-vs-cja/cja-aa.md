---
title: Customer Journey Analytics feature support
description: Customer Journey Analytics features compared with Adobe Analytics features set.
exl-id: be19aa27-58aa-438d-806c-e27c9a289797
solution: Customer Journey Analytics
feature: CJA Basics
---
# Customer Journey Analytics feature support

The following tables list which features in Adobe Analytics (AA) are supported, partially supported or not supported in Customer Journey Analytics (CJA), and which features of CJA are not supported or available in AA. These lists will change over time as features are added to CJA.

## Fully supported features/components

| Adobe Analytics Feature | Notes on support |
| --- | --- |
| Anomaly Detection | Full Support |
| Attribution IQ | Full Support |
| Calculated Metrics | Full Support; Note that any existing calculated metrics in the traditional Analysis Workspace will not be ported to CJA. |
| Calendar events | Full Support. Calendar events have been implemented as [Annotations](/help/components/annotations/overview.md) in Workspace. |
| CSV download | Full Support |
| Custom Calendars | Full Support |
| Date Comparisons | Full Support | 
| Date Ranges | All date range functionality is supported. |
| Dimensions | Full Support; CJA leverages XDM and supports unlimited dimensions. CJA is not tied to the custom eVars or props of traditional Adobe Analytics. |
| GDPR Deletion | Full Support; note that GDPR is now handled in coordination with [!UICONTROL Adobe Experience Platform]. CJA inherits whatever data changes [!UICONTROL Experience Platform] makes to underlying datasets. |
| Lift and Confidence Reporting | Full Support via [Experimentation panel](/help/analysis-workspace/c-panels/experimentation.md) |
| List Variables/List Props | Full Support; CJA leverages XDM and supports unlimited string arrays which can be used similarly to listVars. |
| Merchandising eVars | Full Support via [binding dimensions and binding metrics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html#binding-dimension) |
| Metrics | Full Support; CJA leverages the Experience Data Model (XDM) and supports unlimited metrics and is not tied to the custom success events of traditional Analytics. Note that some standard metrics have been renamed from traditional Analytics: Visitors = People, Visits = Sessions, Hits = Events. |
| Mobile Scorecard/Dashboards | Full Support |
| Panels | Blank Panel, Attribution Panel, Freeform Panel, and Quick Insights are fully supported. |
| PDF Export | Full Support |
| Project Curation | Full Support |
| Project Linking | Full Support |
| Report Time Processing | Full Support; CJA relies exclusively on Report Time Processing. |
| Reporting API Access | Full Support; Available through the [CJA API](https://www.adobe.io/cja-apis/docs/). |
| Scheduled Reports/Projects | Full Support |
| Segments | Full Support; Now called "Filters" - note that any existing segments in traditional Analysis Workspace will not be ported to CJA. |
| Virtual Report Suites | Full Support; Now called [Data Views](/help/data-views/create-dataview.md). |
| VRS Component Curation | Full Support; Now part of Data Views. |
| Streaming Media Analytics | Media data are available using the Analytics Data Connector as part of the Media Concurrent Viewers panel and the Media Playback Time Spent panel in Workspace. |

{style="table-layout:auto"}

## Supported in a new way

| Feature | Notes |
| --- | --- |
| Audience Publishing (Segment Publishing) | Supported if licensed with Adobe's Customer Data Platform or Journey Optimizer products. [Audience Publishing](/help/components/audiences/audiences-overview.md) sends audiences to Real-time Customer Profile in Experience Platform. |
| Classifications | Now called "Lookup Datasets". Classifications used in Analytics can be imported to the Experience Platform and CJA using the Analytics Classifications Source Connector. Lookup datasets can also be uploaded to AEP directly and made available in CJA. |
| Classification Rule Builder | Supported using [substrings](/help/data-views/component-settings/substring.md) in CJA. Uses string manipulations at report time rather than lookup datasets. |
| Custom Sessionization | Support for all custom sessionization features except mobile background hits. |
| Merchandising variable persistence | Full Support via [binding dimensions and binding metrics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html#binding-dimension) |
| Customer Attributes | Now called "Profile Datasets", they do not get automatically imported from Experience Cloud, but will have to be uploaded to AEP before they are available in CJA. |
| Metric deduplication | Now configured on metrics within Data Views. Metric deduplication happens at the person or session level rather than the Dataset, Data View, or Connection level. |
| Entries, Exits, and Time spent dimensions and metrics | Supported (Entries and Exits are now called Session Starts and Session Ends) and are calculated in a slightly different way. |
| eVar persistence settings | eVars are no longer part of CJA. However, persistence settings are now part of Data Views and are available for all dimensions. Keep in mind that persistence is based on report time processing, not data collection processing. Dimensions set within Data Views are limited to a 90 day max persistence and do not support unlimited persistence. |
| IP Obfuscation | For CJA customers using the Analytics Source Connector to populate data from Adobe Analytics into CJA: IP obfuscation settings applied in Adobe Analytics flow through to your CJA data. You can control these settings in Adobe Analytics as needed.<p>For CJA customers using Adobe Experience Platform Web SDK to populate data into Platform and CJA directly: You can use Data Prep for Data Collection in Platform to configure rules that will obfuscate the IP address based on your company's requirements. |
| New vs. Repeat Session Reporting | Formerly accomplished using the Visit Number dimension. New vs. Repeat sessions are supported [with a 13-month lookback window](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=en#new-repeat). |
| Product Variable | Within the Experience Platform, users can use array of Object type fields within a dataset schema to satisfy this use case. Within CJA, customers have the ability to use any number of product variables and are not restricted to a single variable as in Adobe Analytics. |
| Project Sharing | Project sharing is only supported between users of CJA - there is not project sharing between CJA and the traditional Analysis Workspace. |
| Visualizations | All visualizations are supported except for the Map visualization. |
| Report Builder (Excel plugin) | Supported with a new Office 365 plugin for Excel. |
| User Permissions/Data Access Controls | CJA distinguishes between [Adobe Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/administration/admin-getting-started.html) product admins, product profile admins, and users. Only product admins can Create/update/delete Connections, Projects, Filters, or Calculated Metrics that were created by other users, while product admins and product profile admins can edit Data Views. Addtional user permissions are available for things like creating calculated metrics, filter, or annotations. |
| Processing Rules, VISTA Rules, Marketing Channels Processing Rules | Supported using Adobe Experience Platform Data Prep functionality for both WebSDK based datasets as well as data from the Analytics Data Connector. |

{style="table-layout:auto"}

## Partial Support

| Feature | Notes |
| --- | --- |
| Marketing Channels | Marketing Channels data flows into CJA through the Analytics Source Connector. Marketing Channel rules must still be configured in traditional Adobe Analytics and some rules are not supported. For more details, please see [CJA Marketing Channels documentation](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html#cja-usecases). Additionally, for WebSDK implementations, plugins are available for defining marketing channels client-side. Future support for report-time marketing channels processing rules is planned.|
| Cross-device/cross-channel stitching | Supported for datasets containing identity information directly (also known as "field-based" stitching). Graph-based stitching is not yet supported, but planned. See [Cross-Channel Analytics](/help/cca/overview.md). |
| Bot Filtering | For [Adobe Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html)-based datasets, bot filtering is applied. General bot filtering logic for other datasets is not performed by the [!UICONTROL Experience Platform] or CJA. |
| Device, Browser, Referrer, Technology dimensions | Supported for [Adobe Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html)-based datasets. Please refer to our [documentation on which Analytics variables are supported via ADC](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=en).<p>If you don't use Adobe Source Connector to populate data from Adobe Analytics into CJA, but instead use Experience Platform Web SDK data collection, Device and dimensions based on the Device lookup are not currently supported. Future support is planned. |
| GeoSegmentation dimensions | All GeoSegmentation/geography collected into Adobe Analytics flows into CJA through the [Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html). Implementations that do not use the Analytics Source Connector, such as those that rely on AEP Web SDK for digital data collection, will not have the full slate of geographical lookups performed automatically: Country and state are supported globally, city and zip are not.|
| Panels | Blank Panel, Attribution Panel, Freeform Panel, and Quick Insights are fully supported. The Segment Comparison and Analytics for Target (A4T) panels are not supported. |
| Processing Rules | For Analytics Source Connector-based datasets, processing rules are still applied. [Data prep capabilities in Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html) can also be used as a replacement for processing rules for data that is going directly to Platform. |
| A4T | Partial support is provided through fields in the [Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html). Support for A4T friendly names on Target Activities and Experiences is planned.|

{style="table-layout:auto"}

## Not currently supported, but planned

| Feature | Notes |
| --- | --- |
| Alerts | Support is planned. |
| Contribution Analysis | Support is planned. |
| Data Warehouse Reporting (100% row export) | Support is planned from the Analysis Workspace interface. Adobe Experience Platform [[!UICONTROL Query Service]](https://experienceleague.adobe.com/docs/experience-platform/query/home.html) also provides an interface for these use cases in CJA. |
| ID Stitching via Device Graph | Support is planned. |
| Project Templates | Support is planned. |
| Real-Time Reporting | Support is planned. |
| Segment IQ | Support is planned. |
| Currency Conversion | Support is planned. |
| Data Feeds | Support is planned via AEP destinations. |
| Transaction ID Data Sources | Support is planned. |
| Migrating Projects/Filters/Calculated Metrics from AA to CJA | Support is planned. |
| Summary level data sources | Support is planned. |

{style="table-layout:auto"}

## Support not yet planned

| Feature | Notes |
| --- | --- |
| Activity Map | Support is not yet planned. |
| Advertising Cloud | Support is not yet planned. |
| Summary Data Sources | Support is not yet planned. |

{style="table-layout:auto"}

## Will never be supported

* People metric using Cross-Device Coop
* Reports & Analytics Dashboards
* Reports & Analytics Bookmarks
* Reports & Analytics Targets
* Mobile Services

## Features not available in Adobe Analytics

The following table lists wich features are available in Customer Journey Analytics (CJA), and which are not supported or available in Adobe Analytics (AA).

| Feature | More Details |
| --- | --- |
| Any kind of data | CJA is combined with Experience Platform's ability to hold all kinds of data schemas and types. Using [Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html), data can be uniformly represented and organized, ready for combination and exploration. AA is predominantly focused on web and mobile analytics data with some capabilities to [import data](https://experienceleague.adobe.com/docs/analytics/import/home.html). |
| Unlimited Customer Dimensions & Metrics | CJA dimensions are unlimited; values can be numeric, text, objects, lists, or mixtures of all. Dimensions can be nested or hierarchical. AA supports up to a maximum of 75 props and 250 eVars. This removes the current measurement limitations using dimensions and events. |
| Unlimited cardinality / unique values | CJA supports unlimited unique values or dimension items that can be reported on within a single dimension. AA is limited to 500K unique values. This removes reporting and analysis limitations currently existing with large scale AA implementation. |
| Report Time Transformations | Report Time Transformations (better known as Data Views) in CJA allow you to further interpret data from a connection. You can alter or remove data without re-implementation; use substrings to manipulate dimensions; create metrics from any value; filter sub-events. And this can all be done non-destructively. Adobe Analytivs provides limited capabilities through virtual report suites and sessionization. |
| Experimentation Analysis | CJA can evaluate the lift and confidence of any experiment from any data source defined as part of a connection. This allows you to understand cause and effect relationships between customer interactions spanning any channel. AA is limited to experimentation analytics through the Analytics for Target (A4T) integration. |
| Cross-Device Analytics | CJA supports the seamless combination of device specific data sets from unauthenticated and authenticated sessions. You can also backfill historical data to known devices. In AA this is limited to a single report suite and the use of a device graph. |
| SQL Access | Using the Data Distiller option, CJA can remove the limitations of data collected or Adobe's backend processing. You can modify your data with SQL, create new values and datasets unique to your business and continue to explore. AA does not support any kind of SQL access to its data. |
| Enhanced Security and Privacy Options | CJA is HIPAA Ready and offers additional security options for regulation compliance. AA is not HIPAA ready. |

{style="table-layout:auto"}
