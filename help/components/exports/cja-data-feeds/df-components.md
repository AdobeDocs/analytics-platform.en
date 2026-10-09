---
title: Components Available in Customer Journey Analytics Data Feeds
description: Learn which dimensions and metrics are required, unsupported, restricted, or must be substituted when you create Customer Journey Analytics data feeds.
hide: true
feature: Components
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
---
# Component availability in data feeds

{{release-limited-testing}}

Not all Customer Journey Analytics components can be used in data feeds. Some dimensions are included in every data feed, some components cannot be included, and some metrics must be replaced with a substitute.

Use the following information to understand which components you can include when you [create a data feed](/help/components/exports/cja-data-feeds/create-feed.md).

## Required dimensions {#required-dimensions}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_required_dimensions"
>title="Required dimensions"
>abstract="Every data feed must include certain dimensions, identified by a **Required** label next to the dimension name. These dimensions provide the minimum structure needed for event-level analysis."

<!-- markdownlint-enable MD034 -->

The following dimensions are included by default in every data feed and cannot be removed:

| Dimension name | Notes | Data feeds | Other reporting |
|---|---|---|---|
| Timestamp UTC | The date and time the event occurred, represented in UTC time zone. Supports sub-second (micro-second) granularity. | Required | Not available |
| Row ID | The unique identifier for each row included in the data feed. | Required | Not available |
| Session ID | The unique identifier for each session included in the data feed. | Required | Not available |
| Person ID | The person identifier for the data view and connection | Required | Optional standard |
| Account ID [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | Account ID when using the Account container | Required | Optional standard |

## Unsupported dimensions {#unsupported-dimensions}

Customer Journey Analytics standard dimensions cannot be included in data feeds. The following table lists these dimensions:

| Dimension name | Notes | Data feeds |
|---|---|---|
| 5 Minute | Five-minute intervals when events occurred (rounded down) | Not available |
| 15 Minute | Fifteen-minute intervals when events occurred (rounded down) | Not available |
| 30 Minute | Thirty-minute intervals when events occurred (rounded down) | Not available |
| Day | Day an event occurred | Not available |
| Day of Week | Day of the week an event occurred | Not available |
| Day of Month | Day of the month an event occurred | Not available |
| Hour | Hour an event occurred (rounded down) | Not available |
| Hour of Day | Hour of the day an event occurred (rounded down) | Not available |
| Minute | Minute an event occurred (rounded down) | Not available |
| Minute of Hour | Minute of the hour an event occurred (rounded down) | Not available |
| Month | Month an event occurred | Not available |
| Month of Year | Month of the year an event occurred | Not available |
| Quarter | Quarter an event occurred | Not available |
| Quarter of Year | Quarter of the year an event occurred | Not available |
| Second | Second an event occurred (rounded down) | Not available |
| Week | Week an event occurred | Not available |
| Week of Year | Week of the year an event occurred | Not available |
| Year | Year an event occurred | Not available |

## Unsupported metrics {#unsupported-metrics}

The following Customer Journey Analytics standard metrics cannot be included in data feeds:

| Metric name | Notes | Data feeds |
|---|---|---|
| Adobe Visitors Profile | | Not available |
| Adobe Opportunities Union | | Not available |
| Adobe Opportunities Profile | | Not available |
| Adobe Accounts Union | | Not available |
| Adobe Accounts Profile | | Not available |
| Adobe Buying Groups Union | | Not available |
| Adobe Buying Groups Profile | | Not available |
| Adobe Global Accounts Union | | Not available |
| Adobe Global Accounts Profile | | Not available |
| Adobe Persons Union | | Not available |
| Adobe Persons Profile | | Not available |

## Dimensions that cannot be used together {#incompatible-dimensions}

<!-- markdownlint-disable MD034 -->

<!-- pretty sure this isn't being used -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_user_agent"
>title=""
>abstract="User agent data and device lookup data cannot exist in the same data feed configuration." 

<!-- markdownlint-enable MD034 -->

>[!IMPORTANT]
>
>Certain dimensions cannot be used together in Experience Platform datasets, and therefore cannot be included in the same data feed. 
>
>If you choose to include either the **User agent** or **Mobile ID** dimensions in your data feed, the dimensions listed below cannot be added to the data feed.
>
>If you use the Web SDK, this restriction is enforced in datastreams before data arrives in an Experience Platform dataset. For more information, see [Configure device lookup](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/configure#geolocation-device-lookup) in [Create and configure datastreams](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/configure) in the Data Collection guide.

The following dimensions cannot be used together with the **User Agent** or **Mobile ID** dimensions:

>[!NOTE]
>
>The following list uses default dimension names. Dimensions that are renamed in your data view appear in data feeds with their custom names.


* Browser Type
* Browser
* Browser ID
* Mobile Manufacturer
* Mobile Device Type
* Mobile Audio Support
* Mobile DRM
* Mobile Java VM
* Mobile Information Services
* Mobile Image Support
* Mobile Color Depth
* Mobile Net Protocols
* Mobile Device Number
* Mobile Max Email Length
* Mobile Mail Decoration
* Mobile Push To Talk
* Mobile Screen Width
* Mobile Max Browser URL Length
* Mobile Operating System (deprecated)
* Mobile Screen Height
* Mobile Video Support
* Mobile Cookie Support
* Mobile Max Bookmark Length
* Mobile Screen Size
* Mobile Device Name
* Operating System Types
* Operating Systems 
* Operating System ID

## Metrics that require a substitute {#substitute-metrics}

The following Customer Journey Analytics metrics must be substituted:

| Metric name | Notes | Data feeds |
|---|---|---|
| Accounts [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | Based on Account ID specified in the connection | Not available. Use count distinct of Account ID. |
| Buying Group [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | Buying groups based on Buying Group ID in the connection | Not available. Use count distinct of Buying Group ID. |
| Events | Number of rows from all event datasets in a connection | Not available. Use count distinct of Row ID. |
| Global Accounts [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | Based on Global Accounts ID in the connection | Not available. Use count distinct of Global Accounts ID. |
| Opportunities [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | Opportunities based on Opportunity ID in the connection | Not available. Use count distinct of Opportunity ID. |
| People | Based on Person ID specified in a connection | Not available. Use count distinct of Person ID. |
| Conversations | Number of conversations | Not available. Use count distinct of Conversation ID. |
| Session Ends | Number of events that were the last event of a session | Not available |
| Session Starts | Number of events that were the first event of a session | Not available |
| Sessions | Based on the data view's session settings | Not available. Use count distinct of Session ID. |
| Time Spent (seconds) | Sums the time between two different dimension values | Not available |

## Optional standard components {#optional-standard-components}

| Component name | Type | Notes | Data feeds |
|---|---|---|---|
| AM/PM | Time-parting dimension | AM or PM | Not available |
| Batch ID | Dimension | Identifier for an Experience Platform batch | Available |
| Dataset ID | Dimension | Identifier for an Experience Platform dataset | Available |
| Day of Month | Time-parting dimension | 1–31 | Not available |
| Day of Week | Time-parting dimension | Monday through Sunday | Not available |
| Day of Year | Time-parting dimension | 1–366 | Not available |
| Event Depth | Dimension | Sequential numerical value (1, 2, 3, etc.) assigned to each event interaction within a session<p>Resets at the start of each new session</p> | Available |
| Hour of Day | Time-parting dimension | 0–23 | Not available |
| Month of Year | Time-parting dimension | January–December | Not available |
| First-time Sessions | Metric | A person's first defined session within the reporting window | Not available |
| Return Sessions | Metric | Sessions that were not a person's first-time session | Not available |
| Person ID namespace | Dimension | Type of ID the Person ID consists of (for example, email or cookie ID) | Available |
| Global Account ID [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | Dimension | Global Account ID when using the Global Account container | Available |
| Opportunity ID [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | Dimension | Opportunity ID when using the Opportunity container | Available |
| Buying Group ID [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | Dimension | Buying Group ID when using the Buying Group container | Available |
| Quarter of Year | Time-parting dimension | Q1, Q2, Q3, Q4 | Not available |
| Repeat Session | Metric | Sessions that were not a person's first-ever session | Not available |
| Session Type | Dimension | Two values: First-Time or Returning | Not available |
| Time Spent per Event | Dimension | Buckets the Time Spent metric into event buckets | Not available |
| Time Spent per Session | Dimension | Buckets the Time Spent metric into session buckets | Not available |
| Time Spent per Person | Dimension | Buckets the Time Spent metric into person buckets | Not available |
| Weekend/Weekday | Time-parting dimension | Weekend or Weekday | Not available |
