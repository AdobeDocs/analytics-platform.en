---
description: Learn how Intelligent Alerts differ in Customer Journey Analytics from Adobe Analytics
title: Intelligent Alerts feature comparison Customer Journey Analytics and Adobe Analytics
feature: Alerts
role: User, Admin
---
# Intelligent Alerts feature comparison: Customer Journey Analytics and Adobe Analytics

The process of using Intelligent Alerts in Customer Journey Analytics is nearly identical to using Intelligent Alerts in Adobe Analytics. However, there are important differences.

The following sections describe the key differences:

## Hourly alerts are not available in Customer Journey Analytics

Hourly alerts are not available in Customer Journey Analytics like they are in Adobe Analytics. In Customer Journey Analytics, alerts can be configured for daily, weekly, or monthly. 

This is because of the various ways that data can be ingested into Adobe Experience Platform, before it is reported on in Customer Journey Analytics. Data completeness and availability cannot be reliably achieved within an hour, making hourly alerts impractical due to the high potential for incomplete data. For more information, see [Data ingestion times vary](#data-ingestion-times-vary-in-customer-journey-analytics).

## Data ingestion times vary in Customer Journey Analytics

The time required before data is complete and available to be reported on in Customer Journey Analytics varies by organization. 

This is due to the following reasons:

* Platform's ability to hold all kinds of data schemas and types

  Unlike Adobe Analytics (which reports only on web data), [many different types of data can be ingested into Adobe Experience Platform](/help/data-ingestion/data-ingestion.md.) to be reported on in Customer Journey Analytics, and not all types of data can be sent sequentially and in real time. 

* A delay in the delivery of batch data to Platform datasets

  While some data might be available to report on sooner, all [batch data is ingested into a Platform dataset](/help/data-ingestion/data-ingestion.md#ingest-and-use-batch-data.) only after a period of 3 to 9 hours. For alerts to be accurate, data ingestion must be complete, with all batch data available in the dataset.

For these reasons, data ingestion for the various kinds of event data that can be ingested is complete only after some delay, typically ranging from 3 to 9 hours past the data event time. For alerts to be accurate, event data for a given event range must be complete, meaning that we are no longer receiving any event data for the specified event range.

To account for this delay in ingestion time, alerts have a default delay of 9 hours before they are sent. 

You can adjust the default delay of 9 hours to anywhere between 0 and 24 hours. However, decreasing the delay below 9 hours can mean that you are reporting on incomplete data, which results in inaccurate alert information. 

For more information about how to adjust the delay, and the factors you should consider when doing so, see <!--add link -->. 

<!-- Starting with "However," the rest of this information should probably go into the actual documentation where we document the option to adjust the delay. --> 

_ - - - - - - -

**Information below will be added into the documentation where we document the option to adjust the delay**

Consider the following when decreasing the delay time:

* **Understand data availability vs. data completeness**: While some data might be available to report on sooner, all [batch data is ingested into a Platform dataset](/help/data-ingestion/data-ingestion.md#ingest-and-use-batch-data.) only after a period of 3 to 9 hours. For alerts to be accurate, data ingestion must be complete, with all batch data available in the dataset.

* **Determine how long it takes for your data to be complete and available in the dataset**: Data ingestion times differ by organization. Make sure that the delay time you choose for alert delivery is the same or less frequent than the time it takes for the batch data to be available in the Platform dataset<!--add link? -->. 

  >[!TIP]
  >
  >The most accurate way of knowing the time required for all batch data to be complete and ingested into the Platform dataset is to consult the data engineers in your organization.
  >
  >Alternatively, you can get a general idea of how long it takes for the batch delivery in your organization to be available in the Platform dataset by creating the following freeform table in Analysis Workspace:
  > 
  >
  >  1. In a freeform table in Analysis Workspace, add an [!UICONTROL **Events**] metric and a [!UICONTROL **Day**] dimension.
  >
  >  1. Break down the [!UICONTROL **Day**] dimension using an [!UICONTROL **Hours**] dimension.
  >
  >     Hours that have no data will show as 0.  

* **Account for errors in your calculations**: If you decrease the default delay time, we recommend configuring the delay for at least an hour longer than the time it takes your organization for data ingestion completeness. For example, if there is a 3-hour delay before your data ingestion is complete, then you should set the delay to 4 hours.

  



