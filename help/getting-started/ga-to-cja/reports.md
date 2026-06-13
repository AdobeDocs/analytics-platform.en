---
title: GA4 reports in Customer Journey Analytics
description: Find the Customer Journey Analytics equivalent for every GA4 report section.
role: User
solution: Customer Journey Analytics
feature: Basics
exl-id: c2d8f4a1-7b3e-4c9f-a5d2-8e1b6c3f9072
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
subfeature_v2:
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
    internal-label: Dimensions
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
    internal-label: Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
---

# GA4 reports in Customer Journey Analytics

Use this page as a lookup reference when you know which GA4 report you're looking at and want to recreate its approximate equivalent in Analysis Workspace. Reports are organized by GA4's navigation sections. For advanced cross-channel reporting scenarios that become available after migrating GA data to Customer Journey Analytics, see [Report on Google Analytics data](/help/use-cases/third-party/ga/report.md).

## Realtime

+++Realtime

GA4's Realtime report shows activity from the last 30 minutes — active users, the events firing, where users are, what's driving traffic, and which pages they're on.

Customer Journey Analytics has no separate real-time report area. Instead, build a panel in Analysis Workspace and enable the **[!UICONTROL Real-time refresh]** toggle (part of the **Ultimate** package) so its visualizations update every minute:

1. Build a [Freeform](/help/analysis-workspace/c-panels/freeform-panel.md) panel (the toggle also works on [Blank](/help/analysis-workspace/c-panels/blank-panel.md), [Attribution](/help/analysis-workspace/c-panels/attribution.md), and [Next or previous item](/help/analysis-workspace/c-panels/next-previous.md) panels) with the dimensions and metrics you want to monitor. To mirror GA4's real-time cards, use **[!UICONTROL Page]**, **[!UICONTROL Event type]**, **[!UICONTROL Referring Domain]**, or **[!UICONTROL Countries]** as the dimension, with **[!UICONTROL Sessions]** as the metric.
2. Enable the **[!UICONTROL Real-time refresh]** toggle and choose a period from **[!UICONTROL Last 15 minutes]** to **[!UICONTROL Last 24 hours]**. Data is limited to a rolling 24-hour window, and the panel refreshes every minute for up to 30 minutes.

Real-time reporting favors event- and session-level data and can't use stitching, so prefer **[!UICONTROL Sessions]** over **[!UICONTROL People]**. See [Use real-time reporting](/help/components/real-time/use-real-time.md) for the full procedure and [Real-time reporting overview](/help/components/real-time/real-time.md) for entitlement and latency details.

+++

## Acquisition

+++User acquisition (first-touch)

GA4's User acquisition report attributes each user to the channel, source, and medium that brought them to your site for the first time, using first-touch attribution.

In Analysis Workspace, apply a **[!UICONTROL First Touch]** attribution model to the **[!UICONTROL Marketing Channel]** dimension. Marketing Channels must be configured before use. See [Create a marketing channel derived field](/help/getting-started/cja-upgrade/cja-upgrade-marketing-channel.md).

1. Drag the **[!UICONTROL Marketing Channel]** dimension into a [[!UICONTROL Freeform table]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md).
2. Right-click a metric column header and select **[!UICONTROL Use non-default attribution model]**.
3. Select **[!UICONTROL First Touch]** with a lookback window appropriate for your analysis.

Alternatively, use the [[!UICONTROL Attribution] panel](/help/analysis-workspace/c-panels/attribution.md) for a side-by-side comparison of first-touch and last-touch channel performance.

+++

+++Traffic acquisition (session-based)

GA4's Traffic acquisition report attributes each session to the channel, source, and medium that initiated it, using session-based attribution. You can break it down by default channel group, source / medium, referrer, or campaign.

In Analysis Workspace, the **[!UICONTROL Marketing Channel]** dimension with the default **[!UICONTROL Last Touch]** attribution model provides session-based channel reporting:

