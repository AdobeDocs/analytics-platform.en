---
title: Use Derived Fields in Data Feeds
description: Learn how to use derived fields in data feeds.
hide: true
feature: Components
---
# Use derived fields in data feeds

{{release-limited-testing}}

You can perform data transformations on your data feed data using [derived fields](/help/data-views/derived-fields/derived-fields.md).

Many derived field functions perform transformations that you could also apply using SQL, such as replacing values, combining fields, or converting a field's data type, so the method you choose is sometimes a matter of preference.

## Derived fields vs. SQL

The following table compares the advantages and disadvantages of using derived fields or SQL.

| Method | Advantages | Disadvantages |
| --- | --- | --- |
| **Derived fields** | <ul><li>The same logic applies consistently in both Analysis Workspace and your data feed output, because derived fields are included as components in your data feed schema, alongside standard dimensions and metrics.</li><li>Some transformations, particularly those that depend on a Scope setting or that parse a URL, are difficult to replicate in SQL.</li></ul> | Adds processing overhead, which can affect data feed delivery performance.<!--Under a future usage-based pricing model, this could also add cost.--> |
| **SQL** | <ul><li>Not limited by the function and operator limits that apply to derived fields.</li><li>Has no effect on data feed delivery performance.</li></ul> | <ul><li>Logic doesn't apply in Analysis Workspace, so you'd need to duplicate it there separately.</li><li>Some transformations, particularly those that depend on a Scope setting or that parse a URL, are difficult or impractical to replicate.</li></ul> |

{style="table-layout:auto"}

## Derived field functions

The following table describes each derived field function, whether it is best suited to a derived field or to SQL, and any considerations to keep in mind before using it.

