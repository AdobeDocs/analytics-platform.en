---
title: Filters overview
description: Understand what filters are used for and how to create a simple filter.
exl-id: 21183e98-6593-4b22-99c7-4a03231acfe9
feature: Filters
role: User
---

# Filters overview

Customer Journey Analytics lets you build, manage, share, and apply powerful, focused audience filters to your reports. Filters let you identify subsets of persons, sessions or events based on characteristics or interactions. Filters are designed as codified audience insights that you can build for your specific needs, and then verify, edit, and share with other team members.

Filters can be based on: 

- attributes (browser type, device, number of visits, country, gender), 
- interactions (campaigns, keyword search, search engine), 
- exits and entries (persons from Facebook, a defined landing page, referring domain, geofence event), 
- custom variables (form field, defined categories, customer ID), 
- and other criteria.

See [Create filters](/help/components/filters/create-filters.md) for the various options available to create filters. You then build, modify, and save the definition of a filter in the [Filter builder](filter-builder.md). Alternatively, you can create quick filters using the [Quick filter builder](quick-filters.md). And you can also generate filters from visualizations in Workspace, for example using the [Fallout](/help/analysis-workspace/visualizations/fallout/configuring-fallout.md#context-menu) visualization. 

You use the [Filters manager](manage-filters.md) to manage filters.

## Plan filters

Especially, as an administrator, the proper planning of filters improves the chances that the filters are used. Consider the following when planning filters:

- **Audience**: Who will use your filters? Ensure you provide a good filter description so the audience understands:
  - What is this filter useful for?

  - When should I use this filter? 

- **Scope**: Which [Filter container](#filter-containers) best represents the data you are after? Use the smallest container possible.

- **Components**: Decide which components to include in the filter definition, and against which values the conditions should validate.

- **Process**: Consider an approval process for your filter. There is no approval workflow in Customer Journey Analytics but you can still organize a process to determine whether you approve a filter or not. 

- **Modularity**: Define filters with modularity in mind. So, the users of your filters can easily [stack filters](filter-builder.md#stack-filters) to create powerful new filters.


## Filter types

You can create three types of filters:

### Quick filters

Quick filters allow you to explore data easily within a given Workspace project, without the need of creating a filter in the [Filter Builder](/help/components/filters/create-filters.md). You define your filter within the Workspace interface directly. See [Quick filters](quick-filters.md) for more information.

### Regular filters

Regular filters let you identify data (persons, sessions, events) based on one or more conditions. If more than one conditions, you use logical operators like And and Or to define the filter further. You can use containers to group conditions and build more complex filters. See [Filter builder](filter-builder.md) for more information.

### Sequential filters

>[!IMPORTANT]
>
>You must have the **Select** package to create cross-channel sequential filters. Contact your administrator if you're unsure what Customer Journey Analytics package you have. 

Sequential filters let you identify data (persons, sessions, events) based on navigation (page views across your site, interactions with scenes in your mobile app, or using a menu on a set-top box). Sequential filters help you identify, for example, what a person likes and what a person avoids. You use the Then logical operator to define a sequential filter. See [Sequential filters](seg-sequential-build.md) for more information.


<!--
An example of a complex sequential filter if you want to find the persons that 

| Session One | Session Two | Session Three |
| --- | --- | --- |
| The person went to the main landing page A, excluded the campaign page B, and then viewed the Product page C.| The person again went to the main landing page A, excluded the campaign page B, and went again to the Product page C, and then to a new page D. | The person entered and followed that same path as in the first and second visits, then excluded page F to go directly to a targeted product on page G. |
-->

## Filter containers {#containers}

Filters are based on a Person-, Session-, and Event-level hierarchy using a nested container model. The nested containers allow you to define conditions between and within the containers. 


<table style="table-layout: fixed; border: none;" width="100%">

<tr>
<td style="background-color: #E5E4E2;" colspan="3" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_User_18_N.svg"/> Person</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200"></td>
<td style="background-color: #D3D3D3;" colspan="2" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Visit_18_N.svg"/> Session</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg"/> Event</td>
</tr>
</table>

>[!NOTE]
>
>For Adobe Analytics users:
> 
> - The **Person** container is known in Adobe Analytics as the **Visitor** container. 
> - The **Session** container is known in Adobe Analytics as the **Visit** container. 
> - The **Event** container is known in Adobe Analytics as the **Hit** container.
>

A filter sets conditions to filter persons, sessions or events based on conditions. For example, conditions to filter persons based on person characteristics and navigation traits. To further breakdown the data, you can filter on specific sessions, page view events, screen taps, menu choices on a set-top box, and more. But also filter on attributes that you have ingested from a CRM or loyalty system. The [Filter builder](/help/components/filters/filter-builder.md) provides a simple interface to build these subsets and apply conditions in nested, hierarchical Person, Session, or Event containers.

The container architecture employed in the [Filter builder](/help/components/filters/filter-builder.md) defines Person as the outermost container. The container contains overarching data specific for the person across sessions and events like page views, mobile application screens, or menu screens on a set-top box. A nested Session container lets you set rules to break down the person's data based on sessions. A nested Event container lets you break down person information based on individual interactions. Each container lets you report across a person's history, interactions broken down by sessions, or break down individual events. 

### Person container

The Person container includes every session and every event for the persons that qualify for the condition specified in the container. When you define a filter with a simple condition like `Page Name equals Checkout`, then the Person container resolves to:

- All persons that have visited the page with name `Checkout`.
- All sessions for these persons.
- All event data for these persons. 

As the most broadly defined container, reports generated at the Person container level returns events and sessions for all persons that qualify for the filter. The Person container is the most susceptible to change based on defined date ranges.
Person containers can include values based on a person's overall history:

- Days before the first purchase.
- Original entry page or mobile app home screen.
- Original referring domains. 

### Session container

The Session container lets you identify page interactions or mobile app interactions, campaigns, or conversions for a specific session. The Session container is the most commonly used container because it captures behaviors for the entire session once the rule is met. The Session container also lets you define which sessions you want to include or exclude in building and applying a filter.  When you define a filter with a simple condition like `Page Name equals Checkout`, then the Session container resolves to:

- All sessions where a page with name `Checkout` is visited.
- All event data for those sessions.

The session container can help you answer the following questions:

- How many sessions involved both web and call center data sources?
- Which pages contributed to a successful conversion to a sale?

Session containers include values based on events per session:

- Session type.
- Entry page.
- Return frequency.
- Participation metrics.
- Linearly allocated metrics.

Data views in Customer Journey Analytics let you determine how long a session lasts, but also when a new session should be created. For example, you can define a new mobile app session based on every time a user launches your mobile app. See [Session settings](/help/data-views/session-settings.md) for more information. 

### Event container

The Event container defines which page, mobile application, or other type of events that you would like to include or exclude from a filter. It is the most narrow of the containers available to let you identify specific clicks, page view, taps on button in a mobile app where a condition is true. The Event container lets you view a single tracking code, or isolate behavior within a particular area of your mobile app. You may also want to pinpoint a specific value when an action occurs, such as the marketing channel when an order was placed. When you define a filter with a simple condition like `Page Name equals Checkout`, then the Event container resolves to:

- All page view events where the page name equals `Checkout`.

Event containers include value-based, single page breakdowns for:

- Products
- List Props
- List dimensions
- Merchandising dimensions (in the context of events) 


### Logic group container

Logic Group enables you to group conditions into a single sequential filter checkpoint. As part of the sequence, the logic defined in the container identified as [!UICONTROL Logic Group] is evaluated after any prior sequential checkpoint and before any following sequential checkpoint. See [Logic Group](seg-sequential-build.md#logic-group) for more information.

### Nest containers

When creating containers within other containers, you are actually creating a filter within a filter. The following logic is applied to nested containers:

1. Determine what data is included using the outermost container. Any data that does not match this outer rule is discarded in the report.
2. Apply the nested filter definition to the remaining data. The nested filter definition does NOT apply to any data that the first definition discarded.
3. Repeat until all nested container filter definitions have been calculated. The remaining data is then included in the result and used for reporting.

>[!NOTE]
>
>When you nest a filter within a filter (for example, you drag a filter from the Components panel onto your filter definition), a container is created with a copy (not a reference) of the dragged filter definition. 

<!--
You can use nesting between containers and between conditions within a container. Here is what you can nest in each container:


| Container | What container you can nest inside |
| Event | Only event conditions |
| Session | Session


## Out-of-the-box filter template {#template}

Traditional Analytics comes with numerous out-of-the-box templates and calculated metrics. Many of them do not apply in Customer Journey Analytics, or have to be renamed or recreated. Others depend on a solution for context-aware variables in Customer Journey Analytics.

| Filter Name | Description |
| --- | --- |
| All Data | All Data is a required filter that gets dynamically added to reporting when a metric is added to the row of a Freeform table. |
-->

>[!MORELIKETHIS]
>
>[Create filters](create-filters.md)
>[Filter builder](filter-builder.md)
>[Quick filters](quick-filters.md)
>[Sequential filters](seg-sequential-build.md)
>[Manage filters](manage-filters.md)
>
