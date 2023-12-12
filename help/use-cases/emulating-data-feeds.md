---
title: Emulate data feed functionality
description: Understand how you can emulate Adobe Analytics data feeds with data in Experience Platform.
solution: Customer Journey Analytics
feature: Use Cases
hide: yes
hidefromtoc: yes

---
# Emulate data feed functionality

Adobe Analytics data feeds are a powerful way to get raw data out of Adobe Analytics. This use case describes how to get similar type of raw data out of Experience Platform, to use in other platforms outside of Adobe and at your organization's discretion.

## Prerequisites

Make sure that you meet all the following requirements before using the functionality described in this use case:

* A working implementation that sends online and offline data into Experience Platform's data lake.
* Access to Query Service, which is packaged as part of plaform-based applications or the Data Distiller add-on. See [Query Service packaging](https://experienceleague.adobe.com/docs/experience-platform/query/packaging.html?lang=en) for more information.
* Access to Export datasets functionality, available to customers who have purchased the Real-Time CDP Prime or Ultimate package, Adobe Journey Optimizer, or Customer Journey Analytics. See [Export datasets to cloud storage destinations](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en) for more information.
* One or more destinations (for example: Amazon S3, Google Cloud Storage) configured to where you can export the raw data of your data feed.

## Introduction

Emulating an Adobe Analytics data feed involves:

* defining a **scheduled query** that generates the data for your data feed as an output dataset, using **Query Service**.
* defining a **scheduled dataset export** that exports the output dataset to a cloud storage destination, using **Dataset export**.


![Data feed](assets/data-feed.svg)


## Query service

Experience Platform Query Service allows you to query and join any dataset in Experience Platform Data Lake as if it is a database table. You then can capture the results as a new dataset for further use in reporting or for export.

You use the Query Service [user interface](https://experienceleague.adobe.com/docs/experience-platform/query/ui/overview.html?lang=en), a [client connected through the PostgresSQL protocol](https://experienceleague.adobe.com/docs/experience-platform/query/clients/overview.html?lang=en), or [RESTful APIs](https://experienceleague.adobe.com/docs/experience-platform/query/api/getting-started.html?lang=en) to create and schedule queries that collect the data for your data feed. 

### Create Query

You can use all the functionality of standard ANSI SQL for SELECT statements and other limited commands to create and execute the queries that generate the data for your data feed. See [SQL syntax](https://experienceleague.adobe.com/docs/experience-platform/query/sql/syntax.html?lang=en) for more information. Beyond this SQL syntax, Adobe supports:

* prebuilt [Adobe-defined functions (ADF)](https://experienceleague.adobe.com/docs/experience-platform/query/sql/adobe-defined-functions.html?lang=en) that help perform common business-related tasks on event data stored in Experience Platform data lake, including functions for [Sessionization](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-mobile-visit-processing.html?lang=en) and [Attribution](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/overview.html?lang=en),
* several built-in [Spark SQL functions](https://experienceleague.adobe.com/docs/experience-platform/query/sql/spark-sql-functions.html?lang=en),
* [metadata PostgreSQL commands](https://experienceleague.adobe.com/docs/experience-platform/query/sql/metadata.html?lang=en),
* [prepared statements](https://experienceleague.adobe.com/docs/experience-platform/query/sql/prepared-statements.html?lang=en).


#### Examples

Some examples of queries that collect data for your data feeds are listed below. These examples use `demo_system_event_dataset_for_website_global_v1_1` as the sample experience event dataset containing data collected from customers interacting with the website.

+++Top five products

*What are the top five products viewed on the website?*

```sql
select productListItems.name, count(*)
from   demo_system_event_dataset_for_website_global_v1_1
where  eventType = 'commerce.productViews'
group  by productListItems.name
order  by 2 desc
limit 5;
```

+++

+++Product interaction funnel

*What are the various product interactions across the website?*

```sql
select eventType, count(*)
from   demo_system_event_dataset_for_website_global_v1_1
where  eventType is not null
and    eventType <> ''
group  by eventType;
```

+++

+++What do people do

*What do people do on the site before reaching the "Cancel Service" page as the third page in a session?*

This query uses the Adobe Defined Functions `SESS_TIMEOUT` and `NEXT`.

* The `SESS_TIMEOUT()` reproduces the visit groupings found with Adobe Analytics. It performs a similar time-based grouping, but with customizable parameters.
* `NEXT()` and `PREVIOUS()` help you to understand how customers navigate your site.

```sql
SELECT
  webPage,
  webPage_2,
  webPage_3,
  webPage_4,
  count(*) journeys
FROM
  (
      SELECT
        webPage,
        NEXT(webPage, 1, true)
          OVER(PARTITION BY ecid, session.num
                ORDER BY timestamp
                ROWS BETWEEN CURRENT ROW AND UNBOUNDED FOLLOWING).value
          AS webPage_2,
        NEXT(webPage, 2, true)
          OVER(PARTITION BY ecid, session.num
                ORDER BY timestamp
                ROWS BETWEEN CURRENT ROW AND UNBOUNDED FOLLOWING).value
          AS webPage_3,
        NEXT(webPage, 3, true)
           OVER(PARTITION BY ecid, session.num
                ORDER BY timestamp
                ROWS BETWEEN CURRENT ROW AND UNBOUNDED FOLLOWING).value
          AS webPage_4,
        session.depth AS SessionPageDepth
      FROM (
            select a._sampleorg.identification.core.ecid as ecid,
                   a.timestamp,
                   web.webPageDetails.name as webPage,
                    SESS_TIMEOUT(timestamp, 60 * 30)
                       OVER (PARTITION BY a._sampleorg.identification.core.ecid
                             ORDER BY timestamp
                             ROWS BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW)
                  AS session
            from   demo_system_event_dataset_for_website_global_v1_1 a
            where  a._sampleorg.identification.core.ecid in (
                select b._sampleorg.identification.core.ecid
                from   demo_system_event_dataset_for_website_global_v1_1 b
                where  b.web.webPageDetails.name = 'Cancel Service'
            )
        )
)
WHERE SessionPageDepth=1
and   webpage_3 = 'Cancel Service'
GROUP BY webPage, webPage_2, webPage_3, webPage_4
ORDER BY journeys DESC
LIMIT 10;
```

+++

+++How much time

*How much time do you have before a visitor calls the call center after visiting the "Cancel Service" Page?*

To answer this kind of query, you use the `TIME_BETWEEN_NEXT_MATCH()` Adobe Defined Function. Time-between previous or next match functions provide a new dimension, which measures the time that has elapsed since a particular incident.

```sql
select * from (
       select _sampleorg.identification.core.ecid as ecid,
              web.webPageDetails.name as webPage,
              TIME_BETWEEN_NEXT_MATCH(timestamp, web.webPageDetails.name='Call Start', 'seconds')
              OVER(PARTITION BY _sampleorg.identification.core.ecid
                  ORDER BY timestamp
                  ROWS BETWEEN CURRENT ROW AND UNBOUNDED FOLLOWING)
              AS contact_callcenter_after_seconds
       from   demo_system_event_dataset_for_website_global_v1_1
       where  web.webPageDetails.name in ('Cancel Service', 'Call Start')
) r
where r.webPage = 'Cancel Service'
limit 15;
```

+++

+++What is the outcome

*What is the outcome of customers calling the call center?*

For this query, the `demo_system_event_dataset_for_website_global_v1_1` dataset is joined with an example `demo_system_event_dataset_for_call_center_global_v1_1` dataset containing call center interactions. 

```sql
select distinct r.*,
       c._sampleorg.interactionDetails.core.callCenterAgent.callFeeling,
       c._sampleorg.interactionDetails.core.callCenterAgent.callTopic,
       c._sampleorg.interactionDetails.core.callCenterAgent.callContractCancelled
from (
       select _sampleorg.identification.core.ecid ecid,
              web.webPageDetails.name as webPage,
              TIME_BETWEEN_NEXT_MATCH(timestamp, web.webPageDetails.name='Call Start', 'seconds')
              OVER(PARTITION BY _sampleorg.identification.core.ecid
                  ORDER BY timestamp
                  ROWS BETWEEN CURRENT ROW AND UNBOUNDED FOLLOWING)
              AS contact_callcenter_after_seconds
       from   demo_system_event_dataset_for_website_global_v1_1
       where  web.webPageDetails.name in ('Cancel Service', 'Call Start')
) r
, demo_system_event_dataset_for_call_center_global_v1_1 c
where r.ecid = c._sampleorg.identification.core.ecid
and r.webPage = 'Cancel Service'
and c._sampleorg.interactionDetails.core.callCenterAgent.callContractCancelled IN (true,false)
and c._sampleorg.interactionDetails.core.callCenterAgent.callTopic IN ('contract', 'invoice','complaint','wifi')
limit 15;
```

+++

+++Marketing Channel Engagement (Adobe Analytics data)

*What is the engagement across marketing channels for Italian focused web traffic?* 

This example uses the dataset created automatically by the Adobe Analytics source connector, for example `demo_data_sample_org_midvalues`.

```sql
select 
    channel.typeAtSource, count(*) 
from 
    demo_data_sample_org_midvalues 
where 
    (channel.typeAtSource IS NOT NULL
and
    web.webPageDetails.URL LIKE '%/it/it/%')
group by 
    channel.typeAtSource
order by 2 desc;
```

+++

For even more (advanced) sample queries see [abandoned browse](https://experienceleague.adobe.com/docs/experience-platform/query/use-cases/abandoned-browse.html?lang=en), [attribution analysis](https://experienceleague.adobe.com/docs/experience-platform/query/use-cases/attribution-analysis.html?lang=en), [bot filtering](https://experienceleague.adobe.com/docs/experience-platform/query/use-cases/bot-filtering.html?lang=en), and other examples in the Query Service Guide.


#### Identities

In Experience Platform, various identities are available. Ensure you are querying identities correctly. In the examples above, ECID is defined as part of a core object, which itself is part of an identification object, both added to the schema using an Experience Event Core field group (for example: `_sampleorg.identification.core.ecid`). The ECIDs might be organized differently in your schemas.

Alternatively you can use `identityMap` to query for identities. This object is of type `Map` and uses a [nested data structure](#nested-data-structure).

For data ingested using the Adobe Analytics source connector, multiple identities might be available. The primary identifier depends on whether an ECID or AAID exists. See [Primary identifiers in Adobe Analytics data](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=en#how-the-analytics-source-treats-identities) and [AAID, ECID, AACUSTOMID and the Analytics source connector](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aaid-ecid-adc.html?lang=en) for more information

#### Data feed columns

The fields (columns) you can use in your query depend on the schema definition on which your datasets are based. Ensure you do understand the schema underlying the dataset. 

For example, in some of the [example queries](#examples) you queried for *page name*. 

* In Adobe Analytics Data Feed's UI, you would select **[!UICONTROL pagename]** as the column to add to your data feed definition. 
* In Query Service, you include `web.webPageDetails.name` from the `demo_system_event_dataset_for_website_global_v1_1` dataset (based on the **Demo System - Event Schema for Website (Gobal v1.1)** experience event schema) in your query. See the [Web Details schema field group](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/event/web-details.html?lang=en) for more information.

To understand the mapping between former Adobe Analytics data columns and XDM fields in your experience event dataset and underlying schema, see [Analytics fields mapping](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=en) and the [Adobe Analytics ExperienceEvent Full Extension schema field group](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/event/analytics-full-extension.html?lang=en) for more information.

Furthermore, the information automatically collected by the Experience Platform Web SDK (out of the box) might also be relevant to identify columns for your query. See [Automatically collected information](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/automatic-information.html?lang=en) for more information.


#### Lookups

To look up data from other datasets, you use standard SQL functionality (WHERE clause, INNER JOIN, OUTER JOIN, and others). See the [What is the outcome](#examples) query in the examples.

#### Calculations

To perform calculations on fields (columns), simply use the standard SQL functions (for example `COUNT(*)` in the [Product interaction funnel](#examples) query in the examples) or the [math and statistical operators and functions](https://experienceleague.adobe.com/docs/experience-platform/query/sql/spark-sql-functions.html?lang=en#math) part of Spark SQL. 

#### Nested data structure

The schemas on which the datasets are based often contain complex data types including nested data structures. Previously mentioned `identityMap` is an example of a nested data structure. See below for an example of `identityMap` data.

```json
{
   "identityMap":{
      "FPID":[
         {
            "id":"55613368189701342632255821452918751312",
            "authenticatedState":"ambiguous"
         }
      ],
      "CRM":[
         {
            "id":"2394509340-30453470347",
            "authenticatedState":"authenticated"
         }
      ]
   }
}
```

You can use the [`explode()` or other Arrays functions](https://experienceleague.adobe.com/docs/experience-platform/query/sql/spark-sql-functions.html?lang=en#arrays) from Spark SQL to get to the data inside a nested data structure. 

For example:

```sql
select explode(identityMap) from demosys_cja_ee_v1_website_global_v1_1 limit 15;
```

Alternatively you can refer to individual elements using dot notation. For example:

```sql
select identityMap,ecid from demosys_cja_ee_v1_website_global_v1_1 limit 15;
```

See [Working with nested data structures in Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/key-concepts/nested-data-structures.html?lang=en) for more information.

### Schedule Query

You schedule the query to ensure that the query is executed and that the results are generated at your preferred interval. When scheduling the query, you define an output dataset.

#### Using Query Editor

You can schedule a query using the Query Editor. When defining a schedule for a query, you can define the output dataset. See [Query schedules](https://experienceleague.adobe.com/docs/experience-platform/query/ui/query-schedules.html?lang=en) for more information.


#### Using Query Service API

Alternatively you can use the RESTful APIs to define a query and schedule for the query. See [Query Service API guide](https://experienceleague.adobe.com/docs/experience-platform/query/api/getting-started.html?lang=en_) for more information.
Ensure you define the output dataset as part of the optional `ctasParameters` property when creating the query ([Create a query](https://developer.adobe.com/experience-platform-apis/references/query-service/#tag/Queries/operation/createQuery)) or when creating the schedule for a query ([Create a scheduled query](https://developer.adobe.com/experience-platform-apis/references/query-service/#tag/Schedules/operation/createSchedule)).



## Dataset export

Once you have created and scheduled your query, and verified the results in the output datasets are in line with your requirements, you can then export the raw datasets to cloud storage destinations. This export is in Experience Platform Destinations terminology referred to as Dataset export destinations. See [Export datasets to cloud storage destinations](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en) for an overview.

The following cloud storage destinations are supported:

* [Azure Data Lake Storage Gen2](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/adls-gen2.html?lang=en)
* [Data Landing Zone](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone.html?lang=en)
* [Google Cloud Storage](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/google-cloud-storage.html?lang=en)
* [Amazon S3](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/amazon-s3.html?lang=en#changelog)
* [Azure Blob](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/azure-blob.html?lang=en#changelog)
* [SFTP](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/sftp.html?lang=en#changelog)


### Experience Platform UI

You can export and schedule the export of your output datasets through the Experience Platform UI. This section describes the steps involved.

#### Select destination

When you have determined to which cloud storage destination you want to export the output dataset, [select the destination](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#select-destination). When you have not yet configured a destination for your preferred cloud storage, you must [create a new destination connection](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/connect-destination.html?lang=en). 

As part of configuring a destination you can define the file type (JSON or Parquet), whether the resulting file should be compressed or not, and whether a manifest file should be included or not.


#### Select dataset

When you have selected the destination, in the next **[!UICONTROL Select datasets]** step you have to select your output dataset from the list of datasets. If you have create multiple scheduled queries, and you want the output datasets to send to the same cloud storage destination, you can select the corresponding output datasets. See [Select your datasets](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#select-datasets) for more information.

#### Schedule dataset export

Finally, you want to schedule your dataset export as part of the **[!UICONTROL Scheduling]** step. In that step you can define the schedule and whether the output dataset export should be incremental or not. See [Schedule dataset export](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#scheduling) for more information.


#### Final steps

[Review](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#review) your selection and when correct start exporting your output dataset to the cloud storage destination.

You must [verify](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#verify) a successful data export. When exporting datasets, Experience Platform creates one or multiple `.json` or `.parquet` files in the storage location defined in your destination. Expect new files to be deposited in your storage location according to the export schedule you set up. Experience Platform creates a folder structure in the storage location that you specified as part of the selected destination, where it deposits the exported files. A new folder is created for each export time, following the pattern: `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. The default file name is randomly generated and ensures that exported file names are unique.

### Flow Service API

Alternatively, you can export and schedule the export of output datasets using APIs. The steps involved are documented in [Export datasets by using the Flow Service API](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html).

#### Get started

Ensure you have the [required permissions](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#permissions) to export datasets and that the destination to where you want to send your output dataset supports exporting datasets. You then must [gather the values for required and optional headers](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#gather-values-headers) you use in the API calls, as well as [identify the connection spec and flow spec IDs of the destination](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#gather-connection-spec-flow-spec) you are intending to export datasets to.

#### Retrieve eligible datasets

You can [retrieve a list of eligible datasets](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#retrieve-list-of-available-datasets) for export and verify whether your output dataset is part of that list using the [`GET /connectionSpecs/{id}/configs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Configurations/operation/getDatasets) API. 


#### Create source connection

Next you must [create a source connection](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#create-source-connection) for the output dataset, using its unique ID, that you want to export to the cloud storage destination. You use the [`POST /sourceConnections`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Source-connections/operation/postSourceConnection) API.

#### Authenticate to destination (create base connection)

You now must [create a base connection](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#create-base-connection) to properly authenticate and securely store the credentials to your cloud storage destination using the [`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection) API.


#### Provide export parameters

Next, you must [create an additional target connection which stores the export parameters](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#create-target-connection) for your output dataset using, once more, the [`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection) API. These export parameters include location, file format, compression, and more.

#### Set up dataflow

Finally, you [set up the dataflow](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#create-dataflow) to ensure that your output dataset is exported to your cloud storage destination using the [`POST /flows`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflows/operation/postFlow) API. In this step, you can define the schedule for the export, using the `scheduleParams` parameter.

#### Validate dataflow

To [check successful executions of your dataflow](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#get-dataflow-runs), use the [`GET /runs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflow-runs/operation/getFlowRuns) API, specifying the dataflow ID as query parameter. This dataflow ID is an identifier returned when you set up the dataflow.

[Verify](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#verify) a successful data export. When exporting datasets, Experience Platform creates one or multiple `.json` or `.parquet` files in the storage location defined in your destination. Expect new files to be deposited in your storage location according to the export schedule you set up. Experience Platform creates a folder structure in the storage location that you specified as part of the selected destination, where it deposits the exported files. A new folder is created for each export time, following the pattern: `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. The default file name is randomly generated and ensures that exported file names are unique.

## Conclusion

In short, emulating the Adobe Analytics Data Feed functionality implies setting up scheduled queries using Query Service and using results of these queries in scheduled Dataset exports.

>[!IMPORTANT]
>
>Two schedulers are involved in this use case. To guarantee a proper working of the emulated data feed functionality, ensure that the schedules configured in Query Service and Data exports do not interfere.

