---
description: Understand how to use alerts to allow for granular control over notifications, and integration with anomaly detection.
title: Alerts Overview
feature: Workspace Basics
role: User, Admin
exl-id: 029be0c8-ec78-4bb7-a6cd-bb303b5ac82a
---
# Alerts overview

Alerts in Customer Journey Analytics allow you to be notified based on changed percentages or specific data points. 

Depending on your Customer Journey Analytics package, you can also use alerts to be triggered based on anomaly thresholds. These alerts (also known as "Intelligent Alerts"), provide granular controls that integrate with [Anomaly Detection](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md), triggering when you need them most.

Alerts let you:

* Preview how often an alert will trigger
* Send alerts by e-mail or SMS with links to auto-generated Analysis Workspace projects
* Create "stacked" alerts that capture multiple metrics in a single alert
* Build alerts based on anomalies (90%, 95%, 99%, 99.75%, and 99.9% thresholds; % change; above/below) (Available only to Customer Journey Analytics customers with a Select, Prime, or Ultimate package)

The following video tutorial provides a basic overview of alerts: [Alerts](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/intelligent-alerts.html) (5:34)

## Understand how alerts differ

The process of using alerts in Customer Journey Analytics is nearly identical to using alerts in Adobe Analytics. However, there are important differences.

For more information, see [Alerts feature comparison: Customer Journey Analytics and Adobe Analytics](/help/components/c-intelligent-alerts/alerts-feature-comparison.md).

## Anomaly lookback for alerts

>[!NOTE]
>
>Using alerts with anomaly detection (also known as _Intelligent Alerts_) is available only to organizations with a Customer Journey Analytics Select, Prime, or Ultimate package.

If an alert uses anomaly detection, the training period varies based on the granularity selected for the alert.

* Monthly granularity: 15 months + same range last year
* Weekly granularity: 15 weeks + same range last year
* Daily granularity: 35 days + same range last year
* Hourly granularity: 336 hours

For more information, see [Statistical techniques used in Anomaly Detection](/help/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md).

## Create alerts

For information about how to create alerts in Customer Journey Analytics, see [Create alerts](/help/components/c-intelligent-alerts/alert-builder.md).

>[!IMPORTANT]
>
>Using timestamped data to create alerts can cause alerts to fire incorrectly. Adobe recommends using non-timestamped data for alerts.

## Manage alerts

You can manage existing alerts in the Alerts manager. You can perform various management tasks on alerts, such as tagging, renaming, deleting, and more.

For more information about how to manage existing alerts in Customer Journey Analytics, see [Manage alerts](/help/components/c-intelligent-alerts/alert-manager.md).
