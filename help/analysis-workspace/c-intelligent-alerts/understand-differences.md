---
description: Learn how Intelligent Alerts differ in Customer Journey Analytics from Adobe Analytics
title: Intelligent Alerts feature comparison Customer Journey Analytics and Adobe Analytics
feature: Alerts
role: User, Admin
---
# Intelligent Alerts feature comparison: Customer Journey Analytics and Adobe Analytics

Using Intelligent Alerts in Customer Journey Analytics is nearly identical to using Intelligent Alerts in Adobe Analytics. However, there are important differences.

The following sections describe key differences:

## Hourly alerts are not available in Customer Journey Analytics

The main visible difference when using Intelligent Alerts in Customer Journey Analytics is that hourly alerts are not available. In Customer Journey Analytics, alerts can be configured for daily, weekly, or monthly. 

This is because of the way data is collected into Adobe Experience Platform before it is made available in Customer Journey Analytics. For more information, see [Data collection times can vary](#data-collection-times-can-vary).

## Data collection times can vary

Because Platform can hold all kinds of data schemas and types, data collection times can vary. 

Unlike Adobe Analytics, data collection for Adobe Experience Platform does not happen sequentially and in realtime. Instead, data collection for the various kinds of data that can be ingested by Platform is complete only after a period of 3 to 9 hours. 

To account for this collection time, a default delay of 9 hours is in place before alerts are sent. This delay makes hourly alerts unpractical. 

You can adjust the default delay of 9 hours to anywhere between 0 and 24 hours, as described in <!--add link -->. However, consider the following when decreasing the delay time:

* **Data availability vs. data completeness**: While some data might be available to report on sooner, data collection is complete only after a period of 3 to 9 hours. For alerts to be accurate, data collection must be complete.

* **Understand how long your data takes to be complete**: Data collection times differ by organization. You can consult your data engineers to understand how long it takes your organization for data collection completeness. 

  If you decrease the default delay time, it's recommended to make it at least an hour longer than the time it takes your organization for data collection completeness. For example, if there is a 3-hour delay before your data collection is complete, then you should set the delay to 4 hours.

  


This means that reporting on data every hour can result in reporting on incomplete data. 

In Adobe Analytics, data is collected in real-time as users interact with a website. Each interaction or 'hit' is timestamped and processed sequentially, meaning in the order they occur on the website. This allows for the possibility of hourly alerts because the data stream is consistent and ordered.

However, in Customer Journey Analytics, the data collection process is different. Customers can send data in any order, not necessarily in real-time or in the sequence of events as they occur. This lack of sequential order in data reporting makes it challenging to provide accurate hourly alerts.

The reason behind not having hourly alerts in Customer Journey Analytics is tied to the potential for error. If there's a delay or mistake in daily data reporting, the impact is limited to that day. However, if hourly reporting is incorrect, the errors would occur much more frequently (every hour), leading to a significant amount of inaccurate alerts. This could lead to confusion and frustration for users, which is why it's avoided.

In summary, the difference in data collection and processing between Adobe Analytics and Customer Journey Analytics results in the latter not supporting hourly alerts. The potential for frequent errors with hourly alerts in Customer Journey Analytics outweighs the benefits.
