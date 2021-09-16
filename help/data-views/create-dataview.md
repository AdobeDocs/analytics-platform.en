---
title: Create a data view
description: All settings that you can adjust to create or edit a data view.
exl-id: 02494ef6-cc32-43e8-84a4-6149e50b9d78,35cbf69c-e1e5-4cf0-9bb4-6105d3e4c78e
---
# Create a data view

Creating a data view involves either creating metrics and dimensions from schema elements or utilizing standard components. Most schema elements can be either a dimension or a metric depending on your business's requirements. Once you drag a schema element into a data view, options appear on the right where you can adjust how the dimension or metric operates in CJA.

## Configure Data Views settings and containers

1. In Customer Journey Analytics, go to the **[!UICONTROL Data Views]** tab.
2. Click **[!UICONTROL Add]** to create a new data view and configure its settings.

![New data view](assets/new-data-view.png)

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

## Create metrics and dimensions from schema elements

1. In [!UICONTROL Customer Journey Analytics] > [!UICONTROL Data Views], click the [!UICONTROL Components] tab.

![Components tab](assets/components-tab.png)

You can see the [!UICONTROL Connection] at the top left, which contains the datasets, and its [!UICONTROL Schema fields] below. Keep in mind that:

* The components already included are the standard required components (system generated.) 
* Adobe applies the filter **[!UICONTROL Contains data]** by default, so that only Schema fields that contain data appear. If you are looking for a field that does not contain data, remove the filter.

1. Now drag a schema field, such as [!UICONTROL pageTitle], from the left rail into the Metrics or Dimensions section. 

   You can drag the same schema field into the dimensions or metrics sections multiple times and configure the same dimension or metric in different ways.
   For example, from the **[!UICONTROL pageTitle]** field, you can create a dimension called "Product Pages", and another one "Error pages", etc., by renaming the **[!UICONTROL Component Name]** on the right. From the **[!UICONTROL pageTitle]**; field, you can also create metrics from a string value. For example,you could create one or more **[!UICONTROL Orders]** metrics with different attribution settings and different include/exclude values.

   ![Tab 3](assets/components-tab-3.png)

   >[!NOTE]
   >
   >You can drag in whole schema field folders from the left rail and they are automatically sorted into traditional sections. String fields end up in the [!UICONTROL Dimensions] section and numerics in the [!UICONTROL Metrics] section. Or, you can click **[!UICONTROL Add all]** and all schema fields are added.

1. Once you select the component, you see a number of settings appear on the right. Configure the component using the settings described in

* [[!UICONTROL Component] settings overview](/help/data-views/component-settings/overview.md)
* [[!UICONTROL Attribution] component settings](/help/data-views/component-settings/attribution.md)
* [[!UICONTROL Behavior] component settings](/help/data-views/component-settings/behavior.md)
* [[!UICONTROL Format] component settings](/help/data-views/component-settings/format.md)
* [[!UICONTROL Include|exclude] component settings](/help/data-views/component-settings/include-exclude-values.md)
* [[!UICONTROL Metric deduplication] component settings](/help/data-views/component-settings/metric-deduplication.md)
* [[!UICONTROL No value] component settings](/help/data-views/component-settings/no-value-options.md)
* [[!UICONTROL Persistence] component settings](/help/data-views/component-settings/persistence.md)
[[!UICONTROL Value bucketing] component settings](/help/data-views/component-settings/value-bucketing.md)

## Use the [!UICONTROL Duplicate] feature

Duplicating metrics or dimensions and then modifying specific settings is an easy way to create multiple metrics or dimensions from a single schema field. Just select the [!UICONTROL Duplicate] setting underneath the metric's or dimensions's name at the top right. Then modify the new metric or dimension and save it under a more descriptive name.

![Duplicate](assets/duplicate.png)

## Filter schema fields and dimensions/metrics

You can filter schema fields in the left rail by the following data types:

![Filter fields](assets/filter-fields.png)

You can also filter by datasets and by whether a schema field contains data or whether it is an identity. By default, we apply the **[!UICONTROL Contains data]** filter to all data views.

![Filter other](assets/filter-other.png)

## Add a global filter to the data view

You can add filters that apply to an entire data view. This filter is applied to any report that you run in Workspace.

1. Click the [!UICONTROL Settings] tab in [!UICONTROL Data views].
1. Drag a filter from the list in the left rail to the [!UICONTROL Add filters] field.
