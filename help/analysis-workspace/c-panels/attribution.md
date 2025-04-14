---
title: Attribution panel
description: How to use and interpret the attribution panel in Analysis Workspace.
feature: Panels
exl-id: 7fdec05b-5d99-48d1-ac1b-c243cb64e487
role: User
---
# Attribution panel {#attribution-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_attribution_button"
>title="Attribution"
>abstract="Quickly compare and visualize any number of attribution models using success metric, channel and lookback window."
>additional-url="https://www.youtube.com/watch?v=Yu0hy2klzA0" text="Attribution IQ panel"

>[!CONTEXTUALHELP]
>id="workspace_attribution_panel"
>title="Attribution panel"
>abstract="Quickly compare and visualize any number of attribution models for a success metric. Select the channel (dimension), the models to include and the lookback window." 
>additional-url="https://www.youtube.com/watch?v=Yu0hy2klzA0" text="Attribution IQ panel"

<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

_This article documents the Attribution panel in_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**_.<br/>_See [Attribution panel](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/panels/attribution) for the_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics** version of this article._

>[!ENDSHADEBOX]

The **[!UICONTROL Attribution]** panel is an easy way to build an analysis comparing various attribution models. The panel provides you with a dedicated workspace to use and compare attribution models.

Customer Journey Analytics enhances attribution by letting you:

* Define attribution beyond paid media: Any dimension, metric, channel or event can be applied to models (for example, internal search), not just marketing campaigns.
* Use unlimited attribution model comparison: dynamically compare as many models as you want.
* Avoid implementation changes: With report-time processing and context-aware sessions, customer journey context can be built in and applied at run time.
* Construct the session that best matches your attribution scenario.
* Break down attribution by filters: Easily compare the performance of your marketing channels across any important filter (for example, New vs. Repeat customers, Product X vs. Product Y, Loyalty level or CLV).
* Inspect channel cross-over and multi-touch analysis: Use Venn Diagrams and Histograms, and trend attribution results.
* Analyze key marketing sequences visually: explore paths that led to conversion visually with multi-node flow and fallout visualizations.
* Build calculated metrics: use any number of attribution allocation methods.

## Use

To use an **[!UICONTROL Attribution]** panel:

1. Create an **[!UICONTROL Attribution]** panel. For information about how to create a panel, see [Create a panel](panels.md#create-a-panel).

1. Specify the [input](#panel-input) for the panel.

1. Observe the [output](#panel-output) for the panel.

### Panel input

You can configure the Attribution panel using these input settings:

1. Add a **[!UICONTROL Success metric]** and a dimension from the **[!UICONTROL Channel]** that you want to attribute against. Examples include Marketing Channels or custom dimensions, such as internal promotions.

   ![The Attribution panel window showing several selected dimensions and metrics.](assets/attribution-panel.png)

1. Select one or more [attribution models](#attribution-models) from **[!UICONTROL Included models]** and a [lookback window](#lookback-window) from the **[!UICONTROL Lookback window]** that you want to use for comparison.

1. Select **[!UICONTROL Build]** to build the visualizations in the panel.

### Panel output

The **[!UICONTROL Attribution]** panel returns a rich set of data and visualizations that compare attribution for the selected dimension and metric.

   ![The Attribution panel visualizations that compare selected metrics and dimensions.](assets/attr_panel_vizs.png)

### Attribution visualizations

The following visualization are part of the panel ouput.

* **Total metric**: The total number of conversions that occurred over the reporting time window, and are attributed to the dimension you selected.
* **Attribution Comparison Bar**: Visually compares the attributed conversions across each of the dimension items from your selected dimension. Each bar color represents a distinct attribution model.
* **Attribution Comparison Table**: Shows the same data as the bar chart, represented as a table. Selecting different columns or rows in this table filters the bar chart as well as several of the other visualizations in the panel. This table acts similar to any other Freeform table in Workspace - allowing you to add components such as metrics, filters, or breakdowns.
* **Overlap Diagram**: A Venn visualization showing the top three dimension items and how often they participate jointly in a conversion. For example, the size of the bubble overlap indicates how often conversions occurred when a person was exposed to both dimension items. Selecting other rows in the adjacent Freeform table updates the visualization to reflect your selection.
* **Performance Detail**: A scatter visualization to compare up to three attribution models visually.
* **Trended Performance**: Shows the trend of attributed conversions for the top dimension item. Selecting other rows in the adjacent Freeform table updates the visualization to reflect your selection.
* **Flow**: Lets you see which channels are interacted with most commonly, and in what order across a person's journey.

## Attribution models

{{attribution-models-details}}

## Lookback window

{{attribution-lookback-window}}

>[!MORELIKETHIS]
>
> [Create a panel](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>