| Derived field function | Difficulty replicating using SQL | Best fit (Derived field or SQL) | Considerations |
| --- | --- | --- | --- |
| [**Case When**](/help/data-views/derived-fields/derived-fields.md#casewhen)<br/>Applies conditionals based on criteria from one or more fields, then sets the output value based on which condition matches. | Easy to moderate | Either | Reproducible in SQL, but using a derived field keeps the same logic applied consistently in both Analysis Workspace and the data feed output. This is especially useful when a large number of rules are involved, such as a marketing-channel classification. |
| [**Classify**](/help/data-views/derived-fields/derived-fields.md#classify)<br/>Defines a set of values that are replaced by corresponding values in a new derived field. | Easy to moderate | Either | Reproducible in SQL, but using a derived field keeps the same logic applied consistently in both Analysis Workspace and the data feed output. |
| [**Concatenate**](/help/data-views/derived-fields/derived-fields.md#concatenate)<br/>Combines field values into a single new derived field using defined delimiters (for example, page name and marketing channel). | Easy to moderate | Either | Mirrors the functionality of adding multiple dimension columns to a freeform table, which is limited to Full Table Export. A derived field makes similar output available in a data feed. |
| [**Date Math**](/help/data-views/derived-fields/derived-fields.md#datemath)<br/>Returns the difference between two date or date-time fields (for example, days between a booking date and a check-in date), with a Scope of Event, Session, or Person. | Difficult | Derived field | Complex to replicate in SQL. This function depends on a Scope setting. For more information, see [How Scope settings in functions affect data feeds](#scope-settings). |
| [**Deduplicate**](/help/data-views/derived-fields/derived-fields.md#dedup)<br/>Prevents counting a value multiple times, with a Scope of Person or Session (for example, deduplicating a booking confirmation ID). | Difficult | Derived field | This function depends on a Scope setting. For more information, see [How Scope settings in functions affect data feeds](#scope-settings). |
| [**Depth**](/help/data-views/derived-fields/derived-fields.md#depth)<br/>Returns the depth of a field, similar to the standard Event Depth dimension (for example, internal search depth). | Difficult | Derived field | Uses session as the scope, and it is not configurable. <!-- Open question as of 2026-09-09: does the Depth counter carry over across an hourly/daily feed boundary using lookback-window context, or does it restart? Pending confirmation from engineering (Ron Fulkerson / Nate Purser). --> How the counter behaves when a session spans a feed-delivery boundary is still being confirmed with engineering. This function depends on a Scope setting. For more information, see [How Scope settings in functions affect data feeds](#scope-settings). |
| [**Find and Replace**](/help/data-views/derived-fields/derived-fields.md#find-and-replace)<br/>Finds all values in a selected field and replaces them with a different value. | Easy to moderate | Either | Reproducible in SQL, but using a derived field keeps the same logic applied consistently in both Analysis Workspace and the data feed output. |
| [**Lookup**](/help/data-views/derived-fields/derived-fields.md#lookup)<br/>Looks up a value from a lookup dataset using a matching key and returns it in a new derived field. | Easy to moderate | Either | SQL works if a lookup table already exists. |
| [**Lowercase**](/help/data-views/derived-fields/derived-fields.md#lowercase)<br/>Converts values from a field to lowercase. | Easy to moderate | Either | Reproducible in SQL, but using a derived field keeps the same logic applied consistently in both Analysis Workspace and the data feed output. |
| [**Math**](/help/data-views/derived-fields/derived-fields.md#math)<br/>Applies basic mathematical operators (add, subtract, multiply, divide, or raise to a power) to numeric fields, evaluated hit-by-hit. | Easy to moderate | Either | Reproducible in SQL, but using a derived field keeps the same logic applied consistently in both Analysis Workspace and the data feed output. |
| [**Merge Fields**](/help/data-views/derived-fields/derived-fields.md#merge)<br/>Checks whether the first of two or more fields has a value; if not, uses the next field, and so on. | Easy to moderate | Either | None |
| [**Next or Previous**](/help/data-views/derived-fields/derived-fields.md#next-previous)<br/>Resolves the next or previous value of a Visit or Event table field, with a Scope of Person or Session. | Difficult | Derived field | This function depends on a Scope setting. For more information, see [How Scope settings in functions affect data feeds](#scope-settings). |
| [**Regex Replace**](/help/data-views/derived-fields/derived-fields.md#regex-replace)<br/>Replaces a value from a field using a regular expression. | Easy to moderate | Either | Reproducible in SQL, but using a derived field keeps the same logic applied consistently in both Analysis Workspace and the data feed output. |
| [**Split**](/help/data-views/derived-fields/derived-fields.md#split)<br/>Splits a value from a field into a new derived field (for example, converting a delimited list into an array). | Easy to moderate | Either | Reproducible in SQL, but using a derived field keeps the same logic applied consistently in both Analysis Workspace and the data feed output. |
| [**Summarize**](/help/data-views/derived-fields/derived-fields.md#summarize)<br/>Applies aggregation functions (such as sum, count, or most common) to a field, with a Scope of Event, Session, or Person. | Difficult | Derived field | This function depends on a Scope setting. For more information, see [How Scope settings in functions affect data feeds](#scope-settings). |
| [**Trim**](/help/data-views/derived-fields/derived-fields.md#trim)<br/>Trims whitespace, special characters, or a set number of characters from the beginning or end of a field's values. | Easy to moderate | Either | Reproducible in SQL, but using a derived field keeps the same logic applied consistently in both Analysis Workspace and the data feed output. |
| [**Typecast**](/help/data-views/derived-fields/derived-fields.md#typecast)<br/>Changes a field's data type to make it available for additional transformations. | Easy to moderate | Either | Reproducible in SQL, but using a derived field keeps the same logic applied consistently in both Analysis Workspace and the data feed output. |
| [**URL Parse**](/help/data-views/derived-fields/derived-fields.md#urlparse)<br/>Parses out parts of a URL, including the protocol, host, path, query string parameter, or hash value. | Difficult | Derived field | Difficult for a different reason than the Scope-dependent functions above: it has no Scope setting and no lookback-window risk. SQL requires custom string parsing to extract the same components. |

{style="table-layout:auto"}

### How Scope settings in functions affect data feeds {#scope-settings}

[!UICONTROL **Date Math**], [!UICONTROL **Deduplicate**], [!UICONTROL **Next or Previous**], and [!UICONTROL **Summarize**] each depend on a [!UICONTROL **Scope**] setting of Event, Session, or Person (the available options vary by function). [!UICONTROL **Depth**] has no configurable Scope field, but is inherently tied to the session, similar to the standard Event Depth dimension. Any field with a scope writes the same value to every row within that scope, and that value depends on the data within the lookback date range.
<!-- Open question as of 2026-09-09: is the lookback date range boundary anchored to a fixed point (e.g., midnight), or does it float with the feed run time, and is this configurable? Pending confirmation from Ron Fulkerson. -->

Because the [lookback date range](/help/components/exports/cja-data-feeds/create-feed.md#data-feed-lookback-date-range) slides forward with each data feed delivery, the same field can return a different value on a later delivery, even for events that already occurred.

Risk increases with scope size: Person scope carries more risk than Session scope, because a person's history has no natural time boundary within a feed run.

## Derived field function templates

[Derived field function templates](/help/data-views/derived-fields/derived-fields.md#templates) let you quickly create a derived field for a specific use case, such as building marketing channels, detecting bots, or extracting a UTM parameter from a URL. Because a template is built from a chain of pre-built rules, using one is almost always preferable to reproducing the same logic in SQL from scratch.

If a template includes a function that depends on a Scope setting, the template inherits that function's scope caution. See [How Scope settings in functions affect data feeds](#scope-settings).

