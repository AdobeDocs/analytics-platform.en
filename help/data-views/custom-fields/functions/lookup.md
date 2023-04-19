---
title: Custom field Lookup function
description: Description of the custom field Lookup function.
solution: Customer Journey Analytics
feature: Data Views
---

# Lookup

This function provides the ability to define a set of values that are replaced by corresponding values by text entry.

## Input(s) / Operators / Output

| Input Data Type | Input(s) | Included Operators | Output(s) |
|---|---|---|---|
| <ul><li>String</li><li>Numeric</li><li>Date</li></ul> | <ul><li>Sing field</li><li>Lookup file<ul><li>Key Column</li><li>New Field Column</li></ul></li></ul> | <p>N/A</p> | <p>New custom field</p> |

{style="table-layout:auto"}

## Use Case 1

A hotel customer has a file (CSV) that includes a key column for a hotel ID and one or more additional columns associated with the hotel ID (City, Number of Rooms, Name of Hotel, etc.).
They are collecting hotel ID in a dimension and would like to create a new dimension based for Hotel Name based on the value of the hotel ID dimension.

**Field in CJA**

| Hotel ID | Product Views |
|---|---:|
| SLC123 | 200 |
| LX342 | 198 |
| SFO456 | 190 |

{style="table-layout:auto"}

**CSV File Structure and Content**

| hotelID | city | rooms | hotel name |
|---|---|---:|---|
| SLC123 | Salt Lake City | 40 | SLC Downtown |
| LAX342 | Los Angels | 60 | LA Airport |
| SFO456 | San Francisco | 75 | Market Street |

{style="table-layout:auto"}

**Custom Hotel Name Dimension Report Based on hotelID field**

| Hotel Name | Product Views |
|----|----:|
| SLC Downtown | 200 |
| LA Airport | 198 |
| Market Street | 190 |

{style="table-layout:auto"}

### Data

| BEFORE:<br/>Hotel ID Field | AFTER:<br/>Hotel Name Custom Field
|----|----|
| SLC123 | SLC Downtown |
| LAX342 | LA Airport |
| SFO456 | Market Street |

{style="table-layout:auto"}

### Screenshot

![Lookup 1](../assets/lookup-1.png)


## Use Case 2

A customer has several page names that have been collected as URLs instead of the friendly page name. They would like to replace about 10+ URL-based page names with friendly names in the reporting. In many cases, customers will collect both a friendly name and a URL-based value due to some code issue and this breaks the reporting until they can get it fixed in the code.

Assumptions: 

- Values are all part of the same field.
- 1:1 relationship between the value matched and an input value.

### Data

| BEFORE:<br/>Page Name Field | AFTER:<br/>New Custom Page Name Field |
|---|---|
| Home Page | Home Page |
| Flight Search | Flight Search |
| <http://www.expedia.ca/Hotel-Search> | Hotel Search |
| <https://www.expedia.com/Package-Search> | Package Search |
| Deals & Offers | Deals & Offers |
| <http://www.expedia.ca/user/reviews> | Reviews |
| <https://www.expedia.com.br/Generate-Quote/preview> | Generate Quote |

{style="table-layout:auto"}

### Screenshot

![Lookup 2](../assets/lookup-2.png)

