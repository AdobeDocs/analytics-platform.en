---
title: Custom fields
description: A custom field specifies report-time manipulation of schema fields and/or standard components through a set of available functions and function templates.
solution: Customer Journey Analytics
feature: Data Views
hide: yes
hidefromtoc: yes
---

# Custom fields

Custom fields are an important part of the real-time reporting functionality in Customer Journey Analytics (CJA). A custom field allows you to define (often complex) data manipulations on the fly, through a customizable rule builder. You can then use that custom field as a component (metric or dimension) in Workspace or even further define as a component in Data view. 

Custom fields can save a significant amount of time and effort, compared to transforming or manipulating your data in other locations outside of CJA. Such as Data Prep, Data Distiller, or within Extract Transform Load (ETL) / Extract Load Transform (ELT) processes.

Custom fields are defined within [Data views](../data-views.md), and are based on a set of functions and  applied to available schema fields and/or standard components.

Example use cases are:

-   Define a custom Page Name field that corrects improper collected page name values to correct page name values. 

-   Define a custom Marketing Channel field that determines the proper marketing channel based on one or more conditions (for example URL parameter, page URL, page name).


## Custom field interface {#custom-field-interface}

When you create or edit a custom field, you use the custom field interface.

![Custom field dialog](assets/custom-field-dialog.png)


