---
title: Create a Data Feed
description: Learn how to create a data feed and about the file information to provide to Adobe.
hide: true
feature: Components
autotag-review: '2026-05-19T08:45:44.870Z'
TQID: 'https://experienceleague.adobe.com/QgBD7vCkw4YA568XOLlwTnw8eZVZybXr3DFbM1ZKYDw'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
    internal-label: Exports
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
---
# Create a data feed

{{release-limited-testing}}

When creating a data feed, you provide Adobe with: 

* The information about the destination where you want raw data files to be sent

* The data you want to include in each file

* The frequency with which data is sent (including the processing delay to capture late-arriving events)

Before you create a data feed, it's important to have a basic understanding of data feeds and to ensure that you meet all prerequisites. For more information, see [Data feeds overview](data-feed-overview.md). 

## Create and configure a data feed {#create-and-configure-data-feed}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_export_file"
>title="Manifest"
>abstract="Choose whether to include a manifest file with each data feed delivery. Manifest files contain information for each file included in the data feed. When sending data feed data in a single package, you can also choose to include a finish file, but manifest files are recommended. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_notify"
>title="Notify of issues, when complete, and when expiring"
>abstract="Specify one or more email addresses where a notification should be delivered when the data feed completes, is expiring, or encounters issues. Separate multiple email addresses with a comma."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_frequency_granularity"
>title="Frequency and Granularity"
>abstract="**Delivery frequency** (live feeds): How often the data feed is delivered. Hourly deliveries contain one hour's worth of data; daily deliveries contain one day's worth of data. The lookback date range and processing delay can also affect which events are included.<p>**Granularity** (backfill feeds): The time interval used to divide hitorical data. Each chunk contains one day's worth of data and is delivered as quickly as possible, not once per day. This field is always set to Daily and cannot be modified.</p>"

<!-- markdownlint-enable MD034 -->

