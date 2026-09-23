---
title: Apply Data Transformations for Data Feeds
description: Learn about the different ways to transform data feed data, using component settings, derived fields, or SQL.
hide: true
feature: Components
---
# Apply data transformations for data feeds

{{release-limited-testing}}

You can transform your data feed data using any of the following methods:

* [Data view component settings](/help/data-views/component-settings/overview.md)

* [Derived fields](/help/data-views/derived-fields/derived-fields.md)

* SQL 

Each method has advantages and disadvantages. For specific data transformations, one method might be preferable to another, while the method used for other transformations might be a matter of preference. 

The following sections compare the tradeoffs generally and for specific transformations.

## Compare data transformation methods generally

The following table compares the advantages and disadvantages of each method in general.

| Method | Advantages | Disadvantages |
| --- | --- | --- |
| **Component settings** | <ul><li>Applied at report time, before your data feed is delivered.</li><li>The same logic applies consistently in both Analysis Workspace and your data feed output.</li><li>Doesn't use up one of your account's limited derived fields.</li><li>Some transformations, such as persistence and metric deduplication, are difficult to replicate in SQL, and persistence isn't currently possible with a derived field either.</li></ul> | <ul><li>Only available for the specific set of settings each component supports — not as flexible as building custom logic with a derived field.</li><li>Whether a setting affects data feed output at all is still being confirmed for a few settings. See the table below.</li></ul> |
| **Derived fields** | <ul><li>Applied at report time, before your data feed is delivered.</li><li>The same logic applies consistently in both Analysis Workspace and your data feed output.</li><li>Supports more flexible, custom logic than any single component setting, such as chained conditional rules.</li><li>Some transformations, particularly those that depend on a Scope setting or that parse a URL, are difficult to replicate in SQL.</li></ul> | <ul><li>Adds processing overhead, which can affect data feed delivery performance.<!--Under a future usage-based pricing model, this could also add cost.--></li><li>Uses up one of your account's limited derived fields. If a component setting can do the same job, prefer that instead.</li></ul> |
| **SQL** | <ul><li>Not limited by the function and operator limits that apply to derived fields.</li><li>Has no effect on data feed delivery performance.</li></ul> | <ul><li>Applied after your data feed is already delivered.</li><li>Logic doesn't apply in Analysis Workspace, so you'd need to duplicate it there separately.</li><li>Some transformations, particularly those that depend on a Scope setting, that parse a URL, or that deduplicate or persist a value across a scope, are difficult or impractical to replicate.</li></ul> |

{style="table-layout:auto"}

## Compare methods by specific data transformations

The following table lists specific data transformations, showing which method (or methods) can perform each one, how difficult it would be to replicate in SQL, and which method to use. <!--A few transformations are still being confirmed with the engineering team and are marked as open questions — don't treat those as confirmed to affect data feed output until that's resolved.-->

