---
title: View and manage your Customer Journey Analytics usage
description: Shows two methods of estimating usage and one method of managing it.
role: Admin
feature: CJA Basics
exl-id: 7a5d1173-8d78-4360-a97a-1ab0a60af135
---
# View and manage your Customer Journey Analytics usage

To view your CJA usage, you can use several methods:

* Add up the event data rows for each connection. See [Estimate connection size](#estimate size) below. This is an easy way to see your event row data, per connection, for a specific timestamp.
* View your usage in three ways, each of which is described in more detail below:
    * Use Analysis Workspace to report on last month's events.
    * Use Report Builder to report on last month's events.
    * Use the CJA API to create an automated report. 

To manage your CJA usage:

* Define a rolling data window.

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

This method allows you to do some deeper analysis of your usage data, as well as the history of your usage.

1. Before you create the project in Workspace, [create a data view](/help/data-views/create-dataview.md) for each of your connections, without any filters applied.

>[!WARNING]
>
>    Do not create a new connection that encompasses all your data just for measuring usage, as that would effectively double your usage. 

1. In Workspace, create new projects based on each of the data views and pull in all events (from the **[!UICONTROL Metrics]** dropdown) leading up to the first Friday of the month, starting with the first day of your current CJA contract.

   ![Events](assets/events-usage.png)

   This will give you a good idea of how your usage is trending month to month.

1. Depending on your needs, you can drill down by dataset, etc. 

## Create a data block in Report Builder {#arb}

In Report Builder, [create one data block](/help/report-builder/create-a-data-block.md) for each data view, then sum them.

## Create an automated report in the CJA API {#api-report}

1. Use the [CJA reporting API](https://developer.adobe.com/cja-apis/docs/api/#tag/Reporting-API) to run a report on all your event data, **for every connection**. Set this up so that the report runs 

   * on every first Friday of every month.
   * going back to the first day of your current CJA contract.

   This will give you a good idea of how your usage is trending month to month. It will give you the total number of rows on all of your CJA connections.

1. Use Excel to further customize this report.

## Manage your usage by defining a rolling data window {#rolling}

To manage your usage, the [connections UI](/help/connections/create-connection.md) lets you define CJA data retention as a rolling window in months (1 month, 3 months, 6 months, etc.), at the connection level.

The main benefit is that you store or report only on data that is applicable and useful and delete older data that is no longer useful. It helps you stay under your contract limits and reduces the risk of overage cost.

If you leave the default (unchecked), the retention period will be superseded by the Adobe Experience Platform data retention setting. If you have 25 months' worth of data in Experience Platform, CJA will get 25 months of data through backfill. If you deleted 10 of those months in Platform, CJA would retain the remaining 15 months. 

Data retention is based on event dataset timestamps and applies to event datasets only. No rolling data window setting exists for profile or lookup datasets, since there are no applicable timestamps. If your connection includes any profile or lookup datasets, since they are joined with event datasets, the data is retained in CJA based on your data retention settings on the event dataset timestamps.

