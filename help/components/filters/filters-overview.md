---
title: Filters Overview
description: Understand what filters are used for and how to create a simple filter.
exl-id: 21183e98-6593-4b22-99c7-4a03231acfe9
---

# Filters overview {#overview}

Customer Journey Analytics lets you build, manage, share, and apply powerful, focused audience filters to your reports. Filters let you identify subsets of persons based on characteristics or website interactions. Filters are designed as codified audience insights that you can build for your specific needs, and then verify, edit, and share with other team members.

Filters can be based on 

- attributes (browser type, device, number of visits, country, gender), 
- interactions (campaigns, keyword search, search engine), 
- exits and entries (persons from Facebook, 
- a defined landing page, referring domain), 
- custom variables (form field, defined categories, customer ID), 
- and other criteria.

You can build and save filters in the Filter Builder, or generate filters from a Fallout visualization (in Workspace). In addition, filters can be used together as stacked filters. 

Filtering includes the [Filter Builder](/help/components/filters/filter-builder.md) to construct filters and run a pre-test, and the [Filter Manager](/help/components/filters/manage-filters.md) to collect, tag, approve, set security, and share filters across your organization.

The maximum number of filters you can create per IMS organization is 50,000.

## Filter types {#types}

For information about the available types of filters available and how to create them, see [Create filters](/help/components/filters/create-filters.md). 

## Sequential filters {#sequential}

Sequential filters let you identify persons based on navigation and page view across your site, providing a filter of defined actions and interactions. Sequential filters help you identify what a person likes and what a person avoids. When building sequential filters, the THEN operator is used to define and order person navigation.

Here is an example:

<!--![](assets/sequential_fil.png)-->

| Session One | Session Two | Session Three |
| --- | --- | --- |
| The person went to the main landing page A, excluded the campaign page B, and then viewed the Product page C.| The person again went to the main landing page A, excluded the campaign page B, and went again to the Product page C, and then to a new page D. | The person entered and followed that same path as in the first and second visits, then excluded page F to go directly to a targeted product page G. |

## Filter containers {#containers}

Filters are based on a Person-, Session-, and Event-level hierarchy using a nested container model. The nested containers allow you to define person attributes and actions based on rules between and within the containers. 


<table style="table-layout: fixed; border: none;">

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
>The Person container was formerly known as the Visitor container. The Session container was called the Visit container, and the Event container used to be the Hit container.

A Filter sets conditions to filter a person based on the person's attributes or interactions with your site. To set conditions in a filter, you set rules to filter persons based on person characteristics and/or navigation traits. To further break down person data, you can filter based on specific visits and/or page view hits for each person. The Filter Builder provides a simple architecture to build these subsets and apply rules as nested, hierarchical Person, Session, or Event containers.

The container architecture employed in the Filter Builder defines Person as the outermost container, containing overarching data specific for the person across visits and page views. A nested Session container lets you set rules to break down the person's data based on sessions, and a nested Event container lets you break down person information based on individual page views. Each container lets you report across a person's history, interactions broken down by sessions, or break down individual events. 

### Person container {#person}

The Person container includes every visit and page view for persons within a specified time frame. A filter at the Person level returns the page that meets the condition plus all other pages viewed by the person (and only constrained by defined date ranges). As the most broadly defined container, reports generated at the Person container level returns page views across all visits and lets you generate a multi-visit analysis. Therefore, the Person container is the most susceptible to change based on defined date ranges.
Person containers can include values based on a person's overall history:

* Days Before First Purchase
* Original Entry Page
* Original Referring Domains 

### Session container {#session}

The Session container lets you identify page interactions, campaigns, or conversions for a specific session. The Session container is the most commonly used container because it captures behaviors for the entire visit session once the rule is met. The Session container also lets you define which sessions you want to include or exclude in building and applying a filter. It can help you answer the following questions:

- How many sessions engaged with both Web and Call Center data sources?
- Which pages contributed to a successful conversion to a sale?

Session containers include values based on occurrence per session:

- Session Type
- Entry Page
- Return Frequency
- Participation Metrics
- Linearly allocated metrics 

### Event container {#event}

The Event container defines which page events that you would like to include or exclude from a filter. It is the most narrow of the containers available to let you identify specific clicks and page view where a condition is true. The Event container lets you view a single tracking code, or isolate behavior within a particular section of your site. You may also want to pinpoint a specific value when an action occurs, such as the marketing channel when an order was placed.

Event containers include values-based, single-page breakdowns:

- Products
- List Props
- List dimensions
- Merchandising dimensions (in context of events) 

## Out-of-the-box filter template {#template}

Traditional Analytics comes with numerous out-of-the-box template filters (filters) and calculated metrics. Many of them do not apply in CJA, or have to be renamed or recreated. Others depend on a solution for context-aware variables in CJA.

| Filter Name | Description |
| --- | --- |
| All Data | All Data is a required filter that gets dynamically added to reporting when a metric is added to the row of a Freeform table. |
