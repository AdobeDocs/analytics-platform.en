---
title: Import call center and web data
description: Learn how to create a dataset that links call center and website data.
---

# Import call center and web data

Customer Journey Analytics provides the valuable and robust capability to combine datasets from different sources into a single Workspace project. Use this guide to understand how your organization can combine website data with call center data.

## Prerequisites

* The most important component to combining these two sets of data is a common identifier between each source of data. Examples include a customer ID, a hashed email, login username, or phone number.
* Access to both Adobe Experience Platform and Customer Journey Analytics
* If your dataset includes logs from an interactive voice response system, Adobe recommends processing the data to only include prompt interactions prior to importing it into Platform.
* If your dataset includes call logs, Adobe recommends including the following columns:
  * The date/time when the call started
  * Call reason
  * Call center ID
  * Call center agent ID
  * Duration of call
  * Outcome of call
  * Cost of call (if available)
  * Any additional call meta data that your organization wants to include

## Import web and call center data into Platform

Import your data into Adobe Experience Platform. See [Create a schema](https://docs.adobe.com/content/help/en/experience-platform/xdm/tutorials/create-schema-ui.html) and [Ingest data](https://docs.adobe.com/content/help/en/experience-platform/ingestion/home.html) in the Adobe Experience Platform documentation.

When importing data into Platform, following these tips can help increase insight in resulting reports:

* Make sure that the identifier used to link call center and web data together are similarly formatted.
* Include the data source in each dataset. For example, include a `data_source` column in each schema, and set the value of every event to `"Web"` or `"Call center"`, respectively. <!--mapper-->

## Stitch the person ID's together

CJA requires a common identifier to generate a [combined dataset](../connections/combined-dataset.md).

* If your datasets already have a common identifier on every event across both datasets, you can skip this step and proceed to create a connection.
* If either of your datasets have a common identifier on only some events, you can stitch data together using Cross-Channel Analytics. See [Cross-Channel Analytics overview](/help/connections/cca/overview.md) for steps to enable CCA for these two datasets.

## Create a connection in CJA

[Create a connection](/help/connections/create-connection.md) in CJA.

* If CCA is used, a new stitched dataset is available for you to use. Use the newly created stitched ID field as the person ID.
* Otherwise, you can select both original web and call center datasets for use in the connection.

## Create a data view

After creating a connection, you can [Create a data view](/help/data-views/create-dataview.md) for use in Analysis Workspace. <!-- page dimension last touch, session persistence -->
<!-- create calls metric using call center reason (requires data views 2.0). any column that triggers once per call -->

## Create visualizations

The following visualizations can be used to gain insights from your stitched dataset.

### Dataset overlap

This visualization helps you understand how well CCA stitches data together.

1. Create two filters. The variable used in these two filters is the same variable mentioned above that reflects the source of data of each event. See [Create a filter](/help/components/filters/create-filters.md) for more information.
   * Person container where Dataset ID equals your web data
   * Person container where Dataset ID equals your call center data
2. In Analysis Workspace, drag a [Venn](/help/analysis-workspace/visualizations/venn.md) visualization onto the workspace canvas.
3. Drag the two newly created filters to the **[!UICONTROL Add Filter]** area, and the People metric to the **[!UICONTROL Add Metric]** area.

The resulting Venn visualization shows the number of people in your dataset that contain both web and call center data. The larger the overlap, the more people that were successfully stitched. The areas that don't overlap represent people that reside exclusively in one dataset or the other.

### Attribute call center events to web pages

This freeform table lets you see the top pages that contribute to call center events. First, make sure that the desired dimensions and metrics have the correct attribution model:

1. Drag the dimension that holds your web page names onto a Freeform Table visualization.
1. Replace the metric with the desired call center metric that you want to measure conversion.
1. Click the gear icon near the metric header. Click **[!UICONTROL Use non-default attribution model]**.
1. Set the desired [Attribution model](/help/data-views/configure-dataviews.md#Attribution-model).

The resulting report shows the top metric from call center data. <!-- Complement with donut visualization -->

<!-- ### Flow between web data and call center

call reason as an exit dimension, web page name for previous pages

### Histogram


### Fallout

step 1: all sessions
step 2: purchase step 1
step 3: call

another good one

step 1: all sessions
step 2: 

Orrr we could also use dataset ID

### Site sections that result in a call within 30 minutes

Slide 4

Create a bunch of filters - facets to their business. Filters were used because they didn't have all of these in the same dimension, so they could create everything in this report as a single dimension (really filters)

wanted to understand when someone interacts with a facet, whats the highest percentage of people that abandon that channel to call them. not from volume perspective, but percentage perspective.

use sequential segmentation, but you lose the ability to use attribution IQ

## What to do when you've found insight -->

