---
title: Custom field Trim function
description: Description of the custom field Trim function.
solution: Customer Journey Analytics
feature: Data Views
---

# Trim

The ability to trim either whitespace or special characters from either the beginning or the end of a string. Also the ability to specify the number of characters to use for the returned value, either from the front or the end of the string.

## Input(s) / Operators / Output

| Input Data Type | Input(s) | Included Operators | Output(s) |
|---|---|---|---|
| <ul><li>String</li></ul> | <ul> <li>Single Field</li> <li>Flag to trim whitespace</li> <li>Flag to trim special characters<ul> <li>Input of special characters</li> </ul> </li> <li>Flag to trim from left<ul> <li>From <ul> <li>Start string</li> <li>Position<ul> <li>Position #</li> </ul> </li> <li>String<ul> <li>String value</li> <li>Index</li> <li>Flag to include string</li> </ul> </li> </ul> </li> <li>To<ul> <li>Start string</li> <li>Position<ul> <li>Position #</li> </ul> </li> <li>String<ul> <li>String value</li> <li>Index</li> <li>Flag to include string</li> </ul> </li> <li>Length</li> </ul> </li> </ul> </li> <li>Flag to trim from right<ul> <li>From <ul> <li>Start string</li> <li>Position<ul> <li>Position #</li> </ul> </li> <li>String<ul> <li>String value</li> <li>Index</li> <li>Flag to include string</li> </ul> </li> </ul> </li> <li>To<ul> <li>Start string</li> <li>Position<ul> <li>Position #</li> </ul> </li> <li>String<ul> <li>String value</li> <li>Index</li> <li>Flag to include string</li> </ul> </li> <li>Length</li> </ul> </li> </ul> </li> </ul> | <p>N/A</p> | <p>New custom field</p> |

{style="table-layout:auto"}

## Use Case 1

Some of the product data a customer has collected has hidden whitespace characters added which fragments the reporting and is confusing for customers. They would like to easily trim off any excess whitespace.

Assumptions:

- Each response from the survey is collected in a delimited list.

| Product ID |
|---|
| "prod12356  " |
| "prod12356" |
| "prod12356 "|

{style="table-layout:auto"}


### Data

| BEFORE:<br/>Product ID | BEFORE:<br/>Events |
|----|----|
| "prod12356" | 1 |
| "prod12356" | 1 |
| "prod12356 " | 1 |

{style="table-layout:auto"}

| AFTER: New custom field<br/>Product ID | AFTER:<br/>Events |
|---|---|
| "prod12356" | 3 |


### Screenshot

Pending availability in the UI.


## Use Case 2

The data collected includes some erroneous special characters at the end of the page name which need to be removed

| Page Name |
|---|
| homepage# |
| homepage? |
| homepage% |
| homepage& |
| homepage/ |

{style="table-layout:auto"}


### Data

| BEFORE:<br/>Page Name | BEFORE:<br/>Events |
|----|----|
| homepage# | 1 |
| homepage? | 1 |
| homepage% | 1 |
| homepage& | 1 |
| homepage/ | 1 |

{style="table-layout:auto"}

| AFTER: New custom field<br/>Home Page | AFTER:<br/>Events |
|---|---|
| home page | 5 |

### Screenshot

Pending availability in the UI.


## Use Case 3

The first two letters of a storeID collected contain the abbreviation for the state where that store is located. The customer would like to take only the first two characters collected.

| Store ID |
|---|
| CA293842 |
| CA423402 |
| UT123418 |
| UT189021 |
| ID028930 |
| OR234223 |
| NV22342 |

{style="table-layout:auto"}


### Data

| BEFORE:<br/>Store ID | BEFORE:<br/>Events |
|----|----|
| CA293842 | 1 |
| CA423402 | 1 |
| UT123418 | 1 |
| UT189021 | 1 |
| ID028930 | 1 |
| OR234223 | 1 |
| NV22342 | 1 |

{style="table-layout:auto"}

| AFTER: New custom field<br/>Store ID | AFTER:<br/>Events |
|---|---|
| CA | 2 |
| UT | 2 |
| ID | 1 |
| OR | 1 |
| NV | 1 |

{style="table-layout:auto"}

### Screenshot

Pending availability in the UI.

