---
description: Learn how alerts differ in Customer Journey Analytics from Adobe Analytics
title: Alerts feature comparison Customer Journey Analytics and Adobe Analytics
feature: Workspace Basics
role: User, Admin
---
# Alerts feature comparison: Customer Journey Analytics and Adobe Analytics

The process of using alerts in Customer Journey Analytics is nearly identical to using alerts in Adobe Analytics. However, there are important differences.

The following sections describe the key differences.

## Hourly alerts are not available in Customer Journey Analytics

Hourly alerts are not available in Customer Journey Analytics like they are in Adobe Analytics. In Customer Journey Analytics, alerts can be configured for daily, weekly, or monthly. 

This is because of the various ways that data can be ingested into Adobe Experience Platform, before it is reported on in Customer Journey Analytics. Data completeness and availability cannot be reliably achieved within an hour, making hourly alerts impractical due to the high potential for incomplete data. For more information, see [Data ingestion times vary](#data-ingestion-times-vary-in-customer-journey-analytics).

## Data ingestion times vary in Customer Journey Analytics

The time required before data is complete and available to be reported on in Customer Journey Analytics varies by organization. 

This is due to the following reasons:

* Platform's ability to hold all kinds of data schemas and types

  Unlike Adobe Analytics (which reports only on web data), [many different types of data can be ingested into Adobe Experience Platform](/help/data-ingestion/data-ingestion.md) to be reported on in Customer Journey Analytics, and not all types of data can be sent sequentially and in real time. 

* A delay in the delivery of batch data to Platform datasets

  While some data might be available to report on sooner, all [batch data is ingested into a Platform dataset](/help/data-ingestion/data-ingestion.md#ingest-and-use-batch-data.), typically ranging from 3 to 9 hours past the data event time. For alerts to be accurate, data ingestion must be complete, with all batch data available in the dataset. <!--3 to 9 hours is a sweet spot, what we are suggesting.  -->

For these reasons, data ingestion for the various kinds of event data that can be ingested is complete only after some delay, typically ranging from 3 to 9 hours past the data event time. For alerts to be accurate, event data for a given event range must be complete, meaning that Adobe is no longer receiving any event data for the specified event range.

To account for this delay in ingestion time, alerts have a default delay of 9 hours before they are sent. 

You can adjust the default delay of 9 hours to anywhere between 0 and 24 hours. However, decreasing the delay below 9 hours can mean that you are reporting on incomplete data, which results in inaccurate alert information. 

For more information about how to adjust the delay, and the factors you should consider when doing so, see [Create alerts](/help/components/c-intelligent-alerts/alert-builder.md). 

<!-- Starting with "However," the rest of this information should probably go into the actual documentation where we document the option to adjust the delay. --> 

## The option to create an alert from Analysis Workspace is not available

In Analysis Workspace in Adobe Analytics, you can create alerts from Analysis Workspace in any of the ways described below. In Customer Journey Analytics, the options to create alerts from Analysis Workspace are not yet available. Instead, access the Alert Builder, as described in [Create alerts](/help/components/c-intelligent-alerts/alert-builder.md).

In Adobe Analytics, the following options are available:

* Select one or more line items in a freeform table, then right-click and select **[!UICONTROL Create alert from selection]**.

  This instantly pre-populates the alert builder to create an alert with the correct metrics and filters.

* Open a project in Analysis Workspace, then select **[!UICONTROL Components]** > **[!UICONTROL Create alert]**.
   
* Open a project in Analysis Workspace, then use the following shortcut:

  `ctrl (or cmd) + shift + a` 


  



