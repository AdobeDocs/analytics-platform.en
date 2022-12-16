---
title: Estimate and manage your CJA usage
description: Shows two methods of estimating usage and one method of managing it.
role: Admin
feature: CJA Basics
exl-id: 7a5d1173-8d78-4360-a97a-1ab0a60af135
---
# Estimate and manage your CJA usage

To understand your CJA usage, you can use 2 methods:

* Add up the event data rows for each connection. (See **Estimate connection size** below)
* Use Analysis Workspace to report on last month's events. (See **Create a Workspace project using all your event data** below.)

To manage your CJA usage:

* Use the CJA API. (See **Create a report in the CJA API** below.)

## Estimate connection size {#estimate-size}

You may need to know how many rows of event data you currently have in [!UICONTROL Customer Journey Analytics]. To get an accurate account of your organization's event data records (data rows) usage, do the following **for each of the connections created by your organization**. 

>[!NOTE]
>
>Do this on the first Friday of every month, since Adobe runs your latest usage report on that day.  

1. In [!UICONTROL Customer Journey Analytics], click the **[!UICONTROL Connections]** tab. 

    You can now see a list of all your current connections.

1. Click each connection name to get to the Connections Manager.

1. Add up the **[!UICONTROL Records of event data available]** for every connection your organization has created. (Depending on the size of your connection, the number may take awhile to appear.)

    ![event data](assets/event-data.png)

   >[!CAUTION]
   >
   >   This count applies to event data only, not to profile or lookup data. If you have profile and lookup data, the count will be slightly higher. However, there is currently no way to report on profile and lookup data usage in the user interface. This functionality is slated for 2023.

1. Once you have a sum of all event data rows, look up the "Rows of Data" entitlement in the Customer Journey Analytics contract that your company signed with Adobe. 

    This gives you the maximum number of rows of data authorized in the Sales Order. If the number of rows of data that resulted from Step 3 is larger than this number, you are incurring an overage.

1. To remedy this situation, you have several options:

    * Change your [data retention settings](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/manage-connections.html#set-rolling-window-for-connection-data-retention).
    * [Delete any unused connections](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html#implications-of-deleting-data-components).
    * [Delete a dataset in AEP](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html#implications-of-deleting-data-components).
    * Contact your Adobe Account Manager to license additional capacity. 

## Create a Workspace project using all your event data {#workspace-event-data}

1. Before you create the project in Workspace, [create a data view](/help/data-views/create-dataview.md) that pulls in data from ALL your connections and has no filters applied. In other words, it includes all your data.

1. In Workspace, create a new project and pull in all events (from the **[!UICONTROL Metrics]** dropdown) for the previous month.

   ![Events](assets/events-usage.png)

1. do this

## Create a report in the CJA API {#api-report}

Use the [CJA reporting API](https://developer.adobe.com/cja-apis/docs/api/#tag/Reporting-API) to run a report on all your event data.
