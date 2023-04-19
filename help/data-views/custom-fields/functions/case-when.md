---
title: Custom field Case When function
description: Description of the custom field case when function.
solution: Customer Journey Analytics
feature: Data Views
---

# Case When

This function applies conditionals, based on defined criteria from one or more fields. Those criteria are then used to define the values in a new custom field, based on the sequence of the conditions.

## Input / Operators / Output

| Input Data Type | Input | Included Operators | Output |
|---|---|---|---|
| <ul><li>String</li><li>Numeric</li><li>Date/Date-Time</li></ul> | <ul><li>Input Fields</li><li>Criteria</li></ul> | <p><u>Strings</u></p><ul><li>Equals</li><li>Equals any term</li><li>Contains the phrase</li><li>Contains any term</li><li>Contains all terms</li><li>Starts with</li><li>Starts with any term</li><li>Ends with</li><li>Ends with any term</li><li>Does not equal</li><li>Does not equal any term</li><li>Does not contain the phrase</li><li>Does not contain any term</li><li>Does not contain all terms</li><li>Does not start with</li><li>Does not start with any term</li><li>Does not end with</li><li>Does not end with any term</li><li>Is set</li><li>Is not set</li></ul><p><u>Numeric</u></p><ul><li>Equals</li><li>Does not equal</li><li>Is greater than</li><li>Is greater than or equal to</li><li>Is less than</li><li>Is less than or equal to</li><li>Is set</li><li>Is not set</li></ul><p><u>Dates</u></p><ul><li>Equals</li><li>Does not equal</li><li>Is later than</li><li>Is later than or equal to</li><li>Is before</li><li>Is before or equal to</li><li>Is set</li><li>Is not set</li></ul> | New custom field |

{style="table-layout:auto"}

## Use Case 1

You want to define rules to identify various marketing channels, by applying cascading logic to set a marketing channel field to the proper value:

* If the referrer is from a search engine and the page has a query string value where `cid` contains `ps_`, the marketing channel should be identified as a **Paid Search**.
* If the referrer is from a search engine and the page does not have the query string `cid`, the marketing channel should be identified as a **Natural Search**.
* If a page has a query string value where `cid` contains `em_`, the marketing channel should be identified as an **Email**.
* If a page has a query string value where `cid` contains `ds_`, the marketing channel should be identified as a **Display Ad**.
* If a page has a query string value where `cid` contains `so_`, the marketing channel should be identified as a **Paid Social**.
* If the referrer is from a referring domain of twitter.com, facebook.com, linkedin.com, or tiktok.com, the marketing channel should be identified as a **Natural Social**.
* If none of the above rules are matched, then the marketing channel should be identified as **Other Referrer**.

In case your site receives the following sample events, containing Referrer and Page URL, these events should be identified as follows:

Event | Referrer | Page URL | Marketing Channel |
|:----:|----|----|----|
| 1 | <https://facebook.com> | <https://site.com/home> | Natural Social |
| 2 | <https://abc.com> | <https://site.com/?cid=ds_12345678> | Display |
| 3 | |  <https://site.com/?cid=em_12345678> | Email |
| 4 | <https://google.com> | <https://site.com/?cid=ps_abc098765> | Paid Search |
| 5 | <https://google.com> | <https://site.com/?cid=em_765544332> | Email |
| 6 | <https://google.com> |  | Natural Search |

{style="table-layout:auto"}

### Data

Based on the example events listed above, your data looks like:

| Referrer | Page URL |
|----|----|
| <https://facebook.com> | <https://site.com/home> 
| <https://abc.com> | <https://site.com/?cid=ds_12345678> 
|  | <https://site.com/?cid=em_12345678>
| <https://google.com> | <https://site.com/?cid=ps_abc098765> 
| <https://google.com> | <https://site.com/?cid=em_765544332>
| <https://google.com> | 

{style="table-layout:auto"}

After defining a **Marketing Channel** custom field, using (among others) one or more [!UICONTROL Case When] functions, your data should look like:

| Marketing Channel |
|----|
| Natural Social |
| Display |
| Email |
| Paid Search |
| Email |
| Natural Search |

{style="table-layout:auto"}

