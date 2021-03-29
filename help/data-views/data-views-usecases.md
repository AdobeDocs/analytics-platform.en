---
title: Use cases for data views in Customer Journey Analytics
description: Multiple use cases that show the flexibility and power of data views in Customer Journey Analytics
---

# Data views use cases

The possibilities for 

## Create an Orders metric from a pageTitle (string) schema field

For example, when creating a data view, you could create an [!UICONTROL Orders] metric from a [!UICONTROL pageTitle] schema field that is a string. Here are the steps:

1. On the Components tab, drag the [!UICONTROL pageTitle] into the [!UICONTROL Metrics] section under [!UICONTROL Included Components].
   ![](assets/use-case1a.png)
1. Now highlight the metric you just dragged in and rename it under [!UICONTROL Component Settings] on the right:
   ![](assets/orders.png)
1. Open the [!UICONTROL Include/Exclude Values] dialog on the right and specify the following:
   ![](assets/orders2.png)

   The "confirmation" phrase indicates that this is an order. After reviewing all the page titles where those criteria are met, a "1" will be counted for each instance. The result is a new metric (not a calculated metric.) It works with Attribution IQ, filters, and everywhere else you can use standard metrics.
1. You can further specify an attribution model for this metric, such as [!UICONTROL Last Touch], with a [!UICONTROL Lookback window] of [!UICONTROL Session].
   You can also create another [!UICONTROL Orders] metric from the same field and specify a different attribution model for it, such as [!UICONTROL First Touch], and a different [!UICONTROL Lookback window], such as [!UICONTROL 30 days].

## Create multiple dimensions from one schema field

## Use integers as dimensions

34:00

Including bucketing