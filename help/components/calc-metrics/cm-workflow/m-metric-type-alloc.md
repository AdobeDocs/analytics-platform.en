---
description: Learn about metric type and attribution
title: Metric type and Attribution
feature: Calculated Metrics
exl-id: da73a9ba-542e-436c-bdb2-b629b5b6f760
---
# Metric type and Attribution

You can configure the metric type and [attribution model](#attribution-models) for a metric in a calculated metric definition.

1. Select ![Setting](/help/assets/icons/Setting.svg) in the metric component.
1. In the popup dialog:

   ![Metric type and attribution](assets/cm-type-alloc.png)

   * Specify the **[!UICONTROL Metric type]**:

      |  Metric Type  | Definition  |
      |---|---|
      |  **[!UICONTROL Standard]**  | If a formula consists of a single standard metric, it displays identical data to its non-calculated-metric counterpart. Standard metrics are useful to create calculated metrics specific to each individual line item. <p>For example, ![Event](/help/assets/icons/Event.svg) **[!UICONTROL Orders]** ![Divide](/help/assets/icons/Divide.svg) ![Event](/help/assets/icons/Event.svg) **[!UICONTROL Sessions]** takes the orders for that specific line item and divides it by the number of sessions for that specific line item.  |
      |  **[!UICONTROL Grand total]**  | Use  **[!UICONTROL Grand total]** for the reporting period in every line item. If a formula consists of a single Grand total metric, the calculated metric displays the same Grand total number on every line item. Grand total metrics are useful when you want to create calculated metrics that compare against total data. <p>For example, ![Event](/help/assets/icons/Event.svg) **[!UICONTROL Orders]** ![Divide](/help/assets/icons/Divide.svg) ![Event](/help/assets/icons/Event.svg) **[!UICONTROL Total Sessions]** shows the proportion of orders against all sessions, not just the sessions to the specific line item. In this example, you specify **[!UICONTROL Grand Total]** for the ![Event](/help/assets/icons/Event.svg) **[!UICONTROL Sessions]** metric in your calculated metric, which will automatically turn it into ![Event](/help/assets/icons/Event.svg) **[!UICONTROL Total Sessions]**. |

   * Specify **[!UICONTROL Attribution]**. 

     1. You can either:

        * Disable **[!UICONTROL Use non-default attribution model]** to use the default column attribution model, which is Last Touch, with a lookback window of 30 days.
        * Enable **[!UICONTROL Use non-default attribution model]**. In the **[!UICONTROL Column attribution model]** dialog, 
       
          * Select a **[!UICONTROL Model]** from the attribution models.
          * Select a **[!UICONTROL Lookback window]**. If you select **[!UICONTROL Custom Time]**, you can define the time period in **[!UICONTROL Minute(s)]** up to **[!UICONTROL Quarter(s)]**. See [Lookback window](#lookback-window) for more information

     1. Select **[!UICONTROL Apply]** to apply the non-default attribution model. Select Cancel to cancel.

     If you already have defined a non-default attribution model, select **[!UICONTROL Edit]** to modify the selection.

See [Example](#example) for an example of using an attribution model and lookback window.


## Attribution {#attribution}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_nondefaultattributionmodel"
>title="Use non-default attribution model"
>abstract="Enable a non-default attribution model for the selected metric."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attributionmodel"
>title="Model"
>abstract="Select an attribution model for the metric."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_lasttouch"
>title="Last Touch"
>abstract="100% of credit goes to the last dimension value seen by a visitor."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_firsttouch"
>title="First Touch"
>abstract="100% of credit goes to the first dimension value seen by a visitor."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_linear"
>title="Linear"
>abstract="Credit is spread evenly across all dimension values."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_participation"
>title="Participation"
>abstract="100% credit to every dimension value seen by a visitor.<br/>Column totals are overstated."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_sametouch"
>title="Same Touch"
>abstract="Credit is given only to dimension values occurring on the same event as conversion."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_ushaped"
>title="U Shaped"
>abstract="40% credit to the first dimension value, 40% to the last, 20% shared by the middle."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_jcurve"
>title="J Curve"
>abstract="60% credit to the last dimension value, 20% to the first, 20% shared by the middle."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_inversej"
>title="Inverse J"
>abstract="60% credit to the first dimension value, 20% to the last, 20% shared by the middle."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_timedecay"
>title="Time Decay"
>abstract="Dimension values closest in time to a conversion get the most credit."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_custom"
>title="Custom"
>abstract="Define your own position based attribution weighting."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_algorithmic"
>title="Algorithmic"
>abstract="Credit is dynamically determined on a statistical algorithm."

<!-- markdownlint-enable MD034 -->


{{attribution-models-details}}


### Lookback window {#lookback-window}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_lookbackwindow"
>title="Lookback window"
>abstract="This setting determines the window of data attribution that will be applied for each conversion."

<!-- markdownlint-enable MD034 -->

{{attribution-lookback-window}}


### Attribution example {#attribution-example}

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


>[!MORELIKETHIS]
>
>[Attribution component settings](/help/data-views/component-settings/attribution.md)
>[Participation metric](participation-metric.md)
>

