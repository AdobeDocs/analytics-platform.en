---
title: Attribution Overview
description: Learn about the concept of attributing credit of a success event to multiple dimension items.
feature: Attribution
role: User, Admin
exl-id: 47a3523b-d9eb-4272-84b8-090b921cba13
TQID: https://experienceleague.adobe.com/ncY8TuwUb3duwfK3n8u69eyXWUDzI5OMF-AACOoDmIY
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
    internal-label: Segments, Segments (CJA)
  - id: d3c978ee-1ff0-4475-968a-721e2dd99ef1
    internal-label: Freeform tables
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
    internal-label: Dimensions
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
    internal-label: Calculated metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
---
# Attribution overview

Attribution gives analysts the ability to customize how dimension items get credit for success events. For example:

1. A visitor to your site clicks a paid search link to one of your product pages. They add the product to the cart, but do not purchase it.
2. The next day, they see a social media post from one of their friends, click the link, then complete the purchase.

In some reports, you might want the order attributed to Paid search. In other reports, you might want the order attributed to Social. Attribution lets you control this aspect of reporting. It is available to all organizations on Adobe Analytics Ultimate, Prime, Select and Foundation. If you are not sure which type of contract you have with Adobe, contact your organization's Adobe Account Team.

## Value of attribution

A given customer journey isn't linear and often unpredictable. Each customer proceeds at their own pace; often they double back, stall, restart, or engage in other non-linear behavior. These organic actions make it difficult to know the impact of marketing efforts across the customer journey. It also hampers efforts to tie multiple channels of data together.

<!--
![Attribution problem](assets/attribution_iq_problem.png)
-->

Adobe Analytics enhances attribution by letting you:

* Define attribution beyond paid media: Any dimension, metric, channel or event can be applied to models (for example, internal search), not just marketing campaigns.
* Use unlimited attribution model comparison: dynamically compare as many models as you want.
* Avoid implementation changes: With report time processing and context-aware sessions, customer journey context can be built in and applied at run time.
* Construct the session that best matches your attribution scenario.
* Break down attribution by segments: Easily compare the performance of your marketing channels across any important segment (for example, New vs. Repeat customers, Product X vs. Product Y, Loyalty level or CLV).
* Inspect channel cross-over and multi-touch analysis: Use Venn Diagrams and Histograms, and trend attribution results.
* Analyze key marketing sequences visually: explore paths that led to conversion visually with multi-node flow and fallout visualizations.
* Build calculated metrics: use any number of attribution allocation methods.

## Features

Attribution comprises the following features:

* [Attribution panel](/help/analysis-workspace/c-panels/attribution.md): Take any dimension and metric, and quickly compare it with different attribution models.
* [Apply attribution to a metric](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md): Use a non-default attribution on any metric in a project.
* [Apply attribution to a breakdown](/help/components/dimensions/t-breakdown-fa.md#apply-attribution-models-to-breakdowns): Use a non-default attribution on a breakdown. 
* [Compare attribution models](/help/components/apply-create-metrics.md#compare-metrics-with-different-attribution-models): Quickly see how different attribution models compare for any metric.

## Videos


<!--  
Attribution IQ

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Attribution in Freeform tables](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/attribution-iq/using-attribution-iq-in-freeform-tables){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

-->

<!-- 
Attribution IQ 
>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Attribution in calculated metrics](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/attribution-iq/attribution-iq-in-calculated-metrics){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

-->


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Using the Attribution panel](https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/analysis-workspace/panels/build-the-attribution-panel){target="_blank"} for a demo video.

>[!ENDSHADEBOX]


<!-- 
Attribution IQ

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Adding side-by-side comparisons of Attribution models](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/attribution-iq/adding-side-by-side-comparisons-of-attribution-iq-models){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

-->

