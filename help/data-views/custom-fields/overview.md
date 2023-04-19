---
title: Custom fields overview
description: A custom field specifies report-time manipulation of schema fields and/or standard components through a set of available functions.
solution: Customer Journey Analytics
feature: Data Views
---
# Custom fields - Overview

Custom fields are an important part of the real-time reporting functionality in Customer Journey Analytics (CJA). A custom field allows you to define (often complex) data manipulations on the fly, through a customizable rule builder.  You can then use that custom field as a component (metric or dimension) in Workspace or even further define as a component in Data View. 

Using custom fields can save a significant amount of time and effort compared to transforming or manipulating your data in other locations outside of CJA, such as Data Prep, Data Distiller, or within your own Extract Transform Load (ETL) / Extract Load Transform (ELT) processes.

## Collection-time vs. Report-time processing

You often need the ability to process data before it is useful for reporting. You can process that data at several stages in the journey that spans from collecting data to generating your report or visualization.

In Adobe Analytics most of that processing of data occurs immediately after collecting the data. Functionalties like VISTA Rules, Processing Rules, Marketing Channels Processing Rules are available to support this **collection-time processing**. The data is then stored and at report time you can apply additional processing. For example, break down dimensions, apply segmentation, or  select a different attribution model. This **report-time processing** happens on the fly. In Adobe Analytics, it commonly represents a smaller amount of processing  than what happens at collection-time.

![Adobe Analytics collection-time processing](./assets/aa-processing.png)

In contrast, Customer Journey Analytics (CJA) is designed to require minimal upfront collection-time processing before data being is organized and stored. The underlying architecture of CJA is more designed to work with the stored data at report-time and offers its powerful report-time processing functionality not only in  Workspace but also, even more importantly, through the definition of components in your Data Views. 

![CJA report-time processing](./assets/cja-processing.png)

## Functionality

Custom fields are defined within the Data View UI, and are based on a set of functions applied to available schema fields and/or standard components.

Example use cases are:

-   Define a custom Page Name field that corrects improper collected page name values to correct page name values. 

-   Define a custom Marketing Channel field that determines the proper marketing channel based on one or more conditions (for example URL parameter, page URL, page name).

## Next steps

-   Create a custom field

-   Custom field functions