1. Drag the **[!UICONTROL Marketing Channel]** dimension into a [[!UICONTROL Freeform table]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md).
2. Drag desired metrics alongside the default **[!UICONTROL Events]** metric.

GA4's breakdowns map to these Customer Journey Analytics dimensions:

* **Channel**: **[!UICONTROL Marketing Channel]**. Customer Journey Analytics has no built-in channel groupings — define them as a [derived field](/help/data-views/derived-fields/derived-fields.md) using the **[!UICONTROL Marketing channels]** function template, or carry over rules from Adobe Analytics when using the Analytics source connector (see [Use marketing channel dimensions](/help/use-cases/aa-data/marketing-channels.md)).
* **Source / medium and referrals**: **[!UICONTROL Referring Domain]** and **[!UICONTROL Referrer Type]**.
* **Campaign**: GA4's `utm_*` parameters are not collected automatically — each must be mapped to an XDM field during implementation before it appears as a dimension. If campaign values arrive as a tracking code, use the **[!UICONTROL Tracking Code]** dimension.

+++

+++Attribution and conversion paths

GA4's Attribution reports (under Advertising) show how different channels contribute to conversions and allow model comparison and conversion path analysis.

In Analysis Workspace, use the [[!UICONTROL Attribution] panel](/help/analysis-workspace/c-panels/attribution.md):

1. Select the Panels icon and drag an **[!UICONTROL Attribution]** panel onto the canvas.
2. Drag the **[!UICONTROL Marketing Channel]** dimension to the **[!UICONTROL Add Dimension]** box.
3. Drag your conversion metric (for example, a purchase event) to the **[!UICONTROL Add Metric]** box.
4. Select **[!UICONTROL Build]**.

The [!UICONTROL Attribution panel] produces a model comparison table and a [!UICONTROL Channel Flow] visualization showing the top paths visitors took prior to converting. Select **[!UICONTROL Add Model]** to compare multiple attribution models simultaneously.

+++

## Engagement

+++Pages and screens

GA4's Pages and screens report shows performance metrics for individual pages and app screens.

In Analysis Workspace, drag the **[!UICONTROL Page]** dimension into a [[!UICONTROL Freeform table]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) and add your desired metrics. Common metrics include **[!UICONTROL Sessions]**, **[!UICONTROL People]**, **[!UICONTROL Bounce Rate]**, and **[!UICONTROL Time Spent per Session]**.

To group pages by URL path structure (for example, `/blog/` or `/products/`), use the **[!UICONTROL Site Section]** dimension if your implementation defines it, or create a [derived field](/help/data-views/derived-fields/derived-fields.md) that parses the page URL with the **[!UICONTROL URL Parse]** function. If you maintain an explicit page-to-section mapping, a [lookup dataset](/help/connections/standard-lookups.md) can supply the grouping instead.

+++

+++Landing pages

GA4's Landing page report shows which pages users arrive on when they begin a session.

In Analysis Workspace, drag the **[!UICONTROL Entry Page]** dimension into a [[!UICONTROL Freeform table]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md). **[!UICONTROL Sessions]** is the most relevant metric for this dimension.

+++

+++Events

GA4's Events report shows how many times each event fired, with event-level metrics.

In GA4, events have a name and optional parameters (for example, event `video_play` with parameter `video_title`). In Customer Journey Analytics, the standard dimension for the event name is **[!UICONTROL Event type]** (sourced from `xdm.eventType`). Event parameters map to other XDM fields, whose names depend on your implementation.

Drag the **[!UICONTROL Event type]** dimension into a [[!UICONTROL Freeform table]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) to list all event types, alongside the **[!UICONTROL Events]** metric.

+++

+++Key events (conversions)

GA4's Key events report (formerly Conversions) lists each key event by name with its count — events flagged as business-critical in the GA4 property configuration.

Customer Journey Analytics has no "key event" flag; every interaction is an event, so there is no preset list of conversions to open.

To recreate GA4's list of conversions by name, use **segments as rows**. A [[!UICONTROL Freeform table]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) can't place a metric in the row position, but it can place a segment there:

