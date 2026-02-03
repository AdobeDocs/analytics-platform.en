---
title: Compare data processing across Adobe Analytics and Customer Journey Analytics reporting features
description: Understand the differences in data processing for the various reporting features
exl-id: e3deedb2-0171-4fc2-9127-b9543603d4f0
feature: Basics
role: User
---
# Compare data processing across Adobe Analytics and Customer Journey Analytics

You often need the ability to process data before it is useful for reporting. You can process that data at several stages in the journey that spans from collecting data to generating your report or visualization.

In Adobe Analytics most of that processing of data occurs immediately after collecting the data. Functionalties like VISTA Rules, Processing Rules, Marketing Channels Processing Rules are available to support this **collection-time processing**. 
The data is then stored and at report time you can apply additional processing. For example, break down dimensions, apply segmentation, or  select a different attribution model. This **report-time processing** happens on the fly. 

In Adobe Analytics, report-time processing commonly represents a smaller amount of processing  than what happens at collection-time.

![Adobe Analytics collection-time processing](../assets/aa-processing.png)

In contrast, Customer Journey Analytics is designed to require minimal upfront collection-time processing before data is organized and stored. The underlying architecture of Customer Journey Analytics is designed to work with the stored data at report-time. Customer Journey Analytics offers its powerful report-time processing functionality not only in Analysis Workspace. Additional report-time processing functionality is available through the definition of [components](/help/data-views/component-settings/overview.md) and [derived fields](/help/data-views/derived-fields/derived-fields.md) in your data views. 

![Customer Journey Analytics report-time processing](../assets/cja-processing.png)

Understanding the differences in data processing for the various reporting features can be helpful in understanding which metrics are available where and why they may differ. 

For example, *visits* is defined as a metric in Adobe Analytics at data processing time. And *sessions* is calculated as a metric in Customer Journey Analytics at report time. As a result, the two metrics may differ based on the rules for the session definition in a Customer Journey Analytics data view. 

Also, visits and sessions as a metric are not available in datasets created by the Analytics source connector. And therefore would require you to define the session in your query logic to do comparisons.

## Terminology {#terms}

The table below defines terminology for the different types of processing logic that are applied to Adobe Analytics and Customer Journey Analytics:

| Term | Definition | Notes |
| --- | --- | --- |
| Collection-time processing | Logic that is performed when data is being collected and processed, before being stored for reporting and analytics purposes. | This logic is 'baked into' historical data and generally cannot easily be changed. |
| Report-time processing | Logic that is performed at the time a report is run. | This logic can be applied to future and historical data at report runtime in a non-destructive manner. |
| Hit-level logic | Logic applied at a row-by-row level. | Examples: Processing rules, VISTA, certain marketing channel rules. |
| Visit-level logic | Logic that is applied at the visit level. | Examples: Visit and session definition. |
| Visitor-level logic | Logic that is applied at the person level. | Example: Cross-device/cross-channel person stitching. |
| Segment logic | Evaluation of event/visit/person (event/session/person) segment rules. | Example: People who bought red shoes. |
| Calculated metrics | Evaluation of customer-created custom metrics. Calculated metrics can be based on complex formulas,  including segments. | For example, the number of people who bought red shoes. |
| Attribution logic | Logic to calculate attribution. | Example: eVar persistence. |
| Component Settings | Applying customizations to metrics or dimensions, like attribution, behavior, format, and others | Example: value bucketing to combine numeric values based on a range |
| Derived fields | Logic that applies to schema or standard fields as part of defining components in a Data view. | Example: creating a new marketing channel dimension |

{style="table-layout:auto"}

Over time, Adobe Analytics and now Customer Journey Analytics have improved their flexibility by allowing visit and person-level data logic to be performed at report runtime. 

## Types of data processing {#types}

The data processing steps performed by Adobe Analytics and Customer Journey Analytics and the timing of those steps varies from feature to feature. The table below provides a summary of the types of data processing for each feature, and when data processing is applied.

