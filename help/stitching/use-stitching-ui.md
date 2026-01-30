---
title: Use stitching
description: How to use stitching
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: 9a1689d9-c1b7-42fe-9682-499e49843f76
---
# Use stitching

You can enable stitching on one or more event datasets you have configured as part of your connection. The Customer Journey Analytics package that you have licensed determines the number of event datasets you can enable for stitching .

You can enable stitching as part of the [dataset settings](/help/connections/create-connection.md#dataset-settings) for an event dataset when you [create a connection](/help/connections/create-connection.md) or when you [edit a connection](/help/connections/manage-connections.md#edit-a-connection).

## Prerequisites

To enable stitching on an event dataset within the Connections UI: 

* The schema on which the dataset is based should have:

  * multiple fields that are configured as an identity, and which allows you to select different values for a persistent ID and a person ID.
  * at least one field that is marked as primary identity with an associated namespace in case you want to use Identity Map and the primary identity namespace for persistent ID or person ID.

* If you want to use graph-based stitching and you anticipate the event dataset to contribute to the Identity Graph (as the dataset contains relevant person IDs next to persistent IDs), you should [enable the dataset for the Identity service](/help/stitching/faq.md#enable-a-dataset-for-the-identity-service).

## Preflight checks

If you meet the prerequisites, you might want to perform some preflight checks on the data in the event dataset before you enable identity stitching:

* Ensure that identities are marked properly in the schema for the event dataset. [See Identity namespace overview](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/namespaces).
* Verify identity coverage for both persistent ID and person ID:
  * Persistent ID: Query 7 days of data where your persistent ID field is not null and divide by a query of 7 days of data for all events in your dataset. This percentage should be above 95%.

    Example of a query you could use for verification:

    ```sql
    SELECT
      COUNT(*) AS total_events,
      COUNT({PERSISTENT_ID_FIELD}) AS events_with_persistentid,
      ROUND(COUNT({PERSISTENT_ID_FIELD}) / COUNT(*), 2) AS percent_with_persistentid_not_null
    FROM 
      {DATASET_TABLE_NAME}
    WHERE
      TO_TIMESTAMP(timestamp, '{FORMAT_STRING}') >= TIMESTAMP '{START_DATE}'
      AND TO_TIMESTAMP(timestamp, 'FORMAT_STRING') < TIMESTAMP '{END_DATE}';
    ```

    Where:

    * `{PERSISTENT_ID_FIELD}` is the field for the persistent ID. For example: `identityMap.ecid[0]`.
    * `{DATASET_TABLE_NAME}` is the table name for the event dataset.
    * `{FORMAT_STRING}` is the format string for the timestamp field. For example: `MM/DD/YY HH12:MI AM`.
    * `{START_DATE} `is the start date. For example: `2024-01-01 00:00:00`.
    * `{END_DATE}` is the end date in standard format. For example: `2024-01-08 00:00:00`.
  

  * Person ID - Query 7 days of data where your person ID field is not null and divide by a query of 7 days of data for all events in your dataset. This percentage should be above 5%.

     Example of a query you could use for verification:

    ```sql
    SELECT
      COUNT(*) AS total_events,
      COUNT({PERSON_ID_FIELD}) AS events_with_personid,
      ROUND(COUNT({PERSON_ID_FIELD}) / COUNT(*), 2) AS percent_with_personid_not_null
    FROM 
      {DATASET_TABLE_NAME}
    WHERE
      TO_TIMESTAMP(timestamp, '{FORMAT_STRING}') >= TIMESTAMP '{START_DATE}'
      AND TO_TIMESTAMP(timestamp, 'FORMAT_STRING') < TIMESTAMP '{END_DATE}';
    ```

    Where:

    * `{PERSON_ID_FIELD}` is the field for the person ID. For example: `identityMap.crmId[0]`.
    * `{DATASET_TABLE_NAME}` is the table name for the event dataset.
    * `{FORMAT_STRING}` is the format string for the timestamp field. For example: `MM/DD/YY HH12:MI AM`.
    * `{START_DATE}` is the start date. For example: `2024-01-01 00:00:00`.
    * `{END_DATE}` is the end date in standard format. For example: `2024-01-08 00:00:00`.
  


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
   >Ensure that you are entitled to use the identity graph.
   >

   Before that, a **[!UICONTROL Change to identity graph]** dialog is displayed to ensure you have [finished the setup of the identity graph for the dataset](/help/stitching/faq.md#enable-a-dataset-for-the-identity-service) before you use the identity graph for stitching. Select **[!UICONTROL Continue]** to continue.

   * Select a namespace from the **[!UICONTROL Namespace]** drop-down menu.


1. Select a lookback window from the **[!UICONTROL Lookback window]** drop-down menu. The available options are  dependent on the Customer Journey Analytics package that you are entitled to.

Once you save a connection, the stitching process for datasets that are enabled for stitching kicks when the ingestion of data for these datasets starts.

>[!CAUTION]
>
>For datasets that are enabled for stitching in the Connections interface, the backfill status is immediately and incorrectly reported as ![Status green](/help/assets/icons/StatusGreen.svg)&nbsp;**[!UICONTROL _x_ backfills completed]** for the number of backfills completed. Use other ways to verify whether data from the stitched dataset is backfilled.
>


## Limitations

On top of the [field-based stitching limitations](/help/stitching/fbs.md#limitations) and [graph-based stitching limitations](/help/stitching/gbs.md#limitations), the following limitations apply when you enable stitching in the Connections interface:

* You can only stitch an event dataset once as part of a single connection. You cannot define the same event dataset more than once and use a separate stitching configuration for each instance. If you want to apply different stitching configurations on the same dataset, use a separate connection for each configuration.


## Migration

Stitching enabled in the Connections interface can coexist without any issues with request based stitching. 

For example, you have web-based stitched datasets in the data lake as a result of earlier or current stitching requests. You can add stitched data from a call-center dataset using the Connections interface to combine that data with the web-based data. 

Eventually, Adobe will automatically migrate your request based stitched datasets to the new stitching in connections experience.
