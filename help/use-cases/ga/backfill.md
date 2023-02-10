---
title: Ingest Google Analytics historical data into Adobe Experience Platform
description: Explains how to use Customer Journey Analytics (CJA) to ingest your Google Analytics data into Adobe Experience Platform. 
exl-id: 314378c5-b1d7-4c74-a241-786198fa0218
solution: Customer Journey Analytics
feature: Use Cases
---

# Ingest Google Analytics historical data into Adobe Experience Platform

This page focuses on how to ingest your Google Analytics historical data into Adobe Experience Platform as a dataset, allowing you to reference that dataset in a Data View within Customer Journey Analytics. You can combine the steps on this page with [Configuring a live Google Analytics implementation](streaming.md), which generates a recurring dataset. Combine this historical dataset with your current implementation's dataset to get a seamless view of data in Customer Journey Analytics with both current and backfilled data.

## Prerequisites

In order to accomplish these tasks, you need the following access and permissions:

* Access to Adobe Experience Platform
* Access to Google Analytics (GA Standard or GA 360)
* [Admin Access](/help/admin/cja-access-control.md) to Customer Journey Analytics

## Set up a BigQuery Export

The data structure in Universal Analytics properties is different from the data structure in Google Analytics 4 properties. Set up a BigQuery Export based on the property type that you want to export data from:

* [Set up a BigQuery Export for a Universal Analytics property](https://support.google.com/analytics/answer/3416092)
* [Set up a BigQuery Export for a Google Analytics 4 property](https://support.google.com/analytics/answer/9823238)

### Additional requirements for Universal Analytics properties

>[!NOTE]
>
>This section only applies to Universal Analytics properties. If you are exporting from a GA4 property, you can proceed to [Export data to Google Cloud Platform](#export-gcp).

Universal Analytics properties store each record in their data as a user's session instead of individual events. A SQL query to transform the Universal Analytics data into a format compatible with Adobe Experience Platform is required. Apply the `UNNEST` function to the `hits` field in the GA schema, and save it as a BigQuery table.

>[!VIDEO](https://video.tv.adobe.com/v/332634)

```sql
SELECT
   *,
   timestamp_seconds(`visitStartTime` + hit.time) AS `timestamp` 
FROM
   (
      SELECT
         fullVisitorId,
         visitNumber,
         visitId,
         visitStartTime,
         trafficSource,
         socialEngagementType,
         channelGrouping,
         device,
         geoNetwork,
         hit 
      FROM
         `example_bq_table_*`,
         UNNEST(hits) AS hit 
   )
```

## Export data to Google Cloud Platform {#export-gcp}

In Google Cloud Platform, navigate to **Export > Export to GCS**. Once the data is in Google Cloud Storage, it is ready to be pulled into Adobe Experience Platform.

## Import the data from Google Cloud Storage into Experience Platform

1. In Adobe Experience Platform, select **[!UICONTROL Sources]** on the left.
1. Under the Catalog, locate **[!UICONTROL Google Cloud Storage]** option. Click **[!UICONTROL Add data]**.

>[!VIDEO](https://video.tv.adobe.com/v/332676)

>[!TIP]
>
>If you plan to import both historical and live streaming Google Analytics data, make sure that you use the same schema for both datasets. You can merge the datasets in a CJA using a [Combined dataset](/help/connections/combined-dataset.md).

You can map the GA event data into an existing dataset that you created previously, or create a dataset, using whichever XDM schema you choose. Once you have selected the schema, the Experience Platform applies machine learning to automatically pre-map each of the fields in the Google Analytics data to your [XDM schema](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html#ui).

![Schema map](../assets/schema-map.png)

Once you are finished mapping the fields into your XDM schema, you can schedule this import on a recurring basis and apply error validation during the ingestion process. This validation ensures that there aren't any issues with the data you have imported.

## Required XDM fields

Certain XDM fields in Platform require the correct format in order for data to be correctly processed.

* **`timestamp`**: Create a special calculated field in the Experience Platform schema UI. Click **[!UICONTROL Add calculated field]** and wrap the `timestamp` string in a `date` function:

   `date(timestamp, "yyyy-MM-dd HH:mm:ssZ")`

   Save the calculated field to the timestamp data structure in the schema:

   ![Timestamp](../assets/timestamp.png)

* **`_id`**: This field must have a value in it - CJA does not care what the value is. You can add a "1" to the field:

   ![ID](../assets/_id.png)

## Next steps

* If you have current data that you want to stream into Adobe Experience Platform, see [Set up streaming for Google Analytics data](streaming.md).
* If you want to begin reporting on backfilled data, see [Create a connection](/help/connections/create-connection.md).
