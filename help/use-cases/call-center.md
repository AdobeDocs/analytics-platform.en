---
title: Import call center and web data
description: Learn how to create a dataset that links call center and website data.
---

# Import call center and web data

Customer Journey Analytics provides the valuable and robust capability to combine datasets from different sources into a single Workspace project. One challenge frequently encountered is the ability to reliably match up visitor data that use different identifiers. Use this guide to understand how your organization can stitch data from your website to data that originates from your call center.

## Prerequisites

* The most important component to combining these two sets of data is a common identifier between each source of data. Examples include a customer ID, a hashed email, login username, or phone number.
* Access to both Adobe Experience Platform and Customer Journey Analytics
* Adobe recommends performing some basic data cleansing on your call center data prior to importing it into Platform.
* Recommended call center columns include:
  * The date/time when the call started
  * Call reason
  * Call center ID
  * Call center agent ID
  * Duration of call
  * Outcome of call
  * Cost of call (if available)

## Import web and call center data into Platform

Begin importing data into Adobe Experience Platform. See [Create a schema](https://docs.adobe.com/content/help/en/experience-platform/xdm/tutorials/create-schema-ui.html) and [Ingest data](https://docs.adobe.com/content/help/en/experience-platform/ingestion/home.html) in the Adobe Experience Platform documentation.

When importing data into Platform, following these tips can help increase insight in resulting reports:

* Make sure that the transient ID's (the identifier used to link call center and web data together) are similarly formatted.
* Include the data source in each dataset. For example, include a `data_source` column in each schema, and set the value of every event to `"Web"` or `"Call center"`, respectively.

## Stitch the person ID's together

Once you have successfully imported your web and call center data into Platform, you can stitch the identifiers together using Cross-channel Analytics. See [Cross-channel Analytics overview](/help/connections/cca/overview.md) for steps to enable CCA for these two datasets.

## Create a connection in CJA

If CCA is set up correctly, a new stitched dataset is available for you to use. [Create a connection](/help/connections/create-connection.md) using this stitched dataset.

## Create a data view

After creating a connection, you can [Create a data view](/help/data-views/create-dataview.md) for use in Analysis Workspace.

## Create visualizations

The following visualizations can be used to gain insights from your stitched dataset.

### Dataset overlap

This visualization helps you understand how well CCA stitches data together.

1. Create two filters. The variable used in these two filters is the same variable mentioned above that reflects the source of data of each event. See [Create a filter](/help/components/filters/create-filters.md) for more information.
   * Person container where `data_source` equals `"Web"`
   * Person container where `data_source` equals `"Call center"`
2. In Analysis Workspace, drag a [Venn](/help/analysis-workspace/visualizations/venn.md) visualization onto the workspace canvas.
3. Drag the two newly created filters to the **[!UICONTROL Add Filter]** area, and the People metric to the **[!UICONTROL Add Metric]** area.

The resulting Venn visualization shows the number of people in your dataset that contain both web and call center data. The larger the overlap, the more people that were successfully stitched. The areas that don't overlap represent people that reside exclusively in one dataset or the other.

### Attribute call center events to web pages

This freeform table lets you see the top pages that contribute to call center events. First, make sure that the desired dimensions and metrics have the correct attribution model:

1. Go to **[!UICONTROL Data Views]** and click the desired data view to edit it.
2. Click **[!UICONTROL Continue]** to navigate to component settings.
3. Drag the dimension that holds your web page names from available dimensions on the left to the components added area on the right. Alternatively, you can locate the page dimension that already exists under components added if you want to edit its attribution.
   >[!NOTE]
   >
   >If you edit an existing dimension's attribution, all reports that rely on that dimension are changed to reflect the updated attribution model.
4. Once you have the dimension selected, click **[!UICONTROL Use custom attribution model]**. 

4. Drag the `page` dimension onto a Freeform Table visualization.
5. 


6. import web data
7. import call center data
8. see how many visits are in both datasets (how do you determine when they're in both datasets?)
9.  attribute pages to calls when they happen in the same visit
10. use target (AB testing) to test new versions of these pages so they reduce calls (using an eVar to determine A/B?)
11. filter by specific call reason using workspace dropdowns
12. visualize flow of pages > call reason 


talk with trevor about including an out-of-the-box dimension that includes the data set the hit originated from





1. submit request for loan
2. goes into salesforce
3. buncha backend events, did loan officer review it, did they approve, did the user accept, etc.
4. create fallout to see where loans that make it through the whole process, and where it broke down