### Rules

To define the [!UICONTROL Marketing Channel] custom field, you create the following rules in Rule Builder. These rules create values for a new Marketing Channel custom field, based on existing values for both Page URL and Referring URL field.

Note the usage of function Url Parse to fetch the values for Page Url and Referring Url before the Case When rules are applied.

![Concatenate](../assets/case-when-1.png)



## Use Case 2

You have collected several different variations of search within your Product Finding Methods variable. To understand the overall performance of search vs. browse, you must spend a great deal of time combining the results manually.

Imagine your site collects the following values from your Product Finding Methods variable. In the end, all of these values indicate a search.

| Collected value | Actual value |
|---|---|
search p13n_no | search |
search p13n_yes | search |
search refine p13n_no | search |
search refine p13n_yes | search |
search redirect p13n_yes | search |
search-redirect | search |

{style="table-layout:auto"}


### Data

Based on the example values listed above, before defining a new Product Finding Methods custom field using (among others) Case When functions, your data looks like:

| Product Finding Methods Field  |
|----|
| search p13_no | 
| search p13_yes | 
| browse | 
| search refine p13_no | 
| search refine p13_yes | 
| browse | 
| search redirect p13_yes | 
| search-redirect | 
| browse |

{style="table-layout:auto"}

After defining a **Product Finding Method** custom field, using (among others) one or more [!UICONTROL Case When] functions, your data should look like:

| Product Finding Method<br/>(custom field)|
|----|
| search |
| search |
| browse |
| search |
| search |
| browse |
| search |
| search |
| browse |

{style="table-layout:auto"}

### Rules

To define the new [!UICONTROL Product Finding Method] custom field, you create the following rules in Rule Builder. These rules apply [!UICONTROL Case When] logic to all possible variations of the old [!UICONTROL Product Finding Methods] values for search using the [!UICONTROL Contains the phrase] criterion. All variations end up as value `search` for the new [!UICONTROL Product Finding Method] custom variable.

![Case When 2](../assets/case-when-2.png)


## Use Case 3

As a travel company, you would like to bucket trip duration for booked trips so you can report on bucketed lengths of trips. 

Assumptions:

* The organization is collecting trip duration into a numeric field.
* They would like to bucket 1-3 day durations into a bucket called 'short trip'
* They would like to bucket 4-7 day durations into a bucket called 'medium trip'
* They would like to bucket 8+ day durations into a bucket called 'long trip'
* 132 trips were booked for a 1-day duration
* 110 trips were booked for a 2-day duration
* 105 trips were booked for a 3-day duration
* 99 trips were booked for a 4-day duration
* 92 trips were booked for a 5-day duration
* 85 trips were booked for a 6-day duration
* 82 trips were booked for a 7-day duration
* 78 trips were booked for an 8-day duration
* 50 trips were booked for a 9-day duration
* 44 trips were booked for a 10-day duration
* 38 trips were booked for an 11-day duration
* 31 trips were booked for a 12-day duration

Your desired report should look like:

| Trip Duration Type | Bookings |
|----|---:|
| medium trip | 358 |
| short trip | 347 |
| long trip | 241 |

{style="table-layout:auto"}

### Data

Before defining your Trip Duration custom field, your incoming data looks like:

| Trip Duration |
|---:|
| 1 | 
| 12 |
| 3 | 
| 6 | 
| 4 | 
| 8 | 
| 6 | 
| 2 | 
| 1 | 
| 2 | 
| 21 | 
| 8 | 

{style="table-layout:auto"}

After defining a **Trip Duration** custom field, using one or more [!UICONTROL Case When] functions, your data should look like:

| Trip Duration<br/>(custom field) |
|---|
|short trip|
|long trip|
|short trip|
|medium trip
|medium trip
|long trip
|medium trip
|short trip
|short trip|
|short trip|
|long trip|
|long trip|


### Rule

To define the new [!UICONTROL Trip Duration] custom field, you create the following rules in Rule Builder. These rules apply [!UICONTROL Case When] logic to bucket the old Trip Duration values into three values for the new Trip Duration custom field: short trip, medium  trip, and long trip.

![Case When 3](../assets/case-when-3.png)
