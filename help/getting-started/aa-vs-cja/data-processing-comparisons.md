---
title: Compare data processing across Adobe Analytics and Customer Journey Analytics reporting features
description: Understand the differences in data processing for the various reporting features
exl-id: e3deedb2-0171-4fc2-9127-b9543603d4f0
feature: CJA Basics
---
# Compare data processing across Adobe Analytics and Customer Journey Analytics.

You often need the ability to process data before it is useful for reporting. You can process that data at several stages in the journey that spans from collecting data to generating your report or visualization.

In Adobe Analytics most of that processing of data occurs immediately after collecting the data. Functionalties like VISTA Rules, Processing Rules, Marketing Channels Processing Rules are available to support this **collection-time processing**. 
The data is then stored and at report time you can apply additional processing. For example, break down dimensions, apply segmentation, or  select a different attribution model. This **report-time processing** happens on the fly. 

In Adobe Analytics, report-time processing commonly represents a smaller amount of processing  than what happens at collection-time.

![Adobe Analytics collection-time processing](../assets/aa-processing.png)

In contrast, Customer Journey Analytics is designed to require minimal upfront collection-time processing before data being is organized and stored. The underlying architecture of Customer Journey Analytics is designed to work with the stored data at report-time and offers its powerful report-time processing functionality not only in  Workspace but also, even more importantly, through the definition of [components](/help/data-views/component-settings/overview.md) and [derived fields](/help/data-views/derived-fields/derived-fields.md) in your Data views. 

![Customer Journey Analytics report-time processing](../assets/cja-processing.png)

Understanding the differences in data processing for the various reporting features can be helpful in understanding which metrics are available where and why they may differ. 

For example, since "visits" as a metric in Adobe Analytics is defined at data processing time, and "sessions" as a metric in Customer Journey Analytics is calculated at report time, the two metrics may differ based on the rules used for session definition inside the Customer Journey Analytics data view. 

Also, neither visits nor sessions as a metric is available in datasets created by the Analytics Source Connector and therefore would require you to define the session in your query logic in order to do comparisons.

## Terminology {#terms}

The table below defines terminology for the different types of processing logic that are applied to Adobe Analytics and Customer Journey Analytics:

| Term | Definition | Notes |
| --- | --- | --- |
| Collection-time processing | Logic that is performed when data is being collected and processed, before being stored for reporting and analytics purposes. | This logic is 'baked into' historical data and generally cannot easily be changed. |
| Report-time processing | Logic that is performed at the time a report is run. | This logic can be applied to future and historical data at report runtime in a non-destructive manner. |
| Hit-level logic | Logic applied at a row-by-row level. | Examples: Processing rules, VISTA, certain marketing channel rules. |
| Visit-level logic | Logic applied at the visit level. | Examples: Visit and session definition. |
| Visitor-level logic | Logic applied at the person level. | Example: Cross-device/cross-channel person stitching. |
| Segment (filter) logic | Evaluation of event/visit/person (event/session/person) segment (filter) rules. | Example: People who bought red shoes. |
| Calculated metrics | Evaluation of customer-created custom metrics which can be based on complex formulas including segments and filters. | Example: # of people who bought red shoes. |
| Attribution logic | Logic to calculate attribution. | Example: eVar persistence. |
| Component Settings | Applying customizations to metrics or dimensions, like attribution, behaviour, format, and others | Example: value bucketing to combine numeric values based on a range |
| Derived fields | Logic applies to schema or standard fields as part of defining components in a Data view. | Example: creating a new marketing channel dimension |

{style="table-layout:auto"}

Over time, Adobe Analytics and now Customer Journey Analytics have improved their flexibility by allowing visit and person-level data logic to be performed at report runtime. 

## Types of data processing {#types}

The data processing steps which are performed for Adobe Analytics and Customer Journey Analytics and the timing of those steps varies from feature to Analytics feature. The table below provides a summary of the types of data processing for each Analytics feature, and when the data processing is applied.

