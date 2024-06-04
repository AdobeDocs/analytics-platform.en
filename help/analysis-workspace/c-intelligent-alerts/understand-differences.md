---
description: Learn how Intelligent Alerts differ in Customer Journey Analytics from Adobe Analytics
title: Compare Intelligent Alerts in Customer Journey Analytics and Adobe Analytics
feature: Alerts
role: User, Admin
---
# Intelligent Alert feature comparison: Customer Journey Analytics and Adobe Analytics

Using Intelligent Alerts in Customer Journey Analytics is nearly identical to using Intelligent Alerts in Adobe Analytics. 

The following sections describe any differences:

## Hourly alerts not supported in Customer Journey Analytics

The main visible difference when using Intelligent Alerts in Customer Journey Analytics is that hourly alerts are not supported. This is because data collection in Customer Journey Analytics is not sequential, like it is in Adobe Analytics. This means that reporting on data every hour can result in reporting on incomplete data. 

In Adobe Analytics, data is collected in real-time as users interact with a website. Each interaction or 'hit' is timestamped and processed sequentially, meaning in the order they occur on the website. This allows for the possibility of hourly alerts because the data stream is consistent and ordered.

However, in Customer Journey Analytics, the data collection process is different. Customers can send data in any order, not necessarily in real-time or in the sequence of events as they occur. This lack of sequential order in data reporting makes it challenging to provide accurate hourly alerts.

The reason behind not having hourly alerts in Customer Journey Analytics is tied to the potential for error. If there's a delay or mistake in daily data reporting, the impact is limited to that day. However, if hourly reporting is incorrect, the errors would occur much more frequently (every hour), leading to a significant amount of inaccurate alerts. This could lead to confusion and frustration for users, which is why it's avoided.

In summary, the difference in data collection and processing between Adobe Analytics and Customer Journey Analytics results in the latter not supporting hourly alerts. The potential for frequent errors with hourly alerts in Customer Journey Analytics outweighs the benefits.
