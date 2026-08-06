---
description: Learn how to Compare data feeds functionality in Customer Journey Analytics and Adobe Analytics
keywords: clickstream;data feed;datafeed;Data Feed
title: Compare Data Feeds Functionality in Customer Journey Analytics and Adobe Analytics
feature: Components
hide: true
---
# Understand data descrepancies between data feeds and Analysis Workspace

{{release-limited-testing}}

Data feed exports don't always match exactly that is exported from Customer Journey Analytics through a data feed will not usually match exactly with data displayed in Analysis Workspace. Use the following information to understand why:

| **Reason for difference** | **Data feeds** | **Analysis Workspace** |
| --------- | ---------- | --------- |
| **Stitching replays**<br/>Each time a stitching replay runs, historical identity data is retroactively updated. | Reflects stitched identity at the time of export only. Replay results are not applied retroactively to exported files. | Displays the most current stitched data, updated retroactively each time a replay runs. Historical data changes after each replay, so Workspace always reflects the latest identity resolution. |
| **Late-arriving events**<br/>Events that arrive after the data feed export window closes. | Exports data within a fixed time window based on when events are received. <p>Events that arrive after the window closes might not be included in the export. This is influenced by the lookback window you choose.</p> | Processes data at report time, so events are included in reports regardless of when they were received. |
| **Data batching**<br/>Data that is submitted in a batch that spans an extended time period. | Distributes batched data across each day or hour based on the original timestamps. For example, a batch containing 30 days of data is spread over 30 days of exports, so only a small slice appears in any single export. | Displays all data in a batch as soon as it is fully processed, regardless of the time range included in the batch. |

