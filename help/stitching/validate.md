---
title: Validate Identity Stitching In Customer Journey Analytics
description: Learn how to validate identity stitching in Customer Journey Analytics. Measure authentication rates and identification before and after stitching.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: b9b73926-6502-4a48-ba73-c784f80950d3
---
# Validate stitching

The goal of [identity stitching](/help/stitching/overview.md) (or simply, stitching) is to elevate the suitability of an event dataset for cross-channel analysis. This elevation is achieved when all rows of data in the dataset contain the desired highest-order identity that is available. This elevation allows you to:

* Create person-centric reports, while not leaving out anonymous people.
* Connect multiple devices to a single person.
* Connect a person across channels.

This article outlines analysis methods to measure the elevation of one or more newly created stitched datasets and to provide confidence that stitching is delivering these benefits. 

The analysis methods involve [Data view component settings](/help/data-views/component-settings/overview.md) that are typically accessible to admins. The methods also require analysts, who work in an Analysis Workspace project, to create calculated metrics and visualizations. 

While these analysis methods can be used for both field-based stitching and graph-based stitching, some elements may not be present in the dataset, especially in a graph-based stitching scenario. These missing elements can make it difficult to calculate lift directly in Analysis Workspace.

>[!NOTE]
>
>The (validation of) stitching of one or more datasets contributes ultimately to better analysis and insights. However, this article does not discuss the overall value of a Customer Journey Analytics configuration that has all datasets in Experience Platform aligned to the same identity namespace. And that all these datasets are nicely joined together to perform analysis across an entire customer journey. 


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Stitching enablement and validation](https://video.tv.adobe.com/v/3478120?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]



## Stitching in Connections validation

This section details how to validate stitching you have enabled in the Connections interface. 

### Connection recommendations

To validate stitching that you enabled in the Connections interface, select a short and representative period for **[!UICONTROL Dataset backfill]**. For example, one week.

In the example below, you want to stitch the event dataset. You have set up a test connection in which you add the event dataset. For that dataset, you define the **[!UICONTROL ECID]** **[!UICONTROL Namespace]** as the **[!UICONTROL Persistent ID]** and **[!UICONTROL Visitor Hashed Email Address (directMarketing.hashedEmail)]** as the **[!UICONTROL Person ID]**. To validate this stitching, you define a **[!UICONTROL Dataset backfill]** for a small time window (January 24, 2026 - February 10, 2026). You use that small window to validate whether stitching does work as intended.

![Stitching config](/help/stitching/assets/stitching-config.png)

### Data view prerequisites

For the stitching validation, you need to ensure you have all the required dimensions and metrics from your stitched dataset defined in a data view. Create a data view based on the connection you defined earlier. In the **[!UICONTROL Components]** step of the data view configuration, you need to:

* Add **[!UICONTROL Identity Namespace]** from **[!UICONTROL Metrics & Dimensions]** as a dimension to the **[!UICONTROL Dimensions]** list. 

  ![Identity Namespace](/help/stitching/assets/identity-namespace.png)


* Select the **[!UICONTROL Visitor Hashed Email Address Identifier]** that you have defined as the person ID for your events from **[!UICONTROL Schema fields]**. Add the field as a dimension to the **[!UICONTROL Dimensions]** list and as a metric to the **[!UICONTROL Metrics]** list. Modify the **[!UICONTROL Component name]** for the metric to `Email set`.

  ![Email identifier](/help/stitching/assets/email-identifier.png)

Ensure you save the data view.

### Create Workspace project

In Workspace, create a new project and use a freeform table to show the **[!UICONTROL Email set]** metric for the date range you have defined to test your stitching configuration. This freeform table shows the events that do have an email address before stitching.

![Stitching overview freeform table - Email set](/help/stitching/assets/workspace-emailset.png)

To see the events that have an email address set after the stitching process, define a calculated metric `Email stitched namespace`. That calculated metric looks at **[!UICONTROL Events]** that have an **[!UICONTROL Identity Namespace]** equal to the hashed email namespace `email_lc_sha256`.

![Stitching overview - Email stitched namespace calculated metric](/help/stitching/assets/cm-email-stitched-namespace.png)

If you add the new calculated metric **[!UICONTROL Email stitched namespace]** to the freeform table, you see the increase in the number of events that now do have an email address after the stitching process.

![Stitching overview freeform table - Email set and stitched](/help/stitching/assets/workspace-emailset-stitched.png)

You can get further insights when you define two additional calculated metrics.

* **[!UICONTROL Email authentication rate]**. This calculated metric determines the authentication rate before the stitching process. 
 
  ![Email authentication rate calculated metric definition](/help/stitching/assets/cm-email-authentication-rate.png)

* **[!UICONTROL Stitched authentication rate]**. This calculated metric determines the authentication rate after the stitching process.

  ![Stitched authentication rate calculated metric definition](/help/stitching/assets/cm-stitched-authentication-rate.png)

Add these two additional calculated metrics to your freeform table, and you can see the increase in stitched events.

![Stitching overview freeform table - Authenticated](/help/stitching/assets/workspace-authenticated.png)

For more insights, you can add two more calculated metrics (**[!UICONTROL Percent increase]** and **[!UICONTROL Lift]**) to your freeform table to see the impact of your stitching configuration.

![Stitching overview freeform table - Authenticated Lift](/help/stitching/assets/workspace-authenticated-lift.png)



## Request stitching validation

This section details how to validate stitching that you have requested from Adobe. This method is deprecated, but you might still have datasets that were stitched using this method.

### Data view prerequisites

For the stitching validation measurement plan, you need to ensure you have all the required dimensions and metrics from your stitched dataset defined in a data view. Verify that both `stitchedID.id` and `stitchedID.namespace.code` fields are added as dimensions. While the stitched dataset is an exact copy of the original dataset, the stitching process adds these two new columns to the dataset:

* Use `stitchedID.namespace.code` to define a **[!UICONTROL Stitched Namespace]** dimension. This dimension contains the namespace of the identity that the row was elevated to, for example `Email` or `Phone`. Or the namespace that the stitching process falls back to, such as `ECID`. 
  ![Stitched namespace dimension](/help/stitching/assets/stitchednamespace-dimension.png)

* Use `stitchedID.id` to define a **[!UICONTROL Stitched ID value]** dimension. This dimension contains the raw value of the identity. For example: hashed email, hashed phone, ECID. This value is used with **[!UICONTROL Stitched Namespace]**.
  ![Stitched ID dimension](/help/stitching/assets/stitchedid-dimension.png)


Furthermore, you need to add two stitching metrics that are based on the presence of values in a dimension.

1. Use the field that contains the person ID from the stitched dataset to configure a metric that defines whether a person ID is set. Add this person ID even if you are using graph-based stitching as the person ID helps to establish a baseline. In case the person ID is not contained within the dataset, your baseline is 0%. 
   
   In the example below, `personalEmail.address` serves as the identity and is used to create the **[!UICONTROL _Email set]** metric.
   ![Email set metric](/help/stitching/assets/emailset-metric.png)

1. Use the `stitchedID.namespace.code` field to create an **[!UICONTROL Email stitched namespace]** metric. Ensure you specify [Include Exclude values in component settings](/help/data-views/component-settings/include-exclude-values.md), so you only consider values of the namespace you are trying to elevate rows of data to. 
   1. Select **[!UICONTROL Set include/exclude values]**.
   1. Select **[!UICONTROL If all criteria are met]** as the **[!UICONTROL Match]**.
   1. Specify **[!UICONTROL Equals]** `email` as the **[!UICONTROL Criteria]** to select events that have been elevated to the Email namespace.

   ![Email stitched namespace metric](/help/stitching/assets/emailstitchednamespace-metric.png)

### Stitched dimensions

With both of these dimensions added to the data view, use [Freeform tables](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) in Analysis Workspace to check the data that each dimension has.
 
In the **[!UICONTROL Stitched Namespace]** dimension table, you typically see two rows for each dataset. One row represents when the stitching process had to use the fallback method (ECID). The other row shows events associated with the desired identity namespace (email).

For the **[!UICONTROL Stitched ID value]** dimension table, you see the raw values that are coming from the events. In this table, you see that values oscillate between the persistent ID and the desired person ID.

![Check stitched dimensions](/help/stitching/assets/check-data-on-stitching.png)


### Device-centric or person-centric reporting

When you create a connection, you have to define what field or identity is used for the person ID. For instance, on a web dataset, if you choose a device ID as the person ID, then you create device-centric reports and lose the ability to join this data with other offline channels. If you select a cross-channel field or identity, for example email, you lose out on any unauthenticated events. To understand this impact, you need to figure out how much of the traffic is unauthenticated and how much of the traffic is authenticated.

1. Create a calculated metric **[!UICONTROL Unauthenticated events over total]**. Define the rule in the rule builder as shown below:
   ![Unauthenticated events over total](/help/stitching/assets/calcmetric-unauthenticatedeventsovertotal.png)

1. Create a calculated metric **[!UICONTROL Email authentication rate]**, based on the **[!UICONTROL _Email set]** metric that you defined earlier. Define the rule in the rule builder as shown below:
   ![Email authentication rate](/help/stitching/assets/calcmetric-emailauthenticationrate.png)

1. Use the **[!UICONTROL Unauthenticated events over total]** calculated metric, together with the **[!UICONTROL Email authentication rate]** calculated metric, to create a [Donut](/help/analysis-workspace/visualizations/donut.md) visualization. The visualization shows the number of events in the dataset that are unauthenticated and authenticated.

   ![Identification details](/help/stitching/assets/identification-details.png)



### Stitching identification rates

You want to measure the identification performance before and after stitching. To do so, create three additional calculated metrics:

1. A **[!UICONTROL Stitched authentication rate]** calculated metric that calculates the number of events where the stitched namespace is set to the desired identity over the total number of events. When you set up the data view, you created an **[!UICONTROL Email stitched namespace]** metric that included a filter to count only when an event has a namespace set to email. The calculated metric uses this **[!UICONTROL Email stitched namespace]** metric to provide an indication of what percentage of the data has the desired identity.
   ![Stitched authentication rate calculated metric](/help/stitching/assets/calcmetric-stitchedauthenticationrate.png)

1. A **[!UICONTROL Percent increase]** calculated metric that calculates the raw percentage change between the current identification rate and the stitched one.
   ![Percent increase calculated metric](/help/stitching/assets/calcmetric-percentincrease.png)

1. A **[!UICONTROL Lift]** calculated metric that calculates the lift between the current identification rate and the stitched identification rate.
   ![Lift calculated metric](/help/stitching/assets/calcmetric-lift.png)


### Conclusion

If you combine all data in an Analysis Workspace Freeform table, you can start to see the impact and value that stitching provides, inclusive of:

* Current authentication rate: The baseline of the number of events that already had the correct person ID over the total number of events.
* Stitched authentication rate: The new number of events that have the correct person ID over the total number of events.
* Percent increase: The raw percentage increase from the stitched authentication rate minus the baseline current authentication rate.
* Lift: The percent change over the baseline current authentication rate.

![Identification performance](/help/stitching/assets/identification-performance.png)


## Key takeaways

The key takeaways from this article are that stitching validation and analysis helps you:

* Provide a comprehensive custom view of authentication effectiveness by comparing current versus stitched rates.
* Enable clear measurement of the improvement through percentage increases and lift metrics.
* Help identify the true impact of implementing stitching on user authentication.
* Create a standardized way to communicate authentication performance across teams.
* Allow for data-driven decisions about authentication strategy and optimization.

These metrics together give stakeholders a complete picture of how Customer Journey Analytics stitching affects authentication success rates and overall person identification performance.
