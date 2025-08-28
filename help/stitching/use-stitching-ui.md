---
title: Use stitching
description: How to use stitching
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
hide: yes
hidefromtoc: yes
---

# Use stitching

You can enable stitching on one or more event datasets you have configured as part of your connection. The number of event datasets you can enable for stitching is determined by the  Customer Journey Analytics package you have licensed. 

You can enable stitching as part of the [dataset settings](/help/connections/create-connection.md#dataset-settings) for an event dataset when you [create a connection](/help/connections/create-connection.md) or when you [edit a connection](/help/connections/manage-connections.md#edit-a-connection).

To enable stitching, in the event dataset section of the **[!UICONTROL Add datasets]** or **[!UICONTROL Edit dataset]** dialog: 

![Identity stitching options when you enable identity stitching](assets/identity-stitching-ui.png)

1. Select **[!UICONTROL Enable identity stitching]**.
   
   If you enable stitching for an existing event dataset, the **[!UICONTROL Change Person ID]** dialog displays the implications of a change of the Person ID due to the use of stitching. Select **[!UICONTROL Continue]** to continue.

   The **[!UICONTROL Enable identity stitching]** dialog summarizes the consequences of stitching identities. Select **[!UICONTROL Continue]** to continue.

1. Select a persistent ID from the **[!UICONTROL Persistent ID]** drop-down menu.

   If you select **[!UICONTROL Identity Map]** for the persistent ID, you have to select a namespace . You have two options:

   * Enable **[!UICONTROL Use primary identity namespace]** to use the primary identity namespace.
   * Select a namespace from the **[!UICONTROL Namespace]** drop-down menu.

1. Select a person ID from the **[!UICONTROL Person ID]** drop-down menu.

   If you select **[!UICONTROL Identity Map]** for the person ID, you have to select a namespace. You have two options:

   * Enable **[!UICONTROL Use primary identity namespace]** to use the primary identity namespace.
   * Select a namespace from the **[!UICONTROL Namespace]** drop-down menu.

   If you select **[!UICONTROL Identity Graph]** for the person ID, you have to select a namespace. Before that, a **[!UICONTROL Change to identity graph]** dialog is displayed to ensure you have finished the setup of the identity graph before you use the identity graph for stitching. Select **[!UICONTROL Continue]** to continue.

   * Select a namespace from the **[!UICONTROL Namespace]** drop-down menu.


1. Select a lookback window from the **[!UICONTROL Lookback window]** drop-down menu. The options are **[!UICONTROL 1 day]**, **[!UICONTROL 7 days]**, **[!UICONTROL 14 days]**, or **[!UICONTROL 30 days]**.