1. For each conversion, create a segment that isolates its events — for example, an event-scoped segment where `xdm.eventType` equals `commerce.purchases`. Name each segment after the conversion it represents (for example, **Purchases**).
2. Drag each conversion segment into the row area of a [!UICONTROL Freeform table], one per row.
3. Add the **[!UICONTROL Events]** metric as the column. Each row shows that conversion's count, mirroring GA4's key-events list. Use **[!UICONTROL People]** instead to count unique converters.

To add a conversion rate, create a calculated metric (select the **+** icon near the metrics list) defined as a conversion metric divided by **[!UICONTROL Sessions]** or **[!UICONTROL People]**.

Each conversion you isolate here can also be defined as a reusable metric in your data view. See the **Key events &rarr; Custom event metrics** entry under [Common metrics](#common-metrics) for how to set that up.

+++

## Monetization

+++Ecommerce purchases

GA4's Ecommerce purchases report shows product-level purchase data including items, revenue, and quantity.

In Customer Journey Analytics, ecommerce reporting uses the **[!UICONTROL Product]** dimension alongside purchase metrics. This report requires that your implementation sends XDM commerce data (such as `xdm.commerce.purchases`, `xdm.commerce.order`, and `xdm.productListItems`).

1. Drag the **[!UICONTROL Product]** dimension into a [[!UICONTROL Freeform table]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md).
2. Drag ecommerce metrics such as **[!UICONTROL Orders]**, **[!UICONTROL Revenue]**, and **[!UICONTROL Units]** alongside the default **[!UICONTROL Events]** metric.

+++

+++Purchase journey (funnel)

GA4's Purchase journey report shows how users move through your shopping funnel — for example, from add to cart to begin checkout to purchase — and where they drop off.

In Analysis Workspace, use the [**[!UICONTROL Fallout]**](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) visualization:

1. Select the Visualizations icon and drag a **[!UICONTROL Fallout]** visualization onto the canvas.
2. Locate the **[!UICONTROL Page]** dimension and expand it to reveal individual page values.
3. Drag the first funnel step (for example, a product page) into the first **[!UICONTROL Add Touchpoint]** slot.
4. Continue adding touchpoints for each step.

The Fallout visualization accepts any dimension, metric, or segment as a touchpoint, not just pages, so it matches GA4's event-based funnels and extends to sequences that mix events, pages, and segments.

+++

+++Promotions

GA4's Promotions report shows how internal promotions (banners, featured placements) drive product interactions.

In Customer Journey Analytics, promotion data requires that you capture promotion impressions and clicks in XDM schema fields. Once collected, create a [[!UICONTROL Freeform table]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) that includes the promotion name dimension with impression and click metrics. Work with your Customer Journey Analytics administrator to confirm what promotion data is available in your data view.

+++

+++Publisher ads

GA4's Publisher ads report shows ad revenue from Google Ad Manager or AdMob for publisher-monetized properties.

Customer Journey Analytics has no native publisher ad-revenue integration. To report this data, ingest the revenue figures from your ad-monetization platform (such as Google Ad Manager or AdMob) into Adobe Experience Platform as a dataset, using a source connector or direct data ingestion. Once ingested, the data is available for reporting in Customer Journey Analytics.

+++

## Retention

+++Retention overview

GA4's Retention overview report combines several retention views — new versus returning users, and a cohort chart showing how many users return over time.

**New vs. returning users**: use the **[!UICONTROL First Session]** and **[!UICONTROL Return Sessions]** segments as rows in a [[!UICONTROL Freeform table]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md):

1. Drag the **[!UICONTROL First Session]** segment from the Components panel into the table's row area, then drag the **[!UICONTROL Return Sessions]** segment below it.
2. Add your desired metrics alongside the default **[!UICONTROL Events]** metric.
3. To trend over time, drag a [**[!UICONTROL Line]**](/help/analysis-workspace/visualizations/line.md) visualization above the table, then ctrl+click (Windows) or cmd+click (Mac) each row to highlight both segments.

**Retention over time**: use the [**[!UICONTROL Cohort Table]**](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) visualization:

1. Select the Visualizations icon and drag a **[!UICONTROL Cohort Table]** onto the canvas.
2. Drag the **[!UICONTROL People]** metric into both the Inclusion and Return Criteria fields, then select **[!UICONTROL Build]**.

The [!UICONTROL Cohort Table] groups people by their initial period and tracks return behavior over subsequent periods; the inclusion, return, and granularity criteria are all configurable.

+++

## User

+++Demographic details

GA4's Demographic details report covers user characteristics — age, gender, and interests (powered by Google Signals, which requires users to be signed into a Google account with personalization enabled) — along with location (country, region, city) and language.

**Location** maps directly to Customer Journey Analytics dimensions: use **[!UICONTROL Countries]**, **[!UICONTROL Regions]**, or **[!UICONTROL Cities]** in a [[!UICONTROL Freeform table]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md), or the [[!UICONTROL Map]](/help/analysis-workspace/visualizations/map.md) visualization for a geographic overview (drag the **[!UICONTROL People]** metric into the **[!UICONTROL Add Metric]** slot and select **[!UICONTROL Build]**).

**Age, gender, and interests** require first-party data. If your organization collects demographic data through CRM, registration forms, or consent-based surveys, ingest it as a [Profile dataset](/help/connections/create-connection.md#profile-dataset) and join it to event data. This approach produces more reliable data than GA4's inferred Google Signals model because it uses consented, first-party attributes.

+++

+++Tech details

GA4's Tech report shows Browser, Operating System, Screen resolution, and Device category.

In Analysis Workspace, the following dimensions map to GA4's Tech dimensions, each sourced from a standard XDM field:

| GA4 Tech dimension | Analysis Workspace dimension | XDM field |
|---|---|---|
| Browser | **[!UICONTROL Browser]** | `xdm.environment.browserDetails.name` |
| Operating system | **[!UICONTROL Operating System]** | `xdm.environment.operatingSystem` |
| Screen resolution | **[!UICONTROL Monitor Resolution]** | `xdm.device.screenWidth`, `xdm.device.screenHeight` |
| Device category (Mobile, Desktop, Tablet) | **[!UICONTROL Mobile Device Type]** | `xdm.device.type` |
| Device model | **[!UICONTROL Mobile Device]** | `xdm.device.model` |

Drag any of these dimensions from the Components panel into a [[!UICONTROL Freeform table]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md).

>[!NOTE]
>
>Because modern browsers have reduced the detail in the User-Agent string, complete and accurate values depend on collecting [User-Agent Client Hints](https://experienceleague.adobe.com/en/docs/experience-platform/collection/use-cases/client-hints) in your Web SDK configuration.

+++

## Explore

+++Free-form exploration

GA4's Free-form exploration is a blank-canvas table with configurable rows, columns, and optional chart overlays.

Analysis Workspace's [**[!UICONTROL Freeform table]**](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) is the direct equivalent and the foundation of most Workspace projects. Drag any dimension into the rows, any metric into the columns, and any segment into the segment drop zone above the table.

See [Getting started in Analysis Workspace](home.md#getting-started-in-analysis-workspace) for terminology mapping between GA4 Explore and Workspace.

+++

+++Funnel exploration

GA4's Funnel exploration defines a sequence of steps and measures completion and drop-off at each step.

In Analysis Workspace, use the [**[!UICONTROL Fallout]**](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) visualization:

1. Select the Visualizations icon and drag a **[!UICONTROL Fallout]** visualization onto the canvas.
2. Drag the dimension, metric, or segment that represents your first step into the first **[!UICONTROL Add Touchpoint]** slot.
3. Continue adding a touchpoint for each subsequent step in the sequence.

Because any dimension, metric, or segment can serve as a touchpoint, [!UICONTROL Fallout] matches GA4's event-based funnels and extends to cross-channel sequences that mix events, pages, and segments.

+++

+++Path exploration

GA4's Path exploration (Universal Analytics called this Users Flow) visualizes the sequences of pages or events that users navigate through.

In Analysis Workspace, use the [**[!UICONTROL Flow]**](/help/analysis-workspace/visualizations/c-flow/flow.md) visualization:

1. Select the Visualizations icon and drag a **[!UICONTROL Flow]** visualization onto the canvas.
2. Drag a value from the dimension you want to path on (for example, a **[!UICONTROL Page]** or **[!UICONTROL Event type]** value) into the center of the flow.
3. The visualization shows what users did before and after that point.

The [!UICONTROL Flow] visualization is interactive — select any node to expand paths further in either direction. Any dimension can be used, so you can path on pages, events, marketing channels, or custom links.

+++

+++Segment overlap

GA4's Segment overlap exploration shows how multiple user segments intersect, visualized as a Venn diagram.

In Analysis Workspace, use the [**[!UICONTROL Venn]**](/help/analysis-workspace/visualizations/venn.md) visualization:

1. Select the Visualizations icon and drag a **[!UICONTROL Venn]** visualization onto the canvas.
2. Drag up to three segments from the Components panel into the visualization.

The Venn diagram shows intersection sizes, and the [[!UICONTROL Freeform table]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) below it shows the underlying data.

+++

+++Cohort exploration

GA4's Cohort exploration groups users by a shared characteristic (typically acquisition date) and tracks their behavior over time.

In Analysis Workspace, use the [**[!UICONTROL Cohort Table]**](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) visualization:

1. Select the Visualizations icon and drag a **[!UICONTROL Cohort Table]** onto the canvas.
2. Drag the **[!UICONTROL People]** metric into both the Inclusion and Return Criteria fields.
3. Select **[!UICONTROL Build]**.

The [!UICONTROL Cohort Table] groups people by their initial period and tracks return behavior over subsequent periods. By default it cohorts on acquisition date, but the inclusion, return, and granularity criteria are all configurable.

+++

+++User explorer

GA4's User explorer shows individual users, their session history, and a timeline of events.

Customer Journey Analytics supports person-level analysis in two ways:

* **With stitching enabled**: Create a segment scoping to a specific person ID value and apply it to any Workspace project. The **[!UICONTROL Person]** container isolates that individual's stitched activity across sessions and channels.
* **Raw event data**: Use **dataset previews** in the Adobe Experience Platform UI to inspect raw XDM event records. This view is useful for implementation validation and debugging individual events.

+++

+++User lifetime

GA4's User lifetime exploration measures each user's accumulated value and engagement across their entire relationship with your business, rather than within a fixed date range. It combines historical lifetime metrics with Google's machine-learning predictions for purchase probability, churn probability, and predicted revenue.

These map to Customer Journey Analytics in two parts:

**Historical lifetime value** is achievable natively. Because Customer Journey Analytics reports across your full data retention window, you can set a long date range and aggregate each person's accumulated revenue and engagement across that lookback. With stitching or a persistent person ID, the **[!UICONTROL Person]** container ties that activity to one individual, and calculated metrics express per-person value. The result is not an unbounded lifetime, but a long, configurable lookback that approximates one.

**Predictive lifetime value** is not built in. Customer Journey Analytics has no in-product purchase-probability, churn, or predicted-revenue model. To use predictive scores, calculate them externally (for example, in a CRM or data-science workflow) and bring them into Customer Journey Analytics as a Profile dataset, then surface them as dimensions or metrics. Adobe recommends working with an implementation consultant to design this approach.

+++

## Common metrics

+++Active users &rarr; People

GA4's **Active users** counts users who had at least one engaged session in the date range.

In Customer Journey Analytics, the closest equivalent is **[!UICONTROL People]**, a count of unique person IDs in the date range. [!UICONTROL People] includes all identified persons regardless of engagement level, so it is typically higher than GA4's Active users for sites with significant passive traffic.

For a closer behavioral comparison, apply an [engaged-sessions segment](compare-data.md#engaged-sessions) to scope the [!UICONTROL People] metric to users who meet your engagement criteria.

+++

+++Engaged sessions &rarr; Calculated metric

GA4's **Engaged sessions** counts sessions that lasted 10 or more seconds, had 2 or more page views, or included at least one key event.

Customer Journey Analytics has no built-in engaged-sessions metric — you define it as a segment that captures your engagement criteria, then use it alongside the **[!UICONTROL Sessions]** metric. See [Engaged sessions](compare-data.md#engaged-sessions) for the recommended approach and how to derive an engagement rate from it.

+++

+++Engagement rate &rarr; Calculated metric

GA4's **Engagement rate** is the percentage of sessions that were engaged: engaged sessions divided by total sessions.

In Customer Journey Analytics, build it as a calculated metric from your engaged-sessions definition. See [Engaged sessions](compare-data.md#engagement-rate) for step-by-step instructions.

+++

+++Average engagement time &rarr; Time Spent per Session

GA4's **Average engagement time** measures the average time the browser or app was in the foreground during engaged sessions.

In Customer Journey Analytics, use **[!UICONTROL Session Duration (seconds)]**, which measures the elapsed time from the first event to the last event in a session. This component includes periods when the user might not have been actively engaging, so values can differ from GA4's measurement. It is the closest built-in equivalent.

+++

+++Event count &rarr; Events

GA4's **Event count** is the total number of times any event was recorded.

In Customer Journey Analytics, the equivalent metric is **[!UICONTROL Events]** — the total number of event records in the dataset for the selected date range and applied segments.

+++

+++Sessions &rarr; Sessions

GA4's **Sessions** and Customer Journey Analytics's **[!UICONTROL Sessions]** both measure the number of sessions in a date range. Counts can differ due to different session definition rules. See [Data comparison between GA4 and Customer Journey Analytics](compare-data.md#sessions) for details.

+++

+++New users &rarr; First Session segment applied to People

GA4's **New users** counts users who had their first-ever session in the selected date range.

In Analysis Workspace:

1. Locate the **[!UICONTROL First Session]** segment in the Components panel.
2. Drag it into the segment drop zone above your [[!UICONTROL Freeform table]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md).
3. Use the **[!UICONTROL People]** metric to count unique new persons.

+++

+++Bounce rate &rarr; Bounce Rate (with caveats)

GA4's **Bounce rate** is the percentage of sessions that were not engaged (under 10 seconds, no key event, fewer than 2 page views). It is the inverse of Engagement Rate.

Customer Journey Analytics's **[!UICONTROL Bounce Rate]** metric uses a different definition by default and is configurable per data view. These differences produce materially different numbers that measure different behaviors.

To approximate GA4's bounce rate in Customer Journey Analytics, build an Engagement Rate metric and invert it with a second calculated metric defined as `1 - Engagement Rate`. See [Engaged sessions](compare-data.md#engagement-rate) for the step-by-step build.

See [Data comparison between GA4 and Customer Journey Analytics](compare-data.md#bounce-rate) for a detailed explanation of the definitional difference.

+++

+++Key events &rarr; Custom event metrics

GA4's **Key events** (formerly called Conversions) are events designated as important business outcomes in GA4 property configuration.

In Customer Journey Analytics, a conversion is a custom event metric configured in the data view. Any XDM event can be exposed as a metric, and a metric can be set to increment conditionally on an XDM field value — for example, a **[!UICONTROL Purchases]** metric that increments when `xdm.eventType` equals `commerce.purchases`. Locate the relevant metric by its label in the Components panel of Analysis Workspace; the name reflects how your administrator configured it.

To reproduce GA4's Key events *report* (a list of every conversion with its count), see the **Key events (conversions)** entry under [Engagement](#engagement) on this page.

+++

>[!MORELIKETHIS]
>
>* [Report on Google Analytics data](/help/use-cases/third-party/ga/report.md)
