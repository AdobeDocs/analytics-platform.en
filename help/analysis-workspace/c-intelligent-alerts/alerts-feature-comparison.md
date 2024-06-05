---
description: Learn how Intelligent Alerts differ in Customer Journey Analytics from Adobe Analytics
title: Intelligent Alerts feature comparison Customer Journey Analytics and Adobe Analytics
feature: Alerts
role: User, Admin
---
# Intelligent Alerts feature comparison: Customer Journey Analytics and Adobe Analytics

Using Intelligent Alerts in Customer Journey Analytics is nearly identical to using Intelligent Alerts in Adobe Analytics. However, there are important differences.

The following sections describe the key differences:

## Hourly alerts are not available in Customer Journey Analytics

The main visible difference when using Intelligent Alerts in Customer Journey Analytics is that hourly alerts are not available. In Customer Journey Analytics, alerts can be configured for daily, weekly, or monthly. 

This is because of the way data is collected into Adobe Experience Platform before it is made available in Customer Journey Analytics. For more information, see [Data collection times vary](#data-collection-times-vary).

## Data collection times vary in Customer Journey Analytics

The time that is required for data to be collected into Adobe Experience Platform varies by organization. Unlike Adobe Analytics, data collection for Adobe Experience Platform does not happen sequentially and in real time. This is due to the following reasons:

* Platform's ability to hold all kinds of data schemas and types

* A delay in the ETL batch delivery to Platform datasets<!--add link? -->

For these reasons, data collection for the various kinds of data that can be ingested by Platform is complete only after a delay of 3 to 9 hours.

To account for this delay in collection time, alerts have a default delay of 9 hours before they are sent. This delay ensures that data is complete and accurate when the alert is sent. 

This makes hourly alerts unpractical. 

You can adjust the default delay of 9 hours to anywhere between 0 and 24 hours. However, decreasing the delay below 9 hours can mean that you are reporting on incomplete data (because the ETL batch delivery to the dataset might not be complete). This can result in inaccurate alert information. 

For more information about how to adjust the delay, and the factors you should consider when doing so, see <!--add link -->. 

<!-- Starting with "However," the rest of this information should probably go into the actual documentation where we document the option to adjust the delay. --> 

_ - - - - - - -

**Information below will be added into the documentation where we document the option to adjust the delay**

Consider the following when decreasing the delay time:

* **Understand data availability vs. data completeness**: While some data might be available to report on sooner, all batch data is collected into a Platform dataset only after a period of 3 to 9 hours. For alerts to be accurate, data collection must be complete, with all batch data available in the dataset.

* **Determine how long it takes for your data to be complete and available in the dataset**: Data collection times differ by organization. You can consult your data engineers to understand how long it takes your organization before all batch data is complete and collected into the dataset. Make sure that the delay time you choose is the same or less frequent than that of your underlying dataset ETL batch delivery<!--add link? -->. 

  >[!TIP]
  >
  >  Analysts can use the following method to get an idea of how long it takes their organization for data collection to be complete:
  >
  >  1. In a freeform table in Analysis Workspace, add an Events metric and a Day dimension.
  >
  >  1. Break down the Day dimension using an Hours dimension.
  >
  >     Hours that have no data will show as 0.  

* **Account for errors in your calculations**: If you decrease the default delay time, it's recommended to make it at least an hour longer than the time it takes your organization for data collection completeness. For example, if there is a 3-hour delay before your data collection is complete, then you should set the delay to 4 hours.

  



