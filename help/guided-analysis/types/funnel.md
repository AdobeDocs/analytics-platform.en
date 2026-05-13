---
title: Funnel analysis
description: Compare conversion rates between steps.
exl-id: c8b0b71f-8ed3-4aad-a0f8-4d5ad8d7a7bd
feature: Adobe Product Analytics, Guided Analysis
keywords: product analytics
role: User
TQID: https://experienceleague.adobe.com/-AW7cK4fHNV58e539KKcqBx-pRpIpIRWcrS7CA9ZUYc
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
  - id: cb6c7d24-631f-46e5-9e39-3a2705f73962
    internal-label: Calendar
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bcc5edb5-84c3-4940-9f84-ed88b6c16274
    internal-label: Experimentation
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
---
# [!UICONTROL Funnel] analysis {#funnel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_funnel_button"
>title="Funnel"
>abstract="Compare conversion rates between steps."

<!-- markdownlint-enable MD034 -->

The ![ConversionFunnel](/help/assets/icons/ConversionFunnel.svg)**[!UICONTROL Funnel]** analysis provides a visual representation of a critical user journey in your product. The horizontal axis represents each step that a user must pass through. The vertical axis represents the percentage of users or sessions at each step. All steps must be done in eventual order, but can happen at any time within the reporting window.

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Funnel friction analysis](https://video.tv.adobe.com/v/3421663/?quality=12&learn=onn){target="_blank"} for a demo video.

>[!ENDSHADEBOX]


## Use cases

Use cases for this analysis include:

* **Conversion analysis**: You can analyze conversions at each stage of the funnel, such as a retail checkout, account sign-up, subscription flow, or some other critical journey within your product experience. By tracking the number of users who progress from one step to the next, you can identify bottlenecks that have unusual or undesired conversion rates. This information is valuable to understand where you can improve your product journey for immediate results.
* **Experimentation analysis**: You can compare conversion rates across a funnel that has optional steps or steps where an A/B experiment is being run. This information can help you determine which variation of the funnel leads to the highest conversion rate so that you can encourage more users down that path.
* **Onboarding optimization**: Optimize your product's onboarding process by examining user behavior around key events. You can identify which steps that users struggle with or fail to complete.
* **Feature adoption and engagement**: Understand how users interact with specific features in your product. Analyzing the progression of users through feature-related steps lets you see adoption rates and identify areas where users might underuse certain features. You can then use this information to focus on feature improvements to increase adoption rates.
* **Marketing channel effectiveness**: Measure the effectiveness of marketing channels. You can create a segment that focuses on users that interacted with different marketing channels, such as paid search, display, natural search, or direct. You can then compare their journeys to see which channel leads to the best product outcomes.

## Interface

See [Interface](../overview.md#interface) for an overview of the Guided analysis interface. The following settings are specific to this analysis:

### Query rail

The query rail allows you to configure the following components:

* **[!UICONTROL View]**: Switch between this analysis and [Conversion trends](conversion-trends.md).
* **[!UICONTROL Steps]**: The event touchpoints that you want to track. Each bar in the chart represents a step. You can include up to ten steps.
  * [!UICONTROL Compare]: Each step provides an option to compare multiple events in a single funnel step, creating a "forked funnel." This feature allows you to compare the friction of two journeys side-by-side without creating two separate analyses. It is useful when there are step options or an A/B experiment is being run within the funnel. See [Funnel](https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/guided-analysis/funnel) in Customer Journey Analytics tutorials for a video that explains how to compare funnels.
* **[!UICONTROL Counted as]**: The scope that you want applied to the funnel. Options include [!UICONTROL Sessions] and [!UICONTROL Users].
  * [!UICONTROL Sessions]: All steps must happen within the same session to be counted.
  * [!UICONTROL Users]: All steps must happen within the selected reporting window to be counted.
* **[!UICONTROL Segments]**: The segments that you want to compare the funnel across. Each segment selected splits each step into multiple bars. Each color represents a different segment. You can include up to three segments.

### Chart settings

The [!UICONTROL Funnel] analysis offers the following chart settings, which can be adjusted in the menu above the chart:

* **[!UICONTROL Chart type]**: The type of visualization that you want to use. Options include [!UICONTROL Steps].
* **[!UICONTROL Conversion from]**: Determines the percentage calculation from step to step. Options include calculating conversion from the [!UICONTROL First step] or [!UICONTROL Previous step].

### Time comparison

{{apply-time-comparison}}



### Date range

The desired date range for your analysis. There are two components to this setting:

* **[!UICONTROL Interval]**: The date granularity that you want to view trended data by. This setting does not impact non-trended analyses such as [Funnel](funnel.md). 
* **[!UICONTROL Date]**: The starting and ending date. Rolling date range presets and previously saved custom ranges are available for your convenience, or you can use the calendar selector to choose a fixed date range.

<!--
## Example

See below for an example of the analysis.

![Funnel time compare](../assets/funnel-compare.png)

-->
