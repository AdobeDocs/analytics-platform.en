---
description: Understand real-time reporting capabilities in Customer Journey Analytics.
title: Real-Time Reporting Overview
feature: Filters, Segments
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
  * How does this product launch compares to the last product launch?
  * Do your promotions for this important day or event actually work?

* Relevant, but less valuable uses cases for real-reporting are validation use cases. 
You want to validate, for example:

  * Is the campaign journey, you recently launched, actually working?
  * Did your new product page went live, and are you collecting customer data from the page?
  * Is your live media event going ok?

Do not consider real-time reporting for operations monitoring use cases. For example, to answer the question whether your site is actually working?


## Definition

The real-time aspect of real-time reporting for Customer Journey Analytics is defined as data and visualizations that are updated within approximately 5 minutes from the moment the underlying data is ingested through the associated connection.

## Limitations

You should be aware of the following limitation for real-time reporting:

* Real-time reporting only reports on data available on a rolling period of 24 hours. Data that crosses this rolling 24-hour period is not available.
* Attribution, segmentation, calculated metrics, and more only works on the data available within the rolling period of 24 hours.
* Real-time reporting works best on event and session level data and you should be cautious to use real-time reporting for person-level data. <!--Need to explain this a bit better --> Consider the preference for event and session level data when you select dimension, (calculated) metrics. And when you use functionalities like breakdowns, nex or previous, and more in your real-time refresh enabled panel.
* You cannot combine stitching with real-time reporting. <!-- Do we need to explain this in more detail, why? --> As mentioned above, real-time reporting is about event and session level data and not so much about person-based data.
* No heartbeat collected media metrics are available, with the exception of media start and media close metrics. So you can still use real-time reporting to enable a media use case.
