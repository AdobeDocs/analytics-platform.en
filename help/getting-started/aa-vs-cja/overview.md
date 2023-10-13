---
title: Comparison with Adobe Analytics
description: Overview of how Customer Journey Analytics compares to Adobe Analytics.
solution: Customer Journey Analytics
feature: Basics
---
# Comparison with Adobe Analytics

This section of the documentation explains how to compare and understand the differences between Adobe Customer Journey Analytics and Adobe Analytics. 

The fundamental difference between the two solutions is the breadth of data you (can) consider when building your reports and analysis.

In Customer Journey Analytics, *any* data source can be part of the data you use for reporting and analysis. Adobe Analytics is primarily aimed at online data collected from web sites and mobile apps. Adobe Analytics offers capabilities to import data from other sources but the main purpose of this is to provide more context around the previously mentioned online data.

## Data collection

Customer Journey Analytics relies on data stored in Adobe Experience Platform datasets. You have several options to collect and ingest data from these datasets in Experience Platform. These options are outlined in more detail in the [Data Ingestion overview](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-data-ingestion/data-ingestion.html?lang=en).

Adobe Analytics ultimately collects data within the solution itself. Again, you have several options to collect that data, which are outlined in more detail in the [Adobe Analytics Implementation Guide](https://experienceleague.adobe.com/docs/analytics/implementation/home.html?lang=en).

You can use your Adobe Analytics report suite data in Customer Journey Analytics using the [Analytics source connector](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en). This connector ingests the data collected in Adobe Analytics into Experience Platform. You can then create a connection to this dataset in Customer Journey Analytics. See [Use Adobe Analytics report suite data in Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja.html?lang=en) for more information.


## Data processing

Before you can report on data, you often need to process that data to ensure the data can properly be used for reporting. Data processing can happen at collection time and at reporting time. 

In general, Customer Journey Analytics is designed to work with the collected and stored data in Experience Platform dataset at report time. Customer Journey Analytics offers powerful report-time processing functionality to ensure the data is ready for reporting and analysis. If you must map, transform and validate data before it is ingested in Experience Platform, you can use the [Data Prep](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=en) functionality of Experience Platform.

In Adobe Analytics, most of the processing of data occurs immediately after collecting the data.

See [Compare data processing across Adobe Analytics and Customer Journey Analytics](data-processing-comparisons.md) and [Processing rules, VISTA, and classifications versus Data Prep](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/pr-vista-dataprep.html?lang=en) for more information.


## Terminology

Customer Journey Analytics offers flexibility on how you define dimensions and metrics, enabled by the flexibility that the underlying Experience Data Model (XDM) based schemas provide. For example, where Adobe Analytics uses visitors, visits and hits, Customer Journey Analytics uses persons, sessions, and events as equivalent concepts (you can change the naming as you see fit).

See [Compare terminology for Analytics data passed through the Analytics source connector](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/terminology.html?lang=en) for more information on the differences in terminology.


## Virtual reporting environments and sandboxes

Adobe Analytics has the concept of virtual report suites, which allows you to segment your collected data and control access to that segmented data. 

Customer Journey Analytics has a similar concept, called data views. Data views are containers allowing you to determine how to interpret data from a connection. They offer ultimate flexibility to specify and configure dimensions and metrics in preparation for your reporting and analysis.

Experience Platform offers sandboxes which can be thought of as a container holding data and applications for a given environment. The functionality of a sandbox is unrelated to an Adobe Analytics virtual report suite or Customer Journey Analytics data view. Adobe Analytics itself has no dependency or relation with Experience Platform sandboxes at all. Customer Journey Analytics does support Experience Platform sandboxes, but there are some important considerations. 

See [Virtual report suites, Data views, Adobe Experience Platform sandboxes, and the Analytics source connector](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/vrs-dataview-sandbox-adc.html?lang=en) for more information.


## Identities

Customer Journey Analytics supports the identities that you define as part of the schemas to which the datasets containing your data conform. As such, identities are an Experience Platform foundational concept, which Customer Journey Analytics uses when setting up a [connection](../../connections/overview.md) (by defining the Person ID for each dataset) and when applying [stitching](../../stitching/overview.md) for cross-channel analysis. An important identity used by the Experience Platform SDKs and API is the Experience Cloud ID (ECID).

Adobe Analytics uses a more definitive set of identity fields, like the Adobe Analytics ID (AAID). When using the Analytics source connector, these Adobe Analytics identify fields are given special treatment. See [AAID, ECID, AACUSTOMID, and the Analytics source connector](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aaid-ecid-adc.html?lang=en) for more information.


## Supported features

An overview of Adobe Analytics features and how these features are supported by Customer Journey Analytics can be found at [Customer Journey Analytics feature support](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/cja-aa.html?lang=en).





