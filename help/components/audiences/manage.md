---
title: Manage audiences created in Customer Journey Analytics
description: Learn how to manage audiences in Customer Journey Analytics
---

# Manage audiences created in Customer Journey Analytics

Managing previously created audiences lets you

* **Schedule or de-schedule** automatic audience refresh/update. The maximum expiration on the schedule is 1 year. 
* **Renew an audience refreshing schedule** when it is about to expire. Expiring audiences are treated similarly to expiring scheduled reports - the admin gets an email a month before the schedule expires.
* **View the last time an Audience was updated**
* Gain insight into the **amount of time it took to produce an audience** from Customer Journey Analytics (CJA), and the amount of time it took to have the audience appear in Real-time Customer Profile for activation purposes.
* See whether the audiences in CJA are **being actively used by Real-time Customer Profile** or (ideally) any Experience Platform applications that consume the audiences created by CJA.

## Management UI

screenshot

| UI setting | Definition |
| --- | --- |
| Hide/Show filters | Lets you show or hide the following filters in the left rail: <ul><li>Data view</li><li>Owner</li><li>Refresh frequency</li><li>Tags</li></ul> |
| Title & Description |  |
| Data View | 
| Audience Size |  |
| Owner |  |
| Refresh Frequency |  |
| Tags |  |
| Last Refreshed |  |
| Last Modified |  |

{style="table-layout:auto"}

## View and use CJA audiences in Experience Platform

You can view CJA audiences in Platform by going to [!UICONTROL Segments] > [!UICONTROL Create segments] > [!UICONTROL Audiences] tab > [!UICONTROL CJA Audiences].

![](assets/audiences-aep.png)

If you opt to export this Audience to AEP Data lake, it will appear as a dataset conforming to the XDM Individual Profile Schema Class:

![](assets/aep-datalake.png)

