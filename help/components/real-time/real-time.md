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

  * Is the campaign journey you recently launched actually working?
  * When your new product page went live, are you collecting customer data from the page?
  * Is your live media event going ok?

Do not consider real-time reporting for operations monitoring use cases. For example, to answer the question whether a site is properly working. Since the [real-time refresh toggle](use-real-time.md) automatically disables after 30 minutes and the real-time report stops refreshing, you should not use a real-time report as a reliable source for these use cases.

## How it works

Real-time reporting uses a consolidated dataset that is completely separate from the [consolidated (combined) dataset](/help/connections/combined-dataset.md) used for standard reporting. You use the [Real-time refresh toggle](use-real-time.md) to switch between: 

* Real-time reporting on a consolidated dataset that contains up to 24 hours of rolling data.
* Standard reporting on the consolidated dataset that contains up to 13 months of rolling data (or longer in case you have licensed the Extended Data Capacity Add-on).

![Real-time reporting](assets/real-time-reporting-latencies.svg){zoomable="yes"}

### Latencies

How you collect data determines the latency of real-time reporting in Customer Journey Analytics. The illustration above and the table below show approximate latencies for various data collection scenarios when using real-time and (for comparison) standard reporting.

| | Data collection | Real-time reporting latency <br/>(approx. less than) | Standard reporting latency <br/>(approx. less than) |
|:---:|---|--:|--:|
| 1 | Edge Network SDK / APIs into the Edge Network | 7 minutes | 95 minutes | 
| 2 | Streaming connectors |  17 minutes |  105 minutes |
| 3 | Adobe Analytics source connector | 17 minutes |  105 minutes |
| 4 | Other source connectors into the source connectors (including batch data) |  25 hours | 25 hours |


## Limitations

Be aware of the following limitation for real-time reporting:

* Real-time reporting only reports on data available on a rolling period of 24 hours. Data that is more than   24-hour old is not available for real-time reporting. Once the [real-time refresh](use-real-time.md) for a report is disabled or automatically turned off, all relevant data is available once more from the [consolidated dataset](/help/connections/combined-dataset.md) typically used for reporting in Customer Journey Analytics.
* Attribution, segmentation, calculated metrics, and more only work on the data available within the rolling period of 24 hours. For example, a *Repeat visitors* segment includes very few people in a real-time report because the report only includes people who visited multiple times in the last 24 hours. A similar limitation applies when you create a real-time report on people who previously clicked on a campaign that is no longer active.
* Real-time reporting works best on event and session level data and you should be cautious using real-time reporting for person-level data. Since only events from the rolling 24-hour period are available for real-time reports, a person's event history is also limited to this window. Consider the preference for event and session level data when you select a dimension and (calculated) metrics. And when you use functionalities like breakdowns, next or previous, and more in your real-time refresh enabled panel.
* You cannot combine stitching with real-time reporting. Real-time reporting is about event and session level data and is less relevant for person-based data.
* No heartbeat collected media metrics are available, except media start and media close metrics. So, you can still use real-time reporting to enable a media use case.
* When you use the [download or export options](/help/analysis-workspace/export/download-send.md) to download  a project or export data from a freeform table, consider the following:
  * A downloaded CSV project or exported CSV file contains the real-time data available at the moment of download or export.
  * A downloaded PDF project contains non real-time data, similar to the data that is shown when real-time refresh is disabled.
