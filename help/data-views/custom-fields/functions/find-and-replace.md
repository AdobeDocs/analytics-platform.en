---
title: Custom field Find and Replace function
description: Description of the custom field Find & Replace function.
solution: Customer Journey Analytics
feature: Data Views
---

# Find and Replace

This function provides the ability to find all values in a selected field and replace those values with a different value in a new derived field.

## Input(s) / Operators / Output

| Input Data Type | Input(s) | Included Operators | Output(s) |
|---|---|---|---|
| <p>String</p> | <ul><li><span>'When to replace' field criteria</span></li><li><span>'Replace with' field value</span><ul><li><span>User-entered</span></li><li><span>Separate field</span></li></ul></li></ul> | <p><u>Strings</u></p><ul><li>Find All and Replace All</li></ul> | New string-based custom field |

{style="table-layout:auto"}

## Use Case

A customer has received some malformed values for their external marketing channels report. They were expecting 'email marketing' and they have several instances where they have received 'email%20 marketing'. This fractures the reporting and makes it more difficult to see how email is performing in their reporting. They would like to replace 'email%20' with 'email' and have it roll into the correctly captured values.

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


### Data

| BEFORE:<br/>External Marketing Field | AFTER:<br/> External Marketing Custom Field
|----|----|
| email marketing | email marketing |
| email%20marketing | email marketing |
| email marketing | email marketing |
| email marketing | email marketing |
| email%20marketing | email marketing |

{style="table-layout:auto"}


### Screenshot

![Concatenate](../assets/find-and-replace.png)