|  | Name | Description
|---------|----------|--------|
| 1 | **Selector** | Select and drag and drop your ![Function](assets/Smock_Function_18_N.svg) function, ![Function template](assets/Smock_FileTemplate_18_N.svg) function template, ![Schema field](assets/Smock_Folder_18_N.svg) schema field, or standard field on to the rule builder. <br/>You can search for function, function templates, schema, and standard fields using the Search box. <br/>You can filter the selected object list by selecting Filter and specify filters in the Filter field by dialog. You can easily remove filters using the x for each filter. | 
| 2 | **Rule builder** | Build your custom field sequentially using one or more rules. Every rule is always associated with only one function. The function type determines the interface of the rule<br/>See the [Rule interface](#rule-interface) for more information. |
| 3 | **[!UICONTROL **Field Settings**]** | Define the name and description of your custom field. | 
| 4 | **[!UICONTROL **Final Output**]** | Shows an on-the-fly updated preview of  output values, based on data over the last 30 days and the changes you make to the custom field in the Rule builder. |

When accessing the Custom field interface for the first time, the [!UICONTROL Start with a field template] wizard is shown. 

![Custom field wizard](assets/field-template-dialog.png)

1. Select the template that best describes the type of field you are trying to create. 
2. Select the **[!UICONTROL **Select**]** button to continue.

Your Custom field dialog is populated with rules and functions required or useful for the type of field you selected. See [Function templates](#function-templates) for more information on the available templates.

{style="table-layout:auto"}

## Rule interface

When you define a rule in the Rule builder, you use the rule interface.

![Rule Interface](assets/rule-interface.png)

|  | Name | Description
|---------|----------|--------|
| A | **Rule Name** | By default the rule name is **Rule X** (X referring to a sequence number). To edit the name of a rule, select its name and type in the new name, for example `Query Parameter`.
| B | **Function Name** | The selected function name for the rule, for example **URL PARSE**. When the function is the last in the sequence of functions and determines the final output values, the function name is followed by **FINAL OUTPUT**, for example **URL PARSE - FINAL OUTPUT**. <br/>To show a popup with more information on the function, select ![Help](assets/Smock_HelpOutline_18_N.svg).
| C | **Rule Description** | You can optionally add a description to a rule.<br/>Select ![More](assets/More.svg), then select **[!UICONTROL **Add Description**]** to add a description or **[!UICONTROL **Edit Description**]** to edit an existing description.<br/>Use the editor to enter a description. You can use the toolbar to format the text (using style selector, bold, italic, underline, right, left, centered, color, number list, bullet list) and adding links to external information. <br/>To finish editing the description, click outside of the editor. |
| D | **Function Area** | Defines the logic of the function. The interface depends on the type of function. See [Custom field functions](custom-field-functions.md) on detailed information for each of the functions supported. |

{style="table-layout:auto"}

## Create a custom field

1.  In CJA's main interface, select **[!UICONTROL **Data views**]** from the top rail.

2.  Select an existing Data view or create a Data view. See [Data views](../data-views.md) for more information.

3.  Select the **[!UICONTROL **Components**]** tab of the Data view.

4.  Select **[!UICONTROL **Create custom field**]** from the left rail.
   
5.  To define your custom field, use the **[!UICONTROL **Create custom field**]** interface. See [Custom field interface](#custom-field-interface).

    To save your new custom field, select **[!UICONTROL **Save**]**.

6.  Your new custom field is added to the **[!UICONTROL **Custom fields >**]** container, as part of **[!UICONTROL **Schema fields**]** in the left rail of your Data view.


## Edit a custom field

1.  In CJA's main interface, select **[!UICONTROL **Data views**]** from the top rail.

2.  Select an existing Data view. See [Data views](../data-views.md) for more information.

3.  Select the **[!UICONTROL **Components**]** tab of the Data view.

4.  Select **[!UICONTROL **Schema fields**]** tab in [!UICONTROL Connection] pane.

5.  Select **[!UICONTROL **Custom fields >**]** container.

6.  Hover over the custom field that you want to edit, and select ![Edit](assets/Smock_Edit_18_N.svg).

7.  To modify your custom field, use **[!UICONTROL **Edit custom field**]** interface. See [Custom field interface](#custom-field-interface).

    -   Select **[!UICONTROL **Save**]** to save your updated custom field.

    -   Select **[!UICONTROL **Cancel**]** to cancel any changes you made to the custom field.

    -   Select **[!UICONTROL **Save As**]** to save the custom field as a new custom field. The new custom field with have the same name as the original edited custom field with (copy) added to it.

## Delete a custom field

1.  In CJA's main interface, select **[!UICONTROL **Data views**]** from the top rail.

2.  Select an existing Data view. See [Data views](../data-views.md) for more information.

3.  Select the **[!UICONTROL **Components**]** tab of the Data view.

4.  Select **[!UICONTROL **Schema fields**]** tab in [!UICONTROL Connection] pane.

5.  Select **[!UICONTROL **Custom fields >**]** container.

6.  Hover over the custom field that you want to delete, and select ![Edit](assets/Smock_Edit_18_N.svg).

7.  In the Use **[!UICONTROL **Edit custom field**]** interface, select Delete.

    A [!UICONTROL Delete component] dialog asks you to confirm the deletion. Consider any external references there might exist to the custom field outside of the Data view. 
    
    - Select **[!UICONTROL **Continue**]** to delete the custom field.


## Function Templates {#function-template}

To quickly create a custom field for specific use cases, function templates are available. These function templates can be accessed from the Selector area in the Custom field interface or are presented upon first use in the [!UICONTROL Start with a field template] wizard.


+++### Marketing channels template

This template is configured to use the URL PARSE and CASE WHEN functions multiple times to get appropriate values from a URL and use these values to apply the logic to identify the URL to a specific marketing channel.

![Marketing channel template](assets/marketing-channel-template.png)

+++

+++### Data clean up template

>[!WARNING]
>
>Could not find any information on this template.


+++

## Functions Reference {#function-reference}

For each function, find below:

-   inputs, operators and, outputs

-   use cases, including:
    - data before defining the custom field
    - how to define the custom field
    - data after defining the custom field

<!-- CASE WHEN -->

+++ ### Case When

This function applies conditionals, based on defined criteria from one or more fields. These criteria are then used to define the values in a new custom field, based on the sequence of the conditions.

## Inputs / Operators / Outputs

| Input Data Type | Input | Included Operators | Output |
|---|---|---|---|
| <ul><li>String</li><li>Numeric</li><li>Date/Date-Time</li></ul> | <ul><li>Input Fields</li><li>Criteria</li></ul> | <p><u>Strings</u></p><ul><li>Equals</li><li>Equals any term</li><li>Contains the phrase</li><li>Contains any term</li><li>Contains all terms</li><li>Starts with</li><li>Starts with any term</li><li>Ends with</li><li>Ends with any term</li><li>Does not equal</li><li>Does not equal any term</li><li>Does not contain the phrase</li><li>Does not contain any term</li><li>Does not contain all terms</li><li>Does not start with</li><li>Does not start with any term</li><li>Does not end with</li><li>Does not end with any term</li><li>Is set</li><li>Is not set</li></ul><p><u>Numeric</u></p><ul><li>Equals</li><li>Does not equal</li><li>Is greater than</li><li>Is greater than or equal to</li><li>Is less than</li><li>Is less than or equal to</li><li>Is set</li><li>Is not set</li></ul><p><u>Dates</u></p><ul><li>Equals</li><li>Does not equal</li><li>Is later than</li><li>Is later than or equal to</li><li>Is before</li><li>Is before or equal to</li><li>Is set</li><li>Is not set</li></ul> | New custom field |

{style="table-layout:auto"}

## Use Case 1

You want to define rules to identify various marketing channels, by applying cascading logic to set a marketing channel field to the proper value:

- If the referrer is from a search engine and the page has a query string value where `cid` contains `ps_`, the marketing channel should be identified as a **Paid Search**.
- If the referrer is from a search engine and the page does not have the query string `cid`, the marketing channel should be identified as a **Natural Search**.
- If a page has a query string value where `cid` contains `em_`, the marketing channel should be identified as an **Email**.
- If a page has a query string value where `cid` contains `ds_`, the marketing channel should be identified as a **Display Ad**.
- If a page has a query string value where `cid` contains `so_`, the marketing channel should be identified as a **Paid Social**.
- If the referrer is from a referring domain of twitter.com, facebook.com, linkedin.com, or tiktok.com, the marketing channel should be identified as a **Natural Social**.
- If none of the above rules are matched, then the marketing channel should be identified as **Other Referrer**.

In case your site receives the following sample events, containing Referrer and Page URL, these events should be identified as follows:

Event | Referrer | Page URL | Marketing Channel |
|:----:|----|----|----|
| 1 | `https://facebook.com` | <`https://site.com/home`> | Natural Social |
| 2 | <`https://abc.com`> | <`https://site.com/?cid=ds_12345678`> | Display |
| 3 | |  <`https://site.com/?cid=em_12345678`> | Email |
| 4 | <`https://google.com`> | <`https://site.com/?cid=ps_abc098765`> | Paid Search |
| 5 | <`https://google.com`> | <`https://site.com/?cid=em_765544332`> | Email |
| 6 | <`https://google.com`> |  | Natural Search |

{style="table-layout:auto"}

### Data Before

| Referrer | Page URL |
|----|----|
| <`https://facebook.com`> | <`https://site.com/home`> 
| <`https://abc.com`> | <`https://site.com/?cid=ds_12345678`> 
|  | <`https://site.com/?cid=em_12345678`>
| <`https://google.com`> | <`https://site.com/?cid=ps_abc098765`> 
| <`https://google.com`> | <`https://site.com/?cid=em_765544332`>
| <`https://google.com`> | 

{style="table-layout:auto"}

### Custom Field

You define a [!UICONTROL Marketing Channel] custom field. You use the **[!UICONTROL CASE WHEN]** rule in Rule Builder. These rules create values for the [!UICONTROL Marketing Channel] custom field based on existing values for both the `Page URL` and `Referring URL` field.

Note the usage of function **[!UICONTROL **URL PARSE**]** to fetch the values for `Page Url` and `Referring Url` before the **[!UICONTROL **CASE WHEN**]** rules are applied.

![Concatenate](assets/case-when-1.png)

### Data After

| Marketing Channel<br/>(custom field) |
|----|
| Natural Social |
| Display |
| Email |
| Paid Search |
| Email |
| Natural Search |

{style="table-layout:auto"}

## Use Case 2

You have collected several different variations of search within your `Product Finding Methods` variable. To understand the overall performance of search vs. browse, you must spend a great deal of time combining the results manually.

Your site collects the following values from your `Product Finding Methods` variable. In the end, all of these values indicate a search.

| Collected value | Actual value |
|---|---|
search p13n_no | search |
search p13n_yes | search |
search refine p13n_no | search |
search refine p13n_yes | search |
search redirect p13n_yes | search |
search-redirect | search |

{style="table-layout:auto"}


### Data Before

| Product Finding Methods |
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

### Custom Field

You define a new Product Finding Method custom field. You create the following **[!UICONTROL **CASE WHEN**]** rules in Rule Builder. These rules apply logic to all possible variations of the old **[!UICONTROL **Product Finding Methods**]** field values for search using the **[!UICONTROL Contains the phrase]** criterion. All variations end up as value `search` for the new Product Finding Method custom field.

![Case When 2](assets/case-when-2.png)

### Data After

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


## Use Case 3

As a travel company, you would like to bucket trip duration for booked trips so you can report on bucketed lengths of trips. 

Assumptions:

- The organization is collecting trip duration into a numeric field.
- They would like to bucket 1-3 day durations into a bucket called 'short trip'
- They would like to bucket 4-7 day durations into a bucket called 'medium trip'
- They would like to bucket 8+ day durations into a bucket called 'long trip'
- 132 trips were booked for a 1-day duration
- 110 trips were booked for a 2-day duration
- 105 trips were booked for a 3-day duration
- 99 trips were booked for a 4-day duration
- 92 trips were booked for a 5-day duration
- 85 trips were booked for a 6-day duration
- 82 trips were booked for a 7-day duration
- 78 trips were booked for an 8-day duration
- 50 trips were booked for a 9-day duration
- 44 trips were booked for a 10-day duration
- 38 trips were booked for an 11-day duration
- 31 trips were booked for a 12-day duration

Your desired report should look like:

| Trip Duration Type | Bookings |
|----|---:|
| medium trip | 358 |
| short trip | 347 |
| long trip | 241 |

{style="table-layout:auto"}

### Data Before

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

### Custom field

You define a new UICONTROL Trip Duration custom field. You create the following **[!UICONTROL **CASE WHEN**]** rule in Rule Builder. These rules apply logic to bucket the old **[!UICONTROL **Trip Duration**]** field values into three values for the new Trip Duration custom field: `short trip`, `medium  trip`, and `long trip`.

![Case When 3](assets/case-when-3.png)


### Data After

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

+++


<!-- Concatenate -->

+++###Concatenate

Combines two or more fields, custom fields, or user-entered values into a single field with defined delimiters.

## Inputs / Operators / Outputs

| Input Data Type | Input | Included Operators | Output |
|---|---|---|---|
| String | <ul><li>Two or more values to combine<ul><li>Fields</li><li>Derived value from a previous rule</li><li>User-entered value</li></ul></li><li>Delimiters<ul><li>Input or selection of a delimiter for each value</li></ul></li> </ul> | N/A | New string-based custom field |

{style="table-layout:auto"}

## Use Case

You currently collect origin and destination airport codes as separate fields. You would like to take the two fields and combine them into a single dimension separated by a hyphen. So you can analyze the combination of origin and destination to identify top routes booked.

Assumptions:

- Origin and destination values are collected in separate fields in the same table.
- The user determines to use the delimiter '-' between the values.

Imagine the following bookings occur:

- Customer ABC123 books a flight between Salt Lake City (SLC) and Orlando (MCO)
- Customer ABC456 books a flight between Salt Lake City (SLC) and Los Angeles (LAX)
- Customer ABC789 books a flight between Salt Lake City (SLC) and Seattle (SEA)
- Customer ABC987 books a flight between Salt Lake City (SLC) and San Jose (SJO)
- Customer ABC654 books a flight between Salt Lake City (SLC) and Orlando (MCO)

The desired report should look like:

| Origin / Destination | Bookings |
|---|---|
| SLC-MCO | 2 |
| SLC-LAX | 1 |
| SLC-SEA | 1 |
| SLC-SJO | 1 |

{style="table-layout:auto"}


### Data Before

| Origin | Destination |
|----|----|
| SLC | MCO |
| SLC | LAX |
| SLC | SEA |
| SLC | SJO |
| SLC | MCO |

{style="table-layout:auto"}

### Custom field

You define a new Origin - Destination custom field. You use the [!UICONTROL CONCATENATE] function to concatenate the [!UICONTROL Original] and [!UICONTROL Destination] fields using the `-` [!UICONTROL Delimiter].

![Concatenate](assets/concatenate.png)

### After

| Origin - Destination<br/>(custom field) |
|---|
| SLC-MCO |
| SLC-LAX |
| SLC-SEA |
| SLC-SJO |
| SLC-MCO |

{style="table-layout:auto"}

+++


<!-- FIND AND REPLACE -->

+++###Find and Replace

Find all values in a selected field and replace those values with a different value in a new derived field.

## Inputs / Operators / Outputs

| Input Data Type | Input | Included Operators | Output |
|---|---|---|---|
| <p>String</p> | <ul><li><span>'When to replace' field criteria</span></li><li><span>'Replace with' field value</span><ul><li><span>User-entered</span></li><li><span>Separate field</span></li></ul></li></ul> | <p><u>Strings</u></p><ul><li>Find All and Replace All</li></ul> | New string-based custom field |

{style="table-layout:auto"}

## Use Case

You have received some malformed values for your external marketing channels report, for example `email%20 marketing` instead of `email marketing`. These malformed values fracture your reporting and make it more difficult to see how email is performing. You want to replace 'email%20' with 'email'.

**Original Report**

| External Marketing Channels | Sessions |
|---|---|
| email marketing | 500 |
| email%20marketing| 24 |

{style="table-layout:auto"}

**Preferred Report**

| External Marketing Channels | Sessions |
|---|---|
| email marketing | 524 |


### Data Before

| External Marketing |
|----|
| email marketing | 
| email%20marketing |
| email marketing | 
| email marketing | 
| email%20marketing |

{style="table-layout:auto"}

### Custom Field

You define a new Email Marketing custom field. You use the **[!UICONTROL FIND AND REPLACE ]**function to find and replace all occurrences of `email%20marketing` with `email marketing`.

![Concatenate](assets/find-and-replace.png)

### Data After

| External Marketing<br/>(custom field) |
|----|
| email marketing |
| email marketing |
| email marketing |
| email marketing |
| email marketing |

{style="table-layout:auto"}

+++


<!-- LOOKUP -->

+++###Lookup

Defines a set of lookup values that are replaced by corresponding values by text entry.

## Inputs / Operators / Outputs

| Input Data Type | Input | Included Operators | Output |
|---|---|---|---|
| <ul><li>String</li><li>Numeric</li><li>Date</li></ul> | <ul><li>Sing field</li><li>Lookup file<ul><li>Key Column</li><li>New Field Column</li></ul></li></ul> | <p>N/A</p> | <p>New custom field</p> |

{style="table-layout:auto"}

## Use Case 1

You do have a CSV-file that includes a key column for a `hotelID` and one or more additional columns associated with the `hotelID` (`city`, `rooms`, `hotel` `name`).
You are collecting Hotel ID in a dimension but would like to create a Hotel Name dimension derived from the hotelID.

**Current Report**

| Hotel ID | Product Views |
|---|---:|
| SLC123 | 200 |
| LX342 | 198 |
| SFO456 | 190 |

{style="table-layout:auto"}

**CSV-file structure and content**

| hotelID | city | rooms | hotel name |
|---|---|---:|---|
| SLC123 | Salt Lake City | 40 | SLC Downtown |
| LAX342 | Los Angels | 60 | LA Airport |
| SFO456 | San Francisco | 75 | Market Street |

{style="table-layout:auto"}

**Desired Report**

| Hotel Name | Product Views |
|----|----:|
| SLC Downtown | 200 |
| LA Airport | 198 |
| Market Street | 190 |

{style="table-layout:auto"}

### Data Before

| Hotel ID |
|----|
| SLC123 | 
| LAX342 | 
| SFO456 |

{style="table-layout:auto"}


### Custom field

You define a new Hotel Name custom field. You use the **[!UICONTROL **LOOKUP**]** function to define a rule where you can look up values of the **[!UICONTROL **Hotel ID**]** field and replace with new values for your Hotel Name custom field.

![Lookup 1](assets/lookup-1.png)

### Data After

Hotel Name<br/>(custom Field) |
|----|
| SLC Downtown |
| LA Airport |
 Market Street |

{style="table-layout:auto"}


## Use Case 2

A customer has several page names that have been collected as URLs instead of the friendly page name. They would like to replace about 10+ URL-based page names with friendly names in the reporting. Often, customers collect both a friendly name and a URL-based value due to some code issue and this mixed collection of values breaks the reporting until it can be fixed in the code.

Assumptions: 

- Values are all part of the same field.
- 1:1 relationship between the value matched and an input value.

### Data

| Page Name |
|---|
| Home Page | 
| Flight Search | 
| <`http://www.expedia.ca/Hotel-Search`> |
| <`https://www.expedia.com/Package-Search`> |
| Deals & Offers |
| <`http://www.expedia.ca/user/reviews`> | 
| <`https://www.expedia.com.br/Generate-Quote/preview`> |

{style="table-layout:auto"}

### Custom field

YOu define a new Page Name custom field. You use the **[!UICONTROL **LOOKUP**]** function to define a rule where you can look up values of your existing **[!UICONTROL **Page Name**]** field and replace with new values for your Page Name custom field.

![Lookup 2](assets/lookup-2.png)

### Data After

| Page Name<br/>(custom) |
|---|
| Home Page |
| Flight Search |
| Hotel Search |
| Package Search |
| Deals & Offers |
| Reviews |
| Generate Quote |

+++


<!-- LOWERCASE -->

+++###Lowercase

Converts an entire string to lowercase value.

## Inputs / Operators / Outputs

| Input Data Type | Input | Included Operators | Output |
|---|---|---|---|
| <ul><li>String</li></ul> | <ul><li>Sing field</li></ul> | <p>N/A</p> | <p>New custom field</p> |

{style="table-layout:auto"}

## Use Case 1

You are collecting multiple variations of Product Names in both lower and upper case. These variations are fragmenting your reporting.


### Data Before

| Collected Product Names | Product Views |
|----|----|
| Tennis racket | 35 |
| Tennis Racket | 33 |
| tennis racket | 21 |
| Baseball bat | 15 |
| Baseball Bat | 12 |
| baseball bat | 10 |

{style="table-layout:auto"}

### Custom field

You create a new Collected Product Names custom field. You use the ![lowercase](../assets/Smock_Function_18_N.svg) **[!UICONTROL **Lowercase**]** function to convert all values from original **[!UICONTROL **Collected Product Names**]** field into lowercase values for new Collected Product Names custom field.

>[!WARNING]
>
>Screenshot is pending availability...


### Data After

| Collected Product Names<br/>(custom field) | Product Views
|----|----|
| tennis racket | 89 |
| baseball bat | 37 |

{style="table-layout:auto"}

+++


<!-- MERGE FIELDS -->

+++###Merge Fields

Takes values from two different fields and include their respective values in a single dimension. The rule first checks to see if the first value is set. If not, then it uses the second value and so on.

## Inputs / Operators / Outputs

| Input Data Type | Input | Included Operators | Output |
|---|---|---|---|
| <ul><li>String</li><li>Numeric</li><li>Date</li></ul> | <ul><li>Values from two or more fields</li></ul> | <p>N/A</p> | <p>New custom field</p> |

{style="table-layout:auto"}

## Use Case

You want to create a dimension made up of the Page Name field and the Call Reason field with the intent of analyzing the journey across channels (in this case web and call center).

Your current reports:

**Dimension 1 - Page Name**

| Page Name | Sessions | Visitors |
|---|---|---|
| help page | 250 | 200 |
| home page | 500 | 250 |
| product detail page | 300 | 200 |

{style="table-layout:auto"}

**Dimension 2 - Call Reason**

| Call Reason | Sessions | Visitors |
|---|---|---|
| questions about my order | 275 | 250 |
| make a change to my order | 120 | 145 |
| problem with ordering | 100 | 95 |

{style="table-layout:auto"}

Your desired report:

| Cross Channel Interactions | Sessions | Visitors |
|---|---|-----|
| home page | 500 | 250 |
| product detail page | 300 | 200 |
| questions about my order | 275 | 250 |
| help page | 250 | 200 |
| make a change to my order | 120 | 145 |
| problem with ordering | 100 | 95 |

{style="table-layout:auto"}

### Data Before

| Page Name | Call Reason |
|----|----|
| help page | questions about my order |
| home page | make a change to my order |
| product detail page | problem with ordering |

{style="table-layout:auto"}

### Custom field

You define a new Cross Channel Interaction custom field. You use the **[!UICONTROL **MERGE FIELDS**]** rule to merge values from **[!UICONTROL **Page Name**]** field and **[!UICONTROL **Call Reason**]** field into the Cross Channel Interaction custom field.

>[!WARNING]
>
>Screenshot pending availability in the UI...


### Data After

|Cross Channel Interaction<br/>(custom field) |
|---|
| help page |
| home page |
| product detail page |
| questions about my order |
| make a change to my order |
| problem with ordering |

{style="table-layout:auto"}

+++


<!-- REGEX REPLACE -->

+++###Regex Replace

Replaces a field or portion of a field based on a regular expression.

## Inputs / Operators / Outputs

| Input Data Type | Input | Included Operators | Output |
|---|---|---|---|
| <ul><li>String</li></ul> | <ul><li>Sing field</li><li>Regex definition</li><li>Output definition</li></ul> | <p>N/A</p> | <p>New custom field</p> |

{style="table-layout:auto"}

## Use Case

You want to grab a potion of a URL and use that as a unique page identifier to analyze traffic. You want to use the regular expression `[^/]+(?=/$|$)` with the output pattern `$1` to match the end of a URL.


### Data Before

| URL | 
|----|
| <`https://business.adobe.com/products/analytics/adobe-analytics-benefits.html`> | 
| <`https://business.adobe.com/products/analytics/adobe-analytics.html`> | 
| <`https://business.adobe.com/products/experience-platform/customer-journey-analytics.html`> | 
| <`https://business.adobe.com/products/experience-platform/adobe-experience-platform.html`> | 

### Custom field.

You create a Page Identified custom field. You use the **[!UICONTROL **REGEX REPLACE**]** function in a rule to replace values from the **[!UICONTROL **URL**]** field with new values for the Page Identifier custom field using the proper **[!UICONTROL **Regex expression**]** and **[!UICONTROL **Output format**]** setting.

>[!WARNING]
>
>Screenshot pending availability in the UI...


### Data After

| Page Identifier<br/>(custom field) |
|----|
| adobe-analytics-benefits.html |
| adobe-analytics.html |
| customer-journey-analytics.html |
| adobe-experience-platform.html |

+++


<!-- SPLIT -->

+++###Split

Splits up a value based on a delimiter.

## Inputs / Operators / Outputs

| Input Data Type | Input | Included Operators | Output |
|---|---|---|---|
| <ul><li>String</li></ul> | <ul><li>Sing field</li><li>Delimiter</li><li>Start from the left or the right (and associated index) or convert to an array with all values</li></ul> | <p>N/A</p> | <p>New custom field</p> |

{style="table-layout:auto"}

## Use Case 1

You collect survey responses into a delimited string in a single dimension. You want each value in the string to be a unique dimension in a responses report.

Each response from the survey is collected in a delimited list.

| Responses |
|---|
| it was great,made perfect sense,will recommend to others |
| it was great,somewhat confusing,will recommend to others |
| it was not great,very confusing,will not recommend to others |

{style="table-layout:auto"}


### Data Before

| Responses | Events |
|----|----|
| it was great,made perfect sense,will recommend to others | 1 |
| it was great,somewhat confusing,will recommend to others | 1 |
| it was not great,very confusing,will not recommend to others | 1 |

{style="table-layout:auto"}


### Custom field

You define a new Responses (split) custom field. You use the **[!UICONTROL **SPLIT**]** function to split the **[!UICONTROL **Responses**]** field values into an array of values for the new Responses (split) custom field using the `,` as the delimiter.

>[!WARNING]
>
>Screenshot pending availability in the UI...



### Data After

| Responses (split)<br/>(custom field) | Events |
|---|---|
| it was great | 2 |
| will recommend to others | 2 |
| it was not great | 1 |
| made perfect sense | 1 |
| somewhat confusing | 1 |
| very confusing | 1 |
| will not recommend to others | 1 |


## Use Case 2

You collect survey responses into a delimited string in a single dimension. You want the first and second value in the string to be reported in their own dimension in a responses report.

Each response from the survey is collected in a delimited list.

| Responses |
|---|
| it was great,made perfect sense,will recommend to others |
| it was great,somewhat confusing,will recommend to others |
| it was not great,very confusing,will not recommend to others |

{style="table-layout:auto"}


### Data Before

| Responses | Events |
|----|----|
| it was great,made perfect sense,will recommend to others | 1 |
| it was great,somewhat confusing,will recommend to others | 1 |
| it was not great,very confusing,will not recommend to others | 1 |

{style="table-layout:auto"}


### Custom field

You define a new Responses (first value) custom field. You use the **[!UICONTROL **SPLIT**]** function to get the first value from the **[!UICONTROL **Responses**]** field values into new Responses (first value) custom field using the `,` as the delimiter and `1` as the index.
You define a new Responses (second value) custom field. You use the **[!UICONTROL **SPLIT**]** function to get the second value from the **[!UICONTROL **Responses**]** field values into new Responses (second value) custom field using the `,` as the delimiter and `2` as the index.

>[!WARNING]
>
>Screenshot pending availability in the UI...



### Data After

| Responses (first value)<br/>(custom field) | Events |
|---|---|
| it was great | 2 |
| it was not great | 1 |

| Responses (second value)<br/>(custom field) | Events |
|---|---|
| will recommend to others | 2 |
| will not recommend to others | 1 |

{style="table-layout:auto"}

+++


<!-- TRIM -->

+++###TRIM

Trim whitespace or special characters from the beginning or the end of a string, specifying the position and number of characters.

## Inputs / Operators / Outputs

| Input Data Type | Input | Included Operators | Output |
|---|---|---|---|
| <ul><li>String</li></ul> | <ul> <li>Single Field</li> <li>Flag to trim whitespace</li> <li>Flag to trim special characters<ul> <li>Input of special characters</li> </ul> </li> <li>Flag to trim from left<ul> <li>From<ul> <li>Start string</li> <li>Position<ul> <li>Position #</li> </ul> </li> <li>String<ul> <li>String value</li> <li>Index</li> <li>Flag to include string</li> </ul> </li> </ul> </li> <li>To<ul> <li>Start string</li> <li>Position<ul> <li>Position #</li> </ul> </li> <li>String<ul> <li>String value</li> <li>Index</li> <li>Flag to include string</li> </ul> </li> <li>Length</li> </ul> </li> </ul> </li> <li>Flag to trim from right<ul> <li>From<ul> <li>Start string</li> <li>Position<ul> <li>Position #</li> </ul> </li> <li>String<ul> <li>String value</li> <li>Index</li> <li>Flag to include string</li> </ul> </li> </ul> </li> <li>To<ul> <li>Start string</li> <li>Position<ul> <li>Position #</li> </ul> </li> <li>String<ul> <li>String value</li> <li>Index</li> <li>Flag to include string</li> </ul> </li> <li>Length</li> </ul> </li> </ul> </li> </ul> | <p>N/A</p> | <p>New custom field</p> |

{style="table-layout:auto"}

## Use Case 1

You collect product data which includes hidden whitespace characters. These hidden whitespace characters fragment the reporting. You want to trim any excess whitespace.

### Data Before

| Product ID | Events |
|----|----|
| "prod12356" | 1 |
| "prod12356" | 1 |
| "prod12356 " | 1 |

{style="table-layout:auto"}

### Custom field

You define a new Product ID custom field. You use the **[!UICONTROL **TRIM**]** function to trim whitespace from the **Product ID** field values into the new Product ID custom field.

>[!WARNING]
>
>Screenshot pending availability in the UI...


### Data After

| Product ID<br/>(custom field) | AFTER:<br/>Events |
|---|---|
| "prod12356" | 3 |


## Use Case 2

You collect data that includes some erroneous special characters at the end of the Page Name field which must be removed.

### Data Before

| Page Name | Events |
|----|----|
| homepage# | 1 |
| homepage? | 1 |
| homepage% | 1 |
| homepage& | 1 |
| homepage/ | 1 |

{style="table-layout:auto"}

### Custom rule

You define a new Page Name custom field. You use the **[!UICONTROL **TRIM**]** function to **[!UICONTROL **Trim**]** special characters from the **[!UICONTROL **Page Name**]** field values into the new Page Name custom field.

>[!WARNING]
>
>Screenshot pending availability in the UI...



### Data After

| Page Name<br/>(custom field) | Events |
|---|---|
| home page | 5 |


## Use Case 3

You store data, where the first two letters of a storeID contain the abbreviation for the state where that store is located. You only want to use these two state characters in your reports.

### Data Before

| Store ID | Events |
|----|----|
| CA293842 | 1 |
| CA423402 | 1 |
| UT123418 | 1 |
| UT189021 | 1 |
| ID028930 | 1 |
| OR234223 | 1 |
| NV22342 | 1 |

{style="table-layout:auto"}

### Custom field

You define a new Store ID field. You use the **[!UICONTROL **TRIM**]** function to truncate the first two characters of the **[!UICONTROL **Store ID**]** values into the new Store ID custom field.

Pending availability in the UI.


| Store ID<br/>(custom field) | Events |
|---|---|
| CA | 2 |
| UT | 2 |
| ID | 1 |
| OR | 1 |
| NV | 1 |

{style="table-layout:auto"}

+++


<!-- URL PARSE -->

+++###URL Parse


Parse out different parts of a URL including the host, path, or query parameters.

## Inputs / Operators / Outputs

| Input Data Type | Input | Included Operators | Output |
|---|---|---|---|
| <ul><li>String</li></ul> | <ul><li>Sing field</li><li>Parsing option<ul><li>Get protocol</li><li>Get host</li><li>Get path</li><li>Get query value<ul><li>Query param</li></ul></li><li>Get hash value</li></ul></li></ul></li></ul> | <p>N/A</p> | <p>New custom field</p> |

{style="table-layout:auto"}

## Use Case 1

You only want use the referring domain from the referring URL as part of a marketing channel's set of rules.

### Data Before

| Referring URL |
|----|
| <`https://www.google.com/`> |
| <`https://duckduckgo.com/`> | 
| <`https://t.co/`> |
| <`https://l.facebook.com/`>| 

{style="table-layout:auto"}

### Custom field

You define a new Referring Domain custom field. You use the **[!UICONTROL **URL PARSE**]** function to fetch the host from the **Referring URL** and store that in the new Referrer Domain custom field.

![Url Parse 1](assets/url-parse-1.png)

### Data After

Referrer Domain<br/>(custom field) |
|----|
| www.google.com |
| duckduckgo.com |
| t.co |
| l.facebook.com |

{style="table-layout:auto"}


## Use Case 2

You want to use the value of the `cid` parameter of a query string in a Page URL as part of the output of a derived tracking code report.

### Data Before

| Page URL |
|----|
| <`https://www.adobe.com/?cid=abc123`> |
| <`https://www.adobe.com/?em=email1234&cid=def123`> | 
| <`https://www.adobe.com/landingpage?querystring1=test&test2=1234&cid=xyz123`> | 

{style="table-layout:auto"}

### Screenshot

You define a new Query String CID custom field. You use the **[!UICONTROL **URL PARSE**]** function in the Rule Builder to fetch the value of the query string parameter in the Page URL, specifying `cid` as the query parameter. The value is stored in the new Query String CID custom field.

![Url Parse 2](assets/url-parse-2.png)

### Data After

| Query String CID<br/>(custom field) |
|----|
| abc123 |
| def123 |
| xyz123 |

{style="table-layout:auto"}

+++
