---
description: You can view and analyze data anomalies contextually, within Analysis Workspace.
title: Anomaly Detection overview
uuid: 991fde08-198c-4410-9606-d5a4f3dd8339
---

# Anomaly Detection overview

>[!NOTE] You are viewing the documentation for Analysis Workspace in Customer Journey Analytics. Its feature set differs slightly from [Analysis Workspace in traditional Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html). [Learn more...](/help/getting-started/cja-aa.md)

You can view and analyze data anomalies contextually within Analysis Workspace.

[Anomaly Detection on YouTube](https://www.youtube.com/watch?v=krXyQCjXoeU&index=63&list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS) (4:53)

Anomaly Detection provides a statistical method to determine how a given metric has changed in relation to previous data.

Anomaly Detection allows you to separate "true signals" from "noise" and then identify potential factors that contributed to those signals or anomalies. In other words, it lets you identify which statistical fluctuations matter and which don't. You can then identify the root cause of a true anomaly. Furthermore, you can get reliable metric (KPI) forecasts.

Examples of anomalies you might investigate include:

* Drastic drops in average order value
* Spikes in orders with low revenue
* Spikes or drops in trial registrations
* Drops in landing page views
* Spikes in video buffer events
* Spikes in low video bit-rates

Both Anomaly Detection and [Contribution Analysis](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/virtual-analyst/anomaly-detection/anomaly-detection.html) are core workflows in Analysis Workspace. You can run Contribution Analysis against any daily anomaly and embed the result in your Analysis Workspace project.

>[!IMPORTANT] Contribution Analysis is not yet available in Customer Journey Analytics.

Analysis Workspace's anomaly detection algorithm includes

* Support for hourly, weekly, and monthly granularity, in addition to the existing daily granularity.
* Awareness of seasonality (such as "Black Friday") and holidays.

## Turn off anomaly detection

You can turn off anomaly detection at the column level by going to the column settings and un-checking **[!UICONTROL Anomalies]**.

![](assets/turnoff_anomalies.png)
