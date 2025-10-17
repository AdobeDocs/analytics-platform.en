---
title: Use stitching
description: How to use stitching
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
hide: yes
hidefromtoc: yes
exl-id: 9a1689d9-c1b7-42fe-9682-499e49843f76
badgePremium: label="Beta" type="Informative"
---
# Use stitching

You can enable stitching on one or more event datasets you have configured as part of your connection. The number of event datasets you can enable for stitching is determined by the  Customer Journey Analytics package you have licensed.

{{release-limited-testing}}

You can enable stitching as part of the [dataset settings](/help/connections/create-connection.md#dataset-settings) for an event dataset when you [create a connection](/help/connections/create-connection.md) or when you [edit a connection](/help/connections/manage-connections.md#edit-a-connection).

## Prerequisites

To enable stitching on an event dataset within the Connections UI: 

* The schema on which the dataset is based must have defined:

  * multiple fields that are configured as an identity, and which allows you to select different values for a persistent ID and a person ID.
  * at least one field that is marked as primary identity with an associated namespace in case you want to use Identity Map and the primary identity namespace for persistent ID or person ID.

* The event dataset must be [enabled for the Identity service](/help/stitching/faq.md#enable-a-dataset-for-the-identity-service) in case you want to use the Identity Graph and graph-based stitching.

## Enable identity stitching

>[!NOTE]
>
>If **[!UICONTROL Enable identity stitching]** is not available in the Connections interface, use the [request procedure to enable stitching](/help/stitching/use-stitching.md) on a dataset.



To enable stitching, in the event dataset section of the **[!UICONTROL Add datasets]** or **[!UICONTROL Edit dataset]** dialog: 

![Identity stitching options when you enable identity stitching](assets/identity-stitching-ui.png)

1. Select **[!UICONTROL Enable identity stitching]**.
   
   If you enable stitching for an existing event dataset, the **[!UICONTROL Change Person ID]** dialog displays the implications of a change of the person ID due to the use of stitching. Select **[!UICONTROL Continue]** to continue.

   The **[!UICONTROL Enable identity stitching]** dialog summarizes the consequences of stitching identities. Select **[!UICONTROL Continue]** to continue.

1. Select a persistent ID from the **[!UICONTROL Persistent ID]** drop-down menu.

   If you select **[!UICONTROL Identity Map]** for the persistent ID, you have to select a namespace . You have two options:

   * Enable **[!UICONTROL Use primary identity namespace]** to use the primary identity namespace.
   * Select a namespace from the **[!UICONTROL Namespace]** drop-down menu.

1. Select a person ID from the **[!UICONTROL Person ID]** drop-down menu.

   If you select **[!UICONTROL Identity Map]** for the person ID, you have to select a namespace. You have two options:

   * Enable **[!UICONTROL Use primary identity namespace]** to use the primary identity namespace.
   * Select a namespace from the **[!UICONTROL Namespace]** drop-down menu.
 

   If you select **[!UICONTROL Identity Graph]** for the person ID (to use [graph-based stitching](/help/stitching/gbs.md)), you have to select a namespace. 
   
   >[!NOTE]
   >
   >You must be entitled to use the identity graph.
   >

   Before that, a **[!UICONTROL Change to identity graph]** dialog is displayed to ensure you have [finished the setup of the identity graph for the dataset](/help/stitching/faq.md#enable-a-dataset-for-the-identity-service) before you use the identity graph for stitching. Select **[!UICONTROL Continue]** to continue.

   * Select a namespace from the **[!UICONTROL Namespace]** drop-down menu.


1. Select a lookback window from the **[!UICONTROL Lookback window]** drop-down menu. The available options are  dependent on the Customer Journey Analytics package you are entitled to.

Once you save a connection that contains datasets that are enabled for identity stitching, the stitching process for each dataset begins when the ingestion of data for that dataset starts.

## Limitations

On top of the [field-based sitching limitations](/help/stitching/fbs.md#limitations) and [graph-based stitchin limitations](/help/stitching/gbs.md#limitations), the following limitations apply when you enable stitching in the Connections interface:

* You can only stitch an event dataset once as part of a single connection. You cannot define the same event dataset more than one and use a separate stitching configuration for each instance. If you want to apply different stitching configurations on the same dataset, use a separate connection for each configuration.

