---
description: Understand how the segment builder provides a canvas to drag and drop metric, dimensions, segments, and events to segment visitors based on container hierarchy logic, rules, and operators. Understand how you can build and save simple or complex segments that identify visitor attributes and actions across visits and page hits.
title: Build Segments
feature: Filters, Segments
role: User
exl-id: 160021f1-6942-4682-9114-d375307d9912
---
# Build segments {#build-segments}

>[!CONTEXTUALHELP]
>id="components_filters_createaudience"
>title="Create Audience"
>abstract="Audiences can be created from a segment and shared with the Adobe Experience Platform for activation."

>[!CONTEXTUALHELP]
>id="components_filters_datapreview"
>title="Data preview"
>abstract="Compares the data of this segment with data of the data view. The preview percentage is based on the total number in the data view from the **last 90 days**.<br><br/>If the preview is not loading, your connection could still be backfilling."

The **[!UICONTROL Segment builder]** dialog is used to create new or edit existing segments. The dialog is titled **[!UICONTROL New segment]** or **[!UICONTROL Edit segment]** for segments that you create or manage from the [[!UICONTROL Segment] manager](/help/components/segments/seg-manage.md).

>[!BEGINTABS]

>[!TAB Segment builder] 

![Segment details window showing fields and options described in the next section.](assets/filter-builder.png)

>[!TAB Create or Edit segment] 

![Segment details window showing fields and options described in the next section.](assets/create-edit-filter.png)

>[!ENDTABS]

