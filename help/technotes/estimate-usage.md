---
title: Manage your Customer Journey Analytics usage
description: Explains how to manage your Customer Journey Analytics usage.
role: Admin
feature: Basics
exl-id: 7a5d1173-8d78-4360-a97a-1ab0a60af135

---
# Manage your Customer Journey Analytics usage

>[!TIP]
>
>Use the [**[!UICONTROL Usage]** interface](/help/connections/manage-connections.md#usage) to **view** the usage of ingested and reportable rows across all connections in Customer Journey Analytics.



You can manage your Customer Journey Analytics usage in the [**[!UICONTROL Connections]** interface](/help/connections/create-connection.md). In this interface, you can can define the Customer Journey Analytics data retention as a rolling window in months (1 month, 3 months, 6 months, etc.), at the connection level.

The main benefit is that you store or report only on data that is applicable and useful and delete older data that is no longer useful. It helps you stay under your contract limits and reduces the risk of overage cost.

If you leave the default (unchecked), the retention period will be superseded by the Adobe Experience Platform data retention setting. If you have 25 months' worth of data in Experience Platform, Customer Journey Analytics will get 25 months of data through backfill. If you deleted 10 of those months in Platform, Customer Journey Analytics would retain the remaining 15 months. 

Data retention is based on timestamps and applies to event datasets and summary data datasets only. No rolling data window setting exists for profile or lookup datasets, since there are no applicable timestamps. If your connection includes any profile or lookup datasets, since they are joined with event datasets, the data is retained in Customer Journey Analytics based on your data retention settings on the event dataset timestamps.


>[!MORELIKETHIS]
>
>[View your Customer Journey Analytics usage](/help/connections/manage-connections.md#usage)

