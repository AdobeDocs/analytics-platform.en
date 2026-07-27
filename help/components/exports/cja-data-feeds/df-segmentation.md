---
title: Segmentation in Customer Journey Analytics Data Feeds
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
- **Data Feed**: A segment applied directly to an individual feed, in addition to any data view segment.

When both are configured, Customer Journey Analytics combines them — only rows that satisfy both segments are included in the feed output.

## Date range segments

Segments that reference date ranges are supported in data feeds. However, the behavior differs from Analysis Workspace in an important way: **date range conditions in a segment do not override the reporting date range of the feed.**

In Analysis Workspace, applying a date range segment changes the active reporting window to match the segment's date range. In data feeds, the reporting window is always defined by the feed's scheduled delivery (hourly or daily). A segment with a date range condition filters rows within that window — it does not shift or expand the window itself.

This design is intentional. Allowing date range segments to override the reporting window could cause an hourly feed to deliver a much larger window of data than expected, leading to data duplication or excessive output volume.

### Examples

**Example 1 — Segment that includes events from a specific date**

Suppose you apply a segment that returns only events from July 1 and run the feed for July 22:

- The feed delivery window remains July 22.
- The segment filters out all rows, because no events within the July 22 window match the July 1 criteria. The feed runs but delivers no rows.
- If you run a backfill for July 1, the segment behaves as expected — only events matching the July 1 criteria are included.

**Example 2 — Segment that excludes events from a specific date**

Suppose you apply a segment that excludes all events with an order on July 1 and run the feed for July 22:

- The segment applies to the July 22 data. Because there are no July 1 events in the July 22 window, nothing is excluded and all rows are delivered.
- If you run a backfill for July 1, the segment excludes the relevant rows as expected.

## Segments with multiple conditions

For segments that combine date range conditions with other criteria, Customer Journey Analytics evaluates the date range portion as a row filter only — not as a reporting window override. All conditions in the segment are honored within the feed's delivery window.

## Segment qualification and the lookback date range

For segments that use a Person or Session container, qualification is determined by the **Lookback date range** setting, not just the delivery window. If a person qualifies within the lookback date range, all of that person's events in the delivery window are included. The container setting determines the scope:

- **Event container**: Only events that match the segment criteria within the delivery window are included.
- **Session container**: All events in qualifying sessions within the delivery window are included, where session qualification is evaluated over the lookback date range.
- **Person container**: All events within the delivery window are included for any person who qualifies during the lookback date range.

For more information about the lookback date range and how it affects segment qualification, see [Create a data feed](/help/components/exports/cja-data-feeds/create-feed.md).

## Comparison to Analysis Workspace

| Behavior | Analysis Workspace | Data feeds |
|---|---|---|
| Date range segment overrides reporting window | Yes | No |
| Segment filters rows within the reporting window | Yes | Yes |
| Data view segment applies | Yes | Yes |
| Additional segment applied directly to the delivery | No | Yes |

{style="table-layout:auto"}