1. Specify the following details (![Required](/help/assets/icons/Required.svg) is required):

   | Element | Description |
   | --- | --- |
   | **[!UICONTROL Data view]** | You can select the data view for the segment.  The segment you define is available as a segment in the [Settings](/help/data-views/create-dataview.md#settings-filters) tab of a data view. |
   | **[!UICONTROL Project-only segment]** | An info box to explain that the segment is only visible in the project where it is created and that the segment will not be added to your component list. Enable **[!UICONTROL Make this segment available to all your projects and add it to your component list]** to change that setting. This info box is only visible when you create a [quick segment](seg-quick.md) and turn the quick segment info a regular segment using **[!UICONTROL Open builder]** from the [!UICONTROL Quick segment] interface. |
   | **[!UICONTROL Title]** ![Required](/help/assets/icons/Required.svg) | Name the segment, for example, `Last month mobile customers`. |
   | **[!UICONTROL Description]** | Provide a description for the segment, for example, `Segment to define the mobile customers for the last month`. |
   | **[!UICONTROL Tags]**| Organize the segment by creating or applying one or more tags. Start typing to find existing tags you can select. Or press **[!UICONTROL ENTER]** to add a new tag. Select ![CrossSize75](/help/assets/icons/CrossSize75.svg) to remove a tag. |
   | **[!UICONTROL Definition]** ![Required](/help/assets/icons/Required.svg)| Define your segment using the [Definition builder](#definition-builder). |
   
   {style="table-layout:auto"}
   
1. To verify whether your segment definition is correct, use the constantly updated preview of the results of the segment at the top right.
1. To create an audience from the segment and share the audience with Experience Platform, select **[!UICONTROL Create audience from segment]**. See [Create and publish audiences](/help/components/audiences/publish.md) for more information.
1. Select:
   * **[!UICONTROL Save]** to save the segment.
   * **[!UICONTROL Save As]** to save a copy of the segment. 
   * **[!UICONTROL Delete]** to delete the segment.
   * **[!UICONTROL Cancel]** to cancel any changes you made to the segment or cancel the creation of a new segment.


## Definition builder

You use the Definition builder to construct your segment definition. In that construction, you use components, containers, operators and logic.

You can configure the type and scope of your definition: 

1. To specify the type of your definition, specify whether you want the build an include or exclude definition. Select ![Setting](/help/assets/icons/Setting.svg) **[!UICONTROL Options]** and from the drop-down menu **[!UICONTROL Include]** or **[!UICONTROL Exclude]**.
1. To specify the scope of your definition, select from the **[!UICONTROL Include]** or **[!UICONTROL Exclude]** drop-down menu whether you want the scope of the definition to be **[!UICONTROL Event]**, **[!UICONTROL Session]**, **[!UICONTROL Person]**, **[!UICONTROL Global Account]** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, **[!UICONTROL Account]** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, **[!UICONTROL Opportunity]** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, or  **[!UICONTROL Buying Group]** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}

You can always change these settings later.

### Components

A vital part of the construction of your segment definition is using dimensions, metrics, existing segments and date ranges. All these components are available from the component panel in the Segment builder.

![Start building a definition](assets/start-building-filter.gif){width=100%}

To add a component:

1. Drag and drop a component from the components panel onto **[!UICONTROL Drag and drop Metric(s), Segment(s), and/or Dimensions here]**. You can use the ![Search](/help/assets/icons/Search.svg) in the components bar to search for specific components.
1. Specify details for the component. For example, select a value from **[!UICONTROL Select value]**. Or enter a value. What and how you can specify one or more values depends on the component and the operator.
1. Optionally modify the default operator. For example, from **[!UICONTROL equals]** to **[!UICONTROL equals any of]**. See [Operators](seg-operators.md) for a detailed overview of the available operators.

To edit a component:

* Select a new operator for the component from the operator drop-down menu.
* Select or specify a different value for the operator if appropriate. 
* If the component type is a dimension, you can define the attribution model. See [Attribution model](#attribution) for more information.

To delete a component:

* Select ![CrossSize75](/help/assets/icons/CrossSize75.svg) in a component.

### Containers

You can group multiple components in one or more containers and define logic within and between containers. Containers allow you to build complex definitions for your segment.

![Add a container](assets/add-container.gif){Width=100%}

* To add a container, select **[!UICONTROL Add container]** from ![Setting](/help/assets/icons/Setting.svg) **[!UICONTROL Options]**.
* To add an existing component to the container, drag and drop the component into the container.
* To add another component to the container, drag and drop a component from the component panel into the container. Use the blue insertion line as a guide.
* To add another component outside of the container, drag and drop a component from the component panel outside of the container, but inside the main definition container. User the blue insertion line as a guide.
* To modify the logic between components in a container, between containers or between a container and a component, select the appropriate **[!UICONTROL And]**, **[!UICONTROL Or]**, **[!UICONTROL Then]**. When you select Then, you turn the segment into a sequential segment. See [Create sequential segment](seg-sequential-build.md) for more information.
* To switch the container level, select ![Globe](/help/assets/icons/Globe.svg) **[!UICONTROL Global Account]** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, ![Account](/help/assets/icons/Account.svg) **[!UICONTROL Account]** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, ![Opportunity](/help/assets/icons/Opportunity.svg) **[!UICONTROL Opportunity]** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, ![BuyingGroup](/help/assets/icons/BuyingGroup.svg) **[!UICONTROL Buying Group]** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, ![WebPage](/help/assets/icons/WebPage.svg) **[!UICONTROL Event]**, ![Visit](/help/assets/icons/Visit.svg) **[!UICONTROL Session]** or ![User](/help/assets/icons/User.svg) **[!UICONTROL Person]**.

You can use ![Setting](/help/assets/icons/Setting.svg) in a container for the following actions:

| Container action | Description |
|---|---|
| **[!UICONTROL Add container]** | Add a nested container to the container. |
| **[!UICONTROL Exclude]** | Exclude the result from the container in the segment definition. A thin red left bar identifies an exclude container.  |
| **[!UICONTROL Include]** | Include the result from the container in the segment definition. Include is the default. A thin gray left bar identifies an include container. |
| **[!UICONTROL Name container]** | Rename the container from its default description. Type a name in the text field. If you provide no input, the default description is used. |
| **[!UICONTROL Delete container]** | Delete the container from the definition. |


## Date ranges

You can build segments that contain rolling date ranges. This way, you are able to answer questions about ongoing campaigns or events. For example, you can build a segment that includes *everyone who has made an online purchase over the last 60 days*.

![Segment using rolling date range](assets/filter-rolling-date-range.gif)


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Rolling date ranges in segments](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/components/segmentation/rolling-date-ranges-in-segments){target="_blank"} for a demo video.

>[!ENDSHADEBOX]


## Stack segments {#stack}

You can build a segment using segments. When you use segments in a segment, you can optimize your segment and reduce the complexity.

Imagine you want to segment on the combination of device type (2) and US states (50). You could either build 100 segments, each for the unique combination of device type (mobile phone versus tablet) and US state. To get the tablet users in California, you would use one of the 100 segments:

![Simple segment for California and tablet](assets/filter-ca-tablet-single.png)

Or, you could define 52 segments: 50 segments for the US states, one for mobile phone and one for tablet. And then stack the segments to obtain the same results. To get the California tablet users, you would stack two segments:

![Stacked segment for CA and tablet](assets/filter-ca-tablet-stacked.png)


## Attribution {#attribution}

>[!CONTEXTUALHELP]
>id="components_filters_attribution_repeating"
>title="Repeating"
>abstract="Includes instances and persisted values for the dimension."


>[!CONTEXTUALHELP]
>id="components_filters_attribution_instance"
>title="Instance"
>abstract="Includes instances for the dimension."


>[!CONTEXTUALHELP]
>id="components_filters_attribution_nonrepeatinginstance"
>title="Non-repeating instance"
>abstract="Includes unique (non-repeating) instances for the dimension."




When you use a dimension in the Segment builder, you have the options to specify the attribution model for that dimension. The attribution model you select determines whether data qualifies for the condition you have specified for the dimension component.

Select ![Setting](/help/assets/icons/Setting.svg) within the dimension component and select one of the Attribution models from the popup: 

| Models | Description |
|---|---|
| **[!UICONTROL Repeating model (default)]** | Include instance and persisted values for the dimension to determine qualification. |
| **[!UICONTROL Instance]** | Include only instance values for the dimension to determine qualification. |
|  **[!UICONTROL Non-repeating instance]** | Include unique instance (non-repeating) values for the dimension to determine qualification. |


![Attribution model on dimension when building a segment](assets/filter-dimension-attribution.png)

### Example

As part of a segment definition you have specified the following condition: Page Name equals Women. Similar to the example above. You repeat this segment definition using the two other attribution models. So you have three segments each with their own attribution model:

* Women Page - Attribution - Repeating (default)
* Women Page - Attribution - Instance
* Women Page - Attribution - Non-repeating instance


The table below explains, for each attribution model, which incoming events are qualified ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) for that condition.


|  Women Page - Attribution - <br/>*attribution model*  | Event 1:<br/>Page Name equals<br/>Women  | Event 2:<br/>Page Name equals<br/>Men | Event 3:<br/>Page Name equals<br/>Women |  Event 4:<br/>Page Name equals<br/>Women<br/>(persisted) | Event 5:<br/>Page Name equals<br/>Checkout  |  Event 6:<br/>Page Name equals<br/>Women  | Event 7:<br/>Page Name equals<br/>Home  |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:--:|
|  Repeating (default) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  | ![Remove](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  | ![Remove](/help/assets/icons/Remove.svg)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  | ![Remove](/help/assets/icons/Remove.svg)  |
|  Instance  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  | ![Remove](/help/assets/icons/Remove.svg) |![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  | ![Remove](/help/assets/icons/Remove.svg) | ![Remove](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Remove](/help/assets/icons/Remove.svg) |
|  Non-repeating instance  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) |![Remove](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Remove](/help/assets/icons/Remove.svg) | ![Remove](/help/assets/icons/Remove.svg)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  | ![Remove](/help/assets/icons/Remove.svg)  |

An example report on events using the three segments looks like:

![Segment attribution model results](assets/filter-dimension-attribution-results.png)
