---
description: Learn how to compare data feeds functionality in Customer Journey Analytics and Adobe Analytics
keywords: clickstream;data feed;datafeed;Data Feed
title: Compare Data Feeds Functionality in Customer Journey Analytics and Adobe Analytics
feature: Components
hide: true
exl-id: 32b71016-7c53-409f-9ce4-521a40e2eb96
autotag-review: '2026-05-19T08:44:26.806Z'
TQID: 'https://experienceleague.adobe.com/R7c5-VutwSkyghNvwC2gZv2KUEJoa263AN0Tkdg3w4o'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
    internal-label: Exports
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
---
# Compare data feeds in Customer Journey Analytics and Adobe Analytics

{{release-limited-testing}}

Data feeds in both Customer Journey Analytics and Adobe Analytics allow you to export raw data to third-party platforms.

If you previously used data feeds in Adobe Analytics, use the following information to understand differences in available features and concepts.

For a comparison of data feeds against other Customer Journey Analytics export methods, such as Full Table Export, see [Analytics product comparison](/help/getting-started/analytics-product-comparison.md).

## Features available only in Customer Journey Analytics data feeds

The following capabilities are available in Customer Journey Analytics data feeds but are not available in Adobe Analytics data feeds:

* **Derived fields**: Custom components built from rule-based transformations that can be included in your data feed schema. <!-- add benefit -->

* **Stitching**: Cross-device identity resolution that links events across devices to a single person. 

* **Structured data model**: Feeds are built and delivered using structured data rather than flat strings such as post_product_list. Reflects the existing structure from the XDM schema and the data view. 

* **Parquet output**: Files are delivered in Parquet format, which natively supports complex nested and structured data. This means that data is easier to access in a database using industry-standard practices.

* **Segmentation**: Segments applied to the data view are automatically inherited, and additional segments can be applied directly to the feed.

* **Hive-style partition paths**: Output files use Hive-style paths for efficient querying in data lake environments.

* **Component updates apply retroactively**: Changes to components in the data view are reflected historically in backfills.

* **Lookups**: Classifications are not included with Adobe analytics data feeds. In Customer Journey Analytics, all lookups are embedded directly in the data. 

* **Interface that is familiar to Analysis Workspace users**: Components come directly from the data view and are also available in Analysis Workspace. You can select dimensions and metrics using the same component rail as Analysis Workspace, rather than a static list of variable names.

* **More persistence models available**: There are five different persistence models that can be used in Customer Journey Analytics data feeds. 

<!-- * Web MCP when it's added -->

