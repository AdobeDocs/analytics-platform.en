---
title: Estimate and manage your CJA usage
description: 
role: Admin
feature: CJA Basics
---

# Estimate and manage your CJA usage

To understand your CJA usage, you can use 2 methods:

* Add up the event data for each connection (see **Estimate connection size** below)
* Use Analysis Workspace to...

To manage your CJA usage:

* Use the CJA API 

## Estimate connection size {#estimate-size}

You may need to know how many rows of event data you currently have in [!UICONTROL Customer Journey Analytics]. To get an accurate account of your organization's event data records (data rows) usage, do the following **for each of the connections created by your organization**. 

>[!NOTE]
>
>Do this on the first Friday of every month, since Adobe runs your latest usage report on that day.  

1. In [!UICONTROL Customer Journey Analytics], click the **[!UICONTROL Connections]** tab. 

    You can now see a list of all your current connections.

1. Click each connection name to get to the Connections Manager.

1. Add up the **[!UICONTROL Records of event data available]** for all connections created. (Depending on the size of your connection, the number may take awhile to appear.)

    ![event data](assets/event-data.png)

1. Once you have a sum of all event data rows, look up the "Rows of Data" entitlement in the Customer Journey Analytics contract that your company signed with Adobe. 

    This gives you the maximum number of rows of data authorized in the Sales Order. If the number of rows of data that resulted from Step 3 is larger than this number, you are incurring an overage.

1. To remedy this situation, you have several options:

    * Change your [data retention settings](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/manage-connections.html#set-rolling-window-for-connection-data-retention).
    * [Delete any unused connections](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html#implications-of-deleting-data-components).
    * [Delete a dataset in AEP](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html#implications-of-deleting-data-components).
    * Contact your Adobe Account Manager to license additional capacity. 