| Feature | Applied at processing time | Applied at report time | Not available | Notes |
| --- | --- | --- | --- | --- |
| [Adobe Analytics](https://experienceleague.adobe.com/docs/analytics.html?lang=en) reporting<br/>(not including Attribution IQ or virtual report suites with report-time processing) | <ul><li>[Processing rules](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules.html?lang=en)</li><li>[VISTA rules](https://experienceleague.adobe.com/docs/analytics/technotes/terms.html?lang=en)</li><li>Hit-level [marketing channel rules](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/marketing-channels/c-rules.html?lang=en)</li><li>Visit-level marketing channel rules (see note)</li><li>Visit definition</li><li>Attribution logic</li></ul> | <ul><li>Segment logic</li><li>Calculated metrics</li></ul>  |  <ul><li>Cross-Device Analytics (see note)</li></ul> | <ul><li>CDA requires use of virtual report suites with report time processing.</li><li>"Visit-level marketing channel rules" include the following: **Is First Page of Visit**, **Override Last-Touch Channel**, and **Marketing Channel Expiration**. (See [documentation](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=en).)</li></ul>  |
| Adobe Analytics [Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse.html?lang=en) | <ul><li>Processing rules</li><li>VISTA rules</li><li>Hit-level marketing channel rules</li><li>Visit-level marketing channel rules</li><li>Visit definition</li><li>Attribution logic</li></ul> | <ul><li>Segment logic</li></ul> | <ul><li>Calculated metrics</li><li>Cross-Device Analytics</li></ul> |     |
| Adobe Analytics [Data Feeds](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-overview.html?lang=en) |  <ul><li>Processing rules</li><li>VISTA rules</li><li>Hit-level marketing channel rules</li><li>Visit-level marketing channel rules</li><li>Visit definition (visitnum field)</li><li>Attribution logic (in post columns)</li></ul> |   |  <ul><li>Segment logic</li><li>Calculated metrics</li><li>Cross-Device Analytics</li></ul> |  <ul><li>ID mappings for certain marketing channel-related columns in data feeds are not included with data feeds. (See the [data feed documentation](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=en).)</li></ul> |
| Adobe Analytics [Livestream](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md)    | <ul><li> Processing rules</li><li>VISTA rules</li><ul> |   |  <ul><li>Hit-level marketing channel rules</li><li>Visit-level marketing channel rules</li><li>Visit logic</li><li>Attribution logic</li><li>Segment logic</li><li>Calculated metrics</li><li>Cross-Device Analytics</li></ul>  |  |
| Adobe Analytics [Attribution IQ](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/overview.html?lang=en) |  <ul><li>Processing rules</li><li>VISTA rules</li><li>Visit definition (see note)</li><li>Cross-Device Analytics (see note)</li></ul>  |  <ul><li>Hit-level marketing channel rules (see note)</li><li>Visit-level marketing channel rules (see note) Attribution logic</li><li>Segment logic</li><li>Calculated metrics</li></ul>  |  |  <ul><li>CDA requires use of virtual report suites with report time processing.</li><li>Attribution IQ in Core Analytics uses marketing channels that are derived completely at report time (i.e. derived mid-values.)</li><li>Attribution IQ uses a processing-time visit definition except when used in a report-time processing VRS.</li></ul>  |
| Adobe Analytics virtual report suites with [report time processing](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=en) (VRS RTP)  | <ul><li>Processing rules</li><li>VISTA rules</li><li>[Cross-Device Analytics](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=en)</li></ul>  | <ul><li>Visit definition</li><li>Attribution logic</li><li>Segment logic</li><li>Calculated metrics</li><li>Other VRS RTP settings</li></ul>  | <ul><li>Hit-level marketing channel rules</li><li>Visit-level marketing channel rules</li></ul>    | <ul><li>See VRS RTP [documentation](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=en).</li></ul>  |
| [Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=en)-based dataset in Adobe Experience Platform data lake  | <ul><li>Processing rules</li><li>VISTA rules</li><li>Hit-level marketing channel rules</li><li>Field-based stitching (see note)</li></ul>  |   | <ul><li>[Visit-level marketing channel rules](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=en)</li><li>Visit logic</li><li>Attribution logic</li><li>Filter logic</li></ul>  | <ul><li>Must apply your own filter logic and calculated metrics</li><li>Field-based stitching creates a separate stitched dataset in addition to the one created by the Analytics Source Connector.</li></ul>  |
| [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-landing.html?lang=en) reporting  | <ul><li>Implemented as part of Adobe Experience Platform Data Collection</li></ul> | <ul><li>Session definition</li><li>[Data view](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=en) settings<li>Attribution logic</li><li>Calculated metrics</li><li>Filter logic</li></ul> | <ul><li>Visit-level marketing channel rules</li></ul>  | <ul><li>Must use stitched datasets in order to take advantage of cross-channel analytics.</li></ul> | 

{style="table-layout:auto"}
