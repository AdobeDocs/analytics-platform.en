---
title: Custom field Split function
description: Description of the custom field Split function.
solution: Customer Journey Analytics
feature: Data Views
---

# Split

The ability to split up a value based on a delimiter.

## Input(s) / Operators / Output

| Input Data Type | Input(s) | Included Operators | Output(s) |
|---|---|---|---|
| <ul><li>String</li></ul> | <ul><li>Sing field</li><li>Delimiter</li><li>Start from the left or the right (and associated index) or convert to an array with all values</li></ul> | <p>N/A</p> | <p>New custom field</p> |

{style="table-layout:auto"}

## Use Case 1

A customer is collecting survey responses into a delimited list in a single dimension. They would like each value in the list to be a unique value in their responses report.

Assumptions:

- Each response from the survey is collected in a delimited list.

| RESPONSES |
|---|
| it was great,made perfect sense,will recommend to others |
| it was great,somewhat confusing,will recommend to others |
| it was not great,very confusing,will not recommend to others |

{style="table-layout:auto"}


### Data

| BEFORE:<br/>Responses | BEFORE:<br/>Events |
|----|----|
| it was great,made perfect sense,will recommed to others | 1 |
| it was great,somewhat confusing,will recommend to others | 1 |
| it was not great,very confusing,will not recommned to others | 1 |

{style="table-layout:auto"}

| AFTER: New custom field<br/>Responses (split) | AFTER:<br/>Events |
|---|---|
| it was great | 2 |
| will recommend to others | 2 |
| it was not great | 1 |
| made perfect sense | 1 |
| somewhat confusing | 1 |
| very confusing | 1 |
| will not recommend to others | 1 |

### Screenshot

Pending availability in the UI.


## Use Case 2

A customer would like to use the value of a query string as part of the output of a derived tracking code report. They would like to pull the value out of the 'cid' parameter.

Assumption: 

- Dataset has a field for Page URL that contains query string parameters.

### Data

| BEFORE:<br/>Page URL | AFTER: New custom field<br/>Query String CID
|----|----|
| <https://www.adobe.com/?cid=abc123> | abc123 |
| <https://www.adobe.com/?em=email1234&cid=def123> | def123 |
| <https://www.adobe.com/landingpage?querystring1=test&test2=1234&cid=xyz123> | xyz123 |

{style="table-layout:auto"}

### Screenshot

Pending availability in the UI.