| Feature | Applied at processing time | Applied at report time | Not available | Notes |
| --- | --- | --- | --- | --- |
| [Adobe Analytics](https://experienceleague.adobe.com/en/docs/analytics) reporting<br/>(not including advanced attribution features or virtual report suites with report-time processing) | <ul><li>[Processing rules](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/report-suite-general/c-processing-rules/processing-rules)</li><li>[VISTA rules](https://experienceleague.adobe.com/en/docs/analytics/technotes/terms)</li><li>Hit-level [marketing channel rules](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/marketing-channels/c-rules)</li><li>Visit-level marketing channel rules (see note)</li><li>Visit definition</li><li>Attribution logic</li></ul> | <ul><li>Segment logic</li><li>Calculated metrics</li></ul>  |  <ul><li>Cross-Device Analytics (see note)</li></ul> | <ul><li>Cross-Device Analytics requires the use of virtual report suites with report time processing.</li><li>"Visit-level marketing channel rules" include the following: **Is First Page of Visit**, **Override Last-Touch Channel**, and **Marketing Channel Expiration**. (See [documentation](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-usecases/aa-data/marketing-channels).)</li></ul>  |
| Adobe Analytics [Data Warehouse](https://experienceleague.adobe.com/en/docs/analytics/export/data-warehouse/data-warehouse) | <ul><li>Processing rules</li><li>VISTA rules</li><li>Hit-level marketing channel rules</li><li>Visit-level marketing channel rules</li><li>Visit definition</li><li>Attribution logic</li></ul> | <ul><li>Segment logic</li></ul> | <ul><li>Calculated metrics</li><li>Cross-Device Analytics</li></ul> |     |
| Adobe Analytics [Data Feeds](https://experienceleague.adobe.com/en/docs/analytics/export/analytics-data-feed/data-feed-overview) |  <ul><li>Processing rules</li><li>VISTA rules</li><li>Hit-level marketing channel rules</li><li>Visit-level marketing channel rules</li><li>Visit definition (visitnum field)</li><li>Attribution logic (in post columns)</li></ul> |   |  <ul><li>Segment logic</li><li>Calculated metrics</li><li>Cross-Device Analytics</li></ul> |  <ul><li>ID mappings for certain marketing channel-related columns in data feeds are not included with data feeds. (See the [data feed documentation](https://experienceleague.adobe.com/en/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference).)</li></ul> |
| Adobe Analytics [Livestream](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md)    | <ul><li> Processing rules</li><li>VISTA rules</li><ul> |   |  <ul><li>Hit-level marketing channel rules</li><li>Visit-level marketing channel rules</li><li>Visit logic</li><li>Attribution logic</li><li>Segment logic</li><li>Calculated metrics</li><li>Cross-Device Analytics</li></ul>  |  |
| Adobe Analytics [Advanced attribution features](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/attribution/overview) |  <ul><li>Processing rules</li><li>VISTA rules</li><li>Visit definition (see note)</li><li>Cross-Device Analytics (see note)</li></ul>  |  <ul><li>Hit-level marketing channel rules (see note)</li><li>Visit-level marketing channel rules (see note) Attribution logic</li><li>Segment logic</li><li>Calculated metrics</li></ul>  |  |  <ul><li>Cross-Device Analytics requires the use of virtual report suites with report time processing.</li><li>Advanced attribution features in Core Analytics use marketing channels that are derived completely at report time (that is, derived mid-values.)</li><li>Advanced attribution features use a processing-time visit definition except when used in a report-time processing virtual report suite.</li></ul>  |
| Adobe Analytics virtual report suites with [report-time processing](https://experienceleague.adobe.com/en/docs/analytics/components/virtual-report-suites/vrs-report-time-processing) | <ul><li>Processing rules</li><li>VISTA rules</li><li>[Cross-Device Analytics](https://experienceleague.adobe.com/en/docs/analytics/components/cda/overview)</li></ul>  | <ul><li>Visit definition</li><li>Attribution logic</li><li>Segment logic</li><li>Calculated metrics</li><li>Other virtual report suite  report-time processing settings</li></ul>  | <ul><li>Hit-level marketing channel rules</li><li>Visit-level marketing channel rules</li></ul>    | <ul><li>See Virtual report suite report-time processing [documentation](https://experienceleague.adobe.com/en/docs/analytics/components/virtual-report-suites/vrs-report-time-processing).</li></ul>  |
| [Analytics source connector](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/analytics)-based dataset in Adobe Experience Platform data lake  | <ul><li>Processing rules</li><li>VISTA rules</li><li>Hit-level marketing channel rules</li><li>Field-based stitching (see note)</li></ul>  |   | <ul><li>[Visit-level marketing channel rules](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-usecases/aa-data/marketing-channels)</li><li>Visit logic</li><li>Attribution logic</li><li>Segment logic</li></ul>  | <ul><li>Apply your own segment logic and calculated metrics</li><li>Field-based stitching creates a separate stitched dataset in addition to the one created by the Analytics source connector.</li></ul>  |
| [Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-landing) reporting  | <ul><li>Implemented as part of Adobe Experience Platform Data Collection</li></ul> | <ul><li>Session definition</li><li>[Data view](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/data-views) settings<li>Attribution logic</li><li>Calculated metrics</li><li>Segment logic</li></ul> | <ul><li>Visit-level marketing channel rules</li></ul>  | <ul><li>Use stitched datasets to take advantage of cross-channel analytics.</li></ul> |

{style="table-layout:auto"}
