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

When creating a data feed, you provide Adobe with: 

* The information about the destination where you want raw data files to be sent

* The data you want to include in each file

* The frequency with which data is sent (including the processing delay to capture late-arriving hits)

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
>title="Notify when complete"
>abstract="Specify one or more email addresses where a notification should be delivered after the data feed is sent. Multiple email addresses must be separated with a comma."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_lookback_date_range"
>title="Lookback date range"
>abstract="Controls how far back Customer Journey Analytics looks when processing the data feed delivery.<br/>This setting does not alter the frequency window (hour or day). However, the lookback date range can influence the data that is delivered. Segment qualification, session calculation, some derived field transformations, and dimension persistence are all impacted by the lookback date range."

<!-- markdownlint-enable MD034 -->

1. Log in to [experiencecloud.adobe.com](https://experiencecloud.adobe.com) using your Adobe ID credentials.

1. Select [!UICONTROL **Customer Journey Analytics**] from the app switcher ![App](/help/assets/icons/Apps.svg) at the top right of the interface.

1. In the top navigation bar, go to [!UICONTROL **Components**] > [!UICONTROL **Data feeds**].

1. Select [!UICONTROL **Create**] in the upper-right corner of the screen.

   Or, if no data feeds have previously been created, select [!UICONTROL **Create data feed**] within the empty table. 

   A page displays with the following tabs: [!UICONTROL **Details**], [!UICONTROL **Data structure**], and [!UICONTROL **Delivery**].

   ![New data feed page](assets/data-feed-new.png)

1. On the [!UICONTROL **Details**] tab, complete the following fields:
   
   | Field | Function |
   |---------|----------|
   | [!UICONTROL **Name**] | The name of the data feed. Names must be unique within the selected data view, and can be up to 255 characters in length. <!--[Learn more](/help/export/analytics-data-feed/df-faq.md#must-feed-names-be-unique)--> |
   | [!UICONTROL **Tags**] | Apply any tags to the data feed for easier categorization. <!--You can filter on tags as described in [Filter and search the list of data feeds](/help/export/analytics-data-feed/df-manage-feeds.md#filter-and-search-the-list-of-data-feeds) in [Manage data feeds](/help/export/analytics-data-feed/df-manage-feeds.md).-->  |
   | [!UICONTROL **Description**] | Specify a description for the data feed. The description you add is visible when editing the data feed. |
   | [!UICONTROL **Data view**] | Select the data view that contains the data that you want to export.<p>Consider the following when selecting a data view:</p> <ul><li>If multiple data feeds are created for the same data view, each data feed must have different column definitions.</li><li>The list of available columns depends on the login company where the selected data view belongs. If you change the data view, the list of available columns can change. </li></ul> |

1. Select [!UICONTROL **Next**].

1. On the [!UICONTROL **Data structure**] tab, make sure the correct data view is selected in the **[!UICONTROL Data view]** field. 

1. In the [!UICONTROL **Segments**] drop-down menu, search for and select any segments to filter the data included in your feed. 

   When you apply multiple segments, they are joined together with an AND operator. (To join segments with an OR operator, you must first create a new segment in the segment builder, then apply the new segment to the data feed.)

1. Add components to the data feed configuration. In the left rail, locate any components that you want to include, then drag them to the canvas to build your data structure. You can select multiple components by holding **[!UICONTROL Shift]**, or by holding **[!UICONTROL Command]** (on macOS) or **[!UICONTROL Ctrl]** (on Windows).

   Use the following information to understand dimensions that are always included, dimensions that cannot be included, and metrics that must be substituted:

   +++ Dimensions that are always included in data feeds

   The following dimensions are included by default in every data feed and cannot be removed:

   | Dimension name | Notes | Data feeds | Other reporting |
   |---|---|---|---|
   | Timestamp | Timestamp of the event period. Microsecond granularity. Represented in UTC. | Mandatory | Not available |
   | Row ID | Unique row identifier | Mandatory | Not available |
   | Session ID | Unique identifier for each session | Mandatory | Not available |
   | Person ID | The person identifier for the data view and connection | Mandatory | Optional standard |
   | Account ID [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | Account ID when using the Account container | Mandatory | Optional standard |
   
   +++

   +++ Dimensions that cannot be included in data feeds

   Customer Journey Analytics standard dimensions cannot be included in data feeds. The following table lists these dimensions:

   | Dimension name | Notes | Data feeds |
   |---|---|---|
   | 5 Minute | Five-minute intervals when events occurred (rounded down) | Not available |
   | 15 Minute | Fifteen-minute intervals when events occurred (rounded down) | Not available |
   | 30 Minute | Thirty-minute intervals when events occurred (rounded down) | Not available |
   | Day | Day an event occurred | Not available |
   | Day of Week | Day of the week an event occurred | Not available |
   | Day of Month | Day of the month an event occurred | Not available |
   | Hour | Hour an event occurred (rounded down) | Not available |
   | Hour of Day | Hour of the day an event occurred (rounded down) | Not available |
   | Minute | Minute an event occurred (rounded down) | Not available |
   | Minute of Hour | Minute of the hour an event occurred (rounded down) | Not available |
   | Month | Month an event occurred | Not available |
   | Month of Year | Month of the year an event occurred | Not available |
   | Quarter | Quarter an event occurred | Not available |
   | Quarter of Year | Quarter of the year an event occurred | Not available |
   | Second | Second an event occurred (rounded down) | Not available |
   | Week | Week an event occurred | Not available |
   | Week of Year | Week of the year an event occurred | Not available |
   | Year | Year an event occurred | Not available |

   +++

   +++ Metrics that must be substituted in data feeds

   The following Customer Journey Analytics metrics must be substituted:

   | Metric name | Notes | Data feeds |
   |---|---|---|
   | Accounts [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | Based on Account ID specified in the connection | Not available. Use count distinct of Account ID. |
   | Buying Group [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | Buying groups based on Buying Group ID in the connection | Not available. Use count distinct of Buying Group ID. |
   | Events | Number of rows from all event datasets in a connection | Not available. Use count distinct of Row ID. |
   | Global Accounts [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | Based on Global Accounts ID in the connection | Not available. Use count distinct of Global Accounts ID. |
   | Opportunities [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | Opportunities based on Opportunity ID in the connection | Not available. Use count distinct of Opportunity ID. |
   | People | Based on Person ID specified in a connection | Not available. Use count distinct of Person ID. |
   | Conversations | Number of conversations | Not available. Use count distinct of Conversation ID. |
   | Session Ends | Number of events that were the last event of a session | Not available |
   | Session Starts | Number of events that were the first event of a session | Not available |
   | Sessions | Based on the data view's session settings | Not available. Use count distinct of Session ID. |
   | Time Spent (seconds) | Sums the time between two different dimension values | Not available |

   +++

   +++ Optional standard components

   | Component name | Type | Notes | Data feeds |
   |---|---|---|---|
   | AM/PM | Time-parting dimension | AM or PM | Not available |
   | Batch ID | Dimension | Identifier for an Experience Platform batch | Available |
   | Dataset ID | Dimension | Identifier for an Experience Platform dataset | Available |
   | Day of Month | Time-parting dimension | 1–31 | Not available |
   | Day of Week | Time-parting dimension | Monday through Sunday | Not available |
   | Day of Year | Time-parting dimension | 1–366 | Not available |
   | Event Depth | Dimension | Sequential numerical value (1, 2, 3, etc.) assigned to each event interaction within a session<p>Resets at the start of each new session</p> | Available |
   | Hour of Day | Time-parting dimension | 0–23 | Not available |
   | Month of Year | Time-parting dimension | January–December | Not available |
   | First-time Sessions | Metric | A person's first defined session within the reporting window | Not available |
   | Return Sessions | Metric | Sessions that were not a person's first-time session | Not available |
   | Person ID namespace | Dimension | Type of ID the Person ID consists of (for example, email or cookie ID) | Available |
   | Global Account ID [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | Dimension | Global Account ID when using the Global Account container | Available |
   | Opportunity ID [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | Dimension | Opportunity ID when using the Opportunity container | Available |
   | Buying Group ID [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | Dimension | Buying Group ID when using the Buying Group container | Available |
   | Quarter of Year | Time-parting dimension | Q1, Q2, Q3, Q4 | Not available |
   | Repeat Session | Metric | Sessions that were not a person's first-ever session | Not available |
   | Session Type | Dimension | Two values: First-Time or Returning | Not available |
   | Time Spent per Event | Dimension | Buckets the Time Spent metric into event buckets | Not available |
   | Time Spent per Session | Dimension | Buckets the Time Spent metric into session buckets | Not available |
   | Time Spent per Person | Dimension | Buckets the Time Spent metric into person buckets | Not available |
   | Weekend/Weekday | Time-parting dimension | Weekend or Weekday | Not available |

   +++


1. On the [!UICONTROL **Delivery**] tab, specify the following information:
   
   | Field | Function |
   |---------|----------|
   | [!UICONTROL **Feed type**] | Select the type of feed you want to create:<ul><li>[!UICONTROL **Live feed**]: Exports current and future data.</li><li>[!UICONTROL **Backfill feed**]: Exports historical data between two past dates.</li></ul>|
   | [!UICONTROL **Start date**] | Specify the date when you want the data feed to begin. To immediately begin processing data feeds for historical data, ensure that [!UICONTROL **Backfill feed**] is selected, then set this date to any date in the past when data is being collected. The start date is based on the data view's time zone. |
   | [!UICONTROL **End date**] | Specify the date when you want the data feed to end. The end date is based on the data view's time zone. |
   | [!UICONTROL **Frequency**] | Select how often the data feed should be sent. Events with timestamps that fall within the frequency window are included in the data feed delivery. The [!UICONTROL **Lookback date range**] and [!UICONTROL **Processing delay**] fields can also affect which events are included in the data for the delivery frequency that you choose.<p>For live feeds, select to include either one hour's worth of data or one day's worth of data. Backfill feeds must be daily.</p><ul><li>**Daily**: Feeds contain a full day's worth of data, from midnight to midnight in the data view's time zone. Use this option for backfill feeds or for live feeds.</li><li>**Hourly**: Feeds contain a single hour's worth of data. Use this option for live feeds.</li></ul>  |
   | [!UICONTROL **Lookback date range**] | Controls how far back Customer Journey Analytics looks when processing the data feed delivery. <p>This setting does not alter the frequency window (hour or day), which defines the time frame of the events to include in the data feed output. However, the lookback date range can influence the data that is delivered, in the following ways: </p><ul><li>**Segment qualification**: When a segment is applied to your data feed definition, any events within the lookback date range determine whether a person qualifies. The segment's container setting determines the scope. (Possible containers are: Person, Session, or Event. B2B has the following additional containers: Global account, Account, Opportunity, Buying group.)  <p>For example, if a Person container is used and the person qualifies during the lookback date range, then all of that person's events during the frequency window also qualify.</p></li><li>**Session calculation**: Session boundaries are calculated using data within the lookback date range.</li><li>**Derived field transformations**: Any derived field functions that reference containers use the lookback date range in data feed exports.</li><li>**Dimension persistence**: If you choose to set persistence on an individual dimension, you also choose an expiration to determine how long a dimension item persists beyond the event it is set on. <p>The lookback date range affects dimension persistence when the expiration is set to either of the following options in the data view:</p><ul><li>For each dimension in the data feed definition that uses [!UICONTROL **Reporting Window**] as its expiration, the lookback date range becomes the new reporting window.</li><li>For each dimension in the data feed definition that uses [!UICONTROL **Custom Time**] as its expiration, and if the custom time that is selected extends beyond the lookback date range, the custom time is ignored, and the lookback date range is used for dimension expiration.<p>For more information about setting persistence on dimensions within the data view, see [Persistence component settings](/help/data-views/component-settings/persistence.md).</p></li></ul>|
   | [!UICONTROL **Processing delay**] | Choose the amount of time to wait before processing a data feed file. Any late-arriving hits that come in during the processing delay are included in the data feed. <p>Processing delays are useful for various reasons, such as to give mobile implementations an opportunity for offline devices to come online and send data, or to accommodate your organization's server-side processes in managing previously processed files. </p><p>You can delay a feed by 2, 3, 4, or 8 hours.<p>Sessions must start after the processing delay cutoff in order to be included; sessions that start before the cutoff and end within the processing delay are not included.</p>|
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
   | [!UICONTROL **Notify when complete**] | Specify one or more email addresses where a notification should be delivered after the data feed is successfully sent or fails to send. Multiple email addresses must be separated with a comma.  |
   | [!UICONTROL **Enable manifest**] | Choose whether to include a manifest file with each data feed delivery. The manifest file contains information for each file included in the data feed. |
       
1. Select **[!UICONTROL Save]**.    

