---
title: Transitioning from Google Analytics 4 to Customer Journey Analytics
description: Learn key concepts to obtain reports in Customer Journey Analytics, geared towards analysts familiar with Google Analytics 4.
role: User
solution: Customer Journey Analytics
feature: Basics
exl-id: 3d7c8b91-f2a4-4e6b-9c1d-5f8e3a720469
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
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
---

# Transitioning from Google Analytics 4 to Customer Journey Analytics

This guide helps analysts familiar with Google Analytics 4 learn the equivalent concepts and reports in Adobe Customer Journey Analytics. If you are responsible for the technical implementation rather than reporting, see [Upgrade from a third-party analytics solution to Customer Journey Analytics](../cja-upgrade/cja-upgrade-third-party-solution.md) for guidance on Web SDK setup and data ingestion. If your organization still needs to migrate existing Google Analytics data into Adobe Experience Platform, see [Migrate data from Google Analytics](/help/use-cases/third-party/ga/overview.md).

## Key differences between GA4 and Customer Journey Analytics

GA4 and Customer Journey Analytics share the same foundational philosophy: every user interaction is an event, and analysis is performed in a blank-canvas tool where you drag and drop dimensions and metrics to build custom views. If you are familiar with GA4 Explore, Analysis Workspace is likely recognizable immediately.

The most significant differences are where Customer Journey Analytics extends beyond GA4:

* **Cross-channel data**: Customer Journey Analytics can combine web analytics with offline data sources (such as call center records, CRM activity, loyalty programs, or email engagement) in the same analysis. GA4 is limited to digital interactions collected through its SDK.
* **Report-time processing**: Customer Journey Analytics applies logic such as attribution models, session definitions, and segment rules at query time, not at collection time. Changes made to session definitions or attribution models apply retroactively to all historical data without reprocessing.
* **Flexible session definitions**: Session timeout duration, session-starting events, and session-ending events are all configurable per data view in Customer Journey Analytics. GA4's session timeout is adjustable (30-minute default, up to 7 hours 55 minutes) but applies property-wide, and its session-starting and session-ending behavior is fixed.
* **Identity stitching**: Customer Journey Analytics's stitching capability can link cross-device and cross-channel interactions to the same person, producing more accurate person counts than GA4's blended identity model.

## Account and data structure

GA4 and Customer Journey Analytics organize data differently at the platform level.

| GA4 | Customer Journey Analytics |
|---|---|
| Google account | Adobe IMS org |
| Property | Connection + data view |
| Data Stream | [!UICONTROL Event dataset] in Platform |
| Data Filters | Data view component filters |
| Subproperty | Separate data view with filters applied |
| Roll-up property | Connection combining multiple datasets |

The most important structural difference is that a GA4 Property handles both data wiring and reporting as a single object. Customer Journey Analytics separates these concepts into two distinct layers:

* A **connection** links one or more Adobe Experience Platform datasets to Customer Journey Analytics. This step ingests data into Customer Journey Analytics in a format optimized for reporting.
* A **data view** is built on top of a connection and defines which dimensions, metrics, and settings are available for reporting. It is the reporting configuration layer.

Both must exist before you can analyze data in Customer Journey Analytics. There are no report suites in Customer Journey Analytics.

## Getting started in Analysis Workspace

GA4 Explore and Analysis Workspace are both blank-canvas, drag-and-drop analysis tools. The interaction model is the same; the terminology differs slightly.

| GA4 Explore | Analysis Workspace |
|---|---|
| Exploration canvas | Panel |
| Chart or visualization type | Visualization |
| Dimension | Dimension |
| Metric | Metric |
| Segment or filter | Segment |
| Event count | [!UICONTROL Events] |
| Users | [!UICONTROL People] |
| Sessions | [!UICONTROL Sessions] |

>[!TIP]
>
>GA4 segment containers are named Users, Sessions, and Events. In Customer Journey Analytics, the equivalent containers are **[!UICONTROL Person]**, **[!UICONTROL Session]**, and **[!UICONTROL Event]**. The scoping logic is the same.

>[!MORELIKETHIS]
>
>* [Migrate data from Google Analytics](/help/use-cases/third-party/ga/overview.md)