| Transformation | Component setting | Derived field | Difficulty in SQL | Suggested method | Considerations |
| --- | --- | --- | --- | --- | --- |
| **Apply conditional logic or filter values by criteria** | [Include exclude values](/help/data-views/component-settings/include-exclude-values.md) | [Case When](/help/data-views/derived-fields/derived-fields.md#casewhen) | Easy for strings; moderate to difficult for metrics | Component setting | For string values, comparable across all three — largely a matter of preference. For metrics, SQL requires a `CASE` statement combined with a `COUNT`, which is feasible but more complex, so the component setting is the easier path. |
| **Attribute credit for a success event** | [Attribution](/help/data-views/component-settings/attribution.md) | Not available | Not applicable | Component setting | Not applied to metrics in data feeds. There's no data feed behavior to replicate, in SQL or otherwise. |
| **Bucket numeric values into ranges** | [Value bucketing](/help/data-views/component-settings/value-bucketing.md) | Case When (manual) | Difficult | Component setting | Complexity increases from component setting (easiest) to derived field (moderate, using a manual Case When) to SQL (most complex). |
| **Classify values using a lookup-style mapping** | Not available | [Classify](/help/data-views/derived-fields/derived-fields.md#classify) | Easy / Moderate | Derived fields or SQL | Reproducible in SQL, but using a derived field keeps the same logic applied consistently in both Analysis Workspace and the data feed output. |
| **Combine field values with a delimiter** | Not available | [Concatenate](/help/data-views/derived-fields/derived-fields.md#concatenate) | Easy / Moderate | Derived fields or SQL | Mirrors the functionality of adding multiple dimension columns to a freeform table, which is limited to Full Table Export. A derived field makes similar output available in a data feed. |
| **Convert a field's data type** | Not available | [Typecast](/help/data-views/derived-fields/derived-fields.md#typecast) | Easy / Moderate | Derived fields or SQL | Reproducible in SQL, but using a derived field keeps the same logic applied consistently in both Analysis Workspace and the data feed output. |
| **Count metric occurrences (values vs. instances)** | [Behavior](/help/data-views/component-settings/behavior.md) | Custom Math-based workaround | Easy / Moderate | Component setting | All three approaches work; if you can do it natively in Customer Journey Analytics, there's little reason not to. |
| **Deduplicate a value within a scope** | [Metric deduplication](/help/data-views/component-settings/metric-deduplication.md) | [Deduplicate](/help/data-views/derived-fields/derived-fields.md#dedup) | Difficult | Component setting | Depends on a Scope setting. See [How Scope settings affect data feeds](#scope-settings). The component setting and the derived field are roughly equivalent, but prefer the component setting, since it doesn't use up one of your limited derived fields. |
| **Determine a field's depth within a session** | Not available | [Depth](/help/data-views/derived-fields/derived-fields.md#depth) | Difficult | Derived field | Uses session as the scope, and it is not configurable. <!-- Open question as of 2026-09-09: does the Depth counter carry over across an hourly/daily feed boundary using lookback-window context, or does it restart? Pending confirmation from engineering (Ron Fulkerson / Nate Purser). --> How the counter behaves when a session spans a feed-delivery boundary is still being confirmed with engineering. Depends on a Scope setting. See [How Scope settings affect data feeds](#scope-settings). |
| **Find and replace a literal value** | Not available | [Find and Replace](/help/data-views/derived-fields/derived-fields.md#find-and-replace) | Easy / Moderate | Derived fields or SQL | Reproducible in SQL, but using a derived field keeps the same logic applied consistently in both Analysis Workspace and the data feed output. |
| **Format a value for display** | [Format](/help/data-views/component-settings/format.md) | Not available | Difficult | Component setting | Date-time formatting isn't yet reflected in data feed output — feeds currently show the standard timestamp regardless of this setting, though Adobe plans to support this for general availability. Whether numeric formats (decimal, currency, percent) on metrics affect data feed output is still being confirmed with the team. |
| **Group dimensions from summary datasets** | [Summary data group](/help/data-views/component-settings/summary-data-group.md) | Not available | | Component setting | Not yet discussed with the team. Don't assume this affects data feed output until confirmed. |
| **Handle a blank ("no value") field** | [No value options](/help/data-views/component-settings/no-value-options.md) | Not available | | Component setting | Whether this affects data feed output — including whether a blank value is sent as null, and whether "Treat as a value" changes the underlying data — is still being reviewed with the team. |
| **Look up a value from a lookup dataset** | Not available | [Lookup](/help/data-views/derived-fields/derived-fields.md#lookup) | Easy / Moderate | Derived fields or SQL | SQL works if a lookup table already exists. |
| **Lowercase a string** | [Behavior](/help/data-views/component-settings/behavior.md) | [Lowercase](/help/data-views/derived-fields/derived-fields.md#lowercase) | Easy / Moderate | Component setting | Both are equivalent, but prefer the component setting, since it doesn't use up one of your limited derived fields. |
| **Merge multiple fields into one** | Not available | [Merge Fields](/help/data-views/derived-fields/derived-fields.md#merge) | Easy / Moderate | Derived fields or SQL | — |
| **Parse a URL into its components** | [Substring](/help/data-views/component-settings/substring.md) (URL parse method) | [URL Parse](/help/data-views/derived-fields/derived-fields.md#urlparse) | Difficult | Component setting | SQL requires custom string parsing to extract the same components. <!-- Possible discrepancy: in the component settings meeting, Matt and Derek described all Substring methods, including URL parse, as roughly interchangeable across component setting, derived field, and SQL ("either one would work... maybe a preference"), which is a looser SQL-difficulty read than "Difficult." Flagged for Luke to reconcile; not changed without confirmation. --> |
| **Perform basic math on numeric fields** | Not available | [Math](/help/data-views/derived-fields/derived-fields.md#math) | Easy / Moderate | Derived field or SQL | Reproducible in SQL, but using a derived field keeps the same logic applied consistently in both Analysis Workspace and the data feed output. |
| **Persist a dimension value across events** | [Persistence](/help/data-views/component-settings/persistence.md) | Not currently available <!-- Derek: considering adding this to FDL and surfacing it in derived fields; not currently possible. --> | Difficult | Component setting | Much easier to use the component setting than to replicate this logic in SQL. Already confirmed to interact with the lookback date range the same way Scope-dependent derived field functions do. See [Understand the lookback date range](/help/components/exports/cja-data-feeds/create-feed.md#data-feed-lookback-date-range). |
| **Replace a value using a regular expression** | [Substring](/help/data-views/component-settings/substring.md) (Regex method) | [Regex Replace](/help/data-views/derived-fields/derived-fields.md#regex-replace) | Easy / Moderate | Component setting | All three approaches produce the same result; it's a matter of preference. |
| **Resolve the next or previous value in a session** | Not available | [Next or Previous](/help/data-views/derived-fields/derived-fields.md#next-previous) | Difficult | Derived field | Depends on a Scope setting. See [How Scope settings affect data feeds](#scope-settings). |
| **Return the difference between two dates** | Not available | [Date Math](/help/data-views/derived-fields/derived-fields.md#datemath) | Difficult | Derived field | Complex to replicate in SQL. Depends on a Scope setting. See [How Scope settings affect data feeds](#scope-settings). |
| **Scope a metric as event-, profile-, or total-based** | [Scope](/help/data-views/component-settings/scope.md) | Not available | | | <!--Not yet discussed with the team. Don't assume this affects data feed output until confirmed.--> |
| **Split a delimited value** | [Substring](/help/data-views/component-settings/substring.md) (Delimiter or From the Left/Right method) | [Split](/help/data-views/derived-fields/derived-fields.md#split) | Easy / Moderate | Component setting | All three approaches produce the same result; it's a matter of preference. |
| **Summarize or aggregate a value across a scope** | Not available | [Summarize](/help/data-views/derived-fields/derived-fields.md#summarize) | Difficult | Derived field | Depends on a Scope setting. See [How Scope settings affect data feeds](#scope-settings). |
| **Trim characters from a string** | [Substring](/help/data-views/component-settings/substring.md) (Trim method) | [Trim](/help/data-views/derived-fields/derived-fields.md#trim) | Easy / Moderate | Component setting | All three approaches produce the same result; it's a matter of preference. |

{style="table-layout:auto"}

### How Scope settings affect data feeds {#scope-settings}

Date Math, Deduplicate, Next or Previous, and Summarize each depend on a [!UICONTROL **Scope**] setting of Event, Session, or Person (the available options vary by function). Depth has no configurable Scope field, but is inherently tied to the session, similar to the standard Event Depth dimension. Any field with a scope writes the same value to every row within that scope, and that value depends on the data within the lookback date range.
<!-- Open question as of 2026-09-09: is the lookback date range boundary anchored to a fixed point (e.g., midnight), or does it float with the feed run time, and is this configurable? Pending confirmation from Ron Fulkerson. -->

Because the [lookback date range](/help/components/exports/cja-data-feeds/create-feed.md#data-feed-lookback-date-range) slides forward with each data feed delivery, the same field can return a different value on a later delivery, even for events that already occurred.

Risk increases with scope size: Person scope carries more risk than Session scope, because a person's history has no natural time boundary within a feed run.

## Derived field function templates

[Derived field function templates](/help/data-views/derived-fields/derived-fields.md#templates) let you quickly create a derived field for a specific use case, such as building marketing channels, detecting bots, or extracting a UTM parameter from a URL. Because a template is built from a chain of pre-built rules, using one is almost always preferable to reproducing the same logic in SQL from scratch.

If a template includes a function that depends on a Scope setting, the template inherits that function's scope caution. See [How Scope settings affect data feeds](#scope-settings).
