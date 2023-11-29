---
description: Learn about data anomaly detection in Analysis Workspace.
title: How Anomaly Detection works
feature: Anomaly Detection
exl-id: f706cdb9-bc80-42b9-9450-4f68bdb3fd85
---
# Anomaly Detection overview

You can view and analyze data anomalies contextually within Analysis Workspace.

[Anomaly Detection video tutorial](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/anomaly-detection-in-analysis-workspace.html) (4:53)

Anomaly Detection provides a statistical method to determine how a given metric has changed in relation to previous data.

Anomaly Detection allows you to separate "true signals" from "noise" and then identify potential factors that contributed to those signals or anomalies. In other words, it lets you identify which statistical fluctuations matter and which don't. You can then identify the root cause of a true anomaly. Furthermore, you can get reliable metric (KPI) forecasts.

Examples of anomalies you might investigate include:

* Drastic drops in average order value
* Spikes in orders with low revenue
* Spikes or drops in trial registrations
* Drops in landing page views
* Spikes in video buffer events
* Spikes in low video bit-rates

Analysis Workspace's anomaly detection algorithm includes

* Support for hourly, weekly, and monthly granularity, in addition to the existing daily granularity.
* Awareness of seasonality (such as "Black Friday") and holidays.
