---
title: Total Population Reporting
description: Use total population reporting in Customer Journey Analytics to analyze profiles and accounts in your datasets, independent of event activity or panel date ranges.
solution: Customer Journey Analytics
feature: Connections
role: Admin
hide: true
---
# Total population reporting

Total population reporting introduces the ability to analyze and report on entities defined in profile and lookup datasets and beyond time-based series of events from event datasets. This ability enables new classes of queries, metrics, and audience definitions that reflect the full scope of a business's customer base.

Customer Journey Analytics is built around events. Every metric, every visualization, every panel, every report is anchored to a date time range and events occurring during that date time range. You ask the solutions questions like:

| Question | Event | Date time range |
|---|---|---|
| How many people made a purchase last week? | purchase | last week |
| How many accounts visited the pricing page in Q1? | visit | Q1 |

The workspace panel's date time range filters the data, and your dimensions and metrics describe what happened during that date time range.

But not every question your business needs to answer is about something that happened. Sometimes you need to know about your population itself.

| Question | Event | Date time range |
|---|---|---|
|How many active customers do we have right now? | N/A | N/A |
| How many accounts are in our database? | N/A | N/A |
| How many of our members haven't made a purchase in the last 30 days? | N/A | last 30 days |

These questions aren't about events but about people and accounts that exist whether or not these people or accounts have done anything recently. 

Total population reporting introduces a new class of metrics that report on profile data. That profile data, which can contain persons and accounts, in your profile datasets is independent of a panel's date range. With total population reporting, you can mix population-based metrics and event-based metrics in the same analysis, providing a more comprehensive picture of both who your customers are and what the customer have done.

Total population reporting enables Customer Journey Analytics to report on all entities defined in profile and lookup datasets, regardless of event activity. This reporting includes:

* **Profile-based queries**: Analyze attributes (irrespective of events) of profiles (all people, accounts, opportunities, and buying groups).
* **Profile minus event queries**: Identify profiles (all people, accounts, opportunities, and buying groups) that did not perform a specific action or experience during the reporting window.
* **Shared lookups**: Support reuse of lookup datasets across multiple entities to reduce ingest costs and improve performance.

<!--
* **Classification-based queries**: (future enhancement) Analyze lookup datasets such as product catalogs, including items not tied to events.
-->



## Total population reporting metrics

Total population reporting metrics behave differently from the metrics typically used in Customer Journey Analytics:

* Total population reporting metrics are not bound to the panel date range. A total population reporting metric like **[!UICONTROL Total People (Profile)]** returns the current population from your profile dataset, regardless of the date range applied to the panel. Date filters and date-range comparisons do not affect total population reporting metrics the way these filters and comparisons affect event metrics.
* Total population reporting requires a profile dataset on the connection. Total population reporting metrics only appear when your connection includes at least one profile dataset alongside at least one event dataset. Connections with only event datasets continue to work exactly as before and do not show total population reporting metrics.

In Workspace, total population metrics are marked with a distinct icon (TBD) so you can quickly identify which metrics respect the panel's date range and which metrics do not. Total population metrics can be used alongside event metrics in most places, but visualization types that depend on event sequences (like Fallout and Flow) are not supported.

### Standard total population reporting metrics

By default, the system includes three standard total population reporting metrics, available on any data view whose connection includes a profile dataset:

* **Total People (Profile)**: the total count of people in the profile dataset.
* **Total Accounts (Profile)**: the total count of accounts in the profile dataset. [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}
* **Total People (Profile + Event)**: a union count combining profile-scoped people with event-scoped people.

You can also create custom metrics with any of the three scopes, using fields from your profile datasets.

## Requirements, prerequisites and considerations

For total population reporting to properly function, prerequisites, requirements and considerations should be taken into account.

### Connection requirements

For a connection to support total population reporting:

* At least one event dataset is required for the connection. Profile-only connections are not supported.
* At least one profile dataset must be added to the connection. Total population reporting metrics do not appear in data views that are built on connections that contain only event data.
* Shared lookups must be configured for each profile dataset. Shared lookups define how each profile dataset is joined to the events in your connection by specifying the matching key, the namespace (for identity-map fields), and the join path.

#### Profile dataset configuration

When a profile dataset is added to a connection, Customer Journey Analytics populates a default shared lookup configuration that is based on the dataset type:

* For person profile datasets: the default is match-by-container set to [!UICONTROL Person], with the identity map as the key field. You can edit this default. For example, to choose a specific namespace from the identity map rather than the primary key. Or to specify a secondary namespace for cases where the first namespace is not populated (which is common with stitched datasets).
* For account profile datasets [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}: the default is match-by-container set to [!UICONTROL Account] (or [!UICONTROL Global Account], if global accounts are enabled on the connection). The account field can be a single identifier or an identity map. When the account field is an identity map, you select the namespace to use.

You can configure multiple shared lookups on a single profile dataset to support multiple join paths to your events. When the same identity map is used as the key field across multiple shared lookups, the namespace selections must be consistent.

### Data view requirements

For total population reporting metrics to work correctly on a data view:

* The connection must include a profile dataset (see [Connection requirements](#connection-requirements)). If you remove the last remaining profile dataset from a connection, total population reporting metrics are unavailable on data views built from it.
* [Data view level segments](/help/data-views/create-dataview.md#settings-segments) must not be event-explicit. If a segment applied directly to the data view is defined entirely in terms of event-scoped conditions (for example, `hit where page = X`), total population reporting is not possible on that data view. Before relying on total population reporting metrics, validate that any data view level segments are compatible with profile-scoped reporting.
* The metric scope must be set correctly. When creating a custom metric component in the data view builder, select the appropriate scope (event, profile, or profile + event) based on the field's dataset and how you want the metric to behave. The scope cannot be changed after the metric is used in audiences or recurring reports without breaking those dependencies.

### Workspace compatibility

Total population reporting metrics can be used alongside event-based metrics in most Workspace contexts: [freeform tables](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md), [line](/help/analysis-workspace/visualizations/line.md), [bar](/help/analysis-workspace/visualizations/bar.md) and [horizontal bar](/help/analysis-workspace/visualizations/horizontal-bar.md) visualizations, [cohort tables](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) when configured appropriately, and so on. A few visualization types are not supported because they depend inherently on event sequences:

* [Fallout](/help/analysis-workspace/visualizations/fallout/fallout-flow.md)
* [Flow](/help/analysis-workspace/visualizations/c-flow/flow.md)
* additional unsupported visualization types to be confirmed before publication.

When you add a total population reporting metric to an unsupported visualization, Workspace indicates that the metric cannot be used in that context.

### Audience considerations

Audiences built on total population reporting metrics depend on those metrics remaining present in the data view:

* A recurring audience that uses a total population reporting metric fails and moves to an ERROR state if the total population reporting metric is removed from the data view.
* The Customer Journey Analytics interface prevents the removal of a metric while any active recurring audience depends on the metric, and surfaces guidance on the dependency before you confirm removal.
  
### Permissions

To be confirmed: any role or feature access requirements on the customer's IMS organization or product profile before total population reporting metrics are visible. Worth flagging to PM before publication.
