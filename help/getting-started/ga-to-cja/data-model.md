---
title: How the GA4 data model maps to Customer Journey Analytics
description: Understand how GA4's event-based data model translates to XDM schemas and datasets in Customer Journey Analytics.
role: User
solution: Customer Journey Analytics
feature: Basics
exl-id: a5f9e2c7-3b1d-4a8e-b6f0-2c9d7e4a5180
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
    internal-label: Dimensions
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
    internal-label: Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
---

# How the GA4 data model maps to Customer Journey Analytics

GA4 and Customer Journey Analytics are both event-based platforms, which makes the data model translation between them more direct than it was from Universal Analytics. Understanding how GA4's events and parameters correspond to Customer Journey Analytics's XDM fields and datasets makes it easier to interpret reports and collaborate with your implementation team.

## GA4's event-based data model

Every interaction in GA4 is an **event**: a named action with an optional set of **parameters** that provide context. There are no separate object types for page views, sessions, or goals — they are all events.

| GA4 event type | Examples |
|---|---|
| Auto-collected | `page_view`, `session_start`, `first_visit`, `scroll` |
| Enhanced measurement | `file_download`, `video_start`, `form_submit` |
| Recommended | `purchase`, `add_to_cart`, `sign_up` |
| Custom | Any event name you define |

Each event can carry up to 25 parameters. For example, a `purchase` event typically includes `transaction_id`, `value`, `currency`, and `items` as parameters.

## How Customer Journey Analytics stores data

Customer Journey Analytics gets its data from **Adobe Experience Platform**. Data in Platform is stored in **datasets**, each conforming to a **schema** built using the **Experience Data Model (XDM)**. XDM is Adobe's open standard for representing customer experience data.

There are three dataset types used in Customer Journey Analytics:

| CJA dataset type | GA4 equivalent | What it holds |
|---|---|---|
| [!UICONTROL Event dataset] | GA4 event stream | Time-series interactions (page views, clicks, purchases) |
| [!UICONTROL Profile dataset] | GA4 user properties | Person-level attributes (CRM fields, loyalty status, demographics) |
| [!UICONTROL Lookup dataset] | GA4 custom dimensions used as reference tables | Key-value reference data (product catalog, campaign names) |

Customer Journey Analytics has no eVars, props, or success events. All dimensions and metrics are sourced directly from XDM schema fields. There are no limits on the number of unique dimension values.

## Automatically collected events

GA4 automatically collects a set of events through its SDK. The following table maps those events to their XDM or Customer Journey Analytics equivalents.

| GA4 auto-collected event | XDM / Customer Journey Analytics equivalent |
|---|---|
| `page_view` | `xdm.web.webPageDetails.pageViews` (standard XDM field) |
| `session_start` | Session start (automatic, per data view session definition) |
| `first_visit` | [!UICONTROL First Session] segment |
| `scroll` | Custom event (requires explicit implementation mapping) |
| `click` | `xdm.web.webInteraction` fields (requires implementation) |
| `video_start` / `video_complete` | Media Collection schema fields (with Adobe streaming media services) |
| `purchase` | `xdm.commerce.purchases`, `xdm.commerce.order` (standard XDM commerce schema) |
| `add_to_cart` | `xdm.commerce.productListAdds` (standard XDM commerce schema) |

>[!NOTE]
>
>Several of GA4's enhanced measurement events (like scroll, file download, or video) require explicit mapping to XDM fields when implementing using the Web SDK. They do not auto-collect in the same way that GA4's SDK handles them.

## Custom events and parameters

In GA4, custom events have a name and up to 25 parameters. In Customer Journey Analytics, custom events map to custom XDM schema fields defined during implementation:

* The **event name** becomes a field value in an XDM field (typically [`xdm.eventType`](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/experienceevent)).
* Each **parameter** becomes a separate XDM schema field. Any XDM field can be exposed as either a dimension or metric when [configuring a data view](/help/data-views/component-settings/overview.md).

>[!NOTE]
>
>The specific XDM field paths for your organization's custom events are determined during Web SDK implementation. Work with your implementation team to understand your specific field mapping before building reports. See [Architect your schema](../cja-upgrade/cja-upgrade-schema-architect.md) for more information.

## User properties

GA4 user properties are persistent attributes set on a user (for example, `membership_tier` or `account_type`). In Customer Journey Analytics, these map to **Profile datasets** in Platform.

A Profile dataset is ingested separately from event data and joined to it in Customer Journey Analytics using a shared person ID. Common person IDs used in this context include a customer ID or email hash. Once joined, those profile attributes are available as dimensions in Analysis Workspace alongside your event-level data.

This approach gives Customer Journey Analytics more flexibility than GA4's user properties model: GA4 limits you to user properties defined in its SDK, while Customer Journey Analytics Profile datasets can include any attribute from any system (CRM, loyalty platform, support records) as long as it shares a joinable identifier.

If your organization still needs to bring GA data into Adobe Experience Platform, see [Ingest Google Analytics historical data](/help/use-cases/third-party/ga/backfill.md) and [Configure streaming Google Analytics data](/help/use-cases/third-party/ga/streaming.md) for the admin-facing setup guides.
