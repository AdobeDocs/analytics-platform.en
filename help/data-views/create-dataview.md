---
title: How to create a new data view in Customer Journey Analytics.
description: Describes all the settings needed to create new data views.
exl-id: 02494ef6-cc32-43e8-84a4-6149e50b9d78,35cbf69c-e1e5-4cf0-9bb4-6105d3e4c78e
---
# Create a data view

Creating a data view involves either creating metrics and dimensions from schema elements or utilizing standard components. Creating metrics or dimensions gives you an enormous amount of flexibility. Previously, the assumption was that if you had datasets in Adobe Experience Platform, string fields were used as dimensions and numeric fields were used as metrics. In order to change any of these fields, you had to edit your schema in Platform. The data views UI now allows a [more freeform definition of metrics and dimensions](/help/data-views/data-views.md). For more use cases, see [Data views use cases](/help/data-views/data-views-usecases.md).

## 1. Configure Data Views settings and containers

1. In Customer Journey Analytics, go to the **[!UICONTROL Data Views]** tab.
2. Click **[!UICONTROL Add]** to create a new data view and configure its settings.

![](assets/new-data-view.png)

| Setting | Description/Use case |
| --- | --- |
| [!UICONTROL Connection] | This field links the data view to the connection that you established earlier, which contains one or more Adobe Experience Platform dataset/s.|
| [!UICONTROL Name] | Giving the data view a name is mandatory. |
| [!UICONTROL Description] | A detailed description is not mandatory but is recommended. |
| [!UICONTROL Time zone] | Choose which time zone you want your data to be presented in. |
| [!UICONTROL Tags] | [!UICONTROL Tags] let you organize your data views into categories. |
| [!UICONTROL Containers] | You can rename your containers here to determine how they appear in any Workspace project that is based on this data view. [!UICONTROL Containers] are used in filters and fallout/flow, and so on, to define how broad or narrow the scope or context is. [Learn more](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/filters-overview.html?lang=en#filter-containers) |
| [!UICONTROL Person container name is…] | [!UICONTROL Person] (default). The [!UICONTROL Person] container includes every visit and page view for visitors within a specified time frame. You can rename this container to 'User' or any other term you prefer. |
| [!UICONTROL Session container name is…] | [!UICONTROL Session] (default). The [!UICONTROL Session] container lets you identify page interactions, campaigns, or conversions for a specific session. You can rename this container to 'Visit' or any other term you prefer. |
| [!UICONTROL Event container name is…] | [!UICONTROL Event] (default). The [!UICONTROL Event] container defines which page events you would like to include or exclude from a filter. |

Next, you can create metrics and dimensions from schema elements. You can also use Standard components.

## 2. Create metrics and dimensions from schema elements

1. In [!UICONTROL Customer Journey Analytics] > [!UICONTROL Data Views], click the [!UICONTROL Components] tab.

![](assets/components-tab.png)

You can see the [!UICONTROL Connection] at the top left, which contains the datasets, and its [!UICONTROL Schema fields] below. Keep in mind that:

* The components already included are the standard required components (system generated.) 
* Adobe applies the filter **[!UICONTROL Contains data]** by default, so that only Schema fields that contain data appear. If you are looking for a field that does not contain data, remove the filter.

1. Now drag a schema field, such as [!UICONTROL pageTitle], from the left rail into the Metrics or Dimensions section. 

   You can drag the same schema field into the dimensions or metrics sections multiple times and configure the same dimension or metric in different ways. 
   For example, from the **[!UICONTROL pageTitle]** field, you can create a dimension called "Product Pages", and another one "Error pages", etc., by renaming the **[!UICONTROL Component Name]** on the right. From the **[!UICONTROL pageTitle]**; field, you can also create metrics from a string value. For example,you could create one or more **[!UICONTROL Orders]** metrics with different attribution settings and different include/exclude values.

   ![](assets/components-tab-3.png)

   >[!NOTE]
   >
   >You can drag in whole schema field folders from the left rail and they will automatically be sorted into traditional sections. String fields will end up in the [!UICONTROL Dimensions] section and numerics in the [!UICONTROL Metrics] section. Or, you can click **[!UICONTROL Add all]** and all schema fields will be added.

1. Once you select the component, you see a number of settings appear on the right. Configure the component using the settings described below.

### Use [!UICONTROL Standard components]

Besides creating metrics and dimensions from schema elements, you can also use standard components in your data views.

[!UICONTROL Standard components] are components that are not generated from dataset schema fields but are instead system generated. Some system components are required in any data view to facilitate reporting capabilities in Analysis Workspace, while other system components are optional.

![](assets/standard-components.png)

These required standard components are added to each data view by default.

| Component Name | Dimension or Metric | Notes |
| --- | --- | --- |
| [!UICONTROL People] | Metric | This metric is based on the person ID specified in a [!UICONTROL Connection]. |
| [!UICONTROL Sessions] | Metric | This metric is based on the sessionization settings specified below. |
| [!UICONTROL Events] | Metric | This metric represents the number of rows from all event datasets in a [!UICONTROL Connection]. |
| [!UICONTROL Day] | Dimension | The ‘Day’ dimension reports the day that a given metric occurred. The first dimension item is the first day in the date range, and the last dimension item is the last day in the date range. |
| [!UICONTROL Week] | Dimension | The ‘Week’ dimension reports the week that a given metric occurred. The first dimension item is the first week in the date range, and the last dimension item is the last week in the date range.|
| [!UICONTROL Month] | Dimension | The Month dimension reports the month that a given metric occurred. The first dimension item is the first month in the date range, and the last dimension item is the last month in the date range. |
| [!UICONTROL Quarter] | Dimension | The ‘Quarter’ dimension reports the quarter that a given metric occurred. The first dimension item is the first quarter in the date range, and the last dimension item is the last quarter in the date range. |
| [!UICONTROL Year] | Dimension | The ‘Year’ dimension reports the year that a given metric occurred. The first dimension item is the first year in the date range, and the last dimension item is the most recent year in the date range. |
| [!UICONTROL Hour] | Dimension | The ‘Hour’ dimension reports the hour that a given metric occurred (rounded down). The first dimension item is the first hour in the date range, and the last dimension item is the last hour in the date range. |
| [!UICONTROL Minute] | Dimension | The ‘Minute’ dimension reports the minute that a given metric occurred (rounded down). The first dimension item is the first minute in the date range, and the last dimension item is the last minute in the date range. |

### Optional Standard components

Optional Standard components are available under the **[!UICONTROL Standard Components]** tab.

| Component Name | Dimension or Metric | Notes |
| --- | --- | --- |
| [!UICONTROL Session Starts] | Metric | This metric counts the number of events that were the first event of a session. When used in a filter definition (e.g. '[!UICONTROL Session Starts] exists'), it filters down to just the first event of every session. |
| [!UICONTROL Session Ends] | Metric | This metric counts the number of events that were the last event of a session. Similar to [!UICONTROL Session Starts], it can also be used in a filter definition to filter things down to the last event of every session. |
| [!UICONTROL Time Spent (seconds)] | Metric | The [!UICONTROL Time Spent] metric adds up the time between two different values for a dimension. |
| [!UICONTROL Time Spent per Event] | Dimension | [!UICONTROL Time Spent per Event] buckets the [!UICONTROL Time Spent] metric into [!UICONTROL Event] buckets. |
| [!UICONTROL Time Spent per Session] | Dimension | [!UICONTROL Time Spent per Session] buckets the [!UICONTROL Time Spent] metric into [!UICONTROL Session] buckets. |
| [!UICONTROL Time Spent per Person] | Dimension | [!UICONTROL Time Spent per Person] buckets the [!UICONTROL Time Spent] metric into [!UICONTROL Person] buckets. |
| [!UICONTROL Batch ID] | Dimension | Represents the Experience Platform batch that an [!UICONTROL Event] was part of. |
| [!UICONTROL Dataset ID] | Dimension | Represents the Experience Platform dataset that an [!UICONTROL Event] was part of. |

## Use the [!UICONTROL Duplicate] feature

Duplicating metrics or dimensions and then modifying specific settings is an easy way to create multiple metrics or dimensions from a single schema field. Just select the [!UICONTROL Duplicate] setting underneath the metric's or dimensions's name at the top right. Then modify the new metric or dimension and save it under a more descriptive name.

![](assets/duplicate.png)

### Filter schema fields and dimensions/metrics

You can filter schema fields in the left rail by the following data types:

![](assets/filter-fields.png)

You can also filter by datasets and by whether a schema field contains data or whether it is an identity. By default, we apply the **[!UICONTROL Contains data]** filter to all data views.

![](assets/filter-other.png)

## Add a global filter to you data view

You can add filters that apply to your entire data view. This filter will be applied to any report that you run in Workspace.

1. Click the [!UICONTROL Settings] tab in [!UICONTROL Data views].
1. Drag a filter from the list in the left rail to the [!UICONTROL Add filters] field.
