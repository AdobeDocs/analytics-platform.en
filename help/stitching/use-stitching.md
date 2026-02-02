---
title: Request stitching
description: How to request stitching
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: a04c74ab-606e-45a9-a3e4-0d476c8d2426
---
# Request stitching


>[!IMPORTANT]
>
>Request stitching through Adobe is no longer required and this method is deprecated. [Enable stitching in the Connections UI](use-stitching-ui.md).
>

Once your organization meets generic [prerequisites](overview.md#prerequisites), understands common [limitations](overview.md#limitations), and also stitching method specific ([field-based](fbs.md) and [graph-based](gbs.md)) prerequisites and limitations, you can follow these steps to request and start using stitching in Customer Journey Analytics.

## Select options

The Customer Journey Analytics package you are entitled to determines the available stitching methods, options for the initial backfill duration, lookback window, replay frequency, and maximum number of datasets permitted for stitching. See the [Customer Journey Analytics product description](https://helpx.adobe.com/legal/product-descriptions/customer-journey-analytics.html) for more details. Decide on the available options before requesting support.

| | Customer Journey Analytics<br/>Select | Customer Journey Analytics<br/>Prime | Customer Journey Analytics<br/>Ultimate |
|---|---|---|---|
| Available stitching methods | Field-based stitching | Field-based stitching<br/>Graph-based stitching | Field-based stitching<br>Graph-based stitching</li> |
| One-time stitching backfill duration | 13 months | 13 months | 25 months |
| Lookback window and replay frequency | 1 day, every day<br/>up to 7 days, weekly | 1 day, every day<br/>up to 14 days, weekly| 1 day, every day<br/>up to 30 days, weekly |
| Maximum number of datasets permitted for stitching | 5 | 15 | 50 |

## Request support 

1. Contact Adobe Customer Support with the following information:

   - A request to enable stitching.
   - The dataset ID for the dataset that you want to rekey.
   - The column name (identity path and namespace) of the persistent ID for the desired dataset (the identifier that appears on every row).
   - If the dataset supports `identityMap`:
     - For field-based stitching, specify the namespace for both the persistent and person IDs.
     - For graph-based stitching, specify the namespace for the persistent ID and the identity namespace to use for querying the identity graph.
   - If the dataset does not support `identityMap`:
     - For field-based stitching, the column name of the person ID for the desired dataset (the person identifier, which also acts as a link between datasets in the context of a connection). 
     - For graph-based stitching, the identity namespace to use for querying the identity graph.
   - Your preference of lookback window and replay frequency. See your Customer Journey Analytics package for the [options](#options) available.
   - Sandbox name.


2. The Adobe Customer Support works with Adobe engineering to enable stitching upon receiving your request. Once enabled, a rekeyed dataset that contains a stitched ID column appears in Adobe Experience Platform. Adobe Customer Support can provide the new dataset's ID.   
3. When first turned on, Adobe provides a backfill of stitched data. See your Customer Journey Analytics package for the [option](#options) available.
   
4. If you want to use the stitched dataset in a cross-channel analysis, you need to add the stitched dataset to a [connection](../connections/overview.md) in Customer Journey Analytics. Then add any other datasets required for cross-channel analysis, and select the correct person ID for each dataset.
   
5. [Create a data view](/help/data-views/create-dataview.md) based on the connection.

<!-- To do: Paragraph on backfill once product and marketing determine the best way forward. -->

Once the data view is set up, you can run your Customer Journey Analytics reporting analysis across channels and devices.

## Limitations

- Apply any change that you make to the source event dataset schema also to the new stitched dataset schema.

- If you remove the source dataset, the stitched dataset stops processing and gets removed by the system.

- Data usage labels are not automatically propagated to the stitched dataset schema. If you have data usage labels applied to the source dataset schema, you need to apply these data usage labels manually to the stitched dataset schema. See [Managing data usage labels in Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/data-governance/labels/overview) for more information.
