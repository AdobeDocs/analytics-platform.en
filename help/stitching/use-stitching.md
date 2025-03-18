---
title: Use stitching
description: How to use stitching
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: a04c74ab-606e-45a9-a3e4-0d476c8d2426
---
# Use stitching

Once your organization meets all [prerequisites](#prerequisites) and understands common [limitations](#limitations) and stitching method specific ([field-based](#limitations-1) and [graph-based](#limitations-2)) limitations, you can follow these steps to start using stitching in Customer Journey Analytics.

## Select options

The Customer Journey Analytics package you are entitled to determines the available stitching methods, options for the initial backfill duration, lookback window, replay frequency, and maximum number of datasets permitted for stitching. See the [Customer Journey Analytics product description](https://helpx.adobe.com/legal/product-descriptions/customer-journey-analytics.html) for more details. Decide on the available options before requesting support.

| | Customer Journey Analytics<br/>Select | Customer Journey Analytics<br/>Prime | Customer Journey Analytics<br/>Ultimate |
|---|---|---|---|
| Available stitching methods | <li>Field-based stitching</li> | <li>Field-based stitching</li><li>Graph-based stitching</li> | <li>Field-based stitching</li><li>Graph-based stitching</li> | 
| One-time stitching backfill duration | 13 months | 13 months | 25 months | 
| Lookback window and replay frequency |<li>1 day, every day</li><li>up to 7 days, weekly</li> | <li>1 day, every day</li><li>up to 14 days, weekly</li>| <li>1 day, every day</li><li>up to 30 days, weekly</li> | 
| Maximum number of datasets permitted for stitching | 5 | 15 | 50 | 

## Request support 

1. Contact Adobe Customer Support with the following information:

   - A request to enable stitching.
   - The dataset ID for the dataset that you want to rekey.
   - The column name (identity path and namespace) of the persistent ID for the desired dataset (the identifier that appears on every row).
   - For field-based stitching, the column name of the transient ID for the desired dataset (the person identifier, which also acts as a link between datasets in the context of a connection). For graph-based stitching, the identity namespace to use for querying the identity graph.
   - Your preference of lookback window and replay frequency. See your Customer Journey Analytics package for the [options](#options) available.
   - Sandbox name.


2. The Adobe Customer Support works with Adobe engineering to enable stitching upon receiving your request. Once enabled, a new rekeyed dataset that contains a new stitched ID column appears in Adobe Experience Platform. Adobe Customer Support can provide the new dataset's ID.
   
3. When first turned on, Adobe provides a backfill of stitched data. See your Customer Journey Analytics package for the [option](#options) available.
   
4. If you want to use the new stitched dataset in a cross-channel analysis, you need to add the new stitched dataset to a [connection](../connections/overview.md) in Customer Journey Analytics. Then add any other datasets required for cross-channel analysis, and select the correct person ID for each dataset.
   
5. [Create a data view](/help/data-views/create-dataview.md) based on the connection.

<!-- To do: Paragraph on backfill once product and marketing determine the best way forward. -->

Once the data view is set up, you can run your Customer Journey Analytics reporting analysis across channels and devices.

<!-- Uncomment once stitching UI is available (for limited testing)..

### Do It Yourself

|Positive|[!BADGE New Feature]{type=Positive before-title="false"}|

{{release-limited-testing-section}}

Alternatively, you can set up and use stitching through the Customer Journey Analytics user interface:

1. Go to the [Create and manage stitched datasets](stitching-ui.md) and follow steps to rekey your dataset.

2. [Create a connection](/help/connections/create-connection.md) in Customer Journey Analytics using the newly generated dataset and any other datasets that you want to include. Choose the correct person ID for each dataset.

3. [Create a connection](/help/connections/create-connection.md) in Customer Journey Analytics using the newly generated dataset and any other datasets that you want to include. Choose the correct person ID for each dataset.
   
4. [Create a data view](/help/data-views/create-dataview.md) based on the connection.

Once the data view is set up, the cross-channel analysis in Customer Journey Analytics is just like any other analysis in Customer Journey Analytics, except now the data operates across channels and devices.

-->
