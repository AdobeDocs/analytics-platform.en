---
title: Prepare for critical differences when migrating to Customer Journey Analytics
description: Steps to transform Adobe Analytics data into Customer Journey Analytics data
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 5e3f0aa0-ba24-48c8-948c-ebb5c270f34d
---
# Prepare for critical differences when migrating to Customer Journey Analytics

As your organization evolves to use Customer Journey Analytics, explore these steps to prepare your data and to become aware of critical differences between the two technologies. This article is aimed at an administrator audience.

## Get comfortable with Report-time Processing {#report-time}

The reporting in Adobe Analytics relies on a significant amount of data pre-processing to generate results like the persistence that you see in [!UICONTROL eVars]. By contrast, Customer Journey Analytics runs those calculations at report run time.

[!UICONTROL Report time processing] opens the ability to apply settings that are retroactive and create multiple versions of variable persistence without needing to change how the underlying data is collected. 

This shift will result in some differences in how data is reported, especially for any variables that may have a long expiration window. You can begin by evaluating how report-time processing may impact your reporting using a [virtual report suite](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html). 

## Identify critical Segments and Calculated Metrics {#segments-calcmetrics}

Adobe Analytics segments (called [!UICONTROL filters] in Customer Journey Analytics) and calculated metrics are not compatible with Customer Journey Analytics. In many cases, these components can be rebuilt in Customer Journey Analytics using the new schemas and data available. 

To make the transition as smooth as possible for users when they transition between the systems, plan ahead by

1. Identifying the most critical of these components.

2. Documenting their definitions, and 

3. Identifying what fields will be required in the data to replicate them in Customer Journey Analytics as [Filters](/help/components/filters/filters-overview.md) and [Calculated Metrics](/help/components/calc-metrics/calc-metr-overview.md).

Here are a couple of videos to guide you:

* [Move Adobe Analytics segments to Customer Journey Analytics](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/moving-adobe-analytics-segments-to-customer-journey-analytics.html)

* [Move your Calculated Metrics from Adobe Analytics to Customer Journey Analytics](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/components/calc-metrics/moving-your-calculated-metrics-from-adobe-analytics-to-customer-journey-analytics.html)

## Other considerations

* Using the power of Customer Journey Analytics data views, you have a lot more flexibility in the definition of metrics and dimensions within Customer Journey Analytics. For example, you can use the value of a dimension to become the definition of a metric. [Learn more](/help/use-cases/data-views/data-views-usecases.md)

* If you have defined a custom calendar in Adobe Analytics, you will have similar [custom calendar capabilities](/help/components/date-ranges/custom-date-ranges.md) within Customer Journey Analytics. You need to ensure that your calendar is properly defined.

* In Customer Journey Analytics, you can define a custom visit/session timeout as well as define a metric that will start a new session. You can create data views with different session definitions to get insights above and beyond what was possible in Adobe Analytics. This capability may be particularly beneficial for mobile datasets.

* Consider providing a data dictionary for your users – or extend the SDR to include the Experience Platform field name for schema elements.

## Next steps

After moving to Customer Journey Analytics, if you notice any data discrepancies, you can compare your original Adobe Analytics data with the Adobe Analytics data that is now in Customer Journey Analytics. [Learn more](/help/troubleshooting/compare.md)
