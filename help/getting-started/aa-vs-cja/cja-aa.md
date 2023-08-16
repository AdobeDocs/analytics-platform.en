---
title: Customer Journey Analytics feature support
description: Customer Journey Analytics features compared with Adobe Analytics features set.
exl-id: be19aa27-58aa-438d-806c-e27c9a289797
solution: Customer Journey Analytics
feature: Basics
---
# Adobe Customer Journey Analytics feature support

The following tables list which features in Adobe Analytics are supported, partially supported or not supported in Customer Journey Analytics, and which features of Customer Journey Analytics are not supported or available in Adobe Analytics. These lists will change over time as features are added to Customer Journey Analytics.

## Fully supported features/components {#full-support}

| Adobe Analytics Feature | Notes on support |
| --- | --- |
| Anomaly Detection | Full Support |
| Attribution IQ | Full Support |
| Calculated Metrics | Full Support. Any existing calculated metric in the traditional Analysis Workspace is not ported to Customer Journey Analytics. |
| Calendar events | Full Support. Calendar events have been implemented as [Annotations](/help/components/annotations/overview.md) in Workspace. |
| CSV download | Full Support |
| Custom Calendars | Full Support |
| Date Comparisons | Full Support | 
| Date Ranges | All date range functionality is supported. |
| Dimensions | Full Support. Customer Journey Analytics uses XDM and supports unlimited dimensions. Customer Journey Analytics is not tied to the custom eVars or props of traditional Adobe Analytics. |
| GDPR Deletion | Full Support; note that GDPR is now handled in coordination with [!UICONTROL Adobe Experience Platform]. Customer Journey Analytics inherits whatever data changes [!UICONTROL Experience Platform] makes to underlying datasets. |
| Lift and Confidence Reporting | Full Support via [Experimentation panel](/help/analysis-workspace/c-panels/experimentation.md) |
| List Variables/List Props | Full Support. Customer Journey Analytics uses XDM and supports unlimited string arrays which can be used similarly to listVars. |
| Merchandising eVars | Full Support via [binding dimensions and binding metrics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html#binding-dimension) |
| Metrics | Full Support; Customer Journey Analytics uses the Experience Data Model (XDM) and supports unlimited metrics and is not tied to the custom success events of Adobe Analytics. Some standard metrics have been renamed from Adobe Analytics: Visitors = People, Visits = Sessions, Hits = Events. |
| Mobile Scorecard/Dashboards | Full Support |
| Panels | Blank Panel, Attribution Panel, Freeform Panel, and Quick Insights are fully supported. |
| PDF Export | Full Support |
| Project Curation | Full Support |
| Project Linking | Full Support |
| Report Time Processing | Full Support; Customer Journey Analytics relies exclusively on Report Time Processing. |
| Reporting API Access | Full Support; Available through the [Customer Journey Analytics API](https://developer.adobe.com/cja-apis/docs/). |
| Scheduled Reports/Projects | Full Support |
| Segments | Full Support. Now called "Filters" - note that any existing segments in traditional Analysis Workspace are not ported to Customer Journey Analytics. |
| Virtual Report Suites | Full Support. Now called [Data Views](/help/data-views/create-dataview.md). |
| Virtual report suite Component Curation | Full Support. Now part of Data Views. |
| Streaming Media Analytics | Media data are available using the Analytics source connector as part of the Media Concurrent Viewers panel and the Media Playback Time Spent panel in Workspace. |

{style="table-layout:auto"}

## Supported in a new way {#new-support}

| Feature | Notes |
| --- | --- |
| Audience Publishing (Segment Publishing) | Supported if licensed with Adobe's Customer Data Platform or Journey Optimizer products. [Audience Publishing](/help/components/audiences/audiences-overview.md) sends audiences to Real-time Customer Profile in Experience Platform. |
| Classifications | Now called "Lookup Datasets". Classifications used in Analytics can be imported to the Experience Platform and Customer Journey Analytics using the Analytics Classifications Source Connector. Lookup datasets can also be uploaded to Experience Platform directly and made available in Customer Journey Analytics. |
| Classification Rule Builder | Supported using [substrings](/help/data-views/component-settings/substring.md) in Customer Journey Analytics. Uses string manipulations at report time rather than lookup datasets. |
| Custom Sessionization | Custom sessionization can be configured through the [Session settings](../../data-views/create-dataview.md#session-settings) in a Data view. See  [Session settings](../../data-views/session-settings.md) for more information. <br/>Handling of mobile background events is supported through the Adobe Experience Platform Mobile SDK. See [Lifecycle for Edge Network](https://developer.adobe.com/client-sdks/documentation/lifecycle-for-edge-network/) for more information. |
| Currency Conversion | Supported as part of [formatting a metric component](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/format.html?lang=en#currency) in a data view. |
| Merchandising variable persistence | Full Support via [binding dimensions and binding metrics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html#binding-dimension) |
| Customer Attributes | Now called "Profile Datasets", they do not get automatically imported from Experience Cloud, but must be uploaded to Experience Platform before they are available in Customer Journey Analytics. |
| Data Feeds | First-generation data export of datasets is available through the [Experience Platform Data Access API](https://experienceleague.adobe.com/docs/experience-platform/data-access/api.html?lang=en) and through [Experience Platform Destinations](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en). These options provide event/row level export of all data collected or ingested into Experience Platform Data Lake. Post process data columns are not available because post columns are computed at query time. Export of post columns is available through reporting. |
| Metric deduplication | Now configured on metrics within Data Views. Metric deduplication happens at the person or session level rather than the Dataset, Data View, or Connection level. |
| Entries, Exits, and Time spent dimensions and metrics | Supported (Entries and Exits are now called Session Starts and Session Ends) and are calculated in a slightly different way. |
| eVar persistence settings | eVars are no longer part of Customer Journey Analytics. However, persistence settings are now part of Data Views and are available for all dimensions. Keep in mind that persistence is based on report time processing, not data collection processing. Dimensions set within Data Views are limited to a 90-day max persistence and do not support unlimited persistence. |
| IP Obfuscation | For Customer Journey Analytics customers using the Analytics source connector to populate data from Adobe Analytics into Customer Journey Analytics: IP obfuscation settings applied in Adobe Analytics flow through to your Customer Journey Analytics data. You can control these settings in Adobe Analytics as needed.<p>For Customer Journey Analytics customers using Experience Platform Web SDK to populate data into Platform and Customer Journey Analytics directly. You can use Data Prep for Data Collection in Platform to configure rules that obfuscates the IP address based on your company's requirements. |
| New vs. Repeat Session Reporting | Formerly accomplished using the Visit Number dimension. New vs. Repeat sessions are supported [with a 13-month lookback window](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/data-views/data-views-usecases.html?lang=en). |
| Product Variable | Within the Experience Platform, users can use array of Object type fields within a dataset schema to satisfy this use case. Within Customer Journey Analytics, customers can use any number of product variables and are not restricted to a single variable as in Adobe Analytics. |
| Project Sharing | Project sharing is only supported between users of Customer Journey Analytics - there is not project sharing between Customer Journey Analytics and the traditional Analysis Workspace. |
| Visualizations | All visualizations are supported except for the Map visualization. |
| Report Builder (Excel plugin) | Supported with a new Office 365 plugin for Excel. |
| User Permissions/Data Access Controls | Customer Journey Analytics distinguishes between [Adobe Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/administration/admin-getting-started.html) product admins, product profile admins, and users. Only product admins can Create/update/delete Connections, Projects, Filters, or Calculated Metrics that were created by other users, while product admins and product profile admins can edit Data Views. Additional user permissions are available for things like creating calculated metrics, filter, or annotations. |
| Processing Rules, VISTA Rules, Marketing Channels Processing Rules | Supported using Adobe Experience Platform Data Prep functionality for both WebSDK based datasets and data from the Analytics source connector. |
| Marketing Channels | When using the Analytics source connector, Marketing Channels data flows into Customer Journey Analytics through that connector. Marketing Channel rules are configured in traditional Adobe Analytics and some rules are not supported. For more details, please see [Customer Journey Analytics Marketing Channels documentation](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/aa-data/marketing-channels.html). <br/>For WebSDK implementations, report-time marketing channels processing rules are supported through [Derived fields](../../data-views/derived-fields/derived-fields.md). |

{style="table-layout:auto"}

## Partial Support {#partial}

| Feature | Notes |
| --- | --- |
| Cross-device/cross-channel stitching | Supported for datasets containing identity information directly (also known as "field-based" stitching). Graph-based stitching is not yet supported, but planned. See [Stitching](../../stitching/overview.md). |
| Bot Filtering | For [Analytics source connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html)-based datasets, bot filtering is applied. General bot filtering logic for other datasets is not performed by the [!UICONTROL Experience Platform] or Customer Journey Analytics. |
| Device, Browser, Referrer, Technology dimensions | Supported for [Analytics source connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html)-based datasets. Refer to [documentation on which Analytics variables are supported via ADC](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=en).<p>If you use Experience Platform Web SDK data collection, Device and dimensions based on the Device lookup are not currently supported. Future support is planned. |
| GeoSegmentation dimensions | All GeoSegmentation/geography collected into Adobe Analytics flows into Customer Journey Analytics through the [Analytics source connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html). Implementations that do not use the Analytics source connector, but rely on Experience Platform Web SDK for digital data collection, can use the [Experience Edge Geo Lookup service](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en). |
| Panels | Blank Panel, Attribution Panel, Freeform Panel, and Quick Insights are fully supported. The Segment Comparison and Analytics for Target (A4T) panels are not supported. |
| Processing Rules | For Analytics source connector-based datasets, processing rules are still applied. [Data prep capabilities in Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html) can also be used as a replacement for processing rules for data that is going directly to Platform. |
| A4T | Partial support is provided through fields in the [Analytics source connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html). Support for A4T-friendly names on Target Activities and Experiences is planned.|

{style="table-layout:auto"}

## No support, but planned {#planned}

| Feature | Notes |
| --- | --- |
| Alerts | Support is planned. |
| Contribution Analysis | Support is planned. |
| Data Warehouse Reporting | Support is planned from the Analysis Workspace interface. Adobe Experience Platform [[!UICONTROL Query Service]](<https://experienceleague.adobe.com/docs/experience-platform/query/home.html>) also provides an interface for these use cases in Customer Journey Analytics. |
| ID Stitching via Device Graph | Support is planned. |
| Project Templates | Support is planned. |
| Real-Time Reporting | Support is planned. |
| Segment IQ | Support is planned. |
| Transaction ID Data Sources | Support is planned. |
| Migrating Projects/Filters/Calculated Metrics from Adobe Analytics to Customer Journey Analytics | Support is planned. |
| Summary-level data sources | Support is planned. |

{style="table-layout:auto"}

## No support, not yet planned {#not-planned}

| Feature | Notes |
| --- | --- |
| Activity Map | Support is not yet planned. |
| Advertising Cloud | Support is not yet planned. |

{style="table-layout:auto"}

## Never supported {#never}

* People metric using Cross-Device Coop
* Reports & Analytics Dashboards
* Reports & Analytics Bookmarks
* Reports & Analytics Targets

## Adobe Customer Journey Analytics features not available in Adobe Analytics {#cja-not-aa}

The following table lists features that are available in Customer Journey Analytics, but are not supported in Adobe Analytics.

| Feature | More Details |
| --- | --- |
| Accommodation for any kind of data | Customer Journey Analytics is combined with Experience Platform's ability to hold all kinds of data schemas and types. Using [Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html), data can be uniformly represented and organized, ready for combination and exploration. Adobe Analytics is predominantly focused on web and mobile analytics data with some capabilities to [import data](https://experienceleague.adobe.com/docs/analytics/import/home.html). |
| Unlimited Customer Dimensions & Metrics | Customer Journey Analytics dimensions are unlimited; values can be numeric, text, objects, lists, or mixtures of all. Dimensions can be nested or hierarchical. Analytics supports up to a maximum of 75 props and 250 eVars. |
| Unlimited cardinality / unique values | Customer Journey Analytics supports unlimited unique values or dimension items that can be reported on within a single dimension. Adobe Analytics is limited to 500.000 unique values. The unlimited unique values or dimensions removes reporting and analysis limitations currently existing with large-scale Analytics implementation. |
| Report Time Transformations | Report Time Transformations (better known as Data Views) in Customer Journey Analytics allow you to further interpret data from a connection. You can alter or remove data without reimplementation; use substrings to manipulate dimensions; create metrics from any value; filter subevents. And transformation are all done non-destructively. Adobe Analytics provides limited capabilities through virtual report suites and sessionization. |
| Experimentation Analysis | Customer Journey Analytics can evaluate the lift and confidence of any experiment from any data source defined as part of a connection. This evaluation allows you to understand cause-and-effect relationships between customer interactions spanning any channel. Analytics is limited to experimentation analytics through the Analytics for Target (A4T) integration. |
| Cross-Device Analytics | Customer Journey Analytics supports the seamless combination of device-specific datasets from unauthenticated and authenticated sessions. Customer Journey Analytics offers to backfill historical data to known devices. In Analytics, this capability is limited to a single report suite and the use of a device graph. |
| SQL Access | Using the Data Distiller option, Customer Journey Analytics can remove the limitations of data collected on Adobe's backend processing. You can modify your data with SQL, create values and datasets unique to your business and continue to explore. Analytics does not support any kind of SQL access to its data. |
| Enhanced Security and Privacy Options - HIPAA readiness | Customer Journey Analytics is HIPAA ready and offers additional security options for regulation compliance. Adobe Analytics is not HIPAA ready. |

{style="table-layout:auto"}
