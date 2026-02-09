---
title: Data views overview
description: A data view specifies how you want to interpret elements of the data in the Customer Journey Analytics connection, such as metrics, dimensions, sessions, etc.
exl-id: f69e6e38-ac98-49a6-b0ce-f642af2932ae
solution: Customer Journey Analytics
feature: Data Views
role: Admin
---
# Data views overview

A data view is a container specific to Customer Journey Analytics that lets you determine how to interpret data from a [connection](/help/connections/create-connection.md). It specifies all dimensions and metrics available in Analysis Workspace and which columns those dimensions and metrics obtain their data from. Data views are defined in preparation for reporting in Analysis Workspace.

>[!NOTE]
>
>Any settings that you select or change in a data view are retroactive and non-destructive. In other words, they do not permanently change your underlying data.

You can create different data views for the same connection, with very different sets of components (dimensions/metrics). Or create data views with different settings for visit timeout, attribution, etc. For example, you could have one data view where all dimensions are set to [!UICONTROL Last Touch], and simultaneously, another data view (based on the same dataset) with all dimensions set to [!UICONTROL First Touch].

Workspace projects in Customer Journey Analytics are based on data views.

>[!IMPORTANT]
>
>Up to 5,000 metrics and 5,000 dimensions can be added to a single data view.

## Data views capabilities {#capabilities}

Data views let you spontaneously change schema element settings, without having to change the schema in Adobe Experience Platform or re-implementing your Customer Journey Analytics environment.

* You can change a component from a metric to a dimension and vice versa. You can create metrics from string fields or create dimensions from numeric fields. This functionality makes your life easier, because you don't have to create a numeric field in your XDM schema for every metric you want. Instead, you can just spontaneously create it in the data views dialog. Here are some examples:
  * **Create one or more metrics and/or dimensions from a single schema field**. It's a one-to-many relationship. For example, you could create one or more Revenue metrics and/or one or more Revenue dimensions from a single schema field.
  * **Use a string field as a metric**: When you populate a schema in Experience Platform with a dataset, you might not know up front what schema elements you need. For example, you may not have realized that you needed a metric for *Errors on a page*. As a result, you did not create a numeric schema element to this effect. By using a string element as a metric, you can now use the data views settings to specify that any time a string contains the word `error`, it can be used as a metric.
  * **Use a numeric field as a dimension**: For example, if you want to pull the Revenue metric from the Revenue dimension, the Revenue dimension would show each value as a dimension item. And the number of instances for each dimension item as a metric.
  
* You can create multiple metrics with different attribution models or different lookback windows from the same schema field.

* You can edit the ID of a component for cross-data-view compatibility. The component ID is what the reporting API uses to identify a specific metric or dimension. Because you can arbitrarily create many metrics or dimensions from one XDM field, you have the option to define your own component ID. As a result, a metric you use in one Workspace project can be used compatibly across data views (and the API). Even if the metrics are based on totally different fields from different connections, data views, or from a different schema in XDM.

* You can specify the friendly component name that appears in Analysis Workspace. By default, this name is inherited from the schema display name, but you can now overwrite it for this specific data view.

* You can view more schema-related information about components. Such as: 
  
  * which dataset type (event, profile, lookup, summary) the component is originating from, 
  * which schema type (string, integer, etc.) it originating from, and
  * the schema path (the XDM field that it is based on).

* You can tag a component to make searching for it in Workspace easier.

* You can hide a component in reporting. Some metrics and dimensions settings require a second metric or dimension for configuration (like metric deduplication or purchase deduplication, for example). Hiding a component allows you to define a component that can be used in the settings of another component without being exposed in reporting.

* You can apply formatting to a metric, such as showing decimal, time, percent, or currency; specifying decimal places; showing upward trend as green or red; and specifying currency options.

* You can create a metric or dimension based on only some of the values in the schema field. For example, if you wanted an Errors metric, you could create a metric from the page name field but only include pages that contain the word `error`. The Errors metric created this way supports segments, can be inserted into calculated metrics, and works with attribution, flow, fallout, etc.

* For dimensions, you can automatically include or exclude only certain values within a specific field. For example, if a developer sent in a wrong value of `dev mistake` into a field, you could easily exclude it from reporting using an exclude rule. The dimension behaves as if the wrong value never existed in the data.

* You can rename your containers in a data view and have those renamed containers surface in any Workspace project that is based on that data view.

* You can enable the Data Insights Agent for a data view. 

## Data views prerequisites {#prerequisites}

* Before you can create data views, you need to [set up one or more connections to Experience Platform datasets](/help/connections/create-connection.md).
* To create or manage a data view, you need a [set of permissions in Adobe Admin Console](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-overview). 
* If you are using the [Adobe Analytics source connector](/help/data-ingestion/analytics.md) or do have Adobe Analytics background knowledge, you might want to understand how fields in your schemas and datasets relate to the Adobe Analytics counterparts. See [Analytics field mappings](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics) for more information.

## Data view settings you can override in Workspace {#settings-override}

Some data view settings can be overridden in Analysis Workspace at the project level, others cannot.

* [!UICONTROL Lookback window]
* Metric attribution
* Whether or not users see the [!UICONTROL No Value] line item in a report

## Data view settings you cannot override in Workspace {#settings-no-override}

* [!UICONTROL Component type]
* Metric formatting
* Data view name
* Dimension allocation

## Delete data views {#delete}

If you delete a data view in [!UICONTROL Customer Journey Analytics], an error message indicates that any [!UICONTROL Workspace] projects that depend on this deleted data view no longer works.

## Next steps

* [Create data views](/help/data-views/create-dataview.md)
* [Data views use cases](/help/use-cases/data-views/data-views-usecases.md)