The [Functionality comparison](#functionality-comparison) table below covers each of these features in detail, along with differences in features that exist in both products.


## Functionality comparison

The following table compares key concepts and configuration options across Customer Journey Analytics data feeds and Adobe Analytics data feeds.

| **Concepts and configuration options** | **Customer Journey Analytics** | **Adobe Analytics** |
|---------|----------|---------|
| **Data input**<br/>The type of data that can be collected and included in data feeds. | Supports cross-channel data input, including web data, call center data, point-of-sale data, and more. | Primarily supports web and mobile data input. Other data types (such as call center or point-of-sale data) can be ingested via data sources, but with very limited processing capabilities. |
| **Data processing**<br/>Data is processed at different stages, depending on which product you are using. | Data is processed at **report time**, and therefore many reporting features can be used to change historical data, such as stitching, derived fields, and segmentation. | Data is processed at **collection time**, and therefore reporting features such as processing rules and VISTA rules do not affect historical data. |
| **Stitching**<br/>Cross-device and cross-channel identity resolution that links events to a single person. | Supported. Stitched identities can be included in data feed exports when stitching is configured on the connection. | Not supported. Visitor identity is determined at collection time from visitor ID cookies; no post-collection cross-device resolution is available. |
| **Delivery frequency**<br/>Determines how often the data feed is sent and the window of time included in the feed. | **Daily** (midnight to midnight in the data view's time zone) or **Hourly**. | **Daily** (midnight to midnight in the report suite's time zone) or **Hourly**. <p>15-minute feeds are possible but not available by default.</p> |
| **Late-arriving hits**<br/>Hits whose timestamps belong to a previous delivery frequency window but arrive after that window already elapsed. <p>For example, late-arriving hits could come from a mobile app that buffers events while offline and sends them when it reconnects.</p> | The **Processing delay** setting controls how long the system waits after the frequency window closes before triggering the export, allotting extra time for delayed data to arrive. | Late-arriving hits can be **included or excluded** via the **Late-arriving hits** configuration option. <p>The **Lookback window** setting controls how far back the system reaches to include delayed data.</p> |
| **Out-of-order hits**<br/>Hits whose timestamps don't match the order in which they were received. | Because Customer Journey Analytics accepts both streaming and batch data, there is no guarantee that events for a given person will arrive in timestamp order. Although Customer Journey Analytics reorders by timestamp per person, it can only export the data that has arrived. This means that late-arriving hits might be exported after hits with a later timestamp.<p>The **Processing delay** setting helps reduce out-of-order events in data feed output by giving more time for batch data to arrive before the export. Event ordering in the delivery is not guaranteed.</p><p>**Important**: The ultimate consumer of your data feed data must be able to handle timestamps that are out of order, per person, because hit ordering in the data feed delivery is not guaranteed.</p> | Adobe Analytics requires that data arrive in order per visitor at collection time, but hit ordering in the data feed delivery is not guaranteed.|
| **Backfill window**<br/>Exports historical data between two past dates. | Limited to the connection's rolling data window. | Limited to the report suite data retention limit: **25 months** by default. |
| **Schema**<br/>The data feed schema determines which columns are available to include in a data feed. | The data feed schema is based on the data view configuration.  The components that are available to include in the data feed schema are a subset of the components available in the data view configuration. | A pre-defined, static list of ~1,100+ variables. Many columns are exported as **pre- and post-processed pairs** (for example, `eVar1` / `post_eVar1`), which accounts for much of the column count. |
| **Data feed builder**<br/>The interface used to configure which columns are included in a data feed. | Uses a component rail with the same named dimensions and metrics available in the data view, matching the Analysis Workspace experience. | Uses a flat list of raw variable names (such as `eVar1`, `prop5`) selected from a pre-defined set of ~1,100+ columns. Components are not named or described beyond their variable identifier. |
| **Derived fields**<br/>Custom components defined using rule-based transformations applied at report time. | Supported. Derived field components can be included in the data feed schema alongside standard dimensions and metrics. | Not supported. |
| **Component updates**<br/>Whether changes to component configuration are reflected in past and future data feed output. | Changes to components in the data view (such as renaming or removing a dimension) propagate to future data feeds and are also reflected in backfills. | Changes to components in the report suite apply only to data that is collected in the future. |
| **Lookups**<br/>Lookup datasets in Customer Journey Analytics are the equivalent of classifications in Adobe Analytics. | All lookups are embedded directly in the data. | Classifications are not included with Adobe analytics data feeds. |
| **Session definition**<br/>How a visit or session boundary is defined, which affects how events are grouped and attributed. | Defined in the data view. | Defined at collection time. |
| **Segmentation**<br/>The ability to filter data feed output using segments. | Segments applied to the data view are automatically inherited by the data feed. Additional segments can also be applied directly to an individual data feed. For more information, see [Segmentation in data feeds](/help/components/exports/cja-data-feeds/df-segmentation.md). | Not supported. Data feeds export all collected data without segment filtering. |
| **Calculated metrics**<br/>Custom metrics that you can create from existing metrics. | Not supported | Not supported |
| **Persistence model**<br/>How or whether dimension values persist from one event to the next. | Flexible. Persistence settings from the data view (allocation and expiration) are applied at report time when the feed is generated. Supports all allocation settings available in a data view: **Original**, **Most Recent**, **All**, **First Known**, and **Last Known**. | Only **most recent (last touch)** and **original value (first touch)** attribution models are represented. Linear allocation is handled the same as last touch. |
| **Output file format**<br/>The format used for data feed output files delivered to your cloud destination. | Parquet<p>Natively supports complex nested and structured data. Fields such as `post_product_list` are represented as structured arrays/nested objects. </p><p>Requires a Parquet-aware tool to read, such as BigQuery, Snowflake, or Apache Spark.</p><p>The schema structure is embedded within the output file.</p> | TSV<p>Flat, human-readable rows. Does not natively support structured data; complex fields such as product lists must be encoded as proprietary delimited strings requiring custom parsing logic.</p> |
| **Output file paths**<br/>The directory structure used for delivered output files. | Uses **Hive-style partition paths** (for example, `year=2024/month=01/day=15/`), enabling efficient partition pruning when querying data in data lake environments such as Databricks or Apache Spark. | Uses a flat directory structure. Hive-style paths are not supported. |
| **Delivery destinations**<br/>The cloud storage locations where data feed output files can be sent. | Amazon S3, Azure RBAC, Azure SAS, Google Cloud Platform. | Amazon S3, Azure RBAC, Azure SAS, Google Cloud Platform. <p>Also supports **SFTP**.</p> |
| **Similarity to Analysis Workspace**<br/>Whether the data feed builder uses the same components and terminology as Analysis Workspace. | The left rail in data feeds is similar to the Workspace left rail, and components that are available in data feeds are also available in Workspace. | A static list of variable names that do not necessarily match what you see in Analysis Workspace. |
| **Persistence model availability**<br/>The persistence models that are available for dimensions in a data feed. | Five persistence models are available for data feeds: Original, Most Recent, All, First-Known, Last-Known | Two persistence models are available for data feeds: First-Touch and Last-Touch |

{style="table-layout:auto"}

