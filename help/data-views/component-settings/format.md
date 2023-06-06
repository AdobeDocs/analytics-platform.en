---
title: Format component settings
description: Configure how a metric is formatted.
exl-id: 5ce13fe9-29fa-474c-bae3-65f275153a59
solution: Customer Journey Analytics
feature: Data Views
---
# Format component settings

Format lets you determine how a given metric is displayed.

![Format settings](../assets/format-settings.png)

| Setting | Description |
| --- | --- |
| **[!UICONTROL Format]** | Lets you specify the formatting of a metric as Decimal, Time, Percent, or Currency. |
| **[!UICONTROL Decimal Places]** | Not visible on Integer schema data types. Lets you specify the number of decimal places a metric displays. |
| **[!UICONTROL Date]** | Lets you determine how you want the date-time field displayed when used as a dimension in reporting. [Learn more](../../use-cases/data-views/data-views-usecases.md#date-and-date-time-use-cases) |
| **[!UICONTROL Date-Time]** | Lets you determine how you want the date-time field displayed when used as a dimension in reporting. [Learn more](../../use-cases/data-views/data-views-usecases.md#date-and-date-time-use-cases) |
| **[!UICONTROL Currency]** | Lets you determine which currency you want the metric to display in. See [Currency](#currency) more details. |
| **[!UICONTROL Show upward trend as]** | Lets you specify if an upward trend on this metric is good (green) or bad (red). |
| **[!UICONTROL True value]** and **[!UICONTROL False value]** | Only visible on Boolean schema data types. Lets you customize the dimension item label for `true` and `false` values. |

{style="table-layout:auto"}


## Currency

When you select **[!UICONTROL Currency]** as the [!UICONTROL Format] for a metric, you can determine how to display and convert currencies.

### Display currency

To display a currency for a metric:

1.  Enter the number of **[!UICONTROL Decimal places]**.
  
2.  Select a currency from the **[!UICONTROL Display currency in]** list.


### Convert and display currency

[!BADGE New Feature]{type=Positive}

{{release-limited-testing-section}}

To enable the conversion of a currency for a metric:
   
-   Set up your CJA connection to contain at least one event dataset that holds a currency code dimension for every event containing a currency metric. That currency code dimension uses an alphabetic currency code conforming to the [ISO 4217](https://www.iso.org/iso-4217-currency-codes.html) standard for representing currencies. For example USD for $, EUR for &euro;, GBP for £. 
  
-   You have (optionally) applied the [!UICONTROL Currency Code] context label to one or more dimensions that define currency codes available in your dataset.

    To apply the [!UICONTROL Currency Code] context label, in the [!UICONTROL Components] tab of your Data view:

    <!--![Currency Context Label](../assets/currency-context-label.png)-->

    1.  Select the dimension from one of your datasets that holds the currency codes. For example, [!UICONTROL Currency code].

    2.  Select **[!UICONTROL Currency Code]** from the [!UICONTROL Context labels] list.

    Repeat these steps in case that you have more dimensions holding currency codes you want to use for currency conversion.

>[!NOTE]
>
>The metric you select for currency conversion must have a numeric type (Double, Long, Integer, Short, Byte).


To define how to convert and display a currency for a metric:

1.  Enter the number of **[!UICONTROL Decimal places]**.

2.  Select **[!UICONTROL Convert Concurrency]**.

3.  Based on the applied context label, the appropriate dimension from the **[!UICONTROL Currency code dimension]** list is automatically selected. You can select any other dimension, including dimensions to which you additionally applied the Currency code context label.

4.  Select a currency from the **[!UICONTROL Convert and display currency in]** list.

### Frequently Asked Questions

+++ How is currency conversion executed?

Upon report time, the value of the metric and original currency code are converted to USD and then converted to the currency configured for display. For this conversion, the daily currency exchange rates are used, applicable for the time of the event.

+++

