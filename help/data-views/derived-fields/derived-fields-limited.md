---
title: Derived fields
description: A derived field specifies report-time manipulation of schema fields and/or standard components through a set of available functions and function templates.
solution: Customer Journey Analytics
feature: Derived Fields
role: Admin
hide: yes
hidefromtoc: yes
---

# Derived fields {#derived-fields}

{{release-limited-testing}}

>[!IMPORTANT]
>
>This is preliminary documentation of new derived field functions that are not yet generally available. Use this information to learn about the new derived field functions. This documentation is  still subject to change and no legal obligations whatsoever can be derived from the current version of this article. 
><br/>See [Derived fields](derived-fields.md) for information on the derived fields functionality in general and the current available released functions and function templates.
>

## Function reference

{{select-package}}

For each supported function, find details below on:

- specifications: 
  - input data type: type of data supported,
  - input: possible values for input,
  - included operators: operators supported for this function (if any),
  - limitations: limitations that apply for this specific function,
  - output.

- use cases, including:
  - (optional) data before defining the derived field,
  - how to define the derived field,
  - (optional) data after defining the derived field.

- constraints (if applicable).



<!-- DATE MATH -->

### Date Math {#datemath}

>[!CONTEXTUALHELP]
>id="dataview_derivedfields_datemath"
>title="Date Math"
>abstract="This function provides the ability to return the difference between two date or date-time fields."

Returns the difference between two dates or two date-time fields.

+++ Details

## Specifications {#datemath-io}

| Input Data Type | Input | Included Operators | Limitations | Output |
|---|---|---|---|---|
| <ul><li>Date</li><li>Date-time</li></ul> | <ul><li>[!UICONTROL Scope]<ul><li>Event</li><li>Session</li><li>Person</li></ul></li><li>[!UICONTROL Value]:<ul><li>Date</li><li>Date-Time</li><li>Static Date (user entered)</li><li>Static Date-time (user entered)</li><li>Dynamic Date<ul><li>Today</li></ul></li><li>Dynamic Date-time<ul><li>Now</li></ul></li></ul></li><li>[!UICONTROL Granularity]:<ul><li>Seconds</li><li>Minutes</li><li>Hours</li><li>Days</li><li>Weeks</li><li>Months</li><li>Quarters</li><li>Years</li></ul></li><li>For each Date or Date-time return:<ul><li>First (within session or person)</li><li>Last (within session or person)</li></ul></li></ul> | <p>N/A</p>| <p>2 functions per derived field</p> | <p>New derived field</p> |

{style="table-layout:auto"}


## Use case 1 {#datemath-uc1}

 As the marketing analyst of an hotel company you would like to understand the difference of the number of days between customers check-in dates and booking dates over the last week.


### Derived field {#datemath-uc1-derivedfield}

You define a `Days between booking and check-in` derived field. You use the [!UICONTROL DATE MATH] function to define a rule to calculate the days for [!UICONTROL Scope] [!DNL Person] between the [!UICONTROL Booking Date] and [!UICONTROL Check-in Date]. You select [!UICONTROL Day] as [!UICONTROL Output granularity]. And you select [!UICONTROL Return the last] for both [!UICONTROL Booking Date] and [!UICONTROL Check-in Date] to ensure the last person scoped value is used in the calculation.

![Screenshot of the Date Math rule](assets/datemath-1.png)


## Use case 2 {#datemath-uc2}

As a marketing analyst of a brick and mortar shop you want to understand how many days ago was the last visit of a customer to the store. You use geolocation functionality within a mobile app and beacons in the shop to capture physical visits of customers.

### Derived field {#datemath-uc2-derivedfield}

You define a new `Days Since Visit To Shop` derived field. You use the [!UICONTROL DATE MATH] function to define a rule to calculate the days between a Custom Date-Time (which you specify in [!UICONTROL Date]) and the [!UICONTROL Local Time] (from your [!UICONTROL placeContext] field group of your event dataset) with a [!UICONTROL Deduplication scope] of [!UICONTROL Person]. You select [!UICONTROL Return the last] to ensure the last person scoped value for [!UICONTROL Local time] is used in the calculation. You select Day as the [!UICONTROL Output granularity].

