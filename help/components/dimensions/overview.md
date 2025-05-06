---
title: Dimensions overview
description: Learn what dimensions are and how they are used in Customer Journey Analytics
feature: Dimensions
exl-id: 3592808b-17fd-401d-ab12-ff0308b21f45
---
# Dimensions overview

Dimensions are a component type in Customer Journey Analytics that are used to analyze data. For example, you use dimensions when building reports in [Analysis Workspace](/help/analysis-workspace/home.md) or in [Report Builder](/help/report-builder/rb-overview.md).

Customer Journey Analytics dimensions are of unlimited type; values can be numeric, text, objects, lists, or mixtures of all. 

A basic report in Customer Journey Analytics shows rows of dimensions (commonly string values), against a column of metrics (commonly numeric values).

For example, if you combined the Page dimension with the People metric, you would get a ranked report showing your top-visited pages by people:

| Page | People |
| --- | ---: |
| Home page | 800 |
| Product page | 500 |
| Purchase page | 100 |

{style="table-layout:fixed"}

Each dimension represents a different part or facet of your site. You can combine one of more of these dimensions with one or more metrics to create a desired report.


## Create dimensions

Customer Journey Analytics administrators can [create dimensions within a data view](/help/data-views/create-dataview.md#components).

## Default dimensions

When you create a data view, the following time-based components are added by default as dimensions to your data view:

- 15 Minute
- 30 Minute
- 5 Minute
- Day
- Day of Month
- Day of Week
- Day of Year
- Hour
- Hour of Day
- Minute
- Minute of Hour
- Month
- Month of Year
- Quarter
- Quarter of Year
- Second
- Week of Year
- Year

## Add dimension descriptions

Customer Journey Analytics administrators can add descriptions for dimensions and other components either within the data view or directly within Analysis Workspace. For information about how to add descriptions to dimensions, see [Add component descriptions](/help/components/add-component-descriptions.md).
