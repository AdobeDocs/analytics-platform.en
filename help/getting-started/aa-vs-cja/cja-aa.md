---
title: Customer Journey Analytics Feature Support
description: Learn about the Customer Journey Analytics features compared with the Adobe Analytics features set.
exl-id: be19aa27-58aa-438d-806c-e27c9a289797
solution: Customer Journey Analytics
feature: Basics
role: User
---
# Customer Journey Analytics feature support

The following tables list which features are unique to Customer Journey Analytics, and which Adobe Analytics features are supported, partially supported, or not supported in Customer Journey Analytics. These lists will change over time as features are added to Customer Journey Analytics.

## Features unique to Adobe Customer Journey Analytics {#cja-not-aa}

The following table lists features that are available in Customer Journey Analytics, but are not supported in Adobe Analytics.

| Feature | More Details |
| --- | --- |
| **Ability to combine datasets (such as Adobe Analytics report suites)** | Customer Journey Analytics allows you to [combine data](/help/connections/combined-dataset.md) from multiple report suites as if they were a single report suite in Adobe Analytics. |
| **Accommodation for any kind of data** | Customer Journey Analytics is combined with Experience Platform's ability to hold all kinds of data schemas and types. Using [Experience Data Model (XDM)](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home), data can be uniformly represented and organized, ready for combination and exploration. Adobe Analytics is predominantly focused on web and mobile analytics data with some capabilities to [import data](https://experienceleague.adobe.com/en/docs/analytics/import/home). |
| **B2B Edition** | [Customer Journey Analytics B2B Edition](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition?lang=en) helps B2B companies align their marketing, sales, and product teams by providing actionable account insights that drive revenue growth. With the account placed at the center of the data model, all analysis focuses on the account journey. Adding a new layer of entities (accounts, opportunities, and buying groups) on top of person and time-based events, creates a complete picture of the B2B marketing and revenue lifecycle. |
| **BI Extension** | The [BI Extension](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-usecases/data-export/bi-extension) lets you connect Customer Journey Analytics directly to popular BI visualization tools, such as Power BI or Tableau. By using this extension, you can have your BI reports precisely match what you see in Analysis Workspace and other Customer Journey Analytics reporting interfaces. This extension offers a much easier way to get BI reporting for Customer Journey Analytics without the need to recreate reports/metrics from raw data. |
| **Content Analytics** | [Content Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/content-analytics/content-analytics) helps marketers to understand how content impacts the key performance indicators that a business has defined. On top of the behavioral data, Content Analytics collects data on how content is consumed and how content drives impact. |
| **Cross-Device Analytics** | Customer Journey Analytics supports the seamless combination of device-specific datasets from unauthenticated and authenticated sessions. Customer Journey Analytics offers to backfill historical data to known devices. In Adobe Analytics, this capability is limited to a single report suite and the use of a device graph. |
| **Data Insights Agent** | The [Data Insights Agent](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2c-overview/data-analysis-ai?lang=en), part of the AI Assistant in Customer Journey Analytics, is a generative AI conversation agent. It uses components from your data view and your actual data to quickly and efficiently answer data-centric questions by building relevant visualizations in Analysis Workspace. |
| **Dimension enhancements** | Customer Journey Analytics provides greater flexibility when using dimensions: <ul><li>**Custom numeric-based dimensions**: [Create your own numeric-based dimensions within a data view](/help/data-views/create-dataview.md#components).</li><li>**Sort string-based dimensions**: [Sort string-based dimensions alphabetically in a freeform table.](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md#sort-tables) </li></ul><p>In Adobe Analytics, only a handful of built-in numeric dimensions were available, and sorting by string-based dimensions was not possible.</p> |
| **Derived Fields** | [Derived fields](/help/data-views/derived-fields/derived-fields.md) allow for report-time transformations to your data. Data can be combined, corrected, or created on the fly and these transformations apply retroactively to all reporting. |
| **Enhanced security and privacy options** - HIPAA readiness | Customer Journey Analytics is HIPAA ready and offers [additional security options](/help/privacy/cmk.md) for regulation compliance. Adobe Analytics is not HIPAA ready. |
| **Experimentation analysis** | Customer Journey Analytics can [evaluate the lift and confidence of any experiment](/help/analysis-workspace/c-panels/experimentation.md) from any data source defined as part of a connection. This evaluation allows you to understand cause-and-effect relationships between customer interactions spanning any channel. Analytics is limited to experimentation analysis through A4T. |
| **Forecasting** | [Forecasting](/help/analysis-workspace/c-forecast/forecasting.md) is an AI/ML capability that includes a statistical prediction for time-series-related data based on the historical data that already exists in Customer Journey Analytics. Forecasts can appear in freeform tables and line graph visualizations. |
| **Guided analysis** | [Guided analysis](/help/guided-analysis/overview.md) enables users to self-serve high quality data and insights about the customer journey through guided workflows, built on the cross-channel data of Customer Journey Analytics. |
| **Intelligent Captions** | [Intelligent captions](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/visualizations/intelligent-captions) use advanced Machine Learning and Generative AI to provide valuable natural-language insights for Workspace visualizations. Intelligent captions are supported for the following visualizations: Line, Multi-line, Bar, Horizontal bar, Donut, Area, Flow, and Fallout. |
| **Journey Canvas** | [Journey canvas](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/visualizations/journey-canvas/journey-canvas?lang=en) is a visualization in Analysis Workspace that allows you to analyze how people proceed through or fall out of a defined journey. |
| **Product Usage** | [Product usage](https://experienceleague.adobe.com/en/docs/analytics-platform/using/tools/product-usage/usage-overview) shows you how your organization uses Customer Journey Analytics. |
| **Report-time transformations** | [Data views](/help/data-views/data-views.md) in Customer Journey Analytics allow you to interpret data from a connection. You can alter or remove data without changing your implementation. Use substrings to manipulate dimensions. Create metrics from any value, or filter subevents. All of these transformations are done non-destructively. Adobe Analytics provides limited capabilities through virtual report suites and custom session length. |
| **Shared metrics and dimensions across data views** | Shared metrics and dimensions allow you to [apply dimension and metric settings across multiple data views](/help/data-views/shared-metrics-dimensions/smd-overview.md). Changes made to a shared dimension or metric apply to all instances of that dimension or metric across all applicable data views. |
| **SQL access** | Using the Data Distiller option, Customer Journey Analytics can remove the limitations of data collected on Adobe's backend processing. You can modify your data with SQL, create values and datasets unique to your business and continue to explore. Analytics does not support any kind of SQL access to its data. |
| **Stitching** | [Stitching](/help/stitching/overview.md) is a powerful feature that elevates an event dataset's suitability for cross-channel analysis. Cross-channel analysis is a main use case that Customer Journey Analytics can handle. Cross-channel analysis allows you to combine and run reports seamlessly on multiple datasets from different channels, based on a common identifier (person ID). |
| **Templates in Adobe Journey Optimizer** | Customize the new reporting interface in Adobe Journey Optimizer by creating or editing a [template](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/templates/create-templates?lang=en) in Customer Journey Analytics, then saving the template to be used on the Reports page in Journey Optimizer. |
| **Unlimited customer dimensions and metrics** | Customer Journey Analytics dimensions are unlimited; values can be numeric, text, objects, lists, or mixtures of all. Dimensions can be nested or hierarchical. <br/>By contrast, Adobe Analytics supports up to a maximum of 75 props and 250 eVars. |
| **Unlimited unique values** | Customer Journey Analytics supports unlimited unique values or dimension items that can be reported on within a single dimension.<p>There are no [cardinality limits on a dimension](/help/components/dimensions/high-cardinality.md), allowing for any unique value to appear and be counted.</p><p>This approach removes reporting and analysis limitations that can exist with large-scale Adobe Analytics implementations, resulting in [!UICONTROL Low Traffic] labels.</p><p>In Customer Journey Analytics, it is possible to see a [!UICONTROL Uniques Exceeded] label, but these labels occur far less frequently and can be mitigated by applying a segment to the data.</p> |

## Fully supported Adobe Analytics features/components {#full-support}

| Adobe Analytics Feature | Notes on Customer Journey Analytics support |
| --- | --- |
| **Anomaly detection** | Full support |
| **Asset transfer** | Full support |
| **Attribution features** | Full support |
| **Bot detection** | [Full support](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/bot-detection) |
| **Calculated metrics** | Full support. Any existing calculated metric in the traditional Analysis Workspace is not ported to Customer Journey Analytics. |
| **Calendar events** | Full support. Calendar events have been implemented as [Annotations](/help/components/annotations/overview.md) in Workspace. |
| **CSV download** | Full support |
| **Custom calendars** | Full support |
| **Date comparisons** | Full support | 
| **Date ranges** | All date range functionality is supported. |
| **Dimensions**| Full support. Customer Journey Analytics uses XDM and supports unlimited dimensions. Customer Journey Analytics is not tied to the custom eVars or props of traditional Adobe Analytics. |
| **GDPR deletion** | Full support; note that GDPR is now handled in coordination with [!UICONTROL Adobe Experience Platform]. Customer Journey Analytics inherits whatever data changes [!UICONTROL Experience Platform] makes to underlying datasets. |
| **Lift and confidence reporting** | Full support via [Experimentation panel](/help/analysis-workspace/c-panels/experimentation.md) |
| **List variables/List props** | Full support. Customer Journey Analytics uses XDM and supports unlimited string arrays which can be used similarly to listVars. |
| **Merchandising eVars** | Full support through [binding dimensions and binding metrics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/component-settings/persistence) |
| **Metrics** | Full support; Customer Journey Analytics uses the Experience Data Model (XDM) and supports unlimited metrics and is not tied to the custom success events of Adobe Analytics. Some standard metrics have been renamed from Adobe Analytics: Visitors = People, Visits = Sessions, Hits = Events. |
| **Migrating projects, segments, and calculated metrics from Adobe Analytics to Customer Journey Analytics** | Full support. |
| **Mobile scorecard/Dashboards** | Full support |
| **Panels** | Full support for the following panels: Blank panel, Attribution, Freeform, Quick insights, and Next or previous item. |
| **PDF export** | Full Support |
| **Project curation** | Full Support |
| **Project linking** | Full Support |
| **Product templates** | Includes [Pre-built templates](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/templates/use-templates) and [Company templates](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/templates/create-templates#access-a-company-template). |
| **Report time processing** | Full Support; Customer Journey Analytics relies exclusively on report time processing. |
| **Reporting API access** | Full Support; Available through the [Customer Journey Analytics API](https://developer.adobe.com/cja-apis/docs/). |
| **Scheduled reports/projects** | Full Support |
| **Segments** | Full Support. Segments are previously referred to as *Filters* in Customer Journey Analytics. |
| **Streaming Media Collection** | Streaming media data are available using the Analytics source connector as part of the Media Concurrent Viewers panel and the Media Playback Time Spent panel in Workspace. |
| **Summary-level data sources** | Full support |
| **Virtual report suites** | Full Support. [Data views](/help/data-views/create-dataview.md) are the Customer Journey Analytics equivalent of report suites in Adobe Analytics. |
| **Virtual report suite component curation** | Full Support. Component curation is part of data view functionality. |
| **Device, Browser, Referrer, Technology dimensions** | Supported for both [Analytics source connector](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/analytics)-based datasets and for datasets generated by the WebSDK. Refer to [documentation on which Analytics variables are supported via ADC](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics). If you use Experience Platform Web SDK data collection, Device and dimensions based on the Device lookup are not currently supported. Future support is planned. For adding device and browser lookups to your Web SDK datastream, refer to [this documentation](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/configure)|

## Supported in a new way {#new-support}

| Feature | Notes |
| --- | --- |
| **Advertising Cloud** | You can [collect historical data for AMO IDs and EF IDs for use in Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/advertising/integrations/analytics/planning/rvars-to-evars). |
| **Alerts** | The process of [using alerts in Customer Journey Analytics](/help/components/c-intelligent-alerts/alerts-feature-comparison.md) is nearly identical to using alerts in Adobe Analytics. <p>However, due to the timing of data collection in Customer Journey Analytics, hourly alerts are not available. In Customer Journey Analytics, alerts can be configured for daily, weekly, or monthly.</p> |
| **Analytics for Target (A4T)** | The [integration between Adobe Customer Journey Analytics and Target](https://experienceleague.adobe.com/en/docs/target/using/integrate/cja/target-reporting-in-cja) provides powerful analysis and timesaving tools for your optimization program. |
| **Audience publishing** | Supported if licensed with Adobe's Customer Data Platform or Journey Optimizer products. [Audience Publishing](/help/components/audiences/audiences-overview.md) sends audiences to Real-time Customer Profile in Experience Platform. |
| **Classifications** | Lookup Datasets are the equivalent of classifications in Adobe Analytics. Classifications used in Analytics can be imported to the Experience Platform and Customer Journey Analytics using the Analytics Classifications Source Connector. Lookup datasets can also be uploaded to Experience Platform directly and made available in Customer Journey Analytics. |
| **Classification rule builder** | Supported using [substrings](/help/data-views/component-settings/substring.md) in Customer Journey Analytics. Uses string manipulations at report time rather than lookup datasets. |
| **Custom session length** | Session length can be configured through [Session settings](../../data-views/create-dataview.md#session-settings) in a Data view. See  [Session settings](../../data-views/session-settings.md) for more information. <br/>Handling of mobile background events is supported through the Adobe Experience Platform Mobile SDK. See [Lifecycle for Edge Network](https://developer.adobe.com/client-sdks/documentation/lifecycle-for-edge-network/) for more information. |
| **Currency conversion** | Supported as part of [formatting a metric component](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/component-settings/format) in a data view. |
| **Customer attributes** | Profile datasets are the equivalent of customer attribution. Profile datasets are not automatically imported from Experience Cloud, but must be uploaded to Experience Platform before they are available in Customer Journey Analytics. |
| **Data feeds** | First-generation data export of datasets is available through the [Experience Platform Data Access API](https://experienceleague.adobe.com/en/docs/experience-platform/data-access/api) and through [Experience Platform Destinations](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets). These options provide event/row level export of all data collected or ingested into Experience Platform Data Lake. Post-process data columns are not available because post columns are computed at query time. Export of post columns is available through reporting. |
| **Data Warehouse reporting** | [Customer Journey Analytics Full Table Export](/help/analysis-workspace/export/export-cloud.md) is the evolution of Data Warehouse reports in Adobe Analytics, with many new, often-requested features that are not available in Data Warehouse today. |
| **Entries, Exits, and Time spent dimensions and metrics** | Supported (Entries and Exits are now called Session Starts and Session Ends) and are calculated in a slightly different way. |
| **eVar persistence settings** | eVars are no longer part of Customer Journey Analytics. However, persistence settings are now part of Data Views and are available for all dimensions. Keep in mind that persistence is based on report time processing, not data collection processing. Dimensions set within Data Views are limited to a 90-day max persistence and do not support unlimited persistence. |
| **Geo segmentation dimensions** | [Full support](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/configure) |
| **Graph-based stitching** | Through [Graph-based Stitching](https://experienceleague.adobe.com/en/docs/analytics-platform/using/stitching/overview#graph-based-stitching), you can harness the power of the identity graph in [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/en/docs/experience-platform/identity/home) to elevate datasets to their preferred identity. |
| **Alerts** | The process of using [alerts](/help/components/c-intelligent-alerts/intelligent-alerts.md) in Customer Journey Analytics is nearly identical to using alerts in Adobe Analytics. However, there are [important differences](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/alerts/alerts-feature-comparison). |
| **IP obfuscation** | For Customer Journey Analytics customers, using the Analytics source connector to populate data from Adobe Analytics into Customer Journey Analytics: IP obfuscation settings applied in Adobe Analytics flow through to your Customer Journey Analytics data. You can control these settings in Adobe Analytics as needed.<p>For Customer Journey Analytics customers using Experience Platform Web SDK to populate data into Platform and Customer Journey Analytics directly. You can use Data Prep for Data Collection in Platform to configure rules that obfuscates the IP address based on your company's requirements. |
| **Marketing channels** | When using the Analytics source connector, Marketing Channels data flows into Customer Journey Analytics through that connector. Marketing Channel rules are configured in traditional Adobe Analytics and some rules are not supported. See [Customer Journey Analytics Marketing Channels](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-usecases/aa-data/marketing-channels) for more information. <br/>For WebSDK implementations, report-time marketing channel processing rules are supported through [Derived fields](../../data-views/derived-fields/derived-fields.md). |
|  **Merchandising variable persistence** | Full Support through [binding dimensions and binding metrics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/component-settings/persistence) |
| **Metric deduplication** | Configured on metrics within Data Views. Metric deduplication happens at the person or session level rather than the Dataset, Data view, or Connection level. |
| **New versus repeat session reporting** | Formerly accomplished using the Visit Number dimension. New versus Repeat sessions are supported [with a 13-month lookback window](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-usecases/data-views/data-views-usecases). |
| **Processing rules, VISTA rules, Marketing channel processing rules** | Supported using Adobe Experience Platform Data Prep functionality as well as [derived fields](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/derived-fields) for both WebSDK based datasets and data from the Analytics source connector. |
| **Products variable** | Within the Experience Platform, users can use an array of objects within a dataset schema to satisfy this use case. Within Customer Journey Analytics, customers can use any number of product variables and are not restricted to a single variable as in Adobe Analytics. |
| **Project sharing** | Project sharing is only supported between users of Customer Journey Analytics - there is not project sharing between Customer Journey Analytics and the traditional Analysis Workspace. |
| **Report Builder** | Supported with a new Office 365 plugin for Microsoft Excel. |
| **User permissions/Data access controls** | Customer Journey Analytics distinguishes between [Adobe Admin Console](https://experienceleague.adobe.com/en/docs/core-services/interface/administration/admin-tool-experience-cloud) product admins, product profile admins, and users. Only product admins can create, update, and delete connections, projects, segments, or calculated metrics that  other users have created. Product admins and product profile admins can edit data views. Additional user permissions are available for things like creating calculated metrics, segments, or annotations. |
| **Visualizations** | All Workspace visualizations are supported except for the Map visualization. |
| **Cross-device/cross-channel stitching** | Supported for event datasets containing identity information. See [Stitching](../../stitching/overview.md). |

## Partial Support {#partial}

| Feature | Notes |
| --- | --- |
| **Workspace panels** | Blank Panel, Attribution Panel, Freeform Panel, and Quick Insights are fully supported. The Segment Comparison and Analytics for Target (A4T) panels are not supported. |

## No support, but planned {#planned}

| Feature | Notes |
| --- | --- |
| **Real-time reporting** | Support is planned. |
| **Transaction ID data sources** | Support is planned. |

## No support, not yet planned {#not-planned}

| Feature | Notes |
| --- | --- |
| **Activity Map** | Support is not yet planned. |
| **Contribution analysis** | Support is not yet planned. |

## Never be supported {#never}

* People metric using Cross-Device Coop
* Triggers