![Screenshot of the Date Math rule 2](assets/datemath-2.png)


## Use case 3 {#datemath-uc3}

You want to understand the search time in minutes before a customer within a session places an order.

You define a new `Time Between Search And Order In Minutes` derived field that is the result of two [[!UICONTROL CASE WHEN] functions](#case-when) to define [!UICONTROL Search Time] and [!UICONTROL Order Time] values. 
Then you use these two values to calculate the difference with a [!UICONTROL DATE MATH] function with [!UICONTROL Scope] set to [!UICONTROL Session], values set to [!UICONTROL Search Time] and [!UICONTROL Order Time] and [!UICONTROL Output granularity] set to [!UICONTROL Minute]. For both values you select [!UICONTROL Return the first] to ensure the first [!UICONTROL Search Time] and [!UICONTROL Order Time] is returned.

![Screenshot of the Date Math rule 3](assets/datemath-3.png)



<!--
| Visitor ID | Marketing Channel | Events |
|----|---|---:|
| ABC123 | paid search | 1 |
| DEF123 | email | 1 |
| JKL123 | natural search | 1 |

{style="table-layout:auto"}

-->

+++



<!-- DEPTH -->

### Depth {#depth}

>[!CONTEXTUALHELP]
>id="dataview_derivedfields_depth"
>title="Depth"
>abstract="This function provides the ability to return the depth of any field, similar to the functionality of the event depth standard component."

Returns the depth of a field, similar to what is possible with the out-of-the-box [standard Event Depth dimension](/help/components/dimensions/overview.md#standard-dimensions).

+++ Details

## Specifications {#depth-io}

| Input Data Type | Input | Included Operators | Limitations | Output |
|---|---|---|---|---|
| Any | Any field| N/A | 3 functions per derived field | New derived field |

{style="table-layout:auto"}


<!--
## Example Data {#depth-example}

| event# | page name | search | product view | cart add  | order |
|:---:|---|:---:|:---:|:---:|:---:|
| 1 |  home page        |  0  | 0  | 0  | 0 |
| 2 |  search page      |  1  | 0  | 0  | 0 |
| 3 |  product page     |  0  | 0  | 0  | 0 |
| 4 |  cart page        |  0  | 0  | 1  | 0 |
| 5 |  confirmation     |  0  | 0  | 0  | 1 |

-->

## Use case {#depth-uc1}

You want to understand the search depth (which you can also interpret as the number of searches). So you can use that search depth later to lookup the search term associated with a specific search depth.


### Derived field {#depth-uc1-derivedfield}

You define a new `Search Depth` derived field. You use the [!UICONTROL DEPTH] function to define a rule to retrieve the depth of [!UICONTROL Search] and store that in a new derived field.

![Screenshot of the Depth rule](assets/depth-1.png)

+++


<!-- TYPECASE -->

### Typecast {#typecast}

>[!CONTEXTUALHELP]
>id="dataview_derivedfields_typecast"
>title="Typecast"
>abstract="This function provides the ability to change the field type on the fly to make the field available for additional transformations within Customer Journey Analytics."

Change the field type of a field to make it available for additional transformations within Customer Journey Analytics.

+++ Details

## Specifications {#typecast-io}

| Input Data Type | Input | Included Operators | Limit | Output |
|---|---|---|---|---|
| <ul><li>Numeric</li><li>Date</li><li>Date-time</li><li>String</li></ul> | <ul><li>[!UICONTROL Field] | <p><ul><li>Integer<ul><li>To String <strong>(Must)</strong></li></ul></li><li>Double<ul><li>To String <strong>(Must)</strong><ul><li>Include # of decimal places to inherit (max 5?)</li></ul></li><li>To Integer <strong>(Should)</strong></li></ul></li><li>Byte<ul><li>To String <strong>(Must)</strong></li></ul></li><li>Long<ul><li>To String <strong>(Must)</strong></li></ul></li><li>Date<ul><li>To String <strong>(Must)</strong><ul><li>Provide the ability to define the output format</li></ul></li><li>Examples<ul><li>Date (Example of January 7, 2025)<ul><li data-stringify-indent="1" data-stringify-border="0">MM-DD-YY<ul><li data-stringify-indent="2" data-stringify-border="0">Ex. 01-07-25</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">MM-DD-YYYY<ul><li data-stringify-indent="2" data-stringify-border="0">Ex. 01-07-2025</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">DD-MM-YY<ul><li data-stringify-indent="2" data-stringify-border="0">Ex. 07-01-25</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">DD-MM-YYYY<ul><li data-stringify-indent="2" data-stringify-border="0">Ex. 07-01-2025</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">YY-MM-DD<ul><li data-stringify-indent="2" data-stringify-border="0">Ex. 25-01-07</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">YYYY-MM-DD<ul><li data-stringify-indent="2" data-stringify-border="0">Ex. 2025-01-07</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">MM/DD/YY<ul><li data-stringify-indent="2" data-stringify-border="0">Ex. 01/07/25</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">MM/DD/YYYY<ul><li data-stringify-indent="2" data-stringify-border="0">Ex. 01/07/2025</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">YYYY/MM/DD<ul><li data-stringify-indent="2" data-stringify-border="0">Ex. 2025/01/07</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">YY/MM/DD<ul><li data-stringify-indent="2" data-stringify-border="0">Ex. 25/01/07</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">MMM DD, YYYY<ul><li data-stringify-indent="2" data-stringify-border="0">Ex. January 07, 2025</li></ul></li></ul></li></ul></li></ul></li><li>Date-time<ul><li>To String <strong>(Must)</strong><ul><li>Provide the ability to define the output format</li></ul></li><li>Examples<ul><li data-stringify-indent="0" data-stringify-border="0">Date-Time (Example of January 7, 2025 at 1:30pm, 52 seconds)<ul><li data-stringify-indent="2" data-stringify-border="0">MM-DD-YY hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">Ex. 01-07-25 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">MM-DD-YYYY hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">Ex. 01-07-2025 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">DD-MM-YY hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">Ex. 07-01-25 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">DD-MM-YYYY hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">Ex. 07-01-2025 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">YY-MM-DD hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">Ex. 25-01-07 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">YYYY-MM-DD hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">Ex. 2025-01-07 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">MM/DD/YY hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">Ex. 01/07/25 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">MM/DD/YYYY hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">Ex. 01/07/2025 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">YYYY/MM/DD hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">Ex. 2025/01/07 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">YY/MM/DD hh:mm :ss<ul><li data-stringify-indent="3" data-stringify-border="0">Ex. 25/01/07 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">MMM DD, YYYY hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">Ex. January 07, 2025 13:30:52</li></ul></li></ul></li></ul></li><li>String<ul><li>To Numeric <strong>(Should)</strong><ul><li>If we have values that are not numeric in nature, they will return null.</li><li>We will need the user to input the precision and the locale to use.&nbsp;</li></ul></li></ul></li></ul></li></ul></p> | <p>3 functions per derived field</p> | <p>New derived field</p> |

{style="table-layout:auto"}


## Use case 1 {#typecast-uc1}

You have an integer field, screen height (for example device.screenHeight from your event dataset), that you would like to use as a string based dimension.


### Derived field {#typecast-uc1-derivedfield}

You define a  `Screen Height` derived field. You use the [!UICONTROL TYPECAST] function to define a rule to [!UICONTROL Typecast to] [!UICONTROL String] the [!UICONTROL Screen height] field and store that in the new derived field.

![Screenshot of the Typecast rule 1](assets/typecast-1.png)



## Use case 2 {#typecast-uc2}

You want to use Revenue in a Cohort table (which only supports integers), but the Revenue field has a Double type.

![Screenshot of the Typecast rule 2](assets/typecast-2.png)


### Derived field {#typecast-uc2-derivedfield}

You define a  `Revenue (integer)` derived field. You use the [!UICONTROL TYPECAST] function to define a rule to [!UICONTROL Typecast to] [!UICONTROL Integer] the [!UICONTROL Revenue] field and store that in the new derived field.


+++
