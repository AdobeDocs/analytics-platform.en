---
title: Total Population Reporting
description: Learn about total population reporting in Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Connections
role: Admin
---

# Total Population Reporting

Total Population Reporting introduces the ability to analyze and report on entities defined in profile and lookup datasets and beyond time-based series of events from event datasets. This ability enables new classes of queries, metrics, and audience definitions that reflect the full scope of a business's customer base.

Originally, Customer Journey Analytics is built around events. Every metric, every visualization, every panel, every report is anchored to a date time range and events occurring during that data time range. You ask the solutions questions like:

| Question | Event | Date time range |
|---|---|---|
| How many people made a purchase last week? | purchase | last week |
| How many accounts visited the pricing page in Q1 (date/time range)? | visit | Q1 |
  
The workspace panel's date time range filters the data, and your dimensions and metrics describe what happened during that date time range.

But not every question your business needs to answer is about something that happened. Sometimes you need to know about your population itself.

| Question | Event | Date time range |
|---|---|---|
|How many active customers do we have right now? | N/A | N/A |
| How many accounts are in our database? | N/A | N/A |
| How many of our members haven't made a purchase in the last 30 days? | N/A | last 30 days |

These questions aren't about events but about people and accounts that exist whether or not these people or account have done anything recently. 

Total Population Reporting introduces a new class of metrics that report on profile data. That profile data is persons and accounts in your profile datasets is independent of a panel's date range. With Total population reporting, you can mix population-based metrics and event-based metrics in the same analysis, getting a fuller picture of both who your customers are and what they've done.

Total Population Reporting enables Customer Journey Analytics to report on all entities defined in profile and lookup dataserts, regardless of event activity. This reporting includes:

* **Profile-based queries**: Analyze attributes (irrespective of events) of profiles (all people, accounts, opportunities, and buying groups).
* **Profile minus event querie**s: Identify profiles (all people, accounts, opportunities, and buying groups) that did not perform a specific action or experience during the reporting window.
* **Shared lookups**: Support reuse of lookup datasets across multiple entities to reduce ingest costs and improve performance.
* **Classification-based queries**: (future enhancement) Analyze lookup datasets such as product catalogs, including items not tied to events.



## Total population reporting metrics

Total population reporting metrics behave differently from the metrics typically used in Customer Journey Analytics:

* Total population reporting metrics are not bound to the panel date range. A total population reporting metric like **[!UICONTROL Total People (Profile)]** returns the current population from your profile dataset, regardless of the date range applied to the panel. Date filters and ranged comparisons do not affect total population reporting metrics the way these filtes and comparison affect event metrics.
* Total population reporting requires a profile dataset on the connection. Total population reporting metrics only appear when your connection includes at least one profile dataset alongside at least one event dataset. Connections with only event datasets continue to work exactly as before and do not show total population reporting metrics.

In Workspace, total population metrics are marked with a distinct icon (TBD) so you can quickly identify which metrics respect the panel's date range and which metrics do not. Total population metrics can be used alongside event metrics in most places, but a visualization types that depend on event sequences (like Fallout and Flow) are not supported.

### Standard total population metrics

Three standard TPR metrics ship out of the box, available on any data view whose connection includes a profile dataset:

Total People (Profile) the total count of people in the profile dataset
Total Accounts (Profile): the total count of accounts in the profile dataset (B2B connections)
Total People (Profile + Event): a union count combining profile-scoped people with event-scoped people

You can also create custom metrics with any of the three scopes, using fields from your profile datasets.

## Requirements and prerequisites

Before TPR metrics can appear in your data view, several prerequisites must be in place.


### Connection requirements

An event dataset is required. Every CJA connection must include at least one event dataset. Profile-only connections are not supported.
At least one profile dataset must be added to the connection. TPR metrics will not appear in data views built on connections that contain only event data.
Shared Lookups must be configured for each profile dataset. Shared Lookups define how each profile dataset is joined to the events in your connection — the matching key, the namespace (for identity-map fields), and the join path. See Configuring Shared Lookups for details.

#### Profile dataset configuration

When a profile dataset is added to a connection, CJA pre-fills a default Shared Lookup configuration based on the dataset type:

For person profile datasets: the default is match-by-container set to Person, with the identity map as the key field. You can edit this default — for example, to choose a specific namespace from the identity map rather than the primary key, or to specify a secondary namespace for cases where the first isn't populated (common with stitched datasets).
For account profile datasets (B2B): the default is match-by-container set to Account (or Global Account, if global accounts are enabled on the connection). The account field can be a single identifier or an identity map; when it's an identity map, you select the namespace to use.

You can configure multiple Shared Lookups on a single profile dataset to support multiple join paths to your events. When the same identity map is used as the key field across multiple Shared Lookups, the namespace selections must be consistent.

### Data view requirements

For TPR metrics to work correctly on a data view:

The connection must include a profile dataset (see above). If you remove the last profile dataset from a connection, TPR metrics will no longer be available on data views built from it.
Data view-level segments must not be event-explicit. If a segment applied directly to the data view is defined entirely in terms of event-scoped conditions (for example, "hit where page = X"), TPR will not be possible on that data view. Before relying on TPR metrics, validate that any data-view-level segments are compatible with profile-scoped reporting.
The metric scope must be set correctly. When creating a custom metric in the data view builder, choose the appropriate scope (event, profile, or profile + event) based on the field's dataset and how you want the metric to behave. The scope cannot be changed after the metric is used in audiences or recurring reports without breaking those dependencies.

### Audience considerations
Audiences built on TPR metrics carry a dependency on those metrics remaining present in the data view:

A recurring audience that uses a TPR metric will fail and move to an ERROR state if that metric is later removed from the data view.
The CJA UI prevents removal of a metric while any active recurring audience depends on it, and surfaces guidance on the dependency before you confirm removal.

### Workspace compatibility

TPR metrics can be used alongside event-based metrics in most Workspace contexts — freeform tables, line and bar visualizations, cohort tables when configured appropriately, and so on. A few visualization types are not supported because they depend inherently on event sequences:

Fallout
Flow
(additional unsupported visualization types to be confirmed before publication)

When you add a TPR metric to an unsupported visualization, Workspace will indicate that the metric cannot be used in that context.

### Permissions

(To be confirmed: any role/feature-access requirements on the customer's IMS org or product profile before TPR is visible. Worth flagging to PM before publication.)