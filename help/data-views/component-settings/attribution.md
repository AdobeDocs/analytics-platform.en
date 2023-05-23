---
title: Attribution component settings
description: Lets you set default attribution for a metric.
exl-id: bc7ae6e3-7c9b-4994-97ce-690f3bdcbee5
solution: Customer Journey Analytics
feature: Data Views
---
# Attribution component settings

Attribution gives you the ability to customize how dimension items get credit for success events. For example:

1. A visitor to your site clicks a paid search link to one of your product pages. They add the product to their cart, but do not purchase it.
2. The next day, the see a social media post from one of their friends. They click the link, then complete the purchase.

In some reports, you might want the order attributed to Paid search. In other reports, you might want the order attributed to Social. Attribution lets you control this aspect of reporting.

This data view component setting lets you set a default attribution model for a metric. You can override a given metric's attribution model while working in Analysis Workspace.

![Attribution](../assets/attribution-settings.png)

If your organization requires that a metric has multiple attribution settings, you can do one of the following:

* Copy the metric in the data view with each desired attribution setting. You can include the same metric multiple times in a data view, giving each metric a different setting. Make sure that you label each metric appropriately so that analysts understand the difference between these metrics when generating reports.
* Override the metric in Analysis Workspace. In a metric's [Column settings](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md), select **[!UICONTROL Use non-default attribution model]** to change the metric's attribution model and lookback window for that specific report.

## Attribution models

An attribution model determines which dimension items get credit for a metric when multiple values are seen within a metric's lookback window. Attribution models only apply when there are multiple dimension items set within the lookback window. If only a single dimension item is set, that dimension item gets 100% credit regardless of attribution model used.

| Icon | Attribution model | Definition |
| :---: | :--- | --- |
| ![Last Touch](../assets/attribution-models/last_touch1.png) | Last Touch | Gives 100% credit to the touch point occurring most recently before conversion. This attribution model is typically the default value for any metric where an attribution model is not otherwise specified. Organizations typically use this model where the time to conversion is relatively short, such as with analyzing internal search keywords. |
| ![First Touch](../assets/attribution-models/first_touch.png) | First Touch | Gives 100% credit to the touch point first seen within the attribution lookback window. Organizations typically use this model to understand brand awareness or customer acquisition. |
| ![Linear](../assets/attribution-models/linear.png) | Linear | Gives equal credit to every touch point seen leading up to a conversion. It is useful where conversion cycles are longer or require more frequent customer engagement. Organizations typically use this attribution model measuring mobile app notification effectiveness or with subscription-based products. |
| ![Participation](../assets/attribution-models/participation.png) | Participation | Gives 100% credit to all unique touch points. Since every touch point receives 100% credit, metric data typically adds up to more than 100%. If a dimension item appears multiple separate times leading up to a conversion, values are deduplicated to 100%. This attribution model is ideal in situations where you want to understand which touch points customers are exposed to the most. Media organizations typically use this model to calculate content velocity. Retail organizations typically use this model to understand which parts of their site are critical to conversion. |
| ![Same Touch](../assets/attribution-models/same_touch.png) | Same Touch | Gives 100% credit to the same event where the conversion occurred. If a touch point does not happen on the same event as a conversion, It is bucketed under "None". This attribution model is sometimes equated to having no attribution model at all. It is valuable in scenarios where you do not want values from other events affecting how a metric gives credit to dimension items. Product or design teams can use this model to assess the effectiveness of a page where conversion happens. |
| ![U Shaped](../assets/attribution-models/u_shaped.png) | U Shaped | Gives 40% credit to the first interaction, 40% credit to the last interaction, and divides the remaining 20% to any touch points in between. For conversions with a single touch point, 100% credit is given. For conversions with two touch points, 50% credit is given to both. This attribution model is best used in scenarios where you value the first and last interactions the most, but don't want to entirely dismiss additional interactions in between. |
| ![J Curve](../assets/attribution-models/j_shaped.png) | J Curve | Gives 60% credit to the last interaction, 20% credit to the first interaction, and divides the remaining 20% to any touch points in between. For conversions with a single touch point, 100% credit is given. For conversions with two touch points, 75% credit is given to the last interaction, and 25% credit is given to the first. Similar to U-Shaped, this attribution model favors the first and last interactions, but more heavily favors the last interaction. |
| ![Inverse J](../assets/attribution-models/inverse_j.png) | Inverse J | Gives 60% credit to the first touch point, 20% credit to the last touch point, and divides the remaining 20% to any touch points in between. For conversions with a single touch point, 100% credit is given. For conversions with two touch points, 75% credit is given to the first interaction, and 25% credit is given to the last. Similar to J-Shaped, this attribution model favors the first and last interactions, but more heavily favors the first interaction. |
| ![Time Decay](../assets/attribution-models/time_decay.png) | Time Decay | Follows an exponential decay with a custom half-life parameter, where the default is 7 days. The weight of each channel depends on the amount of time that passed between the touch point initiation and the eventual conversion. The formula used to determine credit is `2^(-t/halflife)`, where `t` is the amount of time between a touch point and a conversion. All touch points are then normalized to 100%. Ideal for scenarios where you want to measure attribution against a specific and significant event. The longer a conversion happens after this event, the less credit is given. |
| ![Custom](../assets/attribution-models/custom.png) | Custom | Allows you to specify the weights that you want to give to first touch point, last touch point, and any touch points in between. Values specified are normalized to 100% even if the custom numbers entered do not add to 100. For conversions with a single touch point, 100% credit is given. For interactions with two touch points, the middle parameter is ignored. The first and last touch points are then normalized to 100%, and credit is assigned accordingly. This model is ideal for analysts who want full control over their attribution model and have specific needs that other attribution models do not fulfill. |
| ![Algorithmic](../assets/attribution-models/algorithmic.png) | Algorithmic | Uses statistical techniques to dynamically determine the optimal allocation of credit for the selected metric. The algorithm used for attribution is based on the Harsanyi Dividend from cooperative game theory. The Harsanyi dividend is a generalization of the Shapley value solution (named after Lloyd Shapley, a Nobel Laureate economist) to distributing credit among players in a game with unequal contributions to the outcome.<br>At a high level, attribution is calculated as a coalition of players to which a surplus must be equitably distributed. Each coalition's surplus distribution is determined according to the surplus that was previously created by each subcoalition (or previously participating dimension items) recursively. For more details, see John Harsanyi’s and Lloyd Shapley’s original papers:<br>Shapley, Lloyd S. (1953). A value for n-person games. *Contributions to the Theory of Games, 2(28)*, 307-317.<br>Harsanyi, John C. (1963). A simplified bargaining model for the n-person cooperative game. *International Economic Review 4(2)*, 194-220. |

