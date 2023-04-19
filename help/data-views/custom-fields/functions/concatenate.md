---
title: Custom field Concatenate function
description: Description of the custom field concatenate function.
solution: Customer Journey Analytics
feature: Data Views
---

# Concatenate

This function provides the ability to combine two or more fields, custom fields, or user-entered values into a single field with defined delimiters.

## Input(s) / Operators / Output

| Input Data Type | Input(s) | Included Operators | Output(s) |
|---|---|---|---|
| String | <ul><li>Two or more values to combine<ul><li>Fields</li><li>Derived value from a previous rule</li><li>User-entered value</li></ul></li><li>Delimiter(s)<ul><li>Input or selection of a delimiter for each value</li></ul></li> </ul> | N/A | New string-based custom field |

{style="table-layout:auto"}

## Use Case

A travel company is currently collecting origin and destination airport codes as separate fields. They would like to take the two fields and combine them into a single dimension separated by a hyphen. They would like to analyze the combination of origin and destination to identify top routes booked, etc.

Example:

* Origin and destination values are collected in separate fields in the same table.
* The user determines to use a delimiter of '-' between the values
* Customer ABC123 books a flight between Salt Lake City (SLC) and Orlando (MCO)
* Customer ABC456 books a flight between Salt Lake City (SLC) and Los Angeles (LAX)
* Customer ABC789 books a flight between Salt Lake City (SLC) and Seattle (SEA)
* Customer ABC987 books a flight between Salt Lake City (SLC) and San Jose (SJO)
* Customer ABC654 books a flight between Salt Lake City (SLC) and Orlando (MCO)

Example Report

| O/D Pair | Bookings |
|---|---|
| SLC-MCO | 2 |
| SLC-LAX | 1 |
| SLC-SEA | 1 |
| SLC-SJO | 1 |

{style="table-layout:auto"}


### Data

#### Before

| Origin Field | Destination Field |
|----|----|
| SLC | MCO |
| SLC | LAX |
| SLC | SEA |
| SLC | SJO |
| SLC | MCO |

{style="table-layout:auto"}

#### After

| New Origin / Destination Custom Field |
|---|
| SLC-MCO |
| SLC-LAX |
| SLC-SEA |
| SLC-SJO |
| SLC-MCO |

{style="table-layout:auto"}


### Screenshot

![Concatenate](../assets/concatenate.png)
