---
title: Segmentation in data feeds
description: Learn how to apply segments to Customer Journey Analytics data feeds and understand how date range segments interact with the feed's reporting window.
keywords: clickstream;data feed;datafeed;segmentation;segments;date range
feature: Components
hide: true
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
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
---

# Segmentation in data feeds

{{release-limited-testing}}

Data feeds in Customer Journey Analytics support segmentation, letting you filter which rows are included in each feed delivery. You can apply segments at the data view level, the feed level, or both.

## Where segments are applied

You can apply segments to a data feed in two places:

- **Data view**: A segment configured in the data view that applies to all feeds using that data view.
- **Data feed**: A segment applied directly to an individual feed, in addition to any data view segment.

When both are configured, Customer Journey Analytics combines them — only rows that satisfy both segments are included in the feed output.

## Segments that include a date range

You can use segments that include date ranges within a data feed. However, the reporting window is always defined by the feed's scheduled delivery (hourly or daily). If a segment contains a date range, it filters rows within the data feed window without shifting or expanding the window itself.

This is different from Analysis Workspace, where applying a segment that includes a date range changes the active reporting window to match the segment's date range. 

## Segment qualification and the lookback date range

For segments that use a Person or Session container, qualification is determined by the **Lookback date range** setting, not just the delivery window. If a person qualifies within the lookback date range, all of that person's events in the delivery window are included. The container setting determines the scope:

- **Event container**: Only events that match the segment criteria within the delivery window are included.
- **Session container**: All events in qualifying sessions within the delivery window are included, where session qualification is evaluated over the lookback date range.
- **Person container**: All events within the delivery window are included for any person who qualifies during the lookback date range.

For more information about the lookback date range and how it affects segment qualification, see [Create a data feed](/help/components/exports/cja-data-feeds/create-feed.md).