{style="table-layout:auto"}

## Lookback window

A lookback window is the amount of time a conversion should look back to include touch points. If a dimension item is set outside of the lookback window, the value is not included in any attribution calculations.

* **14 Days**: Looks back up to 14 days from when the conversion happened.
* **30 Days**: Looks back up to 30 days from when the conversion happened.
* **60 Days**: Looks back up to 60 days from when the conversion happened.
* **90 Days**: Looks back up to 90 days from when the conversion happened.
* **Session**: Looks back up to the beginning of the session where a conversion happened. Session lookback windows respect the modified [Session timeout](../create-dataview.md#session-settings).
* **Person (Reporting Window)**: Looks at all visits back up to the first of the month of the current date range. For example, if the report date range is September 15 - September 30, the visitor lookback date range includes September 1 - September 30. If you use this lookback window, you can occasionally see that dimension items are attributed to dates outside of your reporting window.
* **Custom Time:** Allows you to set a custom lookback window from when a conversion happened. You can specify the number of minutes, hours, days, weeks, months, or quarters. For example, if a conversion happened on February 20, a lookback window of five days would evaluate all dimension touchpoints from February 15 to February 20 in the attribution model.

## Example

Consider the following example:

1. On September 15, a visitor arrives to your site through a paid search advertisement, then leaves.
2. On September 18, the visitor arrives to your site again through a social media link they got from a friend. They add several items to their cart, but do not purchase anything.
3. On September 24, your marketing team sends them an email with a coupon for some of the items in their cart. They apply the coupon, but visit several other sites to see if any other coupons are available. They find another through a display ad, then ultimately make a purchase for $50.

Depending on your lookback window and attribution model, channels receive different credit. The following are some notable examples:

* Using **first touch** and a **session lookback window**, attribution looks at only the third visit. Between email and display, email was first, so email gets 100% credit for the $50 purchase.
* Using **first touch** and a **person lookback window**, attribution looks at all three visits. Paid search was first, so it gets 100% credit for the $50 purchase.
* Using **linear** and a **session lookback window**, credit is divided between email and display. Both of these channels each get $25 credit.
* Using **linear** and a **person lookback window**, credit is divided between paid search, social, email, and display. Each channel gets $12.50 credit for this purchase.
* Using **J-shaped** and a **person lookback window**, credit is divided between paid search, social, email, and display.
  * 60% credit is given to display, for $30.
  * 20% credit is given to paid search, for $10.
  * The remaining 20% is divided between social and email, giving $5 to each.
* Using **Time Decay** and a **person lookback window**, credit is divided between paid search, social, email, and display. Using the default 7-day half-life:
  * Gap of zero days between display touch point and conversion. `2^(-0/7) = 1`
  * Gap of zero days between email touch point and conversion. `2^(-0/7) = 1`
  * Gap of six days between social touch point and conversion. `2^(-6/7) = 0.552`
  * Gap of nine days between paid search touch point and conversion. `2^(-9/7) = 0.41`
  * Normalizing these values results in the following:
    * Display: 33.8%, getting $16.88
    * Email: 33.8% getting $16.88
    * Social: 18.6%, getting $9.32
    * Paid Search: 13.8%, getting $6.92

Conversion events that typically have whole numbers are divided if credit belongs to more than one channel. For example, if two channels contribute to an order using a Linear attribution model, both channels get 0.5 of that order. These partial metrics are summed across all people then rounded to the nearest integer for reporting.
