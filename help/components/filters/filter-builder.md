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

* **Analytics top navigation**: Click **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Filters]**.
* **[!UICONTROL Analysis Workspace]**: With a project open in Analysis Workspace, select **[!UICONTROL + Components]** > **[!UICONTROL Create filter]**.
* **[!UICONTROL Reports & Analytics]**: Click **[!UICONTROL Analytics]** > **[!UICONTROL Reports]**, open an existing report and click the **Filter** icon in the left navigation, then click **[!UICONTROL Add]**.
* **[!UICONTROL Report Builder]**: [Add or edit filters in Report Builder](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/data-requests/segmentation.html).

## Builder criteria overview {#section_F61C4268A5974C788629399ADE1E6E7C}

You can add rule definitions and containers to define your filters. (For information about accessing the Filter builder, see [Access the Filter builder](#access-the-filter-builder).)

![](assets/segment_builder_ui_2.png)

1. **[!UICONTROL Title]**: Name the filter.
1. **[!UICONTROL Description]**: Provide a description for the filter. 
1. **[!UICONTROL Tags]**: [Tag the filter](/help/components/filters/manage-filters.md) you are creating by picking from a list of existing tags or creating a new tag.
1. **[!UICONTROL Definitions]**: This is where you [build and configure filters](/help/components/filters/filters-overview.md), add rules, and nest and sequence containers. 
1. **[!UICONTROL Show]**: (Top Container selector.) Lets you select the top-level [container](/help/components/filters/filters-overview.md) ( [!UICONTROL Person], [!UICONTROL Session], [!UICONTROL Event]). The default top-level container is the Event container.
1. **[!UICONTROL Options]**: (gear) icon

   * **[!UICONTROL + Add container]**: Lets you add a new container (below the top-level container) to the filter definition.
   * **[!UICONTROL Exclude]**: Lets you define the filter by excluding one or more dimensions, filters, or metrics.

1. **[!UICONTROL Dimensions]**: Components are dragged and dropped from the Dimensions list (orange sidebar).
1. **[!UICONTROL Operator]**: You can compare and constrain values using selected operators.
1. **[!UICONTROL Value]**: The value you entered or selected for the dimension or filter or metric.
1. **[!UICONTROL Attribution Models]**: Available for dimensions only, these models determine what values in a dimension to filter for. Dimension models are particularly useful in sequential filters.

   * **[!UICONTROL Repeating]** (default): Includes instances and persisted values for the dimension.
   * **[!UICONTROL Instance]**: Includes instances for the dimension.
   * **[!UICONTROL Non-repeating instance]**: Includes unique instances (non-repeating) for the dimension. This is the model applied in Flow when repeat instances are excluded.

   ![](assets/attribution-models.jpg)

      **Example: Event filter where eVar1 = A** 

      |  Example  | A  | A  |  A (persisted) | B  | A  | C  |
      |---|---|---|---|---|---|---|
      |  Repeating  | X  | X  | X  | -  | X  | -  |
      |  Instance  | X  | X  | - | - | X | - |
      |  Non-repeating instance  | X | - | - | -  | X  | -  |
1. **[!UICONTROL And/Or/Then]**: Assigns the [!UICONTROL AND/OR/THEN] operators between containers or rules. The THEN operator lets you [define sequential filters](/help/components/filters/filters-overview.md).
1. **[!UICONTROL Metric]**: (Green sidebar) Metric that was dragged and dropped from the Metrics list.
1. **[!UICONTROL Comparison]** operator: You can compare and constrain values using selected operators.
1. **[!UICONTROL Value]**: The value you entered or selected for the dimension or filter or metric.
1. **[!UICONTROL X]**: (Delete) Lets you delete this part of the filter definition.
1. **[!UICONTROL Experience Cloud publishing]**: Publishing an Adobe Analytics filter to the Experience Cloud lets you use the filter for marketing activity in [!DNL Audience Manager] and in other activation channels. [Learn more...](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-publish.html)
1. **[!UICONTROL Audience library]**: Adobe's audience services manage the translation of person data into audience filters. As such, creating and managing audiences is similar to creating and using filters, with the added ability to share the audience filter to the Experience Cloud. [Learn more...](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html)
1. **[!UICONTROL Search]**: Searches the list of dimensions, filters, or metrics.
1. **[!UICONTROL Dimensions]**: (List) Click the header to expand.
1. **[!UICONTROL Metrics]**: Click the header to expand.
1. **[!UICONTROL Filters]**: Click the header to expand.
1. **[!UICONTROL Data View selector]**: Lets you select the report suite that this filter will be saved under. You can still utilize the filter in all data views.
1. **[!UICONTROL Filter Preview]**: Lets you preview the key metrics to see whether you have a valid filter and how broad the filter is. Represents the breakdown of the dataset you can expect to see if you apply this filter. Shows 3 concentric circles and a list to show the number and percentage of matches for [!UICONTROL Event], [!UICONTROL Person], and [!UICONTROL Session] for a filter run against a dataset. This chart is updated immediately after you create or make changes to your filter definition.
1. **[!UICONTROL Product Compatibility]**: Provides a list of which Adobe Analytics products (Analysis Workspace, [!UICONTROL Reports & Analytics], Data Warehouse) with which the filter you created is compatible. Most filters are compatible with all products. However, not all operators and dimensions are compatible with all Analytics products, especially [Data Warehouse](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segment-reference/seg-compatibility.html). This chart is updated immediately after you make changes to your filter definition.
1. **[!UICONTROL Save]** or **[!UICONTROL Cancel]**: Saves or cancels the filter. After clicking **[!UICONTROL Save]**, you are taken to the Filter Manager where you can manage the filter.

Filters with embedded date ranges continue to operate differently in Analysis Workspace versus [!UICONTROL Reports & Analytics]: In Workspace, a filter with an embedded date range overrides the panel date range. By contrast, [!UICONTROL Reports & Analytics] gives you the intersection of the report date range and the filter's embedded date range.

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

## Add containers {#section_1C38F15703B44474B0718CEF06639EFD}

You can [build a framework of containers](/help/components/filters/filters-overview.md) and then place logic rules and operators between.

1. Click **[!UICONTROL Options > Add container]**.

   A new [!UICONTROL **Event**] container opens without an [!UICONTROL **Event**] (Page View) identified.

   ![](assets/new_container.png)

1. Change the container type as needed.
1. Drag a Dimension, Filter, or Event from the left pane to the container.
1. Continue to add new containers from the top-level **[!UICONTROL Options]** > **[!UICONTROL Add container]** button at the top of the definition, or add containers from within a container to nest logic.

   **OR**

   Select one or more rules and then click **[!UICONTROL Options]** > **[!UICONTROL Add container from selection]**. This turns your selection into a separate container.

## Use date ranges {#concept_252A83D43B6F4A4EBAB55F08AB2A1ACE}

You can build filters that contain rolling date ranges in order to answer questions about ongoing campaigns or events.

For example, you can easily build a filter that includes "everyone who has made a purchase over the past 60 days".

You create a Session container and within it, add the [!UICONTROL Last 60 days] time range and the metric [!UICONTROL Orders is greater than or equal to 1], with an AND operator.

Here is a video on using rolling date ranges in filters:

>[!VIDEO](https://video.tv.adobe.com/v/25403/?quality=12)

## Stack filters {#task_58140F17FFD64FF1BC30DC7B0A1B0E6D}

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

## Filter templates {#concept_5098446CC78D441E93B8E4D1D1EA6558}

Filter templates are provided for common filter use cases, such as "First-time Visits" or "Vists from Mobile Devices". They are available in Workspace projects and in the Filter builder as building blocks for new filters. 

Templates are denoted by the Adobe "A" logo. A sample of the templates are listed below:

<table id="table_98B87D807E9344C9BEBF072C65D87B1B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Template Name </th> 
   <th colname="col2" class="entry"> Definition </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Abandon Cart </td> 
   <td colname="col2">View data for persons that added items to their carts but did not order anything. In the Filter Definition, the container is Visit. The rule for this sequential filter is <p> Cart Additions is not null </p> <p>Then </p> <p>Orders equals 0. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> First Time Visits </td> 
   <td colname="col2">View data for persons that have visited a maximum of one [1] times. In the Filter Definition, the container is Visit. The rule is <p>Visit Number equals 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Non-Purchasers </td> 
   <td colname="col2">View data for persons that have not participated in an order event. In the Filter Definition, the container is Visitor. This filter uses the Exclude logic. The rule is <p>Orders is not null. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Non-Single Page Visit (Non-Bounces) </td> 
   <td colname="col2">View data for persons that visited more than once. In the Filter Definition, the container is Visitor. This filter uses the Exclude logic. The rule is <p>Single Access is not null. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Paid Search </td> 
   <td colname="col2">View data from persons originating from a paid search. In the Filter Definition, the container is Visit. The rule is <p>Paid Search equals 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Purchasers </td> 
   <td colname="col2">View data for persons that have participated in an order event. In the Filter Definition, the container is Visitor. The rule is <p>Orders is not null. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Return Visits </td> 
   <td colname="col2">View data from persons that have visited at least once. In the Filter Definition, the container is Visit. The rule is <p>Visit Number is greater than 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Single Page Visits </td> 
   <td colname="col2"> View data from visits in which you see a single page value, even though you may submit multiple page views during that visit. Single-page visits with exit link events are included in the filter. In the Filter Definition, the container is Visit. The rule is <p>Single Page Visits equals 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Viewed Product Didn't Add to Cart </td> 
   <td colname="col2">View data for persons that viewed products but had no cart additions. In the Filter Definition, the container is Visit. The rule for this sequential filter is <p>Product Views is not null </p> <p>Then </p> <p> Cart Additions equals 0. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visits from Campaign </td> 
   <td colname="col2">View data from persons referred by campaigns. In the Filter Definition, the container is Visit. The rule is <p>Tracking Code is not null. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visits from Mobile Devices </td> 
   <td colname="col2">View data from persons using mobile devices. In the Filter Definition, the container is Visit. The rule is <p>Mobile Device is not null. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visits from Natural Search </td> 
   <td colname="col2">View data from persons not originating from a paid search. In the Filter Definition, the container is Visit. The rule is <p>Paid Search equals 0. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visits from Non-Mobile Device </td> 
   <td colname="col2">View data from persons not using mobile devices. In the Filter Definition, the container is Visit. This filter uses the Exclude logic. The rule is <p>Mobile Device Type equals Mobile Phone </p> <p>Or </p> <p>Mobile Device Type equals Tablet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visits from Phones </td> 
   <td colname="col2">View data from persons using phones. In the Filter Definition, the container is Visit. The rule is <p>Device Type equals Mobile Phone. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visits from Search Engines </td> 
   <td colname="col2">View data from persons referred by search engines. In the Filter Definition, the container is Visit. The rule is <p>Referrer Type equals Search Engines. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visits from Social Sites </td> 
   <td colname="col2">View data from persons referred by social sites. In the Filter Definition, the container is Visit. The rule is <p>Referrer Type equals Social Networks. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visits from Tablets </td> 
   <td colname="col2">View data from persons using tablets. In the Filter Definition, the container is Visit. The rule is <p>Device Type equals Tablet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visits with Visitor ID Cookie </td> 
   <td colname="col2">View data from persons to your site, where a persistent cookie is required. In the Filter Definition, the container is Visit. The rule is <p>Persistent Cookie equals 1. </p> </td> 
  </tr> 
 </tbody> 
</table>