---
title: What is a data view in Customer Journey Analytics?
description: A data view specifies how you want to interpret elements of the data in the CJA connection, such as metrics, dimensions, sessions, etc..
exl-id: f69e6e38-ac98-49a6-b0ce-f642af2932ae
---
# What is a data view?

A data view sits on top of a Customer Journey Analytics (CJA) [connection](/help/connections/create-connection.md). A connection combines one or more datasets from Adobe Experience Platform and connects it to CJA. The data view specifies how you want to interpret elements of the data in the connection, such as metrics, dimensions, sessions, etc.. Data views are defined in preparation for reporting on the data in Workspace. 

>[!NOTE]
>
>Any settings that you select or change in a data view are retroactive and non-destructive. In other words, they will not change your underlying data permanently.

You can create different data views for the same connection, with very different sets of components (dimensions/metrics). Or create data views with different settings for visit timeout, attribution, etc.. For example, you could have one data view where all dimensions are set to [!UICONTROL Last Touch], and simultaneously, another data view (based on the same dataset) with all dimensions set to [!UICONTROL First Touch]. 

Workspace projects in Customer Journey Analytics are based on data views.

## What's new in data views?

The latest update to data views gives you a lot more flexibility in what you can do with data views. These enhancements let you **spontaneously change schema element settings in Data Views, without having to change the schema in Adobe Experience Platform or re-implementing your CJA environment**.

* **You can change a component from a Metric to a Dimension and vice versa**. You can create metrics from string fields or create dimensions from numeric fields. This makes your life easier, because you don't have to create a numeric field in your XDM schema for every metric you want. Instead, you can just spontaneously create it in the data views dialog. Here are some examples:
  * **Create one or more and/or one dimensions from a single schema field**. It's a one-to-many relationship. For example, you could create one or more Revenue metrics and/or one or more Revenue dimensions from a single schema field.
  * **Use a string field as a metric**: When you populate a schema in Experience Platform with a dataset, you might not know up front what schema elements you need. For example, you may not have realized that you needed a metric for "Errors on a page". As a result, you did not create a numeric schema element to this effect. By using a string element as a metric, you can now use the data views settings to specify that any time a string contains the word 'error', it can be used as a metric.
  * **Use a numeric field as a dimension**: For example, if you want to pull the Revenue metric from the Revenue dimension, the Revenue dimension would show each value as a dimension item ($100, $175, $1,000, etc.) and the number of instances for each dimension item. Revenue as a metric would behave like it always has.
  
* **You can create multiple metrics with different attribution models or with different lookback windows** from the same schema field.

* **You can edit the ID of a component** - this is used for cross-data-view compatibility. The component ID is what the reporting API uses to identify a specific metric or dimension. Because you can arbitrarily create many metrics or dimensions from one XDM field, we will give you the option to define your own component ID. As a result, a metric you use in one Workspace project can be compatible across data views (and the API), even if they are based on totally different fields from different connections or data views or from a different schema in XDM.

* **You can specify the friendly component name that will appear in Analysis Workspace**. By default, this name is inherited from the schema display name, but you can now overwrite it for this specific data view.

* **You can view more schema-related information about components** , such as: which dataset type (event, profile, lookup) it came from; which schema type (string, integer, etc.) it came from; and its schema path (the XDM field that it is based on).

* **You can tag a component** to make searching for it in Workspace easier.

* **You can hide a component in reporting**. Some metrics and dimensions settings require a second metric or dimension for configuration (like metric deduplication or purchase deduplication, for example). This allows you to define a metric or dimension that can be used in the settings of another metric or dimension without being exposed directly in reporting (such as purchase ID).

* **You can apply formatting to a metric**, such as showing decimal, time, percent, or currency; specifying decimal places; showing upward trend as green or red; and specifying currency options.

* You can **create a metric or dimension based on only some of the values in the schema field**. For example, if you wanted an "errors" metric, you could create a metric from the page name field but only include pages that contain the word 'error'. The errors metric created from this is supported by filters, insertable into calculated metrics, and it works with attribution, flow, fallout, etc.

* For dimensions, you can **automatically include or exclude only certain values within a specific field**. For example, if a developer sent in a wrong value of `dev mistake` into a field, you could easily exclude it from reporting using an exclude rule and it will behave as if it never existed in the data.

* You can **rename your containers** in a data view and have those renamed containers surface in any Workspace project that is based on that data view.

## Data views prerequisites

* Before you can create data views, you need to [set up one or more connections to Experience Platform datasets](/help/connections/create-connection.md).
* To create or manage a data view, you need a [set of permissions in Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=en#admin-access-permissions). 

## Data view settings you can override in Workspace

Some data view settings can be overridden in Analysis Workspace at the project level, others cannot.

* Lookback window
* Metric Attribution
* Whether or not users see the 'No Value' line item in a report

## Data view settings you cannot override in Workspace

* Component type
* Metric formatting
* Data view name
* Dimension allocation

## Delete data views

If you delete a data view in [!UICONTROL Customer Journey Analytics], an error message will indicate that any Workspace projects that depend on this deleted data view will no longer work.

## Next steps

* [Create data views](/help/data-views/create-dataview.md)
* [Data views use cases](/help/data-views/data-views-usecases.md)
* Details on how [persistence](/help/data-views/persistence.md) works
