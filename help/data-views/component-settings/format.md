---
title: Format component settings
description: Configure how a metric is formatted.
exl-id: 5ce13fe9-29fa-474c-bae3-65f275153a59
solution: Customer Journey Analytics
feature: Data Views
role: Admin
---
# Format component settings {#format-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_metric_format"
>title="Format"
>abstract="Determine how a component is displayed when used in reports."

<!-- markdownlint-enable MD034 -->


Format lets you determine how a given metric is displayed when used in reports.

## Configure format settings for a metric

You can determine how a given metric is displayed by adjusting its format settings.

1. In Customer Journey Analytics, select the [!UICONTROL **Data views**] tab.

1. Select the data view that contains the component whose format setting you want to configure. 

1. Select the [!UICONTROL **Components**] tab.

1. Select the component that you want to configure, then expand the [!UICONTROL **Format**] section on the right side of the page.

   ![Format settings](../assets/format-settings.png)

1. Specify the following information:

   | Setting | Description |
   | --- | --- |
   | **[!UICONTROL Format]** | Lets you specify the formatting of a metric as Decimal, Time, Percent, or Currency. |
   | **[!UICONTROL Decimal]** | Not visible on Integer schema data types. Lets you specify the number of decimal places a metric displays. |
   | **[!UICONTROL Date]** | Lets you determine how you want the date-time field displayed when used as a dimension in reporting. [Learn more](../../use-cases/data-views/data-views-usecases.md#date-and-date-time-use-cases) |
   | **[!UICONTROL Date-Time]** | Lets you determine how you want the date-time field displayed when used as a dimension in reporting. [Learn more](../../use-cases/data-views/data-views-usecases.md#date-and-date-time-use-cases) |
   | **[!UICONTROL Currency]** | Lets you determine which currency you want the metric to display in. <p>If you analyze global data where transactions occur in different currencies, see  [Use currency conversion](#use-currency-conversion).</p> |
   | **[!UICONTROL Show upward trend as]** | Lets you specify if an upward trend on this metric is good (green) or bad (red). |
   | **[!UICONTROL True value]** and **[!UICONTROL False value]** | Only visible on Boolean schema data types. Lets you customize the dimension item label for `true` and `false` values. |

   {style="table-layout:auto"}

## Use currency conversion {#use-currency-conversion}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_metric_format_currencyconversion"
>title="Currency conversion"
>abstract="Select a currency code dimension to configure and display currency in a selected currency type."

<!-- markdownlint-enable MD034 -->

Currency conversion in Customer Journey Analytics can be extremely valuable for businesses that operate internationally. By removing the complexities of manual currency conversion, currency conversion in Customer Journey Analytics brings uniformity and clarity to financial data. Currency conversion keeps track of daily historical exchange rates and maintains those daily rates for a period of 4 years. 

For example, if an e-commerce business operates in the US, UK, and EU, sales data can be automatically converted to USD, ensuring easy comparison and holistic understanding of performance.

>[!NOTE]
>
>Before you begin configuring a metric for currency conversion, consider the following:
>
>* The metric you select for currency conversion must have a numeric type (Double, Long, Integer, Short, Byte).
>* Set up your Customer Journey Analytics connection to contain at least one event dataset that holds a currency code dimension for every event containing a currency metric. That currency code dimension uses an alphabetic currency code conforming to the [ISO 4217](https://www.iso.org/iso-4217-currency-codes.html) standard for representing currencies. These values should be in full uppercase format, such as USD for $, EUR for &euro;, GBP for £. 

To determine how currencies are displayed and converted for a given metric:

1. Begin configuring the metric for which you want to use currency as the format, as described above, in [Configure format settings for a metric](#configure-format-settings-for-a-metric). 

1. With the metric selected, make the following selections in the [!UICONTROL **Format**] section on the right side of the page:

   * In the [!UICONTROL **Format**] field, select [!UICONTROL **Currency**]. 

   * In the [!UICONTROL **Decimal places**] field, choose the number of decimal places the metric displays.

     This option is available only if the metric has a numeric type of 'Double'.

   * Select the [!UICONTROL **Convert Currency**] option.

   * In the [!UICONTROL **Select currency code dimension**] field, select the dimension that represents the currency you are converting from (the currency that your data is based on). For example, select a dimension called [!UICONTROL **Currency code**].

     If you don't have a dimension in your current data schema that contains a currency code field, you can create a new currency code field using [Data Prep](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html), [Data Distiller](https://experienceleague.adobe.com/docs/experience-platform/query/data-distiller/overview.html), or [Derived Fields](/help/data-views/derived-fields/derived-fields.md). Data Prep is suitable only for new implementations because it is only on a go-forward basis. Depending on an organization's setup, Data Distiller and Derived Fields can be used to access the currency code values historically.

   * In the [!UICONTROL **Convert and display currency in**] field, choose the currency in which you want data to be converted.

1. Repeat these steps if you want to apply currency conversion to additional metrics.



### Frequently Asked Questions

+++ How is currency conversion executed?

Upon report time, the value of the metric and original currency code are converted to USD and then converted to the currency configured for display. For this conversion, the daily currency exchange rates are used, applicable for the time of the event.

+++

