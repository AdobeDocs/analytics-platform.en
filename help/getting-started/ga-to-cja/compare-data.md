---
title: Why GA4 and Customer Journey Analytics data differs
description: Understand why data between GA4 and Customer Journey Analytics can differ, and how to audit discrepancies.
role: User
solution: Customer Journey Analytics
feature: Basics
exl-id: 7e4b9a2f-1c5d-4b8a-e3f9-6d2c8b7a4051
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
---

# Why GA4 and Customer Journey Analytics data differs

It is normal for GA4 and Customer Journey Analytics to report different numbers for the same time period and the same apparent metric. Different data collection methods, metric definitions, identity models, and session rules all contribute to discrepancies. This page explains the most common sources of difference and provides guidance for auditing unexplained gaps.

## Engaged sessions

GA4 treats a session as **engaged** if it lasted 10 or more seconds, included at least one key event, or had 2 or more page views. This single definition underpins several GA4 metrics, including Engagement Rate, Bounce Rate, and the engagement threshold behind Active users.

Customer Journey Analytics has no built-in engaged session metric or dimension; you define engagement to match your business. Adobe recommends creating a segment that captures your engagement criteria and reusing that segment wherever engagement matters. Your administrator can also promote this definition to a metric in the data view so that it is available to everyone.

When formulating your own criteria, pick the signals that genuinely indicate value for your site. Three common building blocks for engagement include:

* **Duration**: A minimum session length, such as 10 or more seconds
* **Depth**: A minimum number of events or page views, such as 2 or more
* **Action**: The presence of a conversion or key event, such as a sign-up or purchase

You can combine them with `OR` so a session counts as engaged if it meets any one condition (the way GA4 does) or combine them with `AND` for a more strict requirement. If parity with GA4 is your goal, start from its defaults and tune from there.

### Engagement rate

Once you have an engaged sessions definition, engagement rate is the share of sessions that were engaged. To build it as a calculated metric:

1. In Analysis Workspace, select the **[!UICONTROL +]** icon near the metrics list to open the Calculated Metric Builder.
2. Name it "Engagement Rate" and set the format to **[!UICONTROL Percent]**.
3. Define the formula as your engaged sessions segment divided by **[!UICONTROL Sessions]**.
4. Select **[!UICONTROL Save]**.

### Bounce rate

In GA4, a bounce is the inverse of an engaged session, so GA4's bounce rate equals `1 - Engagement Rate`. Build it in Customer Journey Analytics as a second calculated metric using that formula.

Customer Journey Analytics also provides a built-in **[!UICONTROL Bounce Rate]** metric, but its default definition differs: it counts sessions in which only a single event was recorded, which is directionally opposite to GA4's definition for many sites. Comparing GA4's bounce rate to the default [!UICONTROL Bounce Rate] metric — rather than to your `1 - Engagement Rate` calculation — produces materially different numbers.

>[!TIP]
>
>The session definition in Customer Journey Analytics is configurable per data view. The bounce and engagement definitions can be tuned to match GA4's criteria (10-second duration, 2+ page views, or a key event) if that parity is a reporting requirement for your organization.

## Sessions

Both GA4 and Customer Journey Analytics default to a 30-minute inactivity timeout, and both keep a session going across midnight and across a mid-session campaign change. (Universal Analytics reset sessions in both of those cases, so they are a common source of confusion, but they are not differences between GA4 and Customer Journey Analytics.) The rules that do differ are:

| Rule | GA4 | Customer Journey Analytics |
|---|---|---|
| Inactivity timeout | Adjustable property-wide (30-minute default, up to 7 hours 55 minutes) | Configurable per data view |
| Session-starting events | `session_start` only (automatic) | Configurable; any event can start a session |
| Session-ending events | None | Configurable; any event can end a session |

Because Customer Journey Analytics's session definition is configurable, session counts depend on how your data view is set up. Matching a data view's timeout and session-starting events to your GA4 property brings session counts closer between platforms.

## People and Active users

GA4's primary user metric, **Active users**, counts users who had at least one engaged session in the date range. The **[!UICONTROL People]** metric in Customer Journey Analytics counts unique person IDs in the date range.

Expect these metrics to differ for several reasons:

* **Engagement threshold**: GA4 Active users excludes visitors who had no [engaged session](#engaged-sessions). The [!UICONTROL People] metric in Customer Journey Analytics includes everyone regardless of engagement level.
* **[!UICONTROL Stitching]**: If stitching is enabled, a person who visited from both a mobile device and a desktop can be counted as one person in Customer Journey Analytics but two users in GA4. Stitching typically makes the [!UICONTROL People] metric lower than GA4 users on stitched datasets.
* **Identity model**: GA4 uses a cascading identity model; Customer Journey Analytics uses whichever person ID is defined in the dataset. These differences affect person counts independently of stitching.

## Identity and stitching

GA4 uses a cascading identity model to identify users:

1. User-ID (if set by your implementation)
2. Google Signals (if the user is signed into a Google account with personalization enabled)
3. Device ID (cookie-based client ID)

In most implementations, that person ID is an ECID (Experience Cloud ID). The optional **[!UICONTROL Stitching]** feature can then resolve cross-device and cross-channel identities using field-based or graph-based methods, allowing a mobile app session and a desktop browser session to be associated with the same person.

Because identity resolution differs between platforms, user-level counts rarely match exactly. This discrepancy is expected and does not indicate a data quality problem.

## Attribution

GA4 applies a reporting attribution model configured at the property level (under Admin), with data-driven attribution as the default. Like Customer Journey Analytics, GA4 evaluates this model at report time, so changing it updates historical and future reports retroactively. In GA4, however, the model is property-wide and affects only key-event reports that use event-scoped traffic dimensions (such as Source, Medium, and Campaign).

Customer Journey Analytics also applies attribution at report time, but with more granular control. There are two places to configure it:

* **Data view settings**: An [attribution model](/help/data-views/component-settings/attribution.md) can be set on any metric component in the data view, establishing the default for that metric across all reports. No attribution model is applied by default. You can configure a data view to contain multiple copies of the same metric, each using a different default attribution model.
* **Component-level override**: After dragging a metric into a [!UICONTROL Freeform table], right-click its column header and select **[!UICONTROL Use non-default attribution model]** to override it for that instance. You can also drag the same metric into the table multiple times, each using a different attribution model for a direct side-by-side comparison.

Because GA4 defaults to data-driven attribution while Customer Journey Analytics applies no model unless you configure one, conversion and channel metrics are likely to differ until you align them. Setting GA4 to a last-click model and configuring a matching last-touch model in Customer Journey Analytics is the most reliable way to establish a like-for-like baseline. Any model change in Customer Journey Analytics applies retroactively to all historical data without reprocessing.

## Auditing discrepancies

When numbers differ more than expected, three audit paths are available:

* **Assurance**: Adobe's in-product validation tool confirms that XDM events are firing correctly, reaching the Edge Network, and being written to Platform datasets. Use this tool to verify your implementation before comparing report numbers.
* **Dataset previews**: In the Platform UI, you can preview raw rows in any dataset. Compare these against GA4's DebugView or BigQuery export to verify field-level accuracy.
* **Adobe Consulting**: For persistent unexplained discrepancies, your Adobe Account Team can arrange a formal implementation audit with an Adobe consultant.
* **Ingestion review**: If you suspect the discrepancy originates in how GA data was brought into Platform rather than in reporting definitions, review the ingestion setup in [Migrate data from Google Analytics](/help/use-cases/third-party/ga/overview.md).
