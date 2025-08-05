---
description: Understand real-time reporting capabilities in Customer Journey Analytics.
title: Real-Time Reporting Overview
feature: Real-time Reporting
hide: yes
hidefromtoc: yes
role: User
badgePremium: label="Beta"
exl-id: 12fbb760-936d-4e30-958f-764febca5ae7
---
# Real-time reporting overview

Real-time reporting in Customer Journey Analytics displays and updates data and visualizations within one or more panels in Analysis Workspace in real time.

{{release-limited-testing}}

{{ultimate-package}}

## Use cases

This section provides an overview of typical valuable and less valuable use cases. And also information when not to consider real-time reporting.

* The most valuable use cases for real-time reporting are around major sales, promotions, or product launches. 
As part of that launch you want to know:

  * How do the sales compare to your last sale?
  * How does this product launch compare to the last product launch?
  * Do your promotions for this important day or event actually work?

* Relevant, but less valuable uses cases for real-time reporting are validation use cases. 
You want to validate, for example:

  * Is the campaign journey you recently launched, actually working?
  * When your new product page went live, are you collecting customer data from the page?
  * Is your live media event going ok?

Do not consider real-time reporting for operations monitoring use cases. For example, to answer the question: is a site actually working?


## Definition

The real-time aspect of real-time reporting for Customer Journey Analytics is defined as data and visualizations that are updated within approximately 5 minutes from the moment the underlying data is ingested through the associated connection.

## Limitations

You should be aware of the following limitation for real-time reporting:

* Real-time reporting only reports on data available on a rolling period of 24 hours. Data that crosses this rolling 24-hour period is not available.
* Attribution, segmentation, calculated metrics, and more only work on the data available within the rolling period of 24 hours.
* Real-time reporting works best on event and session level data and you should be cautious using real-time reporting for person-level data. <!--Need to explain this a bit better --> Since only events from the rolling 24-hour period are available for real-time reports, a person's event history is also limited to this window. Consider the preference for event and session level data when you select dimension, (calculated) metrics. And when you use functionalities like breakdowns, next or previous, and more in your real-time refresh enabled panel.
* You cannot combine stitching with real-time reporting. <!-- Do we need to explain this in more detail, why? --> Real-time reporting is about event and session level data and less relevant for person-based data.
* No heartbeat collected media metrics are available, with the exception of media start and media close metrics. So you can still use real-time reporting to enable a media use case.
* When you use the [download or export options](/help/analysis-workspace/export/download-send.md) to download  a project or export data from a freeform table, consider the following:
  * A downloaded CSV project or exported CSV file contains the real-time data available at the moment of download or export.
  * A downloaded PDF project contains non real-time data, similar to the data shown when real-time refesh is disabled.
