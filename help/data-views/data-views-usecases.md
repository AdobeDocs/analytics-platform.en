---
title: Use cases for data views in Customer Journey Analytics
description: Multiple use cases that show the flexibility and power of data views in Customer Journey Analytics
exl-id: 6ecbae45-9add-4554-8d83-b06ad016fea9
---
# Data views use cases

These use cases show the flexibility and power of data views in Customer Journey Analytics.

## 1. Create an Orders metric from a pageTitle (string) schema field

For example, when creating a data view, you could create an [!UICONTROL Orders] metric from a [!UICONTROL pageTitle] schema field that is a string. Here are the steps:

1. On the Components tab, drag the [!UICONTROL pageTitle] into the [!UICONTROL Metrics] section under [!UICONTROL Included Components].
   ![](assets/use-case1a.png)
1. Now highlight the metric you just dragged in and rename it under [!UICONTROL Component Settings] on the right:
   ![](assets/orders.png)
1. Open the [!UICONTROL Include/Exclude Values] dialog on the right and specify the following:
   ![](assets/orders2.png)

   The "confirmation" phrase indicates that this is an order. After reviewing all the page titles where those criteria are met, a "1" will be counted for each instance. The result is a new metric (not a calculated metric.) A metric that has included/excluded values can be used everywhere any other metric can be used. It works with Attribution IQ, filters, and everywhere else you can use standard metrics.
1. You can further specify an attribution model for this metric, such as [!UICONTROL Last Touch], with a [!UICONTROL Lookback window] of [!UICONTROL Session].
   You can also create another [!UICONTROL Orders] metric from the same field and specify a different attribution model for it, such as [!UICONTROL First Touch], and a different [!UICONTROL Lookback window], such as [!UICONTROL 30 days].

## 2. Use integers as dimensions

Previously, integers would automatically be treated as metrics in CJA. Now, numerics (including custom events from Adobe Analytics) can be treated as dimensions. Here is an example:

1. Drag the [!UICONTROL call_length_min] integer into the [!UICONTROL Dimensions] section under [!UICONTROL Included Components]:

   ![](assets/integers.png)

1. You can now add [!UICONTROL Value Bucketing] to present this dimension in a bucketed fashion in reporting. (Without bucketing, each instance of this dimension would appear as a line item in Workspace reporting.)

   ![](assets/bucketing.png)

## 3. Use numeric dimensions as "metrics" in flow diagrams

You can use a numeric dimension to get “metrics” into your [!UICONTROL  Flow] visualization. 

1. On the Data Views [Components](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=en#configure-component-settings) tab, drag the [!UICONTROL Marketing Channels] schema field into the [!UICONTROL Metrics] area under [!UICONTROL Included components]. 
2. In Workspace reporting, this flow shows [!UICONTROL Marketing Channels] flowing into [!UICONTROL Orders]:

![](assets/flow.png)

## 4. Do sub-event filtering

You can filter events to display only what you want to see. For example, use the include/exclude functionality in Data Views to focus only on products that generated sales of more than 50 Dollars. So if you have an order that includes a 50 Dollar product purchase and a 25 Dollar product purchase, we would remove only the 25 Dollar product purchase, not the entire order.

1. On the Data Views [Components](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=en#configure-component-settings) tab, drag the [!UICONTROL Orders] schema field into the [!UICONTROL Metrics] area under [!UICONTROL Included components].
1. Select the metric and configure the following on the right side:
   1. Under [!UICONTROL Format], select [!UICONTROL Currency].
   1. Under [!UICONTROL Currency], select USD.
   1. Under [!UICONTROL Include/Exclude Values], select the checkbox next to [!UICONTROL Set include/exclude values].
   1. Under [!UICONTROL Match], select [!UICONTROL If all criteria are met].
   1. Under [!UICONTROL Criteria], select [!UICONTROL is greater than or equal].
   1. Specify "50" as the value.

For more information on other data views settings, see [Create data views](/help/data-views/create-dataview.md).
For a conceptual overview of data views, see [Data views overview](/help/data-views/data-views.md).