1. Log in to [experiencecloud.adobe.com](https://experiencecloud.adobe.com) using your Adobe ID credentials.

1. Select [!UICONTROL **Customer Journey Analytics**] from the app switcher ![App](/help/assets/icons/Apps.svg) at the top right of the interface.

1. In the top navigation bar, go to [!UICONTROL **Components**] > [!UICONTROL **Exports**].

1. Select the [!UICONTROL **Data feeds**] tab.

1. Select [!UICONTROL **Create**] in the upper-right corner of the screen.

   Or, if no data feeds have previously been created, select [!UICONTROL **Create data feed**] within the empty table. 

   A page displays with the following tabs: [!UICONTROL **Details**], [!UICONTROL **Data structure**], and [!UICONTROL **Delivery**].

   ![New data feed page](assets/data-feed-new.png)

1. On the [!UICONTROL **Details**] tab, complete the following fields:
   
   | Field | Function |
   |---------|----------|
   | [!UICONTROL **Name**] | The name of the data feed. Names must be unique within the selected data view, and can be up to 255 characters in length. <!--[Learn more](/help/export/analytics-data-feed/df-faq.md#must-feed-names-be-unique)--> |
   | [!UICONTROL **Tags**] | Apply any tags to the data feed for easier categorization. <!--You can filter on tags as described in [Filter and search the list of data feeds](/help/export/analytics-data-feed/df-manage-feeds.md#filter-and-search-the-list-of-data-feeds) in [Manage data feeds](/help/export/analytics-data-feed/df-manage-feeds.md).-->  |
   | [!UICONTROL **Description**] | Specify a description for the data feed (up to 500 characters). The description you add is visible when editing the data feed. |
   | [!UICONTROL **Data view**] | Select the data view that contains the data that you want to export.<p>Consider the following when selecting a data view:</p> <ul><li>If multiple data feeds are created for the same data view, each data feed must have different column definitions.</li><li>The list of available columns depends on the login company where the selected data view belongs. If you change the data view, the list of available columns can change. </li></ul> |

1. Select [!UICONTROL **Next**].

1. On the [!UICONTROL **Data structure**] tab, make sure the correct data view is selected in the **[!UICONTROL Data view]** field. 

   <!--add screenshot-->

1. In the [!UICONTROL **Segments**] drop-down menu, search for and select any segments to filter the data included in your feed. 

   When you apply multiple segments, they are joined together with an AND operator. To join segments with an OR operator, you must first create a new segment in the segment builder, then apply the new segment to the data feed.

   Segments you apply here are in addition to any segments that might already be applied in your data view.

1. (Optional) In the left rail, use the **search** field to locate specific components. Or, select the **Sort** icon ![Sort components icon](/help/assets/icons/SortOrderDown.svg) to apply any of the following sort options:

   | Option | Function |
   | --------- | ---------- |
   | [!UICONTROL **Recommended**] | Sorts components with those that are recommended at the top of the list. Components that are used most frequently and most recently by you or by others in your organization are shown higher in the list. |
   | [!UICONTROL **Alphabetical**] | Sorts components alphabetically. |
   | [!UICONTROL **Categorical**] | Sorts components similar to [!UICONTROL **Recommended**], except that calculated metrics and standard metrics are grouped separately instead of being mixed together. |

1. Add components to the data feed configuration. The left rail shows only components that are valid for data feeds. 

   * **Drag-and-drop**: Drag components from the left rail to the canvas. Hold **[!UICONTROL Shift]**, or hold **[!UICONTROL Command]** (macOS) or **[!UICONTROL Ctrl]** (Windows) to select and drag multiple components at once.
   * **Plus button**: Select the Plus ![Add](/help/assets/icons/Add.svg) icon next to any component in the left rail to add it to the canvas.
   * **[!UICONTROL Show all]**: Select **[!UICONTROL Show all]** at the bottom of the component list to open a dialog showing all available components. Select the checkbox next to each component you want to add, then select **[!UICONTROL Add selected]**. When a search term or filter tag is active in the left rail, an **[!UICONTROL Add all]** button also appears, letting you add all filtered results at once.

   Consider the following when adding fields:
   
   * Some components are required, unsupported, or have restrictions in data feeds. For details, see [Component availability in data feeds](/help/components/exports/cja-data-feeds/df-components.md).
   
   * When you add a component that belongs to an XDM array field (for example, an Adobe Journey Optimizer proposition field) or a map field, a dialog prompts you to add any other components from the same sub-container. In the data feed output, all of these components appear in a single column. For more information, see [Sub-container components in data feeds](/help/components/exports/cja-data-feeds/df-sub-event.md)

1. (Optional) Reorder components on the canvas by dragging them. The order you define is preserved as the column order in the exported data feed file.

1. (Optional) Resize columns on the canvas by dragging the column border. 

   Column widths are saved in a cookie and persist the next time you return to this data feed on the same browser.

1. (Optional) Change the component ID that is displayed in the data feed output.

   1. Hover over a component on the canvas, then select the information icon.

   1. In the Component ID field, specify a new component ID.

      <!--add screenshot-->

1. (Optional) Use the **[!UICONTROL Feed summary]** and **[!UICONTROL Schema preview]** panels on the right side of the page to review your data structure before proceeding:

   * The **[!UICONTROL Feed summary]** shows a live count of the total components, columns, dimensions, and metrics that you added.
   * The **[!UICONTROL Schema preview]** shows a JSON representation of the data feed schema that updates as you add or reorder components. 
   * The **[!UICONTROL Example rows]** button opens a dialog that shows example output rows so you can verify that the structure looks correct. This dialog shows example data only and does not reflect your actual data.

   <!--add screenshot-->

1. On the [!UICONTROL **Delivery**] tab, in the [!UICONTROL **Schedule**] section, choose the type of feed you want to create (live or backfill), then specify the reporting window, frequency, and other configuration options:

   <!--add screenshot-->

   | Field | Function |
   |---------|----------|
   | [!UICONTROL **Feed type**] | Select the type of feed you want to create:<ul><li>[!UICONTROL **Live feed**]: Exports current and future data.</li><li>[!UICONTROL **Backfill feed**]: Exports historical data. </li></ul> |
   | [!UICONTROL **Start date**] | The date when the data feed begins. For live feeds, this must be today or a future date. For backfill feeds, this must be a past date within the data view's data retention window. The start date is based on the data view's time zone. |
   | [!UICONTROL **Expiration date**] <br/>Available only for live feeds| The date when the data feed expires and no longer runs. The date is based on the data view's time zone. |
   | [!UICONTROL **End date**]<br/>Available only for backfill feeds | The date when the data feed ends. The end date cannot be in the future. The date is based on the data view's time zone. |
   | [!UICONTROL **Frequency**]<br/>Available only for live feeds | Select how often the data feed should be sent. Events with timestamps that fall within the frequency window are included in the data feed delivery. The [!UICONTROL **Lookback date range**] and [!UICONTROL **Processing delay**] fields can also affect which events are included in the data for the delivery frequency that you choose.<p>Select to include either one hour's worth of data or one day's worth of data.</p><ul><li>**Daily**: Feeds contain a full day's worth of data, from midnight to midnight in the data view's time zone.</li><li>**Hourly**: Feeds contain a single hour's worth of data.</li></ul> |
   | [!UICONTROL **Granularity**]<br/>Available only for backfill feeds | The time interval used to divide historical data into chunks. Each chunk contains a full day's worth of data, from midnight to midnight in the data view's time zone. <p>Granularity determines how the data is grouped, not how often it is delivered. Backfill data is delivered as quickly as possible, not once per day.</p><p>This field is always set to [!UICONTROL **Daily**] and cannot be modified.</p> |
   | [!UICONTROL **Lookback date range**] | Controls how far back Customer Journey Analytics looks when processing the data feed delivery. The default is 30 days.<p>The frequency window (hour or day) determines which events are included in the data feed, while the **lookback date range** provides the needed historical context to classify those events correctly.</p><p>Segment qualification, dimension persistence, session calculation, and derived field transformations can all affect the events that are included.</p> <p>Before configuring this option, see the details and examples described in the section below, [Understand the lookback date range](#data-feed-lookback-date-range).</p> |
   | [!UICONTROL **Processing delay**] | Choose the amount of time that Customer Journey Analytics waits before processing a data feed file. Any late-arriving events that come in during the processing delay are included in the data feed. <p>The minimum processing delay is 2 hours, but some types of data require a longer delay. The delay you choose depends on the types of data in your connection, such as streaming, batch, stitched, lookup, or profile data.</p><p>Choose a delay that is long enough for the slowest data in your connection to finish processing. If the delay is too short, data that is still processing is not included in the data feed file.</p><p>Before configuring this option, see the details and examples described in the section below, [Understand the processing delay](#data-feed-processing-delay).</p> |
   | [!UICONTROL **Compression format**] | Select the compression format for the Parquet output files delivered to your cloud destination. Choose from the following formats:<ul><li>[!UICONTROL **Snappy**]: Fast compression and decompression with moderate file sizes. Widely supported by modern data platforms such as BigQuery, Snowflake, and Apache Spark.</li><li>[!UICONTROL **GZip**]: Broadly compatible, including with tools that do not natively support Snappy. Recommended if your downstream pipeline requires a widely recognized compression standard.</li><li>[!UICONTROL **Z Standard (Zstd)**]: High compression efficiency with fast decompression. Suitable if minimizing file size is a priority and your tools support Zstd.</li></ul> |

1. On the [!UICONTROL **Delivery**] tab, in the [!UICONTROL **Destination**] section, configure the destination where you want the data to be sent.  

   >[!NOTE]
   >
   >Consider the following when configuring a report destination:
   >
   ><!--* Adobe recommends using a cloud account for your report destination. [Legacy FTP and SFTP accounts](/help/components/locations/configure-import-accounts.md) are available, but are not recommended.-->
   >* Any cloud accounts that you previously configured are available to use for data feeds. You can configure cloud accounts from the Locations manager, in [Components > Exports > Location accounts](/help/components/exports/cloud-export-accounts.md).
   >
   >* Cloud accounts are associated with your Customer Journey Analytics user account. Other users cannot use or view cloud accounts that you configure unless you make them available to all users in your organization.
   >
   >* You can edit any locations that you create from the Locations manager in [Components > Exports > Locations](/help/components/exports/cloud-export-locations.md).

   Complete the following fields:
   
   | Field | Function |
   |---------|----------|
   | [!UICONTROL **View destinations for all users**] | If you are a system administrator, you can enable this option to view destinations created by all users in your organization. When this option is disabled, only destinations you created are displayed. |
   | [!UICONTROL **Account**] | Do either of the following:<ul><li>**Use an existing account:** Select the drop-down menu next to the **[!UICONTROL Account]** field. Or, begin typing the account name, then select it from the drop-down menu. <p>Accounts are available to you only if you configured them or if they are shared with an organization you are a part of.</p></li><li>**Create a new account:** Select **[!UICONTROL Add account]** within the **[!UICONTROL Account]** drop-down menu. For information about how to configure the account, see [Configure cloud export accounts](/help/components/exports/cloud-export-accounts.md).</li></ul> |
   | [!UICONTROL **Location**] | Do either of the following:<ul><li>**Use an existing location:** Select the drop-down menu next to the **[!UICONTROL Location]** field. Or, begin typing the location name, then select it from the drop-down menu.</li><li>**Create a new location:** Select **[!UICONTROL Add location]** within the **[!UICONTROL Location]** drop-down menu. For information about how to configure the location, see [Configure cloud export locations](/help/components/exports/cloud-export-locations.md).</li></ul> |
   | [!UICONTROL **Notify by email when complete**] | Specify one or more email addresses where a notification should be delivered after the data feed is successfully sent or fails to send. Multiple email addresses must be separated with a comma.  |
   | [!UICONTROL **Enable manifest**] | Choose whether to include a manifest file with each data feed delivery. The manifest file contains information for each file included in the data feed. |
       
1. Select **[!UICONTROL Save]**.    

## Understand the lookback date range {#data-feed-lookback-date-range}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_lookback_date_range"
>title="Lookback date range"
>abstract="Controls how far back Customer Journey Analytics looks when processing each delivery.<p>The frequency window (hour or day) determines which events are included in the data feed, while the **lookback date range** provides the needed historical context to classify those events correctly.</p><p>Segment qualification, dimension persistence, session calculation, and derived field transformations can all affect the events that are included.</p><p>A longer lookback improves accuracy; a shorter lookback improves performance.</p>"

<!-- markdownlint-enable MD034 -->

The lookback date range controls how far back Customer Journey Analytics looks when processing each data feed delivery. 

Events must still have timestamps that fall within the frequency window (hour or day) to be included in the delivery, but the data that falls within the **lookback date range** provides the needed historical context to classify those events correctly. 

When configuring this option, consider the following important concepts:

* A longer lookback date range typically results in more accurate data; a shorter range results in better delivery performance.
* The lookback date range, together with the frequency window, function similarly to the Analysis Workspace reporting date range. However, there are [key differences](/help/components/exports/cja-data-feeds/df-comparison-workspace.md#differences). These differences can result in data discrepancies between Workspace reports and data feed deliveries.

Segment qualification, session calculation, dimension persistence, and derived field transformations are each considered when processing data within the lookback date range:

### Segment qualification

When a segment is applied to your data feed definition, data within the lookback date range determines which events, sessions or people qualify for the segment. The segment's container setting determines the scope. (Possible containers are: Person, Session, or Event. B2B includes the following additional containers: Global account, Account, Opportunity, Buying group.)

>[!BEGINSHADEBOX]

**Example:**

Suppose you want to create a data feed to understand the behavior of users who are part of a specific marketing campaign, Campaign B. 

To accomplish this, you apply a segment to the data feed called _Users in Campaign B_, indicating that only those events tied to users in this segment should be included in the data feed.

In this case, users are included in the data feed only if they meet **both** of the following conditions:

* The user had an event with a timestamp that is within the data feed frequency window (the given hour or day of the data feed).
* The user qualified for the _Campaign B_ segment **sometime within the lookback date range**.

  For a qualifying event that occurred 9 days ago, this means the user **would be included** in the data feed if the lookback date range were set to 30 days, but the user **would not be included** in the data feed if the lookback date range were set to 7 days.

>[!ENDSHADEBOX]

### Session calculation

Session boundaries are calculated using all events in the lookback date range, not just the events in the delivery window. A session that started before the delivery window is still recognized as the same session.

The Session ID is based on the person, the session start time, and the session settings in your data view. A session keeps the same Session ID across deliveries, so you can join events from a session that spans multiple hourly or daily deliveries.

Consider the following when working with sessions in data feeds:

* If a session started before the lookback date range, its earlier events are not available, so session values can differ from Analysis Workspace. For more information, see [Understand data discrepancies between data feeds and Analysis Workspace](/help/components/exports/cja-data-feeds/df-comparison-workspace.md).
* Changing the session settings in your data view changes Session IDs. Session IDs in later deliveries won't match Session IDs in earlier deliveries.

### Dimension persistence

When you set persistence on an individual dimension, you also set an expiration to determine how long the dimension item persists beyond the event it is set on. 

The lookback date range affects dimension persistence when the expiration is set to either of the following options in the data view: 

* [!UICONTROL **Person Reporting Window**]: The lookback date range becomes the new reporting window for each dimension in the data feed definition that uses [!UICONTROL **Person Reporting Window**] as its expiration.
* [!UICONTROL **Custom Time**]: If the custom time that is selected extends beyond the lookback date range, the custom time is ignored, and the lookback date range is used for dimension expiration for each dimension in the data feed definition that uses [!UICONTROL **Custom Time**] as its expiration. Values that occurred before the lookback date range are not considered. 

  For more information about setting persistence on dimensions within the data view, see [Persistence component settings](/help/data-views/component-settings/persistence.md).

To get the most accurate data, consider setting the lookback date range to a value equal to or greater than the persistence set on dimensions in your data. However, keep in mind that a shorter lookback date range results in better performance for data feed deliveries. 

>[!BEGINSHADEBOX]

**Example:**

Suppose that in your data feed you want to know which marketing campaign users originally saw before coming to your site.

To accomplish this, you set persistence on the Campaigns dimension with Original as the allocation model. 

In this case, the original campaign is shown in the data feed output only if users meet **both** of the following conditions:

* The user had an event with a timestamp that is within the data feed frequency window (the given hour or day of the data feed).

* The user qualified for the original campaign **sometime within the lookback date range**.

  If the user qualified for the original campaign 9 days ago, the original campaign **is included** in the data feed if the lookback date range is set to 30 days, but the original campaign **is not included** in the data feed if the lookback date range is set to 7 days.

>[!ENDSHADEBOX]

### Derived field transformations

Any derived field functions that reference containers use the lookback date range in data feed exports. What date capabilities exist in derived fields? <!--Not sure how this applies.-->

## Understand the processing delay {#data-feed-processing-delay}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_processing_delay"
>title="Processing delay"
>abstract="The amount of time that Customer Journey Analytics waits before processing a data feed file. Any late-arriving events that come in during the processing delay are included in the data feed.<p>The minimum processing delay is 2 hours, but some types of data require a longer delay. Choose a delay that is long enough for the slowest data in your connection to arrive in the Experience Platform data lake and be ingested into Customer Journey Analytics. If the delay is too short, data that is still processing is not included in the data feed file.</p><p>Stitching can add up to 4 hours. To account for this, add 4 hours to the delay for any stitched data.</p>"

<!-- markdownlint-enable MD034 -->

### How the processing delay works

The processing delay is the amount of time that Customer Journey Analytics waits before processing a data feed file. Any late-arriving events that come in during the processing delay are included in the data feed. 

Processing delays are needed for various reasons, such as to account for pipeline latency, to give mobile implementations an opportunity for offline devices to come online and send data, or to accommodate your organization's server-side processes in managing previously processed files.

The minimum processing delay is 2 hours, but some types of data require a longer delay.

>[!BEGINSHADEBOX]

**Example:**

Suppose an hourly data feed includes data from 1:00 PM to 2:00 PM and the processing delay is 2 hours. Processing for that data feed file begins at 4:00 PM and includes any data that arrived before processing begins.

>[!ENDSHADEBOX]

### Choose a processing delay based on your data

Different types of data take varying amounts of time to become available in Customer Journey Analytics. Data goes through two processing phases, and the time for each phase adds to the total. 

Choose a processing delay that is long enough for the slowest data in your connection to complete both phases. If the delay is too short, data that is still processing is not included in the data feed file.

#### Phase 1: Data arrives in the Experience Platform data lake 

Arrival times vary based on the type of data you are collecting. Choose a delay that accommodates the type of data you are collecting. 

* **Event datasets from the Edge Network or streaming ingestion**: Data typically arrives in the data lake within 60 minutes (see [Latencies](/help/technotes/guardrails.md#latencies)).

* **Analytics source connector datasets**: Data typically arrives in the data lake within 2.25 hours (see [Latencies](/help/technotes/guardrails.md#latencies)).
  
  <!--When using the Analytics Source Connector, the minimum processing delay increases from 2 hours to 6 hours (?) to account for the source connector data. (checking to see if this is feasible) -->

* **Datasets from other source connectors**: Latency varies by source connector and by when batches are sent. Upstream processing in Experience Platform, such as Data Prep, can add more time.

* **Lookup datasets**: The time for data to arrive in the data lake depends on how often data is uploaded. Lookup data is typically uploaded as a full copy of a database, in which only a small percentage of records have changed. Upload lookup data in smaller batches to shorten processing time.

  Small uploads are usually processed within the minimum delay. 

  Large uploads (for example, a weekly upload of millions of records) are processed at a lower priority and can take 3 to 4 hours longer. In the case of large uploads, event data is not delayed, but lookup values might not reflect the newest updates. 

* **Profile datasets**: The time for data to arrive in the data lake depends on how often data is uploaded. Profile data is typically ingested in large batches, such as a daily snapshot of the full profile table. Upload profile data in smaller batches to shorten processing time.

  Small uploads are usually processed within the minimum delay. 

  Large uploads (for example, a weekly upload of millions of records) are processed at a lower priority and can take 3 to 4 hours longer. In the case of large uploads, event data is not delayed, but profile values might not reflect the newest updates. 

#### Phase 2: Data is ingested from the data lake into Customer Journey Analytics

Data ingestion times vary depending on whether the dataset has stitching enabled.

* **Non-stitched datasets**: This can take up to 90 minutes (see [Latencies](/help/technotes/guardrails.md#latencies)).

* **Stitched datasets**: Stitching can add up to 4 hours on top of the 90 minutes it takes for non-stitched datasets (see [Latencies](/help/technotes/guardrails.md#latencies)). If stitching is enabled for the connection, set the delay to at least 6 hours, and potentially 8 hours. Data that is updated by a stitching replay is generally not included in data feed files that were already processed.

  When stitching is enabled, the minimum processing delay increases from 2 hours to 6 hours to account for the stitched data.

>[!BEGINSHADEBOX]

**Example:**

If your connection includes multiple types of data, choose a delay that accommodates the slowest data. In the example below, that is approximately 8 hours.

Stitching can add up to 4 hours to ingestion into Customer Journey Analytics. To account for this, add 4 hours to the delay for any stitched data.

| Data source | Phase 1: Arrival in the data lake | Phase 2: Ingestion into Customer Journey Analytics | Total |
| --- | --- | --- | --- |
| Edge Network or streaming ingestion | 60 minutes | 90 minutes <p>Without stitching</p> | 2.5 hours |
| Analytics source connector | 2.25 hours | 90 minutes + 4 hours for stitching <p>With stitching</p> | 7.75 hours |

>[!ENDSHADEBOX]


