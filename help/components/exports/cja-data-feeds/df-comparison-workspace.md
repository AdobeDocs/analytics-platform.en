---
description: Learn how to Compare data feeds functionality in Customer Journey Analytics and Adobe Analytics
keywords: clickstream;data feed;datafeed;Data Feed
title: Compare Data Feeds Functionality in Customer Journey Analytics and Adobe Analytics
feature: Components
hide: true
---
# Understand data descrepancies between data feeds and Analysis Workspace

{{release-limited-testing}}

The data in a data feed export doesn't always match exactly with what you see in Analysis Workspace. Use the following information to understand why:

## Lookback date range (Data feeds) vs. Reporting date range (Analysis Workspace)

The lookback date range in data feeds is similar to the reporting date range in Analysis Workspace, but there are key differences.

### Similarities

Both are used for segment qualification for Person containers and persistence. 

### Differences

A Workspace report adjusts to include segments or dimensions whose persistence or date logic extend beyond the reporting date range. 

| Key differences | Reporting date range (Analysis Workspace) | Lookback date range (Data feeds) |
|---------|---------|----------|
| **Data boundary**<br/>Whether data is included in a report | Flexible<p>Data that falls outside the reporting date range can be included if segments or dimensions include persistence or date logic that cause them to extend beyond the reporting date range.</p><ul><li>**Dimension persistence**: Automatically persist beyond the reporting date range. This is possible because data is aggregated, which mitigates costs.</li><li>**Segments that include date range components**: Extends beyond the reporting date range by default.<p>Users can choose to limit the segment to the reporting date range when they create the segment.</p></li></ul> | Fixed<p>Data is limited to the lookback date range regardless of segment or persistence logic.</p></p><ul><li>**Dimension persistence**: Cannot persist beyond the lookback date range. Data is not aggregated.</li><li>**Segments that include date range components**: Always limited to the Lookback date range.</li></ul> |
| **Reporting window**<br/>The time frame to report on | The same as the reporting window (the time frame that you want to report on). | Not the same as the time frame you want to report on. <p>The time frame to report on is the Frequency window, which can be a single hour or a single day.</p> |



The graphic below illustrates how these differences can result in Workspace reports not exactly matching data feed deliveries. 

In this example, Event A occurred 85 days ago and sits on a dimension with a 90-day persistence setting (e.g. a campaign-click attribution window). The event is included in the Analysis Workspace report and not in the data feed delivery.

![Data differences between workspace and data feeds](assets/data-feed-data-differences.png)


| **Reason for difference** | **Data feeds** | **Analysis Workspace** |
| --------- | ---------- | --------- |
| **Lookback window**<br/>Determines how far back Customer Journey Analytics looks when finding events that qualify for a data feed delivery or a Workspace report. | The lookback window is called the [Lookback date range](/help/components/exports/cja-data-feeds/create-feed.md#create-and-configure-a-data-feed). <p>The lookback is 30 days by default.</p><p>Events can not extend beyond the Lookback date range.</p><p>(Even if events contain segment qualification, session calculation, derived field transformations, or dimension persistence, they can only extend to the time set by the Lookback date range.)</p> | The lookback window is called the **Reporting window**.<p>The lookback is 90 days by default.</p><p>Events can extend beyond the Reporting window.</p><p>(Events can extend beyond the reporting window and still be included in a Workspace report if the events are influenced by segment qualification, session calculation, derived field transformations, and dimension persistence.)</p>|
| **Stitching replays**<br/>Each time a stitching replay runs, historical identity data is retroactively updated. | Reflects stitched identity at the time of export only. Replay results are not applied retroactively to exported files. | Displays the most current stitched data, updated retroactively each time a replay runs. Historical data changes after each replay, so Workspace always reflects the latest identity resolution. |
| **Late-arriving events**<br/>Events that arrive after the data feed export window closes. | Exports data within a fixed time window based on when events are received. <p>Events that arrive after the window closes might not be included in the export. This is influenced by the lookback window you choose.</p> | Processes data at report time, so events are included in reports regardless of when they were received. |
| **Data batching**<br/>Data that is submitted in a batch that spans an extended time period. | Distributes batched data across each day or hour based on the original timestamps. For example, a batch containing 30 days of data is spread over 30 days of exports, so only a small slice appears in any single export. | Displays all data in a batch as soon as it is fully processed, regardless of the time range included in the batch. |

