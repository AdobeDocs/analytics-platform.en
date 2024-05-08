---
title: Dimensions overview
description: Learn what dimensions are and how they are used in Customer Journey Analytics
feature: Dimensions
---
# Dimensions overview

Dimensions are a component type in Customer Journey Analytics that are used to analyze data. For example, you use dimensions when building reports in [Analysis Workspace](/help/analysis-workspace/home.md) or in [Report Builder](/help/report-builder/report-buider-overview.md).

Customer Journey Analytics dimensions are a unlimited; values can be numeric, text, objects, lists, or mixtures of all. 

A basic report in Customer Journey Analytics shows rows of dimensions (commonly string values), against a column of metrics (commonly numeric values).

For example, if you combined the 'Page' dimension with the 'Visits' metric, you would get a ranked report showing your top-visited pages:

| `Page` | `Visits` |
| --- | --- |
| `Home page` | `800` |
| `Product page` | `500` |
| `Purchase page` | `100` |

Each dimension represents a different part or facet of your site. You can combine one of more of these dimensions with one or more metrics to create a desired report.

## Create dimensions

Customer Journey Analytics administrators can [create numeric-based dimensions within a data view](/help/data-views/create-dataview.md#components).

## Add dimension descriptions

Customer Journey Analytics administrators can add descriptions for dimensions and other components either within the data view or directly within Analysis Workspace. For information about how to add descriptions to dimensions, see [Add component descriptions](/help/components/add-component-descriptions.md).
