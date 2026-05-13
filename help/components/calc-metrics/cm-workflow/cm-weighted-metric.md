---
description: Shows examples of calculated metrics.
title: Calculated metrics examples
feature: Calculated Metrics
exl-id: 5e73ab52-627a-4064-bfb7-354c0ba1e4ee
TQID: https://experienceleague.adobe.com/awAk0boIVigYBssgLcSz3t-5eExHhasCVDtwoa3v19k
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
    internal-label: Metrics
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
    internal-label: Calculated metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
---
# Calculated metrics examples

This article shows examples of how to define more advanced calculated metrics.

## Bounce rate

You want to calculate the bounce rate. 

+++ Details

The definition of a bounce is subject for another discussion but for this example, you define a Bounced events segment where Session Start equals 1 and Session Ends equals 1. You use this segment do define the rate of bounced sessions to sessions.


### Segment

![Bouncing events](assets/example-bounce-bouncedevents.png)

### Calculated metric

![Bounce rate](assets/example-bounce-rate.png)


### Derived fields

Alternatively, you can define a [bounce rate using derived fields](/help/data-views/derived-fields/derived-fields.md#bounces).

Derived fields are part of a Data view which has the advantage that not every user can override or modify the definition of a Bounce rate metric. That advantage also introduced a limitation. Users that do not have access to a data view cannot use derived fields and have to resort to segments and calculated metrics to define a bounce rate.

See for more background information on how to calculate bounces and bounce rate in Customer Journey Analytics, this [blog post](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/calculating-bounces-amp-bounce-rate-in-adobe-customer-journey/ba-p/706446).

+++


## Conditional page views

You want to define a calculated metric that calculates only page views for the pages that have been visited in over 100 sessions.

+++ Details 

![Conditional page views](assets/conditional-page-views.png)

+++

## Page views for top 30% sessions

You want to define a calculated metric that calculates only page views for the top 30% sessions.

+++ Details

![Top 30% page views](assets/top30-page-views.png)

+++
