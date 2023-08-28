---
description: The Filter builder provides a canvas to drag and drop Metric Dimensions, Filters, and Events to filter persons based on container hierarchy logic, rules, and operators. This integrated development tool lets you build and save simple or complex filters that identify person attributes and actions across visits and events.
title: Build filters
feature: Filters
exl-id: 2107f301-4137-4e97-9aa7-07824b842e16
---
# Filter builder

The [!UICONTROL Filter builder] lets you build simple or complex filters that identify person attributes and actions across visits and events. It provides a canvas to drag and drop metric dimensions, events, or other filters in order to filter persons based on hierarchy logic, rules, and operators.

For information about how to create quick filters that apply only to the project where they are created, see [Quick filters](/help/components/filters/quick-filters.md).

## Access the Filter builder

You can access the Filter builder in any of the following ways:

* **Top navigation**: Click **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Filters]**.
* **[!UICONTROL Analysis Workspace]**: With a project open in Analysis Workspace, select **[!UICONTROL + Components]** > **[!UICONTROL Create filter]**.
* **[!UICONTROL Report Builder]**: [Work with Filters in Report Builder](/help/report-builder/work-with-filters.md).

## Builder criteria overview {#section_F61C4268A5974C788629399ADE1E6E7C}

You can add rule definitions and containers to define your filters. (For information about accessing the Filter builder, see [Access the Filter builder](#access-the-filter-builder).)

![](assets/segment_builder_ui_2.png)

| UI element | Description|
| --- | --- |
| **[!UICONTROL Title]** |  Name the filter |
| **[!UICONTROL Description]** |  Provide a detailed description for the filter. |
| **[!UICONTROL Tags]** | [Tag the filter](/help/components/filters/manage-filters.md) you are creating by picking from a list of existing tags or creating a new tag. |
| **[!UICONTROL Definitions]** | This is where you [build and configure filters](/help/components/filters/filters-overview.md), add rules, and nest and sequence containers. |
| **[!UICONTROL Include]** | (Top Container selector.) Lets you select the top-level [container](/help/components/filters/filters-overview.md) ( [!UICONTROL Person], [!UICONTROL Session], [!UICONTROL Event]). The default top-level container is the Event container. |
| **[!UICONTROL Options]** | (gear) icon | <ul><li>**[!UICONTROL + Add container]**: Lets you add a new container (below the top-level container) to the filter definition.</li><li>**[!UICONTROL Exclude]**: Lets you define the filter by excluding one or more dimensions, filters, or metrics.</li></ul> |
| **[!UICONTROL Dimensions]** | Components are dragged and dropped from the Dimensions list (orange sidebar). |
| **[!UICONTROL Operator]** | You can compare and constrain values using selected operators. (equals, does not equal, contains, contains all of, etc.) |
| **[!UICONTROL Value]** | The value you entered or selected for the dimension or filter or metric. |
| **[!UICONTROL Attribution Models]** | Available for dimensions only, these models determine what values in a dimension to filter for. Dimension models are particularly useful in sequential filters.<ul><li>**[!UICONTROL Repeating]** (default): Includes instances and persisted values for the dimension.</li><li>**[!UICONTROL Instance]**: Includes instances for the dimension.</li><li>**[!UICONTROL Non-repeating instance]**: Includes unique instances (non-repeating) for the dimension. This is the model applied in Flow when repeat instances are excluded.</li></ul>For an example, see the "Attribution models" section below. |
| **[!UICONTROL And/Or/Then]** | Assigns the [!UICONTROL AND/OR/THEN] operators between containers or rules. The THEN operator lets you [define sequential filters](/help/components/filters/filters-overview.md). |
| **[!UICONTROL Metric]** | (Green sidebar) Metric that was dragged and dropped from the Metrics list. |
| **[!UICONTROL X]** | (Delete) Lets you delete this part of the filter definition. |
| **[!UICONTROL Create audience from filter]** | Creating an audience from a filter lets you share the filter it with Adobe Experience Platform for activation. [Learn more...](/help/components/audiences/audiences-overview.md) |
| **[!UICONTROL Search component]** | Searches the list of dimensions, filters, or metrics. |
| **[!UICONTROL Dimensions]** | (List) The list of dimensions you can include in the filter. Click the header to expand. |
| **[!UICONTROL Metrics]** | The list of metrics you can include in the filter. Click the header to expand. |
| **[!UICONTROL Filters]** | The list of existing filters you can include in the filter. Click the header to expand. |
| **[!UICONTROL Data View selector]** | Lets you select the report suite that this filter will be saved under. You can still utilize the filter in all data views.|
| **[!UICONTROL Filter Preview]** | Lets you preview the key metrics to see whether you have a valid filter and how broad the filter is. Represents the breakdown of the dataset you can expect to see if you apply this filter. Shows 3 concentric circles and a list to show the number and percentage of matches for [!UICONTROL People], [!UICONTROL Sessions], and [!UICONTROL Reports Run] for a filter run against a dataset.<p>This chart is updated immediately after you create or make changes to your filter definition. |
| **[!UICONTROL Save]** or **[!UICONTROL Cancel]** | Saves or cancels the filter. After clicking **[!UICONTROL Save]**, you are taken to the Filter Manager where you can manage the filter. |

## Build a filter {#build-filters}

1. Simply drag a Dimension, Filter, or Metric Event from the left pane to the [!UICONTROL Definitions] field.

   ![](assets/drag_n_drop_dimension.png)

1. Set the [operator](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segment-reference/seg-operators.html) from the drop-down menu.
1. Enter or select a value for the item selected.
1. Add additional containers if needed, using **[!UICONTROL And]**, **[!UICONTROL Or]**, or **[!UICONTROL Then]** rules.
1. After placing the containers and setting the rules, see the results of the filter in the validation chart at the top right. The validator indicates the percentage and absolute number of page views, visits, and unique persons that match the filter you created.
1. Under **[!UICONTROL Tags]**, [tag](/help/components/filters/manage-filters.md) the container by selecting an existing tag or creating a new one.
1. Click **[!UICONTROL Save]** to save the filter.

   You are taken to the [Filter manager](/help/components/filters/manage-filters.md), where you can tag, share, and manage your filter in multiple ways.

## Add containers {#containers}

You can [build a framework of containers](/help/components/filters/filters-overview.md) and then place logic rules and operators between.

1. Click **[!UICONTROL Options > Add container]**.

   A new [!UICONTROL **Event**] container opens without an [!UICONTROL **Event**] (Page View) identified.

   ![](assets/new_container.png)

1. Change the container type as needed.
1. Drag a Dimension, Filter, or Event from the left pane to the container.
1. Continue to add new containers from the top-level **[!UICONTROL Options]** > **[!UICONTROL Add container]** button at the top of the definition, or add containers from within a container to nest logic.

   **OR**

   Select one or more rules and then click **[!UICONTROL Options]** > **[!UICONTROL Add container from selection]**. This turns your selection into a separate container.

## Use date ranges {#date-ranges}

You can build filters that contain rolling date ranges in order to answer questions about ongoing campaigns or events.

For example, you can easily build a filter that includes "everyone who has made a purchase over the past 60 days".

You create a Session container and within it, add the [!UICONTROL Last 60 days] time range and the metric [!UICONTROL Orders is greater than or equal to 1], with an AND operator.

Here is a video on using rolling date ranges in filters:

>[!VIDEO](https://video.tv.adobe.com/v/25403/?quality=12)

## Stack filters {#stack}

Stacking filters works by combining the criteria in each filter using an 'and' operator, and then applying the combined criteria. This can be done in a Workspace project directly or in Filter builder. 

For example, stacking a "mobile phone users" filter and a "US geography" filter would return data only for mobile phone users in the US.

Think of these filters as building blocks or modules that you can include in a filter library, for users to use as they see fit. That way, you can dramatically reduce the number of filters needed. For example, assume you have 40 filters:

* 20 for mobile phone users in different countries (US_mobile, Germany_mobile, France_mobile, Brazil_mobile, etc.) 
* 20 for tablet users in different countries (US_tablet, Germany_tablet, France_tablet, Brazil_tablet, etc.)

By using filter stacking, you can reduce your filter count to 22 and stack them as needed. You would need to create these filters:

* one filter for mobile users 
* one filter for tablet users 
* 20 filters for the different geographies

>[!NOTE]
>
>When stacking two filters, they are by default joined by an AND statement. This cannot be changed to an OR statement.

1. Go to the Filter builder.

1. Provide a title and description for the filter.

1. Click **[!UICONTROL Show filters]** to bring up the list of filters in the left navigation.

1. Drag the filters you want to stack to the filter definition canvas.

1. Select [!UICONTROL **Save**].

## Attribution models {#attribution}

![](assets/attribution-models.jpg)

**Example: Event filter where eVar1 = A** 

|  Example  | A  | A  |  A (persisted) | B  | A  | C  |
|---|---|---|---|---|---|---|
|  Repeating  | X  | X  | X  | -  | X  | -  |
|  Instance  | X  | X  | - | - | X | - |
|  Non-repeating instance  | X | - | - | -  | X  | -  |