---
title: Custom field Merge Fields function
description: Description of the custom field Merge Fields function.
solution: Customer Journey Analytics
feature: Data Views
---

# Merge Fields

This function provides the ability to take values from two different fields and include their respective values in a single dimension. The rule first checks to see if the first value is set. If not, then it will use the second value and so on.

## Input(s) / Operators / Output

| Input Data Type | Input(s) | Included Operators | Output(s) |
|---|---|---|---|
| <ul><li>String</li><li>Numeric</li><li>Date</li></ul> | <ul><li>Values from two or more fields</li></ul> | <p>N/A</p> | <p>New custom field</p> |

{style="table-layout:auto"}

## Use Case

A customer would like to create a new dimension made up of the page name field and the call reason field with the intent of analyzing the journey across channels (in this case web and call center).

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

**New Custom Dimension - Cross Channel Interactions**

| Cross Channel Interactions | Sessions | Visitors |
|---|---|-----|
| home page | 500 | 250 |
| product detail page | 300 | 200 |
| questions about my order | 275 | 250 |
| help page | 250 | 200 |
| make a change to my order | 120 | 145 |
| problem with ordering | 100 | 95 |

{style="table-layout:auto"}

### Data

| BEFORE:<br/>Page Name Field | BEFORE:<br/>Call Reason Field
|----|----|
| help page | questions about my order |
| home page | make a change to my order |
| product detail page | problem with ordering |

{style="table-layout:auto"}

| AFTER:<br/>New Cross Channel Interaction Custom Field |
|---|
| help page |
| home page |
| product detail page |
| questions about my order |
| make a change to my order |
| problem with ordering |

{style="table-layout:auto"}


### Screenshot

Not available yet?
