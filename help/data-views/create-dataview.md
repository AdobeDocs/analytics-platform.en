---
title: Create or edit a data view
description: All settings that you can adjust to create or edit a data view.
exl-id: 02494ef6-cc32-43e8-84a4-6149e50b9d78
solution: Customer Journey Analytics
feature: Data Views
---
# Create or edit a data view

Creating a data view involves either creating metrics and dimensions from schema elements or utilizing standard components. Most schema elements can be either a dimension or a metric depending on your business's requirements. Once you drag a schema element into a data view, options appear on the right where you can adjust how the dimension or metric operates in CJA.

Here is a video on the topic:

>[!VIDEO](https://video.tv.adobe.com/v/35110/?quality=12&learn=on)

## Configure a data view

1. Log in to [Customer Journey Analytics](https://analytics.adobe.com) and go to the **[!UICONTROL Data Views]** tab.
2. Click **[!UICONTROL Add]** to create a data view, or click on an existing data view to edit it.

![New data view](assets/new-data-view.png)

### Data view settings

Provides overarching settings for the data view.

| Setting | Description |
| --- | --- |
| [!UICONTROL Connection] | This field links the data view to the connection that you established earlier, which contains one or more Adobe Experience Platform datasets. |
| [!UICONTROL Name] | Required. The name of the data view. This value appears in the top-right dropdown in Analysis Workspace. |
| [!UICONTROL Description] | Optional. Adobe recommends a detailed description so that users understand why the data view exists and who it is designed for. |

{style="table-layout:auto"}

### Containers

Designates the name of containers for the data view. Container names are frequently used in [filters](/help/components/filters/filters-overview.md#Filter-containers).

| Setting | Description |
| --- | --- |
| [!UICONTROL Person container name] | [!UICONTROL Person] (default). The [!UICONTROL Person] container includes every session and event for visitors within the specified time frame. If your organization uses a different term (for example, "Visitor" or "User"), you can rename the container here. |
| [!UICONTROL Session container name] | [!UICONTROL Session] (default). The [!UICONTROL Session] container lets you identify page interactions, campaigns, or conversions for a specific session. You can rename this container to 'Visit' or any other term your organization prefers. |
| [!UICONTROL Event container name] | [!UICONTROL Event] (default). The [!UICONTROL Event] container defines individual events in a dataset. If your organization uses a different term (for example, "Hits" or "Page Views"), you can rename the container here. |

{style="table-layout:auto"}

### Calendar

Indicates the calendar format that you want the data view to follow. You can have multiple data views based on the same [Connection](/help/connections/create-connection.md) and give them different calendar types or time zones. These data views can allow teams that use different calendar types to accommodate their respective needs with the same underlying data.

| Setting | Description |
| --- | --- |
| [!UICONTROL Time zone] | Choose which time zone you want your data to be presented in. If you choose a time zone that operates on Daylight Savings Time, data is automatically adjusted to reflect that. In the spring when clocks adjust one hour ahead, a one-hour gap is present. In the fall when clocks adjust one hour behind, one hour is repeated during the DST shift. |
| [!UICONTROL Calendar Type] | Determine how weeks of the month are grouped.<br>**Gregorian:** Standard calendar format. Quarters are grouped by month.<br>**4-5-4 Retail:** A standardized 4-5-4 retail calendar. The first and last months of the quarter contains 4 weeks, while the second month of the quarter consists of 5 weeks.<br>**Custom (4-5-4):** Similar to the 4-5-4 calendar except you can choose the first day of the year and which year that the "extra" week occurs.<br>**Custom (4-4-5):** The first and second months of each quarter contain 4 weeks, while the last week of each quarter consist of 5 weeks.<br>**Custom (5-4-4):** The first month of each quarter consists of 5 weeks, while the second and third month of each quarter consists of 4 weeks. |
| [!UICONTROL First month of the year] and [!UICONTROL First day of week] | Visible for the Gregorian calendar type. Specify what month you want the calendar year to start on, and what day you want each week to start on. |
| [!UICONTROL First day of current year] | Visible for custom calendar types. Specify what day of the year that you want the current year to start. The calendar automatically formats the first day of each week based on this value. |
| [!UICONTROL Year in which the "extra" week occurs] | With most 364-day calendars (52 weeks of 7 days each), each year accumulates leftover days until they form an extra week. This extra week is then added to the last month of that year. Specify which year that you want the extra week added to. |

{style="table-layout:auto"}

## Set a data view's components

Next, you can create metrics and dimensions from schema elements. You can also use Standard components.

1. Log in to [Customer Journey Analytics](https://analytics.adobe.com) and go to the **[!UICONTROL Data Views]** tab.
1. Click **[!UICONTROL Add]** to create a data view, or click on an existing data view to edit it.
1. Click the **[!UICONTROL Components]** tab.

   ![Components tab](assets/components-tab.png)

   You can see the [!UICONTROL Connection] at the top left, which contains the datasets, and its [!UICONTROL Schema fields] below. Note that the components already included are standard required components (system generated) for all data views. Adobe also applies the filter **[!UICONTROL Contains data]** by default, so that only Schema fields that contain data appear. If you want a field that does not contain data, remove this filter.

1. Drag a schema field, such as `pageTitle`, from the left rail into the Metrics or Dimensions section.

   You can drag the same schema field into the dimensions or metrics sections multiple times and configure the same dimension or metric in different ways. For example, from the `pageTitle` field, you can create a dimension called "Product Pages", and another one "Error pages", by using different [Component settings](component-settings/overview.md) on the right.

   ![Tab 3](assets/components-tab-3.png)

   If you drag a schema field folder from the left rail, they are automatically sorted into typical sections. String fields end up in the [!UICONTROL Dimensions] section and numeric schema types end up in the [!UICONTROL Metrics] section. You can also click **[!UICONTROL Add all]** and all schema fields are added to their respective locations.

1. Once you select the component, a number of settings appear on the right. Configure the component using [Component settings](component-settings/overview.md). Available component settings depend on if the component is a dimension/metric and the schema data type. Settings include:

   * [[!UICONTROL Attribution]](component-settings/attribution.md)
   * [[!UICONTROL Behavior]](component-settings/behavior.md)
   * [[!UICONTROL Format]](component-settings/format.md)
   * [[!UICONTROL Include exclude values]](component-settings/include-exclude-values.md)
   * [[!UICONTROL Metric deduplication]](component-settings/metric-deduplication.md)
   * [[!UICONTROL No value options]](component-settings/no-value-options.md)
   * [[!UICONTROL Persistence]](component-settings/persistence.md)
   * [[!UICONTROL Value bucketing]](component-settings/value-bucketing.md)

## Duplicate metrics or dimensions

Duplicating metrics or dimensions and then modifying specific settings is an easy way to create multiple metrics or dimensions from a single schema field. Select the [!UICONTROL Duplicate] setting underneath the metric's or dimensions's name at the top right. Modify the new dimension or metric and save it under a more descriptive name.

![Duplicate](assets/duplicate.png)

## Filter schema fields or datasets

You can filter schema fields in the left rail by the following data types:

![Filter fields](assets/filter-fields.png)

You can also filter by datasets and by whether a schema field contains data or whether it is an identity. By default, Adobe initially applies the **[!UICONTROL Contains data]** filter to all data views.

![Filter other](assets/filter-other.png)

## Settings tab

1. Log in to [Customer Journey Analytics](https://analytics.adobe.com) and go to the **[!UICONTROL Data Views]** tab.
1. Click **[!UICONTROL Add]** to create a data view, or click on an existing data view to edit it.
1. Click the **[!UICONTROL Settings]** tab.

### Global filter

You can add filters that apply to an entire data view. This filter is applied to any report that you run in Workspace. Drag a filter from the list in the left rail to the [!UICONTROL Add filters] field.

### Session settings

Determine the time period of inactivity between events before a session expires and a new one is started. A time period is required. You can optionally also force a new session to start when an event contains a certain metric.

Once all desired settings are specified, click **[!UICONTROL Save and finish]**.
