---
title: Create and publish audiences
description: Learn how to publish audiences from Customer Journey Analytics
exl-id: 0221f9f1-df65-4bd6-a31d-33d1a1ba0cfe
feature: Audiences
role: User
---
# Create and publish audiences {#create-and-publish-audiences}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_audiences_refreshfrequency"
>title="Refresh frequency"
>abstract="See how often an audience's membership is reevaluated.<br/>One time audiences are evaluated only once."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_audiences_audiencelimit"
>title="Audience limit"
>abstract="Refreshing audiences are limited based on how often they refresh."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="component_audiences_refreshlookbackwindow"
>title="Refresh lookback window"
>abstract="Define the number of lookback days from today that an audience is evaluated from."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="component_audiences_audiencesizelimit"
>title="Audience size limit"
>abstract="Audiences cannot exceed a size of 20 million members."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="component_audiences_namespacesincluded"
>title="Namespaces included"
>abstract="The identities in this audience are comprised of the namespaces below."

<!-- markdownlint-enable MD034 -->




This topic discusses how to create and publish audiences identified in Customer Journey Analytics to [Real-Time Customer Profile](https://experienceleague.adobe.com/en/docs/experience-platform/profile/home) in Adobe Experience Platform for customer targeting and personalization. 

Read this [overview](/help/components/audiences/audiences-overview.md) to familiarize yourself with the concept of Customer Journey Analytics audiences.

## Create and publish an audience {#create}

1. To create and publish an audience, do one of the following:

   | Creation method | Details |
   | --- | --- |
   | From within the **[!UICONTROL Audiences]** interface. | Select **[!UICONTROL Components]** > **[!UICONTROL Audiences]** from the main Customer Journey Analytics menu. The Audiences interface displays. Select **[!UICONTROL Create audience]** creaand the [!UICONTROL Audience builder] opens. |
   | From a visualization in Analysis Workspace | Many visualizations in Analysis Workspace allow you to create an audience using the context menu. For example, you can select **[!UICONTROL Create audience]** from the context menu of an item in a [Freeform table](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) or a node in [Journey canvas](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md).<p>Using this method pre-populates the filter in the Audience builder with the dimension or dimension item that you selected.</p><p>The following visualizations allow you to create an audience using the right-click menu:</p><ul><li>[Cohort table](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md)</li><li>[Fallout](/help/analysis-workspace/visualizations/fallout/fallout-flow.md)</li><li>[Flow](/help/analysis-workspace/visualizations/c-flow/flow.md)</li><li>[Freeform table](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)</li><li>[Journey canvas](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md)</li><li>[Venn](/help/analysis-workspace/visualizations/venn.md)</li></ul><p>**Note:** Audiences cannot include calculated metrics. If you try to create an audience that contains a calculated metric, the calculated metric is not included in the audience definition.</p> |
   | From the filter creation/editing UI | Check the box that says **[!UICONTROL Create an audience from this filter]**. Using this method pre-populates the filter. See [Create filters](/help/components/filters/create-filters.md) for more information. |

   {style="table-layout:auto"}

1. Build the audience using the [Audience builder](#audience-builder).

1. Interpret the data using the [Date preview](#data-preview) panel.

1. Select **[!UICONTROL [!UICONTROL View sample IDs]]** to view a sample of IDs in this audience. In the **[!UICONTROL Sample IDs]** dialog you can use ![Search](/help/assets/icons/Search.svg) [!UICONTROL *Search sample IDs*] to search for sample IDs.

1. Double-check your audience configuration and select **[!UICONTROL Publish]**.
   You receive a confirmation message that the audience is published. Publication takes only a minute or two for this audience to show up in Experience Platform.

1. Select **[!UICONTROL View audience in AEP]** within the same message and you are taken to the [Segment UI](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/ui/overview) in Adobe Experience Platform. See below for more information.

## Audience builder

Configure these settings to define or update your audience.

![Screenshot of create an audience sbowing settings described in the next section.](assets/create-audience.png)

| Setting | Description |
| --- | --- |
| ![Data](/help/assets/icons/Data.svg) | Select a data view to use for the audience creation. |
| **[!UICONTROL Name]** | The name of the audience. For example, `Really Interested in Potential Car Buyers` |
| **[!UICONTROL Tags]** | Any tags that you want to assign to the audience for organizational purposes. You can select one or more pre-existing tags or enter a new one.|
| **[!UICONTROL Description]** | A description of the audience, to differentiate it from others. For example, `Build an audience of really interested potential car buyers` |
| **[!UICONTROL Refresh frequency]** | The frequency at which you want to refresh the audience.<p/>You can choose between <ul><li>**[!UICONTROL One time]** audience: an audience (default) that needs no refreshing. For example, this option could be helpful for specific, one-time campaigns.<br/>You have to specify a **[!UICONTROL One time date range]**. You can use ![Calendar](/help/assets/icons/Calendar.svg) to enter a date range.</li><li>A refreshing audience. You can select from the following options:<ul><li>**[!UICONTROL Every 4 hour]**s: an audience that refreshes every 4 hours.</li><li>**[!UICONTROL Daily]**: an audience that refreshes daily</li><li>**[!UICONTROL Weekly]**: an audience that refreshes weekly.</li><li>**[!UICONTROL Monthly]**: an audience that refreshes monthly</li></ul></li>For refreshing audiences, you have to specify:<ul><li>**[!UICONTROL Refresh lookback window]**. Define the number of lookback days from today that an audience is evaluated. You can select from options or define a Custom time. The maximum is 90 days.</li><li>**[!UICONTROL Expiration date]**: Define when the audience stops refreshing. You can use ![Calendar](/help/assets/icons/Calendar.svg) to select a date. The default is 1 year from the creation date. Expiring audiences are treated similarly to expiring scheduled reports. The admin gets an email a month before the audience expires.</li></ul> Note that there is a limit of 75 to 150 audience refreshes, depending on your Customer Journey Analytics entitlement.</li></ul> |
| **[!UICONTROL Filter]** | Filters are the main input to the audience. Drag and drop one or more filters from the left ![Segmentation](/help/assets/icons/Segmentation.svg) **[!UICONTROL Filter]** panel on to the Filter area. You can use the ![Search](/help/assets/icons/Search.svg) [!UICONTROL *Search filters*] to search for filters. You can add up to 20 filters. Filters can be joined with **[!UICONTROL And]** or **[!UICONTROL Or]** operators.<p>When creating an audience from a visualization in Analysis Workspace (such as a freeform table or Journey canvas), any filters applied to the panel or to the column are preserved. You can remove any filters that are automatically applied.</p> |
| **[!UICONTROL Data preview]** | Select ![Info](/help/assets/icons/Info.svg) to show or hide the [Data preview](#data-preview) for the selected date range. |

## Data preview

The Data preview panel provides the following information.

| Element | Description |
| --- | --- |
| **[!UICONTROL Total people]** | A summary number of the total number of people in this audience. The maximum size is 20 million people. If your audience exceeds 20 million people, you must reduce the audience size before you can publish. |
| **[!UICONTROL Audience size limit]** | Visualization to show how far from the 20 million limit this audience is. |
| **[!UICONTROL Estimated audience return]** | You can use this value to retarget people in this audience that come back to your site, mobile app or other channel.<p>You can select the time frame (**[!UICONTROL Next 7 days]**, **[!UICONTROL Next 2 weeks]**, or **[!UICONTROL Next month]**) for the estimated number of customers who may return. |
| **[!UICONTROL Estimated to return]** | This number gives you an estimated number of returning customers over the time frame that you selected. This number is predicted using the historical churn rate for this audience. |
| **[!UICONTROL Preview metrics]** | You can select a specific metric to see how data for that metric is based on the audience you define.  Each Preview metric displays a total for the metric based on the audience. And a percentage of the audience based metric from the overall total of the metric, as defined by the data view. For example, 381 people (the metric you selected) are the result of your audience definition, which is 5% of the total people available in the data view. You can select any metric that is available in your data view.  |
| **[!UICONTROL Namespaces included]** | The specific namespaces that are associated with the people in your audience. Examples include ECID, CRM ID, email addresses, etc. |
| **[!UICONTROL Sandbox]** | The [Experience Platform sandbox](https://experienceleague.adobe.com/en/docs/experience-platform/sandbox/home) in which this audience resides. When you publish this audience to Platform, you can only work with the audience within the confines of this sandbox. |

{style="table-layout:auto"}

## What happens after an audience is created and published? {#after-audience-created} 

After you create and publish an audience in Customer Journey Analytics, the audience is available in Experience Platform. An Adobe Experience Platform streaming segment is created only if your organization is set up for streaming segmentation.

* The audience in Platform shares the same name and description as the Customer Journey Analytics audience. The name is appended with the Customer Journey Analytics audience ID to ensure that the audience is unique.
* Any changes made to the name or description of the audience in Customer Journey Analytics are reflected in Experience Platform.
* If an audience is deleted in Customer Journey Analytics, the audience continues to be available in Experience Platform until the profile membership of the audience expires. The profile membership expires after 420 days for one-time audiences and after 16 days for recurring audiences.

## Latency considerations {#latency}

At several points prior to, during, and after audience publishing, latencies can occur. Here is an overview of possible latencies.

![Latencies in audience publishing as described in this section.](assets/latency-diagram.svg)

|  | Latency point | Latency duration |
| --- | --- | --- |
| Not shown | Adobe Analytics to Analytics source connector (A4T) | Up to 30 minutes |
| 1 | Data ingestion into Data Lake (from Analytics source connector or other sources) | Up to 90 minutes |
| 2 | Data ingestion from Experience Platform Data Lake into Customer Journey Analytics | Up to 90 minutes |
| 3 | Audience publishing to Real-Time Customer Profile, including automatic creation of the streaming segment, and allowing the segment to be ready to receive the data. | A few seconds |
| 4 | Refresh frequency for audiences |<ul><li>One-time refresh (latency of less than 5 minutes)</li><li>Refresh every 4 hours, daily, weekly, monthly (latency goes hand in hand with the refresh rate) |
| 5 | Creating destination in Adobe Experience Platform: Activating the new segment | 1-2 hours |

{style="table-layout:auto"}

## Use Customer Journey Analytics audiences in Experience Platform {#audiences-aep}

Customer Journey Analytics takes all the namespace and ID combinations from your published audience and streams them into Real-Time Customer Data Platform . Customer Journey Analytics sends the audience to Experience Platform with the primary identity set, according to what was selected as the [!UICONTROL Person ID] when the connection was configured.

Real-Time Customer Data Platform then examines each namespace/ID combination and looks for a profile that it may be part of. A profile is basically a cluster of linked namespaces, IDs and devices. If it finds a profile, it adds the namespace and ID to the other IDs in this profile as a segment membership attribute. For example, <user@adobe.com> can be targeted across all their devices and channels. If a profile is not found, a new one is created.

To view Customer Journey Analytics audiences in Platform:

1. Expand **[!UICONTROL Customer]** in the left panel, then select **[!UICONTROL Audiences]**. <!-- is there a folder called "Customer Journey Analytics? -->

1. Select the **[!UICONTROL Browse]** tab.

1. To locate the audience that you published from Customer Journey Analytics, do any of the following:

   ![Audiences option in the left panel](assets/aep-audiences.png)

   * Sort the table by the **[!UICONTROL Origin]** column to view audiences that show [!UICONTROL **Customer Journey Analytics**] as the origin.
   
   * Filter ![Filter](/help/assets/icons/Filter.svg) on **[!UICONTROL Origin]** and select **[!UICONTROL Customer Journey Analytics]**.
   
   * Use the ![Search](/help/assets/icons/Search.svg) search field.

For more information about using Audiences in Platform, see the [Audiences](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/ui/segment-builder) section in the [Segment Builder UI guide](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/ui/segment-builder) in the Experience Platform documentation.
   

## FAQs {#faq}

Frequently asked questions on audience publishing.

+++**What happens if a user is no longer a member of an audience in Customer Journey Analytics?**

In this case, an exit event is sent to Experience Platform from Customer Journey Analytics.

+++

+++**What happens if you delete an audience in Customer Journey Analytics?**

When a Customer Journey Analytics Audience is deleted, that audience is no longer shown in the Experience Platform UI. However, profiles associated with that audience are not deleted in Experience Platform.

+++

+++**If a corresponding profile does not exist in Real-Time Customer Data Platform, is a new profile created?**

Yes, it will.

+++

+++**Does Customer Journey Analytics send the audience data over as pipeline events or as a flat file that also goes to the data lake?**

Customer Journey Analytics streams the data into Real-Time Customer Data Platform via pipeline, and this data is also collected into a system dataset in the data lake.

+++

+++**What identities does Customer Journey Analytics send over?**

Whichever identity/namespace pairs that were specified in the [Connection setup](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-connections/create-connection). Specifically, the step when a user selects the field they want to use as the Person ID.

+++

+++**Which ID is chosen as the primary identity?**

See above. Only one identity per Customer Journey Analytics person is sent.

+++

+++**Does Real-Time Customer Data Platform process the Customer Journey Analytics messages as well? Can Customer Journey Analytics add identities to a profile identity graph through audience sharing?**

No. Only one identity per person is sent, so there would be no graph edges for Real-Time Customer Data Platform to consume. 

+++

+++**What time of day do daily, weekly, and monthly refreshes occur? What day of the week do weekly refreshes occur?**

The timing of the refresh is based on when the original audience was published and anchors to that time of day (and day of week or month).

+++

+++**Can you configure the daily, weekly, and monthly time of refresh?**

No, users cannot configure the time of refresh.

+++


## Next steps

* To manage this audience, go to the [Management UI](/help/components/audiences/manage.md).
