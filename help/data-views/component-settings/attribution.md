---
title: Attribution component settings
description: Lets you set default attribution for a metric.
exl-id: bc7ae6e3-7c9b-4994-97ce-690f3bdcbee5
solution: Customer Journey Analytics
feature: Data Views
role: Admin
---
# Attribution component settings {#attribution-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_dataview_component_metric_attribution"
>title="Attribution"
>abstract="Configure the default attribution model applied to a metric in reports."

<!-- markdownlint-enable MD034 -->


Attribution lets you customize how dimension items get credit for success events. 

![Data views window highlighting the Set attribution option](../assets/attribution-settings.png)

For example:

1. A person on your site clicks a paid search link to one of your product pages. They add the product to their cart, but do not purchase it.
2. The next day, they see a social media post from one of their friends. They click the link, then complete the purchase.

In some reports, you might want the order attributed to Paid search. In other reports, you might want the order attributed to Social. Attribution lets you control this aspect of reporting.

## Set a component's default attribution model

You can set a default attribution model for a given metric by updating the metric's setting in the data view. Doing so overrides the metric's attribution model any time it's used in Analysis Workspace.

>[!NOTE]
>
>Consider the following when enabling attribution on a metric:
>
>* **When using the component in a report with *a single dimension*:** The component's attribution ignores the allocation model when a non-default attribution model is used.
>
>* **When using the component in a report with *multiple dimensions*:** The component's attribution retains the allocation model when a non-default attribution model is used.
>
>   Multiple dimensions are available only when [exporting data to the cloud](/help/analysis-workspace/export/export-cloud.md).
>
> For more information about allocation, see [Persistence component settings](/help/data-views/component-settings/persistence.md).

To update a component's default attribution model: 

1. Go to the data view that contains the component whose default attribution model you want to update.

1. Select the component, then expand the Attribution section on the right side of the screen.

   ![Data views window highlighting the Set attribution option](../assets/attribution-settings.png)

1. Select [!UICONTROL **Set attribution**], then select the attribution model in the [!UICONTROL **Attribution Model**] drop-down menu.

   See [Attribution models](#attribution-models) to learn about each attribution model.

1. Select [!UICONTROL **Save and continue**].

>[!TIP]
>
>If your organization requires that a metric has multiple attribution settings, you can do one of the following:
>
> * Copy the metric in the data view with each desired attribution setting. You can include the same metric multiple times in a data view, giving each metric a different setting. Make sure that you label each metric appropriately so that analysts understand the difference between these metrics when generating reports.
>
> * Override the metric in Analysis Workspace. In a metric's [Column settings](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md), select **[!UICONTROL Use non-default attribution model]** to change the metric's attribution model and lookback window for that specific report.

## Attribution models {#attribution-models}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_dataviews_component_attribution_attributionmodels"
>title="Model"
>abstract="Select an attribution model for the metric."

<!-- markdownlint-enable MD034 -->

{{attribution-models-details}}


## Lookback window

{{attribution-lookback-window}}



## Attribution example {#attribution-example}

Consider the following example:

1. On September 15, a person arrives to your site through a paid search advertisement, then leaves.
1. On September 18, the person arrives to your site again through a social media link they got from a friend. They add several items to their cart, but do not purchase anything.
1. On September 24, your marketing team sends them an email with a coupon for some of the items in their cart. They apply the coupon, but visit several other sites to see if any other coupons are available. They find another through a display ad, then ultimately make a purchase for $50.

Depending on your lookback window and attribution model, channels receive different credit. The following are some examples:

* Using **first touch** and a **session lookback window**, attribution looks at only the third visit. Between email and display, email was first, so email gets 100% credit for the $50 purchase.

* Using **first touch** and a **person lookback window**, attribution looks at all three visits. Paid search was first, so it gets 100% credit for the $50 purchase.

* Using **linear** and a **session lookback window**, credit is divided between email and display. Both of these channels each get $25 credit.
Using **linear** and a **person lookback window**, credit is divided between paid search, social, email, and display. Each channel gets $12.50 credit for this purchase.

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


