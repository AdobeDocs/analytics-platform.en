---
description: The Filter builder provides a canvas to drag and drop Metric Dimensions, Filters, and Events to filter persons based on container hierarchy logic, rules, and operators. This integrated development tool lets you build and save simple or complex filters that identify person attributes and actions across visits and events.
title: Build filters
feature: Filters
role: User
exl-id: 160021f1-6942-4682-9114-d375307d9912
---
# Filter builder

The **[!UICONTROL Filter builder]** dialog is used to create new or edit existing filters. The dialog is titled **[!UICONTROL New filter]** or **[!UICONTROL Edit filter]** for filters that you create or manage from the [[!UICONTROL Filters] manager](/help/components/filters/manage-filters.md).

1. Specify the following details (![Required](/help/assets/icons/Required.svg) is required):

   >[!BEGINTABS]
   
   >[!TAB Filter builder] 
   
   ![Filter details window showing fields and options described in the next section.](assets/filter-builder.png)

   >[!TAB Create / Edit filter] 
   
   ![Filter details window showing fields and options described in the next section.](assets/create-edit-filter.png)
   
   >[!ENDTABS]

   

   | Element | Description |
   | --- | --- |
   | **[!UICONTROL Project-only filter]** | An info box to explain that the filter is only visible in the project where it is created and that the filter will not be added to your component list. Enable **[!UICONTROL Make this filter available to all your projects and add it to your component list]** to change that setting. This info box is only visible when you create a [quick filter](quick-filters.md) and turn the quick filter info a regular filter using **[!UICONTROL Open builder]** from the [!UICONTROL Quick filter] interface. |
   | **[!UICONTROL Title]** ![Required](/help/assets/icons/Required.svg) | Name the filter, for example, `Last month mobile customers`. |
   | **[!UICONTROL Description]** | Provide a description for the filter, for example, `Filter to define the mobile customers for the last month`. |
   | **[!UICONTROL Tags]**| Organize filters by creating or applying a tag. Start typing to find existing tags you can select. Or press **[!UICONTROL Enter]** to add a new tag. Select ![CrossSize75](/help/assets/icons/CrossSize75.svg) to remove a tag. |
   | **[!UICONTROL Definition]** ![Required](/help/assets/icons/Required.svg)| Define your filter using the [Definition builder](#definition-builder). |
   
   {style="table-layout:auto"}
   
1. To verify whether your filter definition is correct, use the constantly updated preview of the results of the filter at the top right.
1. To create an audience from the filter and share the audience with Experience Platform, select **[!UICONTROL Create audience from filter]**. See [Create and publish audiences](/help/components/audiences/publish.md) for more information.
1. Select:
   * **[!UICONTROL Save]** to save the filter.
   * **[!UICONTROL Save As]** to save a copy of the filter. 
   * **[!UICONTROL Delete]** to delete the filter.
   * **[!UICONTROL Cancel]** to cancel any changes you made to the filter or cancel the creation of a new filter.


## Definition builder

You use the Definition builder to construct your filter definition. In that construction, you use components, containers, operators and logic.

You can configure the character and level of your your definition: 

1. To specify the type of your definition, specify whether you want the build an include or exclude definition. Select ![Setting](/help/assets/icons/Setting.svg) **[!UICONTROL Options]** and from the dropdown toggle **[!UICONTROL Include]** or **[!UICONTROL Exclude]**.
1. To specify the level of your definition, select from the **[!UICONTROL Include]** or **[!UICONTROL Exclude]** dropdown whether you want the definition to be based on **[!UICONTROL Event]**, **[!UICONTROL Session]** or **[!UICONTROL Person]**. 

You can always change these settings at a later time.

### Components

A vital part of the construction of your filter definition is using dimensions, metrics, existing filters and date ranges. All these components are available from the component panel in the Filter builder.

![Start building a definition](assets/start-building-filter.gif){width=100%}

To add a component:

1. Drag and drop a component from the components panel onto **[!UICONTROL Drag and drop Metric(s), Filter(s), and/or Dimensions here]**. You can use the ![Search](/help/assets/icons/Search.svg) in the components bar to search for specific components.
1. Specify details for the component. For example select a value from **[!UICONTROL Select value]**. Or enter a value. What and how you can specify one or more values depends on the component and the operator.
1. Optionally modify the default operator. For example, from **[!UICONTROL equals]** to **[!UICONTROL equals any of]**. See [Operators](operators.md) for a detailed overview of the available operators.

To edit a component:

* Select a new operator for the component from the operator dropdown list.
* Select or specify a different value for the operator if appropriate. 
* If the component type is a dimension, you can define the attribution model. See [Attribution model](#attribution-models) for more information.

To delete a component:

* Select ![CrossSize75](/help/assets/icons/CrossSize75.svg) in a component.

### Containers

You can group multiple components in one or more containers and define logic within and between containers. Containers allow you to build complex definitions for your filter.

![Add a container](assets/add-container.gif){Width=100%}

* To add a container, select **[!UICONTROL Add container]** from ![Setting](/help/assets/icons/Setting.svg) **[!UICONTROL Options]**.
* To add an existing component to the container, drag and drop the component into the container.
* To add another component to the container, drag and drop a component from the component panel into the container. Use the blue insertion line as a guide.
* To add another component outside of the container, drag and drop a component from the component panel outside the container but inside the main definition container. User the blue insertion line as a guide.
* To modify the logic between components in a container, between containers or between a container and a component, select the appropriate **[!UICONTROL And]**, **[!UICONTROL Or]**, **[!UICONTROL Then]**.
* To switch the container level, select ![WebPage](/help/assets/icons/WebPage.svg) **[!UICONTROL Event]**, ![Visit](/help/assets/icons/Visit.svg) **[!UICONTROL Session]** or ![User](/help/assets/icons/User.svg) **[!UICONTROL Person]**.

You can use ![Setting](/help/assets/icons/Setting.svg) in a container for the following actions:

| Container action | Description |
|---|---|
| **[!UICONTROL Add container]** | Add a nested container to the container. |
| **[!UICONTROL Exclude]** | Exclude the result from the container in the filter definition. An exclude container is identified by a red thin left bar. |
| **[!UICONTROL Include]** | Include the result from the container in the filter definition. This is the default. And include container is identified by a gray thin left bar. |
| **[!UICONTROL Name container]** | Rename the container from its default description. Type a name in the text field. If you provide no input, the default description is used. |
| **[!UICONTROL Delete container]** | Delete the container from the definition. | 


## Date ranges

You can build filters that contain rolling date ranges in order to answer questions about ongoing campaigns or events. For example, you can build a filter that includes *everyone who has made an online purchase over the last 60 days*.

![Filter using rolling date range](assets/filter-rolling-date-range.gif)

+++ Here is a video on using rolling date ranges in filters

>[!VIDEO](https://video.tv.adobe.com/v/25403/?quality=12)

{{videoaa}}

+++

## Stack filters {#stack}

You can build a filter using filters. When you use filters in a filter you can optimize your filter and reduce the complexity.

Imagine you want to filter on the combination of device type (mobile phone versus tablet) and US states (50 in total). You could either build 100 filters, each for the unique combination of device type and US state. To get the Californian tablet users you would use one of the filters:

![Simple filter for CA and tablet](assets/filter-ca-tablet-single.png)

Or, you could define 52 filters: 50 filters for the US states, one for mobile phone and one for tablet. And then stack the filters to obtain the same results. To get the Californian tablet users you would stack two filters:

![Stacked filter for CA and tablet](assets/filter-ca-tablet-stacked.png)


## Attribution models {#attribution}

![](assets/attribution-models.jpg)

**Example: Event filter where eVar1 = A** 

|  Example  | A  | A  |  A (persisted) | B  | A  | C  |
|---|---|---|---|---|---|---|
|  Repeating  | X  | X  | X  | -  | X  | -  |
|  Instance  | X  | X  | - | - | X | - |
|  Non-repeating instance  | X | - | - | -  | X  | -  |
