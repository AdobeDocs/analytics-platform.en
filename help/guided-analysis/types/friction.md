---
title: Friction view
description: Compare conversion rates between steps.
exl-id: c8b0b71f-8ed3-4aad-a0f8-4d5ad8d7a7bd
feature: Adobe Product Analytics, Guided Analysis
keywords: product analytics
role: User
---
# [!UICONTROL Friction] view

The **[!UICONTROL Friction]** view provides a visual representation of a critical user journey in your product. The horizontal axis represents each step that a user must pass through. The vertical axis represents the percentage of users or sessions at each step. All steps must be done in eventual order, but can happen at any time within the reporting window.

>[!VIDEO](https://video.tv.adobe.com/v/3421663/?learn=on)

## Use cases

Use cases for this view type include:

* **Conversion analysis**: You can analyze conversions at each stage of the funnel, such as a retail checkout, account sign-up, subscription flow, or some other critical journey within your product experience. By tracking the number of users who progress from one step to the next, you can identify bottlenecks that have unusual or undesired conversion rates. This information is valuable to understand where you can improve your product journey for immediate results.
* **Experimentation analysis**: You can compare conversion rates across a funnel that has optional steps or steps where an A/B experiment is being run. This information can help you determine which variation of the funnel leads to the highest conversion rate so that you can encourage more users down that path.
* **Onboarding optimization**: Optimize your product's onboarding process by examining user behavior around key events. You can identify which steps that users struggle with or fail to complete.
* **Feature adoption and engagement**: Understand how users interact with specific features in your product. Analyzing the progression of users through feature-related steps lets you see adoption rates and identify areas where users might underuse certain features. You can then use this information to focus on feature improvements to increase adoption rates.
* **Marketing channel effectiveness**: Measure the effectiveness of marketing channels. You can create a segment that focuses on users that interacted with different marketing channels, such as paid search, display, natural search, or direct. You can then compare their journeys to see which channel leads to the best product outcomes.

## Query rail

The query rail allows you to configure the following components:

* **[!UICONTROL View]**: Switch between this view type and [Conversion trends](conversion-trends.md).
* **[!UICONTROL Steps]**: The event touchpoints that you want to track. Each bar in the chart represents a step. You can include up to ten steps.
  * [!UICONTROL Compare]: Each step provides an option to compare multiple events in a single funnel step, creating a "forked funnel." This feature allows you to compare the friction of two journeys side-by-side without creating two separate analyses. It is useful when there are step options or an A/B experiment is being run within the funnel. See [Funnel friction analysis](https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/guided-analysis/funnel/funnel-friction-analysis) in Customer Journey Analytics tutorials for a video that explains how to compare funnels.
* **[!UICONTROL Counted as]**: The scope that you want applied to the funnel. Options include [!UICONTROL Sessions] and [!UICONTROL Users].
  * [!UICONTROL Sessions]: All steps must happen within the same session to be counted.
  * [!UICONTROL Users]: All steps must happen within the selected reporting window to be counted.
* **[!UICONTROL Segments]**: The segments that you want to compare the funnel across. Each segment selected splits each step into multiple bars. Each color represents a different segment. You can include up to three segments.

## Chart settings

The Friction view offers the following chart settings, which can be adjusted in the menu above the chart:

* **[!UICONTROL Chart type]**: The type of visualization that you want to use. Options include [!UICONTROL Steps].
* **[!UICONTROL Conversion from]**: Determines the percentage calculation from step to step. Options include calculating conversion from the [!UICONTROL First step] or [!UICONTROL Previous step].

## Time comparison

{{apply-time-comparison}}

![Friction time compare](../assets/friction-compare.png){style="border:1px solid gray"}

## Date range

The desired date range for your analysis. There are two components to this setting:

* **[!UICONTROL Interval]**: The date granularity that you want to view trended data by. This setting does not impact non-trended views such as Friction. 
* **[!UICONTROL Date]**: The starting and ending date. Rolling date range presets and previously saved custom ranges are available for your convenience, or you can use the calendar selector to choose a fixed date range.
