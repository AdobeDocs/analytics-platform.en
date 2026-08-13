---
title: Configure the lookback date range in a data feed
description: Learn how the lookback date range controls which events are included in a data feed and how it differs from the Analysis Workspace reporting window.
keywords: clickstream;data feed;datafeed;Data Feed
feature: Components
hide: true
---

# Lookback date range

{{release-limited-testing}}

The lookback date range controls how far back Customer Journey Analytics looks when finding events that qualify for a data feed delivery. The default is 30 days.

This setting does not change the frequency window (hourly or daily). The frequency window determines the time frame of events included in a given delivery. However, events that fall outside the frequency window can still be included if they occurred within the lookback date range. Whether an event is included depends on the following factors:

- **Segment qualification**: When a segment is applied to your data feed definition, any events within the lookback date range determine whether a person qualifies. The segment's container setting determines the scope.

  For example, if a segment called *people who purchased* is applied:
  - A one-week lookback includes events for the given hour or day (the frequency window) for people who purchased in the last 7 days.
  - A 90-day lookback includes events for people who purchased in the last 90 days.

- **Session calculation**: Session boundaries are calculated using data within the lookback date range.

- **Derived field transformations**: Any derived field functions that reference containers use the lookback date range in data feed exports.

- **Dimension persistence**: If you set persistence on a dimension, you also choose an expiration that determines how long a dimension item persists beyond the event it is set on. The lookback date range affects dimension persistence when the expiration is configured in the data view as follows:
  - For dimensions that use **Reporting Window** as the expiration, the lookback date range becomes the new reporting window.
  - For dimensions that use **Custom Time** as the expiration, if the custom time extends beyond the lookback date range, the custom time is ignored and the lookback date range is used instead.

  For more information, see [Persistence component settings](/help/data-views/component-settings/persistence.md).

## Choose the right lookback date range

Consider the following when configuring the lookback date range:

- **Performance vs. completeness**: A longer lookback date range typically includes more events; a shorter range results in better delivery performance.

- **Dimension persistence alignment**: Set the lookback date range to a value equal to or greater than the longest persistence set on any dimension in your feed. For example, if a campaign dimension has a 30-day expiration and a person clicked on that campaign two weeks ago, a 7-day lookback date range would not persist that value.

## Lookback date range vs. Analysis Workspace reporting window

The lookback date range in data feeds is similar to the reporting date range in Analysis Workspace — both determine how far back Customer Journey Analytics looks when finding qualifying events. However, key differences between the two can result in data discrepancies between Workspace reports and data feed deliveries.

### Similarities

Both the lookback date range and the Analysis Workspace reporting date range determine how far back Customer Journey Analytics looks when finding events that qualify for a data feed delivery or a Workspace report.

### Differences

| | Reporting date range (Analysis Workspace) | Lookback date range (Data feeds) |
| --- | --- | --- |
| **Data boundary** | Flexible. Events that fall outside the reporting date range can still be included in a Workspace report if they are influenced by dimension persistence, segment qualification, session calculation, or derived field transformations. | Fixed. Events that fall outside the lookback date range are never included in a data feed, regardless of dimension persistence, segment qualification, session calculation, or derived field transformations. |
| **Reporting window** | The same as the reporting window — the time frame you want to report on. | Not the same as the time frame you want to report on. The time frame to report on is the frequency window, which is a single hour or a single day. |
| **Default** | 90 days | 30 days |

>[!BEGINSHADEBOX]

**Example**

Event A occurred 85 days ago and sits on a dimension with a 90-day persistence setting, such as a campaign-click attribution window.

- **Analysis Workspace**: The event is included in the report because 85 days falls within the default 90-day reporting window and the dimension's persistence extends to 90 days.
- **Data feed with a 30-day lookback**: The event is not included because 85 days falls outside the 30-day lookback date range. Even though the dimension persistence setting is 90 days, the lookback date range takes precedence.

![Data differences between workspace and data feeds](assets/data-feed-data-differences.png)

>[!ENDSHADEBOX]

## Other reasons for data discrepancies

Beyond the lookback date range, the following factors can also cause discrepancies between data feed deliveries and Analysis Workspace reports.

| Factor | Data feeds | Analysis Workspace |
| --- | --- | --- |
| **Stitching replays** | Reflects stitched identity at the time of export only. Replay results are not applied retroactively to exported files. | Displays the most current stitched data, updated retroactively each time a replay runs. Historical data changes after each replay, so Workspace always reflects the latest identity resolution. |
| **Late-arriving events** | Exports data within a fixed time window based on when events are received. Events that arrive after the window closes might not be included, depending on the lookback window you choose. | Processes data at report time, so events are included in reports regardless of when they were received. |
| **Data batching** | Distributes batched data across each day or hour based on the original timestamps. For example, a batch containing 30 days of data is spread over 30 days of exports, so only a small slice appears in any single export. | Displays all data in a batch as soon as it is fully processed, regardless of the time range included in the batch. |
