---
title: Emulate data feed functionality
description: Understand how you can emulate Adobe Analytics data feeds with data in Experience Platform.
solution: Customer Journey Analytics
feature: Use Cases
hide: yes
hidefromtoc: yes
role: Admin

---
# Emulate data feed functionality

Adobe Analytics data feeds are a powerful way to get raw data out of Adobe Analytics. This use case describes how to get similar type of raw data out of Experience Platform, so you can use the data in other platforms, tools outside of Adobe and at your organization's discretion.

## Introduction

Emulating an Adobe Analytics data feed involves:

* defining a **scheduled query** that generates the data for your data feed as an output dataset ![output dataset](assets/output-dataset.svg), using **Query Service**.
* defining a **scheduled dataset export** that exports the output dataset to a cloud storage destination, using **Dataset export**.

![Data feed](assets/data-feed.svg)


## Prerequisites

Make sure that you meet all the following requirements before using the functionality described in this use case:

* A working implementation that collects data into Experience Platform's data lake.
* Access to the the Data Distiller add-on to ensure you are entitled to execute batch queries. See [Query Service packaging](https://experienceleague.adobe.com/docs/experience-platform/query/packaging.html?lang=en) for more information.
* Access to Export datasets functionality, available when you have purchased the Real-Time CDP Prime or Ultimate package, Adobe Journey Optimizer, or Customer Journey Analytics. See [Export datasets to cloud storage destinations](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en) for more information.
* One or more destinations (for example: Amazon S3, Google Cloud Storage) configured to where you can export the raw data of your data feed.


## Query service

Experience Platform Query Service allows you to query and join any dataset in Experience Platform data lake as if it is a database table. You then can capture the results as a new dataset for further use in reporting or for export.

You use the Query Service [user interface](https://experienceleague.adobe.com/docs/experience-platform/query/ui/overview.html?lang=en), a [client connected through the PostgresQL protocol](https://experienceleague.adobe.com/docs/experience-platform/query/clients/overview.html?lang=en), or [RESTful APIs](https://experienceleague.adobe.com/docs/experience-platform/query/api/getting-started.html?lang=en) to create and schedule queries that collect the data for your data feed. 

### Create Query

You can use all the functionality of standard ANSI SQL for SELECT statements and other limited commands to create and execute queries that generate the data for your data feed. See [SQL syntax](https://experienceleague.adobe.com/docs/experience-platform/query/sql/syntax.html?lang=en) for more information. Beyond this SQL syntax, Adobe supports:

* prebuilt [Adobe-defined functions (ADF)](https://experienceleague.adobe.com/docs/experience-platform/query/sql/adobe-defined-functions.html?lang=en) that help perform common business-related tasks on event data stored in Experience Platform data lake, including functions for [Sessionization](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-mobile-visit-processing.html?lang=en) and [Attribution](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/overview.html?lang=en),
* several built-in [Spark SQL functions](https://experienceleague.adobe.com/docs/experience-platform/query/sql/spark-sql-functions.html?lang=en),
* [metadata PostgreSQL commands](https://experienceleague.adobe.com/docs/experience-platform/query/sql/metadata.html?lang=en),
* [prepared statements](https://experienceleague.adobe.com/docs/experience-platform/query/sql/prepared-statements.html?lang=en).


#### Identities

In Experience Platform, various identities are available. When creating your queries, ensure you are querying identities correctly. 

Often you find identities in a separate field group. In an implementation ECID (`ecid`) can be defined as part of a field group with a `core` object, which itself is part of an `identification` object. (for example: `_sampleorg.identification.core.ecid`). The ECIDs might be organized differently in your schemas.

Alternatively, you can use `identityMap` to query for identities. This object is of type `Map` and uses a [nested data structure](#nested-data-structure).


#### Data feed columns

The XDM fields you can use in your query depend on the schema definition on which your datasets are based. Ensure you do understand the schema underlying the dataset. 

To ease the mapping between the Data Feed columns and XDM fields, you should consider to include the [Adobe Analytics ExperienceEvent Template](https://github.com/adobe/xdm/blob/master/extensions/adobe/experience/analytics/experienceevent-all.schema.json) field group in your experience event schema. See [Best practices for data modeling](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/best-practices.html?lang=en) and more specifically [Adobe application schema field groups](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/best-practices.html?lang=en#adobe-application-schema-field-groups).

For example, in case you want to use *page name* as part of your data feed: 

* In Adobe Analytics Data Feed's UI, you would select **[!UICONTROL pagename]** as the column to add to your data feed definition. 
* In Query Service, you include `web.webPageDetails.name` from the `sample_event_dataset_for_website_global_v1_1` dataset (based on the **Sample Event Schema for Website (Gobal v1.1)** experience event schema) in your query. See the [Web Details schema field group](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/event/web-details.html?lang=en) for more information.

To understand the mapping between former Adobe Analytics data feed columns and XDM fields in your experience event dataset and underlying schema, see [Analytics fields mapping](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=en) and the [Adobe Analytics ExperienceEvent Full Extension schema field group](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/event/analytics-full-extension.html?lang=en) for more information.

Furthermore, the [automatically collected information by the Experience Platform Web SDK (out of the box)](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/automatic-information.html?lang=en) might be relevant to identify columns for your query.

#### Hit level data and identification

Based on the implementation, hit level data traditionally collected in Adobe Analytics is now stored as timestamped event data in Experience Platform. The following table is extracted from [Analytics field mapping](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=en#generated-mapping-fields) and shows examples how to map hit level specific Adobe Analytics Data Feed columns with corresponding XDM fields in your queries. The table also shows examples of how hits, visits and visitors are identified using XDM fields.

| Data feed column | XDM field | Type | Description |
|---|---|---|---|
| hitid_high + hitid_low | _id | string | A unique identifier to identify a hit. |
| hitid_low | _id | string | Used in conjunction with hitid_high to uniquely identify a hit. |
| hitid_high | _id | string | Used in conjunction with hitid_high to uniquely identify a hit. |
| hit_time_gmt | receivedTimestamp | string | The timestamp of the hit, based in Unix time. |
| first_hit_time_gmt | _experience.analytics.endUser.firstTimestamp | string | Timestamp of the very first hit of the visitor in Unix time. |
| cust_hit_time_gmt | timestamp | string | This is only used in timestamp-enabled datasets. This is the timestamp sent with the it, based on Unix time. |
| visid_high + visid_low | identityMap | object | A unique identifier for a visit. |
| visid_high + visid_low | endUserIDs._experience.aaid.id | string | A unique identifier for a visit. |
| visid_high | endUserIDs._experience.aaid.primary | boolean | Used in conjunction with visid_low to uniquely identify a visit. |
| visid_high | endUserIDs._experience.aaid.namespace.code | string | Used in conjunction with visid_low to uniquely identify a visit. |
| visid_low | identityMap | object | Used in conjunction with visid_high to uniquely identify a visit. |
| cust_visid | identityMap | object | The customer visitor I.D |
| cust_visid | endUserIDs._experience.aacustomid.id | object | The customer visitor ID. |
| cust_visid | endUserIDs._experience.aacustomid.primary | boolean | The customer visitor ID namespace code. |
| cust_visid | endUserIDs._experience.aacustomid.namespace.code | string | Used in conjunction with visid_low to uniquely identify the customer visitor id. |
| geo\_* | placeContext.geo.* | string, number | Geolocation data, like country, regio, city, and others |
| visit_page_num | _experience.analytics.session.depth | number | A variable used in the Hit Depth dimension. This value increases by 1 for each hit the user generates, and resets after each visit. |
| event_list | commerce.purchases, commerce.productViews, commerce.productListOpens, commerce.checkouts, commerce.productListAdds, commerce.productListRemovals, commerce.productListViews, \_experience.analytics.event101to200.*, ..., \_experience.analytics.event901_1000.\* | string | Standard commerce and custom events triggered on the hit. |
| page_event | web.webInteraction.type | string | The type of hit that is sent in the image request (standard hit, download link, exit link, or custom link clicked). |
| page_event | web.webInteraction.linkClicks.value | number | The type of hit that is sent in the image request (standard hit, download link, exit link, or custom link clicked). |
| page_event_var_1 | web.webInteraction.URL | string | A variable that is only used in link tracking image requests. This variable contains the URL of the download link, exit link, or custom link clicked. |
| page_event_var_2 | web.webInteraction.name | string | A variable that is only used in link tracking image requests. This lists the custom name of the link, if it is specified. |
| first_hit_ref_type | _experience.analytics.endUser.firstWeb.webReferrer.type | string |  The numeric ID, representing the referrer type of the very first referrer of the visitor. |
| first_hit_time_gmt | _experience.analytics.endUser.firstTimestamp | integer | Timestamp of the very first hit of the visitor in Unix time. | 
| paid_search | search.isPaid | boolean | A flag that is set if the hit matches paid search detection. |
| ref_type | web.webReferrertype | string | A numeric ID representing the type of referral for the hit. |

#### Post columns

Adobe Analytics Data Feeds use the concept of columns with a `post_` prefix, which are columns containing data after processing. See [Data feeds FAQ](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/df-faq.html?lang=en#post) for more information.

Data collected in datasets through the Experience Platform Edge Network (Web SDK, Mobile SDK, Server API) has no concept of `post_` fields, which explains why `post_` prefixed and *non* `post_` prefixed data feed columns in the Analytics field mapping map to the same XDM fields. For example, both `page_url` and `post_page_url` data feed columns map to the same `web.webPageDetails.URL` XDM field. 

See [Compare data processing across Adobe Analytics and Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/data-processing-comparisons.html?lang=en) for an overview of the difference in processing of data.

The `post_` prefix column type of data, when collected in Experience Platform data lake, does however require advanced transformations before it can successfully be used in a data feed use case. Performing these advanced transformations in your queries involves the use of [Adobe-defined functions](https://experienceleague.adobe.com/docs/experience-platform/query/sql/adobe-defined-functions.html?lang=en) for sessionization, attribution, and deduplication. See [Examples](#examples) on how to use these functions.

#### Lookups

To look up data from other datasets, you use standard SQL functionality (`WHERE` clause, `INNER JOIN`, `OUTER JOIN`, and others).

#### Calculations

To perform calculations on fields (columns), use the standard SQL functions (for example `COUNT(*)` or the [math and statistical operators and functions](https://experienceleague.adobe.com/docs/experience-platform/query/sql/spark-sql-functions.html?lang=en#math) part of Spark SQL. Additionally, [window functions](https://experienceleague.adobe.com/docs/experience-platform/query/sql/adobe-defined-functions.html?lang=en#window-functions) provide support to update aggregations and return single items for each row in an ordered subset. See [Examples](#examples) on how to use these functions.

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

You can use the [`explode()` or other Arrays functions](https://experienceleague.adobe.com/docs/experience-platform/query/sql/spark-sql-functions.html?lang=en#arrays) from Spark SQL to get to the data inside a nested data structure, for example:

```sql
select explode(identityMap) from demosys_cja_ee_v1_website_global_v1_1 limit 15;
```

Alternatively you can refer to individual elements using dot notation. For example:

```sql
select identityMap.ecid from demosys_cja_ee_v1_website_global_v1_1 limit 15;
```

See [Working with nested data structures in Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/key-concepts/nested-data-structures.html?lang=en) for more information.


#### Examples

For example queries that use data from datasets in the Experience Platform data lake, are tapping on the additional capabilities of Adobe Defined Functions and/or Spark SQL, and which would deliver similar results to an equivalent Adobe Analytics data feed, see

* [abandoned browse](https://experienceleague.adobe.com/docs/experience-platform/query/use-cases/abandoned-browse.html?lang=en), 
* [attribution analysis](https://experienceleague.adobe.com/docs/experience-platform/query/use-cases/attribution-analysis.html?lang=en), 
* [bot filtering](https://experienceleague.adobe.com/docs/experience-platform/query/use-cases/bot-filtering.html?lang=en),
* and other example use cases in the Query Service guide.


### Schedule Query

You schedule the query to ensure that the query is executed and that the results are generated at your preferred interval.

#### Using Query Editor

You can schedule a query using the Query Editor. When scheduling the query, you define an output dataset. See [Query schedules](https://experienceleague.adobe.com/docs/experience-platform/query/ui/query-schedules.html?lang=en) for more information.


#### Using Query Service API

Alternatively you can use the RESTful APIs to define a query and schedule for the query. See [Query Service API guide](https://experienceleague.adobe.com/docs/experience-platform/query/api/getting-started.html?lang=en) for more information.
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

