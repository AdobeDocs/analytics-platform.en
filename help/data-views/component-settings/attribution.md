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


## Example

{{attribution-example}}
