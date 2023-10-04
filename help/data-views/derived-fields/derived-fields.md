---
title: Derived fields
description: A derived field specifies report-time manipulation of schema fields and/or standard components through a set of available functions and function templates.
solution: Customer Journey Analytics
feature: Derived Fields
exl-id: bcd172b2-cd13-421a-92c6-e8c53fa95936
---
# Derived fields

Derived fields are an important aspect of the real-time reporting functionality in Adobe Customer Journey Analytics. A derived field allows you to define (often complex) data manipulations on the fly, through a customizable rule builder. You can then use that derived field as a component (metric or dimension) in [Workspace](../../analysis-workspace/home.md) or even further define the derived field as a component in [Data view](../data-views.md). 

Derived fields can save a significant amount of time and effort, compared to transforming or manipulating your data in other locations outside of Customer Journey Analytics. Such as [Data Prep](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html), [Data Distiller](https://experienceleague.adobe.com/docs/experience-platform/query/data-distiller/overview.html?lang=en), or within your own Extract Transform Load (ETL) / Extract Load Transform (ELT) processes.

Derived fields are defined within [Data views](../data-views.md), are based on a set of functions defined as rules, and applied to available standard and/or schema fields.

Example use cases are:

- Define a derived Page Name field that corrects improper collected page name values to correct page name values. 

- Define a derived Marketing Channel field that determines the proper marketing channel based on one or more conditions (for example URL parameter, page URL, page name).

## Derived field interface

When you create or edit a derived field, you use the derived field interface.

![Screenshot of the Derived field dialog](assets/derived-field-dialog.png)


|  | Name | Description |
|---------|----------|--------|
| 1 | **Selector** | You use the selector area to select and drag and drop your function, function template, schema field, or standard field on to the rule builder. <br/>Use the drop-down to select between: <br/>![Function](assets/Smock_Function_18_N.svg) [!UICONTROL Functions] - lists available [functions](#function-reference), </br>![Function template icon](assets/Smock_FileTemplate_18_N.svg) [!UICONTROL Function templates] - lists available [function templates](#function-templates), <br/>![Schema field icon](assets/Smock_Folder_18_N.svg)  [!UICONTROL Schema fields] - lists fields available from dataset categories (event, profile, lookup) and previously defined derived fields, and <br/>![Standard field icon](assets/Smock_DragHandle_18_N.svg) [!UICONTROL Standard fields] - standard available fields (like Platform Dataset ID). Only string and numeric standard fields are displayed in the selector. If the function supports other data types, standard fields with these other data types can be selected for values or fields within the rule interface.<br/>You can search for function, function templates, schema, and standard fields using the ![Search  icon](assets/Smock_Search_18_N.svg) Search box. <br/>You can filter the selected object list by selecting ![Filter icon](assets/Smock_Filter_18_N.svg) Filter and specify filters in the [!UICONTROL Filter fields by] dialog. You can easily remove filters using ![Close icon](assets/CrossSize75.svg) for each filter. | 
| 2 | **Rule builder** | You build your derived field sequentially using one or more rules. A rule is a specific implementation of a function and is therefore always associated with only one function. You create a rule by dragging and dropping a function into the rule builder. The function type determines the interface of the rule.<br/>See the [Rule interface](#rule-interface) for more information. <br/>You can insert a function at the start, end, or in between rules already available in the rule builder. The last rule in the rule builder determines the final output of the derived field. |
| 3 | **[!UICONTROL **Field Settings**]** | You can name and describe your derived field and inspect its field type. | 
| 4 | **[!UICONTROL **Final Output**]** | This area shows an on-the-fly updated preview of output values, based on data over the last 30 days and the changes you make to the derived field in the rule builder. |

{style="table-layout:auto"}

## Field template wizard

When you access the derived field interface for the first time, the [!UICONTROL Start with a field template] wizard is shown. 

1. Select the template that best describes the type of field you are trying to create. 
2. Select the **[!UICONTROL **Select**]** button to continue.

Your derived field dialog is populated with rules (and functions) required or useful for the type of field that you selected. See [Function templates](#function-templates) for more information on the available templates.

## Rule interface

When you define a rule in the rule builder, you use the rule interface.

![Screenshot of the Derived Field Rule Interface](assets/rule-interface.png)

|  | Name | Description |
|---------|----------|--------|
| A | **Rule Name** | By default the rule name is **Rule X** (X referring to a sequence number). To edit the name of a rule, select its name and type in the new name, for example `Query Parameter`. |
| B | **Function Name** | The selected function name for the rule, for example [!UICONTROL URL PARSE]. When the function is the last in the sequence of functions and determines the final output values, the function name is followed by [!UICONTROL - FINAL OUTPUT], for example [!UICONTROL URL PARSE - FINAL OUTPUT]. <br/>To show a popup with more information on the function, select ![Help icon](assets/Smock_HelpOutline_18_N.svg). |
| C | **Rule Description** | You can optionally add a description to a rule.<br/>Select ![More icon](assets/More.svg), then select **[!UICONTROL **Add Description**]** to add a description or **[!UICONTROL **Edit Description**]** to edit an existing description.<br/>Use the editor to enter a description. You can use the toolbar to format the text (using style selector, bold, italic, underline, right, left, centered, color, number list, bullet list) and adding links to external information. <br/>To finish editing the description, click outside of the editor. |
| D | **Function Area** | Defines the logic of the function. The interface depends on the type of function. The dropdown for [!UICONTROL Field] or [!UICONTROL Value] shows all categories of fields (rules, standard fields, fields) available, based on the type of input the function expects. <!-- Alternatively, you can drag and drop a field from the Schema and Standard fields selector on to a Field or Value. When that dragged field is originating from a Lookup dataset, a Lookup function is automatically inserted before the function you define.  See [Function reference](#function-reference) on detailed information for each of the functions supported. --> |

{style="table-layout:auto"}

## Create a derived field

1. Select an existing Data view or create a Data view. See [Data views](../data-views.md) for more information.

2. Select the **[!UICONTROL **Components**]** tab of the Data view.

3. Select **[!UICONTROL **Create derived field**]** from the left rail.
   
4. To define your derived field, use the [!UICONTROL Create derived field] interface. See [Derived field interface](#derived-field-interface).

    To save your new derived field, select **[!UICONTROL **Save**]**.

5. Your new derived field is added to the [!UICONTROL Derived fields >] container, as part of **[!UICONTROL **Schema fields**]** in the left rail of your Data view.


## Edit a derived field

1. Select an existing Data view. See [Data views](../data-views.md) for more information.

2. Select the **[!UICONTROL **Components**]** tab of the Data view.

3. Select **[!UICONTROL **Schema fields**]** tab in the [!UICONTROL Connection] pane on the left.

4. Select **[!UICONTROL **Derived fields >**]** container.

5. Hover over the derived field that you want to edit, and select ![Edit icon](assets/Smock_Edit_18_N.svg).

6. To edit your derived field, use the [!UICONTROL Edit derived field] interface. See [Derived field interface](#derived-field-interface).

   - Select **[!UICONTROL **Save**]** to save your updated derived field.

   - Select **[!UICONTROL **Cancel**]** to cancel any changes you made to the derived field.

   - Select **[!UICONTROL **Save As**]** to save the derived field as a new derived field. The new derived field has the same name as the original edited derived field with `(copy)` added to it.

## Delete a derived field

1. Select an existing Data view. See [Data views](../data-views.md) for more information.

2. Select the **[!UICONTROL **Components**]** tab of the Data view.

3. Select **[!UICONTROL **Schema fields**]** tab in [!UICONTROL Connection] pane.

4. Select **[!UICONTROL **Derived fields >**]** container.

5. Hover over the derived field that you want to delete, and select ![Edit icon](assets/Smock_Edit_18_N.svg).

6. In the Use **[!UICONTROL **Edit derived field**]** interface, select Delete.

    A [!UICONTROL Delete component] dialog asks you to confirm the deletion. Consider any external references there might exist to the derived field outside of the Data view. 
    
   - Select **[!UICONTROL **Continue**]** to delete the derived field.

>[!NOTE]
>
>Derived fields are managed at a Connection level in Customer Journey Analytics. Any change made to a derived field in any of the Data views associated with that Connection applies across all these associated Data views.



## Function templates

To quickly create a derived field for specific use cases, function templates are available. These function templates can be accessed from the selector area in the derived field interface or are presented upon first use in the [!UICONTROL Start with a field template] wizard.


### Marketing channels

This template is configured to use the [Url Parse](#dnl-url-parse) and [Case When](#dnl-case-when) functions multiple times to get appropriate values from a URL. Logic is then applied on these values to associate the URL to a specific marketing channel.

+++ Details

To use the template, you have to specify the correct parameters for each function listed as part of the rules in the template. See [Function reference](#function-reference) for more information.

![Screenshot of the Marketing channel template rule builder](assets/marketing-channel-template.png)

+++

<!--

+++ Data clean up template

>[!WARNING]
>
>Could not find any information on this template.
+++

-->

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
  - data before defining the derived field,
  - how to define the derived field,
  - data after defining the derived field.

- constraints (if applicable).

>[!NOTE]
>
>The Lookup function has been renamed to [Classify](#classify). See the [Classify](#classify) function for more information.

<!-- CASE WHEN -->

### Case When

Applies conditionals, based on defined criteria from one or more fields. These criteria are then used to define the values in a new derived field, based on the sequence of the conditions.

+++ Details

## Specifications {#casewhen-io}

| Input Data Type | Input | Included Operators | Limitations | Output |
|---|---|---|---|---|
| <ul><li>String</li><li>Numeric</li><li>Date</li></ul> | <ul><li>[!UICONTROL If], [!UICONTROL Else If] container:</p><ul><li>[!UICONTROL Value]</li><ul><li>Rules</li><li>Standard fields</li><li>Fields</li></ul><li>[!UICONTROL Criterion] (see included operators, based on selected value type)</li></ul></li><li>[!UICONTROL Then set value to], [!UICONTROL Otherwise set value to]:</p><ul><li>[!UICONTROL Value]</li><ul><li>Rules</li><li>Standard fields</li><li>Fields</li></ul></ul></li></ul> | <p>Strings</p><ul><li>Equals</li><li>Equals any term</li><li>Contains the phrase</li><li>Contains any term</li><li>Contains all terms</li><li>Starts with</li><li>Starts with any term</li><li>Ends with</li><li>Ends with any term</li><li>Does not equal</li><li>Does not equal any term</li><li>Does not contain the phrase</li><li>Does not contain any term</li><li>Does not contain all terms</li><li>Does not start with</li><li>Does not start with any term</li><li>Does not end with</li><li>Does not end with any term</li><li>Is set</li><li>Is not set</li></ul><p>Numeric</p><ul><li>Equals</li><li>Does not equal</li><li>Is greater than</li><li>Is greater than or equal to</li><li>Is less than</li><li>Is less than or equal to</li><li>Is set</li><li>Is not set</li></ul><p>Dates</p><ul><li>Equals</li><li>Does not equal</li><li>Is later than</li><li>Is later than or equal to</li><li>Is before</li><li>Is before or equal to</li><li>Is set</li><li>Is not set</li></ul> | <ul><li>5 functions per derived field</li><li>200 operators per derived field. An example of one single operator is 'Referring Domain contains google'. </li></ul> |<p>New derived field</p> |

{style="table-layout:auto"}

## Use case 1 {#casewhen-uc1}

You want to define rules to identify various marketing channels, by applying cascading logic to set a marketing channel field to the proper value:

- If the referrer is from a search engine and the page has a query string value where `cid` contains `ps_`, the marketing channel should be identified as a [!DNL *Paid Search*].
- If the referrer is from a search engine and the page does not have the query string `cid`, the marketing channel should be identified as a [!DNL *Natural Search*].
- If a page has a query string value where `cid` contains `em_`, the marketing channel should be identified as an [!DNL *Email*].
- If a page has a query string value where `cid` contains `ds_`, the marketing channel should be identified as a [!DNL *Display Ad*].
- If a page has a query string value where `cid` contains `so_`, the marketing channel should be identified as a [!DNL *Paid Social*].
- If the referrer is from a referring domain of [!DNL twitter.com], [!DNL facebook.com], [!DNL linkedin.com], or [!DNL tiktok.com], the marketing channel should be identified as a [!DNL *Natural Social*].
- If none of the above rules are matched, then the marketing channel should be identified as [!DNL *Other Referrer*].

In case your site receives the following sample events, containing [!UICONTROL Referrer] and [!UICONTROL Page URL], these events should be identified as follows:

| [!DNL Event] | [!DNL Referrer] | [!DNL Page URL] | [!DNL Marketing Channel] |
|:--:|----|----|----|
| 1 | `https://facebook.com` | `https://site.com/home` | [!DNL Natural Social] |
| 2 | `https://abc.com` | `https://site.com/?cid=ds_12345678` | [!DNL Display] |
| 3 | |  `https://site.com/?cid=em_12345678` | [!DNL Email] |
| 4 | `https://google.com` | `https://site.com/?cid=ps_abc098765` | [!DNL Paid Search] |
| 5 | `https://google.com` | `https://site.com/?cid=em_765544332` | [!DNL Email] |
| 6 | `https://google.com` |  | [!DNL Natural Search] |

{style="table-layout:auto"}

### Data before {#casewhen-uc1-databefore}

| [!DNL Referrer]| [!DNL Page URL] |
|----|----|
| `https://facebook.com` | `https://site.com/home` |
| `https://abc.com` | `https://site.com/?cid=ds_12345678` |
|  | `https://site.com/?cid=em_12345678` |
| `https://google.com` | `https://site.com/?cid=ps_abc098765` |
| `https://google.com` | `https://site.com/?cid=em_765544332` |
| `https://google.com` | 

{style="table-layout:auto"}

### Derived field {#casewhen-uc1-derivedfield}

You define a new `Marketing Channel` derived field. You use the [!UICONTROL CASE WHEN] functions to define rules that create values for the based on existing values for both the `Page URL` and `Referring URL` field.

Note the usage of the function [!UICONTROL URL PARSE] to define rules to fetch the values for `Page Url` and `Referring Url` before the [!UICONTROL CASE WHEN] rules are applied.

![Screenshot of the Case when rule 1](assets/case-when-1.png)

### Data after {#casewhen-uc1-dataafter}

| [!DNL Marketing Channel] |
|----|
| [!DNL Natural Social] |
| [!DNL Display] |
| [!DNL Email] |
| [!DNL Paid Search] |
| [!DNL Email] |
| [!DNL Natural Search] |

{style="table-layout:auto"}


## Use case 2 {#casewhen-uc2}

You have collected several different variations of search within your [!DNL Product Finding Methods] dimension. To understand the overall performance of search vs. browse, you must spend a great deal of time combining the results manually.

Your site collects the following values for your [!DNL Product Finding Methods] dimension. In the end, all of these values indicate a search.

| Collected value | Actual value |
|---|---|
| [!DNL search p13n_no] | [!DNL search] |
| [!DNL search p13n_yes] | [!DNL search] |
| [!DNL search refine p13n_no] | [!DNL search] |
| [!DNL search refine p13n_yes ]| [!DNL search] |
| [!DNL search redirect p13n_yes] | [!DNL search] |
| [!DNL search-redirect] | [!DNL search] |

{style="table-layout:auto"}


### Data before {#casewhen-uc2-databefore}

| [!DNL Product Finding Methods] |
|----|
| [!DNL search p13_no] | 
| [!DNL search p13_yes] | 
| [!DNL browse] | 
| [!DNL search refine p13_no] | 
| [!DNL search refine p13_yes] | 
| [!DNL browse] | 
| [!DNL search redirect p13_yes] | 
| [!DNL search-redirect] | 
| [!DNL browse] |

{style="table-layout:auto"}

### Derived field {#casewhen-uc2-derivedfield}

You define a `Product Finding Methods (new)` derived field. You create the following [!UICONTROL CASE WHEN] rules in rule builder. These rules apply logic to all possible variations of the old [!UICONTROL Product Finding Methods] field values for `search` and `browse` using the [!UICONTROL Contains the phrase] criterion.

![Screenshot of the Case When rule 2](assets/case-when-2.png)

### Data after {#casewhen-uc2-dataafter}

| [!DNL Product Finding Methods (new)] |
|----|
| [!DNL search] |
| [!DNL search] |
| [!DNL browse] |
| [!DNL search] |
| [!DNL search] |
| [!DNL browse] |
| [!DNL search] |
| [!DNL search] |
| [!DNL browse] |

{style="table-layout:auto"}


## Use case 3 {#casewhen-uc3}

As a travel company, you would like to bucket trip duration for booked trips so you can report on bucketed lengths of trips. 

Assumptions:

- The organization is collecting trip duration into a numeric field.
- They would like to bucket 1-3 day durations into a bucket called '[!DNL short trip]'
- They would like to bucket 4-7 day durations into a bucket called '[!DNL medium trip]'
- They would like to bucket 8+ day durations into a bucket called '[!DNL long trip]'
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

| [!DNL Trip Duration Type] | [!DNL Bookings] |
|----|---:|
| [!DNL medium trip] | 358 |
| [!DNL short trip] | 347 |
| [!DNL long trip] | 241 |

{style="table-layout:auto"}

### Data before {#casewhen-uc3-databefore}

| [!DNL Trip Duration] |
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

### Derived field {#casewhen-uc3-derivedfield}

You define a `Trip Duration (bucketed)` derived field. You create the following [!UICONTROL CASE WHEN] rule in rule builder. This rule applies logic to bucket the old [!UICONTROL Trip Duration] field values into three values: `short trip`, `medium  trip`, and `long trip`.

![Screenshot of the Case When rule 3](assets/case-when-3.png)


### Data after {#casewhen-uc3-dataafter}

| [!DNL Trip Duration (bucketed)] |
|---|
| [!DNL short trip] |
| [!DNL long trip] |
| [!DNL short trip] |
| [!DNL medium trip] |
| [!DNL medium trip] |
| [!DNL long trip] |
| [!DNL medium trip] |
| [!DNL short trip] |
| [!DNL short trip] |
| [!DNL short trip] |
| [!DNL long trip] |
| [!DNL long trip] |


## More information

Customer Journey Analytics uses a nested container structure, modeled after Adobe Experience Platform's [XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=en) (Experience Data Model). See [Containers](../create-dataview.md#containers) and [Filter containers](../../components/filters/filters-overview.md#filter-containers) for more background information. This container model, albeit flexible by nature, imposes some constraints when using the rule builder. 

Customer Journey Analytics uses the following default container model:

<p align="center">
<img src="./assets/containers.png" width="50%" valign="middle">
</p>

The following constraints apply and are enforced when *selecting* and *setting* values.

|  |  Constraints |
|:---:|----|
| **<span style='color: red'>A</span>** | Values you *select* within the same [!UICONTROL If], [!UICONTROL Else If] construct (using [!UICONTROL And] or [!UICONTROL Or]) in a rule must originate from the same container and can be of any type (string ![String](assets/Smock_ABC_18_N.svg), numeric ![Numeric](assets/Smock_123_18_N.svg), and so forth). <br/>![Screenshot of dependency A](assets/dependency-a.png)|
| **<span style='color: red'>B</span>** | All the values you *set* across a rule must be from the same container and have the same type or a derived value of the same type. <br/> ![Screenshot of Dependency B](assets/dependency-b.png) |
| **<span style='color: blue'>C</span>** | The values you *select* across [!UICONTROL If], [!UICONTROL Else If] constructs in the rule do *not* have to originate from the same container and do *not* have to be of the same type. <br/> ![Screenshot of Dependency C](assets/dependency-c.png)  |

{style="table-layout:auto"}

+++

<!-- CLASSIFY -->

### Classify

Defines a set of values that are replaced by corresponding values in a new derived field.

+++ Details

>[!NOTE]
>
>This function was originally named Lookup but has been renamed to Classify to accommodate a forthcoming Lookup function with different functionality.

## Specifications {#classify-io}

| Input Data Type | Input | Included Operators | Limitations | Output |
|---|---|---|---|---|
| <ul><li>String</li><li>Numeric</li><li>Date</li></ul> | <ul><li>[!UICONTROL Field to classify]:<ul><li>Rules</li><li>Standard fields</li><li>Fields</li></ul></li><li>[!UICONTROL When value equals] and [!UICONTROL Replace values with]:</p><ul><li>String</li></ul><li>Show original values<ul><li>Boolean</li></ul></li></ul> | <p>N/A</p> | <p>5 functions per derived field<br/>100 rows per function</p> | <p>New derived field</p> |

{style="table-layout:auto"}


## Use case 1 {#classify-uc1}

You do have a CSV-file that includes a key column for `hotelID` and one or more additional columns associated with the `hotelID`: `city`, `rooms`, `hotel name`.
You are collecting [!DNL Hotel ID] in a dimension but would like to create a [!DNL Hotel Name] dimension derived from the `hotelID` in the CSV file.

**CSV-file structure and content**

| [!DNL hotelID] | [!DNL city] | [!DNL rooms] | [!DNL hotel name] |
|---|---|---:|---|
| [!DNL SLC123] | [!DNL Salt Lake City] | 40 | [!DNL SLC Downtown] |
| [!DNL LAX342] | [!DNL Los Angeles] | 60 | [!DNL LA Airport] |
| [!DNL SFO456] | [!DNL San Francisco] | 75 | [!DNL Market Street] |
| [!DNL AMS789] | [!DNL Amsterdam] | 50 | [!DNL Okura] |

{style="table-layout:auto"}

**Current Report**

| [!DNL Hotel ID] | Product Views |
|---|---:|
| [!DNL SLC123] | 200 |
| [!DNL LX342] | 198 |
| [!DNL SFO456] | 190 |
| [!DNL AMS789] | 150 |

{style="table-layout:auto"}


**Desired Report**

| [!DNL Hotel Name] | Product Views |
|----|----:|
| [!DNL SLC Downtown] | 200 |
| [!DNL LA Airport] | 198 |
| [!DNL Market Street] | 190 |

{style="table-layout:auto"}

### Data before {#classify-uc1-databefore}

| [!DNL Hotel ID] |
|----|
| [!DNL SLC123] | 
| [!DNL LAX342] | 
| [!DNL SFO456] |
| [!DNL AMS789] | 

{style="table-layout:auto"}


### Derived field {#classify-uc1-derivedfield}

You define a `Hotel Name` derived field. You use the [!UICONTROL CLASSIFY] function to define a rule where you can classify values of the [!UICONTROL Hotel ID] field and replace with new values. 

If you want to include original values that you have not defined as part of the values to classify (for example Hotel ID AMS789), ensure you select **[!UICONTROL Show original values]**. This ensures AMS789 will be part of the output for the derived field, despite that value not being classified.

![Screenshot of the Classify rule 1](assets/classify-1.png)

### Data after {#classify-uc1-dataafter}

| [!DNL Hotel Name] |
|----|
| [!DNL SLC Downtown] |
| [!DNL LA Airport] |
| [!DNL Market Street] |

{style="table-layout:auto"}


## Use case 2 {#classify-uc2}

You have collected URLs instead of the friendly page name for several pages. This mixed collection of values breaks the reporting.

### Data before {#classify-uc2-databefore}

| [!DNL Page Name] |
|---|
| [!DNL Home Page] | 
| [!DNL Flight Search] | 
| `http://www.adobetravel.ca/Hotel-Search` |
| `https://www.adobetravel.com/Package-Search` |
| [!DNL Deals & Offers] |
| `http://www.adobetravel.ca/user/reviews` | 
| `https://www.adobetravel.com.br/Generate-Quote/preview` |

{style="table-layout:auto"}

### Derived field {#classify-uc2-derivedfield}

You define a `Page Name (updated)` derived field. You use the [!UICONTROL CLASSIFY] function to define a rule where you can classify values of your existing [!UICONTROL Page Name] field and replace with updated correct values.

![Screenshot of the Classify rule 2](assets/classify-2.png)

### Data after {#classify-uc2-dataafter}

| [!DNL Page Name (updated)] |
|---|
| [!DNL Home Page] |
| [!DNL Flight Search] |
| [!DNL Hotel Search] |
| [!DNL Package Search] |
| [!DNL Deals & Offers] |
| [!DNL Reviews] |
| [!DNL Generate Quote] |


## More information {#classify-moreinfo}

The following additional functionality is available in the Classify rule interface:

- To quickly clear all table values, select ![Erase](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Erase_18_N.svg) **[!UICONTROL Clear all table values]**.
- To upload a CSV file containing original values for When values equal and new values for Replace values with, select ![CSV](https://spectrum.adobe.com/static/icons/workflow_18/Smock_FileCSV_18_N.svg) **[!UICONTROL Upload CSV]**.
- To download a template for creating a CSV file with original and new values to upload, select ![Download](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Download_18_N.svg) **[!UICONTROL Download CSV template]**.
- To download a CSV file with all original and new values populated in the rule interface, select ![Download](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Download_18_N.svg) **[!UICONTROL Download CSV values]**.
 

+++

<!-- CONCATENATE -->

### Concatenate

Combines field values into a single new derived field with defined delimiters.

+++ Details

## Specifications {#concatenate-io}

| Input Data Type | Input | Included Operators | Limitations | Output |
|---|---|---|---|---|
| <ul><li>String</li></ul> | <ul><li>[!UICONTROL Value]:<ul><li>Rules</li><li>Standard fields</li><li>Fields</li><li>String</li></ul></li><li>[!UICONTROL Delimiter]:<ul><li>String</li></ul></li> </ul> | <p>N/A</p>| <p>2 functions per derived field</p> | <p>New derived field</p> |

{style="table-layout:auto"}


## Use case {#concatenate-uc}

You currently collect origin and destination airport codes as separate fields. You would like to take the two fields and combine them into a single dimension separated by a hyphen (-). So you can analyze the combination of origin and destination to identify top routes booked.

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
|----|---:|
| SLC-MCO | 2 |
| SLC-LAX | 1 |
| SLC-SEA | 1 |
| SLC-SJO | 1 |

{style="table-layout:auto"}


### Data before {#concatenate-uc-databefore}

| Origin | Destination |
|----|---:|
| SLC | MCO |
| SLC | LAX |
| SLC | SEA |
| SLC | SJO |
| SLC | MCO |

{style="table-layout:auto"}

### Derived field {#concatenate-derivedfield}

You define a new [!UICONTROL Origin - Destination] derived field. You use the [!UICONTROL CONCATENATE] function to define a rule to concatenate the [!UICONTROL Original] and [!UICONTROL Destination] fields using the `-` [!UICONTROL Delimiter].

![Screenshot of the Concatenate rule](assets/concatenate.png)

### Data after {#concatenate-dataafter}

| Origin - Destination<br/>(derived field) |
|---|
| SLC-MCO |
| SLC-LAX |
| SLC-SEA |
| SLC-SJO |
| SLC-MCO |

{style="table-layout:auto"}

+++

<!-- FIND AND REPLACE -->

### Find and Replace

Finds all values in a selected field and replaces those values with a different value in a new derived field.

+++ Details

## Specifications {#findreplace-io}

| Input Data Type | Input | Included Operators | Limitations | Output |
|---|---|---|---|---|
| <ul><li>String</li></ul> | <ul><li>[!UICONTROL Value]<ul><li>Rules</li><li>Standard fields</li><li>Fields</li></ul></li><li>[!UICONTROL Find all], [!UICONTROL and replace all with]:<ul><li>String</li></ul></li></ul></ul> | <p>Strings</p><ul><li>[!UICONTROL Find all], [!UICONTROL and replace all with]</li></ul> | <p>5 functions per derived field</p> | <p>New derived field</p> |

{style="table-layout:auto"}


## Use case {#findreplace-uc}

You have received some malformed values for your external marketing channels report, for example `email%20 marketing` instead of `email marketing`. These malformed values fracture your reporting and make it more difficult to see how email is performing. You want to replace `email%20marketing` with `email marketing`.

**Original Report**

| [!DNL External Marketing Channels] | [!DNL Sessions] |
|---|--:|
| [!DNL email marketing] | 500 |
| [!DNL email %20marketing] | 24 |

{style="table-layout:auto"}

**Preferred Report**

| [!DNL External Marketing Channels] | [!DNL Sessions] |
|---|--:|
| [!DNL email marketing] | 524 |


### Data before {#findreplace-uc-databefore}

| [!DNL External Marketing] |
|----|
| [!DNL email marketing] | 
| [!DNL email%20marketing] |
| [!DNL email marketing] | 
| [!DNL email marketing] | 
| [!DNL email%20marketing] |

{style="table-layout:auto"}

### Derived field {#findreplace-uc-derivedfield}

You define an `Email Marketing (updated)` derived field. You use the [!UICONTROL FIND AND REPLACE] function to define a rule to find and replace all occurrences of `email%20marketing` with `email marketing`.

![Screenshot of the Find and Replace rule](assets/find-and-replace.png)

### Data after {#findreplace-uc-dataafter}

| [!DNL External Marketing (updated)] |
|----|
| [!DNL email marketing] |
| [!DNL email marketing] |
| [!DNL email marketing] |
| [!DNL email marketing] |
| [!DNL email marketing] |

{style="table-layout:auto"}

+++


<!-- LOOKUP

### Lookup

Lookup values using a field from a lookup dataset and returns value in a new derived field or for further rule processing.

+++ Details

## Specification {#lookup-io}

| Input Data Type | Input | Included Operators | Limit | Output |
|---|---|---|---|---|
| <ul><li>String</li><li>Numeric</li><li>Date</li></ul> | <ul><li>[!UICONTROL Field to apply lookup]:</li><ul><li>Rules</li><li>Standard fields</li><li>Fields</li></ul><li>[!UICONTROL Lookup dataset]</li><ul><li>Dataset</li></ul><li>[!UICONTROL Matching key]<ul><li>Rules</li><li>Fields</li></ul></li><li>Values to return<ul><li>Rules</li><li>Fields</li></ul></li></ul> | <p>N/A</p> | <p>3 functions per derived field</p> | <p>New derived field or value for further processing in next rule</p> |

{style="table-layout:auto"}

## Use case {#lookup-uc}

You would like to lookup the activity name using the activity id collected when your customers clicked on a personalized banner shown through Adobe Target. You want to use a lookup dataset with Analytics for Target (A4T) activities containing activity ids and activity names.

### A4T lookup dataset {#lookup-uc-lookup}

| Activity Id | Activity Name |
|---|---|
| 415851 | MVT Test Category Pages |
| 415852 | Luma - Campaign Max 2022 |
| 402922 | Home Page Banners |

{style="table-layout:auto"}

### Derived field {#lookup-uc-derivedfield}

You define an `Activity Name` derived field. You use the [!UICONTROL LOOKUP] function to define a rule to lookup the value from your collected data, specified in the [!UICONTROL Field to apply lookup] field. You select the lookup dataset from the [!UICONTROL Lookup dataset] list, selecting the identifier field from the [!UICONTROL Matching key list] and the field to return from the [!UICONTROL Values to return] list.

![Screenshot of the Lowercase rule](assets/lookup.png)

## More info

You can quickly insert a [!UICONTROL Lookup] function in the rule builder, already containing one or more other functions.

  1. Select **[!UICONTROL Schema fields]** from selector.
  1. Select ![Schema field icon](assets/Smock_Folder_18_N.svg) **[!UICONTROL Lookup datasets]**.
  1. Select your lookup dataset and find the field you want to use for lookup.
  1. Drag the lookup field and drop the field on any of the available input fields for a function (for example Case When). When valid, a blue **[!UICONTROL + Add box]** will allow you to drop the field and automatically insert a Lookup function before the function you dropped the lookup field on, and populate the Lookup function with relevant values for all fields.
     ![Lookup drag](assets/lookup-drag.png) 

+++

-->

<!-- LOWERCASE -->

### Lowercase

Converts values from a field to lowercase and stores it into a new derived field.

+++ Details

## Specification {#lowercase-io}

| Input Data Type | Input | Included Operators | Limit | Output |
|---|---|---|---|---|
| <ul><li>String</li><li>Numeric</li><li>Date</li></ul> | <ul><li>[!UICONTROL Field]:</li><ul><li>Rules</li><li>Standard fields</li><li>Fields</li></ul> | <p>N/A</p> | <p>2 functions per derived field</p> | <p>New derived field</p> |

{style="table-layout:auto"}

## Use case {#lowercase-uc}

You would like to convert all collected product names into lowercase for proper reporting.

### Data before {#lowercase-uc-databefore}

| Collected Product Names | Product Views |
|---|---:|
| Tennis racket | 35 |
| Tennis Racket | 33 |
| tennis racket | 21 |
| Baseball bat | 15 |
| Baseball Bat | 12 |
| baseball bat | 10 |

{style="table-layout:auto"}

### Derived field {#lowercase-uc-derivedfield}

You define a `Product Names` derived field. You use the [!UICONTROL LOWERCASE] function to define a rule to convert the value from the [!UICONTROL Collected Product Names] field to lowercase and store that in the new derived field.

![Screenshot of the Lowercase rule](assets/lowercase.png)


### Data after {#lowercase-uc-dataafter}

| Product Names | Product Views |
|---|---|
| tennis racket | 89 |
| baseball bat | 37 |

{style="table-layout:auto"}

+++

<!-- MERGE FIELDS -->

### Merge Fields

Merges values from two different fields into a new derived field.

+++ Details

## Specification {#merge-fields-io}

| Input Data Type | Input | Included Operators | Limit | Output |
|---|---|---|---|---|
| <ul><li>String</li><li>Numeric</li><li>Date</li></ul> | <ul><li>[!UICONTROL Field]:</li><ul><li>Rules</li><li>Standard fields</li><li>Fields</li></ul> | <p>N/A</p> | <p>5 functions per derived field</p> | <p>New derived field</p> |

{style="table-layout:auto"}

## Use case {#merge-fields-uc}

You would like to create a dimension made up from the page name field and the call reason field with the intent of analyzing the journey across channels.

### Data before {#merge-fields-uc-databefore}

| Page Name | Session | Visitors |
|---|--:|--:|
| help page | 250 | 200 |
| home page | 500 | 250 |
| product detail page | 300 | 200 |

{style="table-layout:auto"}

| Call Reason | Session | Visitors |
|---|--:|--:|
| questions about my order | 275 | 250 |
| make a change to my order | 150 | 145 |
| problem with ordering | 100 | 95 |

{style="table-layout:auto"}

### Derived field {#merge-fields-uc-derivedfield}

You define a `Cross Channel Interactions` derived field. You use the [!UICONTROL MERGE FIELDS] function to define a rule to merge the values from the [!UICONTROL Page Name] field and [!UICONTROL Call Reason] field and store that in the new derived field.

![Screenshot of the Merge Fields rule](assets/merge-fields.png)

### Data after {#merge-fields-uc-dataafter}

| Cross Channel Interactions | Sessions | Visitors |
|---|--:|--:|
| home page | 500 | 250 |
| product detail page | 300 | 200 |
| questions about my order | 275 | 250 |
| help page | 250 | 200 |
| make a change to my order | 150 | 145 |
| problem with ordering | 100 | 95 |

{style="table-layout:auto"}

## More information {#merge-fields-moreinfo}

You have to select the same type of fields within a Merge Fields rule. For example, if you select a Date field, all other fields you want to merge have to be Date fields.

![Screenshot of constraint on merge fields](assets/merge-fields-constraint.png)

+++


<!-- REGEX REPLACE -->

### Regex Replace

Replaces a value from a field using a regular expression into a new derived field.

+++ Details

## Specification {#regex-replace-io}

| Input Data Type | Input | Included Operators | Limit | Output |
|---|---|---|---|---|
| <ul><li>String</li><li>Numeric</li></ul> | <ul><li>[!UICONTROL Field]:</li><ul><li>Rules</li><li>Standard fields</li><li>Fields</li></ul></ul><ul><li>[!UICONTROL Regex]:</li><ul><li>String</li></ul></li><li>[!UICONTROL Output Format]:<ul><li>String</li></ul></ul><ul><li>Case sensitive</li><ul><li>Boolean</li></ul></li></ul></li> | <p>N/A</p> | <p>1 function per derived field</p> | <p>New derived field</p> |

{style="table-layout:auto"}

## Use case {#regex-replace-uc}

You would like to grab a potion of a URL and use that as a unique page identifier to analyze traffic. You use `[^/]+(?=/$|$)` for the regular expression to capture the end of the URL and `$1` as the output pattern.

### Data before {#regex-replace-uc-databefore}

| Page URL|
|---|
| `https://business.adobe.com/products/analytics/adobe-analytics-benefits.html` |
| `https://business.adobe.com/products/analytics/adobe-analytics.html` |
| `https://business.adobe.com/products/experience-platform/customer-journey-analytics.html` |
| `https://business.adobe.com/products/experience-platform/adobe-experience-platform.html` |

{style="table-layout:auto"}

### Derived field {#regex-replace-uc-derivedfield}

You create a `Page Identifier` derived field. You use the [!UICONTROL REGEX REPLACE] function to define a rule to replace value of the [!UICONTROL Referring URL] field using a [!UICONTROL Regex] of `[^/]+(?=/$|$)` and [!UICONTROL Output format] of `$1`.

![Screenshot of the Regex Replac rule](assets/regex-replace.png)


### Data after {#regex-replace-uc-dataafter}

| Page Identifier |
|---|
| adobe-analytics-benefits.html |
| adobe-analytics.html |
| customer-journey-analytics.html |
| adobe-experience-platform.html |

## More information

Customer Journey Analytics uses a subset of the Perl regex syntax. The following expressions are supported:

| Expression | Description |
| --- | --- |
| `a` | A single character `a`. |
| `a\|b` | A single character `a` or `b`. |
| `[abc]` | A single character `a`, `b`, or `c`. |
| `[^abc]` | Any single character except `a`, `b`, or `c`. |
| `[a-z]` | Any single character in the range of `a`-`z`. |
| `[a-zA-Z0-9]` | Any single character in the range of `a`-`z`, `A`-`Z`, or digits `0`-`9`. |
| `^` | Matches the beginning of the line. |
| `$` | Matches the end of the line. |
| `\A` | Start of string. |
| `\z` | End of string. |
| `.` | Matches any character. |
| `\s` | Any whitespace character. |
| `\S` | Any non-whitespace character. |
| `\d` | Any digit. |
| `\D` | Any non-digit. |
| `\w` | Any letter, number, or underscore. |
| `\W` | Any non-word character. |
| `\b` | Any word boundary. |
| `\B` | Any character that is not a word boundary. |
| `\<` | Start of word. |
| `\>` | End of word. |
| `(...)` | Capture everything enclosed. |
| `(?:...)` | Non-marking capture. Prevents the match from being referenced in the output string. |
| `a?` | Zero or one of `a`. |
| `a*` | Zero or more of `a`. |
| `a+` | One ore more of `a`. |
| `a{3}` | Exactly 3 of `a`. |
| `a{3,}` | 3 or more of `a`. |
| `a{3,6}` | Between 3 and 6 of `a`. |

You can use these sequences in the [!UICONTROL Output format] any number of times and in any order to achieve the desired string output.

| Output placeholder sequence | Description |
| --- | --- |
| `$&` | Outputs what matched the whole expression. |
| `$n` | Outputs what matched the nth sub expression. For example, `$1` outputs the first sub expression. |
| ``$` `` | Outputs the text between the end of the last match found (or the start of the text if no previous match was found), and the start of the current match. |
| `$+` | Outputs what matched the last marked sub expression in the regular expression. |
| `$$` | Outputs the string character `"$"`. |

{style="table-layout:auto"}

+++

<!-- SPLIT -->

### Split

Splits a value from a field into a new derived field.

+++ Details

## Specification {#split-io}

| Input Data Type | Input | Included Operators | Limit | Output |
|---|---|---|---|---|
| <ul><li>String</li><li>Numeric</li></ul> | <ul><li>[!UICONTROL Field]:</li><ul><li>Rules</li><li>Standard fields</li><li>Fields</li></ul></ul><ul><li>[!UICONTROL Method]:</li><ul><li>From the left</li><li>From the right</li><li>Convert to array</li></ul></li><li>For Delimiter:<ul><li>String</li></ul><li>For Index:<ul><li>Numeric</li></ul></li> | <p>N/A</p> | <p>5 functions per derived field</p> | <p>New derived field</p> |

{style="table-layout:auto"}

## Use case 1 {#split-uc1}

You collect voice app responses into a delimited list in a single dimension. You would like each value in the list to be a unique value in the responses report.

### Data before {#split-uc1-databefore}

| Voice App Responses | Events |
|---|--:|
| it was great,made perfect sense,will recommend to others | 1 |
| it was great,somewhat confusing,will recommend to others | 1 |
| it was not great,very confusing,will not recommned to others | 1 |

{style="table-layout:auto"}

### Derived field {#split-u1-derivedfield}

You create a `Responses` derived field. You use the [!UICONTROL SPLIT] function to define a rule to use the  [!UICONTROL Convert to array] method to convert the values from the [!UICONTROL Voice App Response] field using `,` as the [!UICONTROL Delimiter].

![Screenshot of the Split rule 1](assets/split-1.png)

### Data after {#split-uc1-dataafter}

| Responses | Events |
|---|--:|
| it was great | 2 |
| will recommend to others | 2 |
| it was not great | 1 |
| made perfect sense | 1 |
| somewhat confusing | 1 |
| very confusing | 1 |
| will not recommend to others | 1 |

{style="table-layout:auto"}

## Use case 2 {#split-uc2}

You collect voice app responses into a delimited list in a single dimension. You would like the responses from the first value in the list into its own dimension. You would like to put the last value in the list into its own dimension.

### Data before {#split-uc2-databefore}

| Responses | Events |
|---|--:|
| it was great,made perfect sense,will recommed to others | 1 |
| it was great,somewhat confusing,will recommend to others | 1 |
| it was not great,very confusing,will not recommned to others | 1 |

{style="table-layout:auto"}

### Derived field {#split-u2-derivedfield}

You create a  `First Response` derived field. You use the [!UICONTROL SPLIT] function to define a rule to take the first value from the [!UICONTROL Responses] field from the left of the response `,` as the delimiter. 

![Screenshot of the Split rule - first value](assets/split-2.png)

You create a `Second Response` derived field to take the last value  from the [!UICONTROL Responses] field by selecting From the right, 1 as the Delimiter and 1 as the Index.

![Screenshot of the Split rule - last value](assets/split-3.png)

### Data after {#split-uc2-dataafter}

| First Response | Events |
|---|--:|
| it was great | 2 |
| it was not great | 1 |

{style="table-layout:auto"}

| Second Response | Events |
|---|--:|
| will recommend to others | 2 |
| will not recommend to others | 1 |

{style="table-layout:auto"}

+++


<!-- TRIM -->

### Trim

Trims whitespace, special characters or number of characters from either the beginning or the end of field values into a new derived field.

+++ Details

## Specification {#trim-io}

| Input Data Type | Input | Included Operators | Limit | Output |
|---|---|---|---|---|
| <ul><li>String</li></ul> | <ul><li>[!UICONTROL Field]<ul><li>Rules</li><li>Standard fields</li><li>Fields</li></ul></li><li>Trim whitespace</li><li>Trim special characters<ul><li>Input of special characters</li></ul></li><li>Trim from left<ul><li>From&nbsp;<ul><li>String start</li><li>Position<ul><li>Position #</li></ul></li><li>String<ul><li>String value</li><li>Index</li><li>Flag to include string</li></ul></li></ul></li><li>To<ul><li>String end</li><li>Position<ul><li>Position #</li></ul></li><li>String<ul><li>String value</li><li>Index</li><li>Flag to include string</li></ul></li><li>Length</li></ul></li></ul></li><li>Trim from right<ul><li>From&nbsp;<ul><li>String end</li><li>Position<ul><li>Position #</li></ul></li><li>String<ul><li>String value</li><li>Index</li><li>Flag to include string</li></ul></li></ul></li><li>To<ul><li>String start</li><li>Position<ul><li>Position #</li></ul></li><li>String<ul><li>String value</li><li>Index</li><li>Flag to include string</li></ul></li><li>Length</li></ul></li></ul></li></ul> | <p>N/A</p> | <p>1 function per derived field</p> | <p>New derived field</p> |

{style="table-layout:auto"}

## Use case 1 {#trim-uc1}

You collect product data, however that data contains hidden whitespace characters which fragments reporting. You would like to easily trim any excess whitepace

### Data before {#trim-uc1-databefore}

| Product ID | Events |
|---|--:|
| `"prod12356 "` | 1 |
| `"prod12356"` | 1 |
| `" prod12356"` | 1 | 

{style="table-layout:auto"}

### Derived field {#trim-u1-derivedfield}

You create a `Product Identifier` derived field. You use the [!UICONTROL TRIM] function to define a rule to **[!UICONTROL Trim whitespace]** from the **[!UICONTROL Product ID]** field.

![Screenshot of the Split rule 1](assets/trim-1.png)

### Data after {#trim-uc1-dataafter}

| Product Identifier | Events |
|---|--:|
| `"prod12356"` | 3 |

{style="table-layout:auto"}

## Use case 2 {#trim-uc2}

Your data on page names collected includes some erroneous special characters at the end of the page name which need to be removed.

### Data before {#trim-uc2-databefore}

| Name | Events |
|---|--:|
| home page# | 1 |
| home page? | 1 |
| home page% | 1 |
| home page& | 1 |
| home page/ | 1 |

{style="table-layout:auto"}

### Derived field {#trim-u2-derivedfield}

You create a  `Page Name` derived field. You use the [!UICONTROL TRIM] function to define a rule to [!UICONTROL Trim special characters] from the [!UICONTROL Name] field using the [!UICONTROL Special characters] `#?%&/`.

![Screenshot of the Split rule - first value](assets/trim-2.png)

### Data after {#trim-uc2-dataafter}

| Page Name | Events |
|---|--:|
| home page | 5 |

{style="table-layout:auto"}


## Use case 3 {#trim-uc3}

You collect data including a storeID. The storeID contains the abbreviated US state code as the first two characters. You want to only use that state code in your reporting.

### Data before {#trim-uc3-databefore}

| storeID | Events |
|---|--:|
| CA293842 | 1 |
| CA423402 | 1 |
| UT123418 | 1 |
| UT189021 | 1 |
| ID028930 | 1 |
| OR234223 | 1 |
| NV22342 | 1 |

{style="table-layout:auto"}

### Derived field {#trim-u3-derivedfield}

You create a  `Store Identifier` derived field. You use the [!UICONTROL TRIM] function to define a rule to [!UICONTROL Truncate from right] the [!UICONTROL storeID] field from String end to position `3`.

![Screenshot of the Split rule - first value](assets/trim-3.png)

### Data after {#trim-uc3-dataafter}

| Store Identifier | Events |
|---|--:|
| CA | 2 |
| UT | 2 |
| ID | 1 |
| OR | 1 |
| NV | 1 |

{style="table-layout:auto"}
+++


<!-- URL PARSE -->

### URL Parse

Parses out different parts of a URL including protocol, host, path, or query parameters.

+++ Details

## Specifications {#urlparse-io}

| Input Data Type | Input | Included Operators | Limit | Output |
|---|---|---|---|---|
| <ul><li>String</li></ul> | <ul><li>[!UICONTROL Field]:</li><ul><li>Rules</li><li>Standard fields</li><li>Fields</li></ul><li>[!UICONTROL Option]:<ul><li>[!UICONTROL Get protocol]</li><li>[!UICONTROL Get host]</li><li>[!UICONTROL Get path]</li><li>[!UICONTROL Get query string value]<ul><li>[!UICONTROL Query parameter]:<ul><li>String</li></ul></li></ul></li><li>[!UICONTROL Get hash value]</li></ul></li></ul></li></ul> | <p>N/A</p> | <p>5 functions per derived field</p> | <p>New derived field</p> |

{style="table-layout:auto"}


## Use case 1 {#urlparse-uc1}

You only want use the referring domain from the referring URL as part of a marketing channel's set of rules.

### Data before {#urlparse-uc1-databefore}

| [!DNL Referring URL] |
|----|
| `https://www.google.com/` |
| `https://duckduckgo.com/` | 
| `https://t.co/` |
| `https://l.facebook.com/`| 

{style="table-layout:auto"}

### Derived field {#urlparse-uc1-derivedfield}

You define a  `Referring Domain` derived field. You use the [!UICONTROL URL PARSE] function to define a rule to fetch the host from the [!UICONTROL Referring URL] field and store that in the new derived field.

![Screenshot of the Url Parse rule 1](assets/url-parse-1.png)

### Data after {#urlparse-uc1-dataafter}

| [!DNL Referrer Domain] |
|----|
| [!DNL www.google.com] |
| [!DNL duckduckgo.com] |
| [!DNL t.co] |
| [!DNL l.facebook.com] |

{style="table-layout:auto"}


## Use case 2 {#urlparse-uc2}

You want to use the value of the `cid` parameter of a query string in a [!DNL Page URL] as part of the output of a derived tracking code report.

### Data before {#urlparse-uc2-databefore}

| [!DNL Page URL] |
|----|
| `https://www.adobe.com/?cid=abc123` |
| `https://www.adobe.com/?em=email1234&cid=def123` | 
| `https://www.adobe.com/landingpage?querystring1=test&test2=1234&cid=xyz123` | 

{style="table-layout:auto"}

### Derived field {#urlparse-uc2-derivedfield}

You define a `Query String CID` derived field. You use the [!UICONTROL URL PARSE] function to define a rule to fetch the value of the query string parameter in the [!UICONTROL Page URL] field, specifying `cid` as the query parameter. The output value is stored in the new derived field.

![Screenshot of the Url Parse rule 2](assets/url-parse-2.png)

### Data after {#urlparse-uc2-dataafter}

| [!DNL Query String CID] |
|----|
| [!DNL abc123] |
| [!DNL def123] |
| [!DNL xyz123] |

{style="table-layout:auto"}

+++

## Limitations

The following limitations apply to the Derived field functionality in general:

- You can use a maximum of ten different schema fields (not including standard fields) when defining rules for a derived field. 
  - From this maximum of ten different schema fields, only a maximum of three lookup schema or profile schema fields are allowed.
- You can have a maximum of 100 derived fields per Customer Journey Analytics connection.

## More information

- [Making the Most of Your Data: A Framework for Using Derived Fields in Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/making-the-most-of-your-data-a-framework-for-using-derived/ba-p/601670)

- [Derived Fields Use Cases for Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/derived-fields-use-cases-for-customer-journey-analytics/ba-p/601679)
