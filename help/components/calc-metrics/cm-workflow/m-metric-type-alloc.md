---
description: Learn about
title: Metric Type and Attribution
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
>id="cja_components_calculatedmetrics_nondefaultattributionmodel"
>title="Use non-default attribution model"
>abstract="Enable a non-default attribution model for the selected metric."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_attributionmodel"
>title="Model"
>abstract="Select an attribution model for the metric."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_attribution_lasttouch"
>title="Last Touch"
>abstract="100% of credit goes to the last dimension value seen by a visitor."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_attribution_firsttouch"
>title="First Touch"
>abstract="100% of credit goes to the first dimension value seen by a visitor."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_attribution_linear"
>title="Linear"
>abstract="Credit is spread evenly across all dimension values."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_attribution_participation"
>title="Participation"
>abstract="100% credit to every dimension value seen by a visitor.<br/>Column totals are overstated."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_attribution_sametouch"
>title="Same Touch"
>abstract="Credit is given only to dimension values occurring on the same event as conversion."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_attribution_ushaped"
>title="U Shaped"
>abstract="40% credit to the first dimension value, 40% to the last, 20% shared by the middle."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_attribution_jcurve"
>title="J Curve"
>abstract="60% credit to the last dimension value, 20% to the first, 20% shared by the middle."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_attribution_inversej"
>title="Inverse J"
>abstract="60% credit to the first dimension value, 20% to the last, 20% shared by the middle."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_attribution_timedecay"
>title="Time Decay"
>abstract="Dimension values closest in time to a conversion get the most credit."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_attribution_custom"
>title="Time Decay"
>abstract="Dimension values closest in time to a conversion get the most credit."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_attribution_algorithmic"
>title="Algorithmic"
>abstract="Credit is dynamically determined on a statistical algorithm."

<!-- markdownlint-enable MD034 -->



{{attribution-models-details}}


### Lookback window {#lookback-window}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_attribution_lookbackwindow"
>title="Lookback window"
>abstract="This setting determines the window of data attribution that will be applied for each conversion."

<!-- markdownlint-enable MD034 -->



{{attribution-lookback-window}}


### Example

{{attribution-example}}


>[!MORELIKETHIS]
>
>[Attribution component settings](/help/data-views/component-settings/attribution.md)
>[Participation metric](participation-metric.md)
>

