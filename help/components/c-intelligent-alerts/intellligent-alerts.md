---
description: The new Intelligent Alerts system allows for more granular control over alerts and integrates anomaly detection with the alert system.
title: Intelligent Alerts overview
feature: Workspace Basics
role: User, Admin
---
# Intelligent Alerts overview

>[!NOTE]
>
>Intelligent Alerts are available to all customers. However, to use Anomaly Detection within Intelligent Alerts, you must have Customer Journey Analytics Select, Prime, or Ultimate.

Intelligent Alerts (or just "alerts") in Customer Journey Analytics allow you to be notified when abnormal events occur in your data. 

You can set alerts to be triggered based on anomaly thresholds, changed percentages, or specific data points. Alerts provide granular controls that integrate with [Anomaly Detection](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md), triggering when you need them most.

Intelligent Alerts let you:

* Build alerts based on anomalies (90%, 95%, 99%, 99.75%, and 99.9% thresholds; % change; above/below)
* Preview how often an alert will trigger
* Send alerts by e-mail or SMS with links to auto-generated Analysis Workspace projects
* Create "stacked" alerts that capture multiple metrics in a single alert

The following video tutorial provides a basic overview of alerts: [Intelligent Alerts](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/intelligent-alerts.html) (5:34)

## Understand how alerts differ in Customer Journey Analytics from Adobe Analytics

The process of using Intelligent Alerts in Customer Journey Analytics is nearly identical to using Intelligent Alerts in Adobe Analytics. However, there are important differences.

For more information, see [Intelligent Alerts feature comparison: Customer Journey Analytics and Adobe Analytics](/help/components/c-intelligent-alerts/alerts-feature-comparison.md).

## Anomaly lookback for alerts

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
>Using timestamped data to create alerts can cause alerts to fire incorrectly. Adobe recommends using non-timestamped data for Intelligent Alerts.

## Manage alerts

You can manage existing alerts in the Alerts manager. You can perform various management tasks on alerts, such as tagging, renaming, deleting, and more.

For more information about how to manage existing alerts in Customer Journey Analytics, see [Manage alerts](/help/components/c-intelligent-alerts/alert-manager.md).
