---
description: Learn how to prepare to map data feed columns from Adobe Analytics to Customer Journey Analytics.
keywords: clickstream;data feed;datafeed;Data Feed
title: Prepare to Map Data Feed Columns from Adobe Analytics to Customer Journey Analytics
feature: Data Feeds
hide: yes
hidefromtoc: yes
---
# Prepare to map data feed columns from Adobe Analytics to Customer Journey Analytics

When transitioning from Adobe Analytics data feeds to Customer Journey Analytics data feeds, it's natural to want to map every Adobe Analytics data feed column to a data feed column in Customer Journey Analytics.

However, mapping data feed columns from Adobe Analytics to Customer Journey Analytics is rarely a one-to-one mapping. This is due to the following factors:

* **[Schema architecture](#schema-architecture)**: Adobe Analytics data feed columns are derived from Analytics variables, while Customer Journey Analytics data feed columns are derived from XDM schema fields in Experience Platform and data view components in Customer Journey Analytics.

* **[Implementation type](#implementation-type)**: Adobe Analytics and Customer Journey Analytics each support multiple implementation configurations. The steps required to map individual fields depend on these implementations.

* **[Data processing](#data-processing)**: Fundamental data processing differences exist between Adobe Analytics and Customer Journey Analytics.

* **[Unused columns](#unused-columns)**: Adobe Analytics contains more than 1,100 data feed columns. Identify which of these columns your organization uses so you can plan to map only the needed columns.

Before you begin mapping Adobe Analytics data feed columns to Customer Journey Analytics data feed columns, review the sections below to better understand these key factors that affect mapping.

After you review this information, follow the mapping instructions for each Adobe Analytics data feed column that you plan to keep in Customer Journey Analytics, as described in [Data column reference](/help/components/exports/cja-data-feeds/c-df-contents/datafeeds-reference.md).

## Schema architecture

The Experience Data Model (XDM) schema, together with data views used in Customer Journey Analytics, is more flexible than the Adobe Analytics variable-based model. As such, your organization's XDM schema likely does not contain fields that translate to one-to-one data feed column mappings. 

Consider the following points about schema architecture:

* A lack of one-to-one column mappings does not mean that your Customer Journey Analytics XDM schema is insufficient. Rather, it means that you first need to determine which Adobe Analytics data feed columns you currently use, then map only those columns to Customer Journey Analytics data feeds.

* The Customer Journey Analytics XDM schema supports cross-channel data (such as call center data), which is not available in Adobe Analytics. These cross-channel fields are examples of new columns that can be included in Customer Journey Analytics data feeds that aren't supported in Adobe Analytics.

* Fields are eligible for inclusion in a Customer Journey Analytics data feed only after they are included in the XDM schema in Experience Platform, then curated for use within the data view in Customer Journey Analytics. 

  For detailed information about this process for each potential Adobe Analytics data feed column, see [Data column reference](/help/components/exports/cja-data-feeds/c-df-contents/datafeeds-reference.md).

>[!TIP]
>
>If possible, consult the team or individual who architected the XDM schema for your organization's Customer Journey Analytics implementation. Many of the decisions about which Adobe Analytics fields were needed in Customer Journey Analytics were made when the XDM schema was created. For more information, see [Architect your schema for use with Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md).

## Implementation type

<!--  tons of different AA implementations + tons of different CJA schemas -->

The number of fields that are available to map to in your Customer Journey Analytics XDM schema can differ depending on how data is collected for your Customer Journey Analytics implementation, as follows:

* **New Web SDK implementations**: If your Customer Journey Analytics implementation uses a custom schema, many columns that exist in Adobe Analytics data feeds likely do not exist in Customer Journey Analytics. Likewise, Customer Journey Analytics may contain fields that don't exist in Adobe Analytics data feeds. 

* **Analytics Source Connector implementations**: One-to-one field mappings exist by default for many data feed columns because the Analytics Source Connector uses the Analytics Experience Event field group in the XDM schema. For information about which Adobe Analytics fields map to fields in this field group, see [Analytics field mappings](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics) in the Exprience Platform documentation.

<!-- **Data layer**: ??? -->

## Data processing

Data processing differs between Adobe Analytics and Customer Journey Analytics, as follows:

**Adobe Analytics**: Many data feed fields are exported as two separate columns: one containing pre-processed data and another containing post-processed data. (Post-processed data includes server-side logic, processing rules, VISTA rules, dimension persistence rules, and so forth.)

Because Adobe Analytics exports data for some fields in two separate columns (one for pre-processed data and one for post-processed data), Adobe Analytics contains more data feed columns than Customer Journey Analytics. Keep this in mind when mapping fields.

**Customer Journey Analytics**: Fields are available for data feeds after they are created in the data view. Typically, fields in Customer Journey Analytics data views only include post-processed data. However, you can usually approximate the Adobe Analytics pre-processed version of a field by creating a second version of the field within the Customer Journey Analytics data view and configuring it to expire on hit.

## Unused columns

There are over 1,100 data feed columns available to be exported in Adobe Analytics. Of those columns, not all will be used in your Customer Journey Analytics data feeds.

To determine which columns to use:

* **Identify fields that apply only to Adobe Analytics**: Certain columns in Adobe Analytics data feeds are specific to the data processing engine for Adobe Analytics, and therefore don't apply to Customer Journey Analytics. Examples of such columns are `exclude_hit` and `hit_source`. 

* **Idendify fields that apply to your organization**: While not all Adobe Analytics customers export all of the available columns, many customers export more than they actually use. 

  Before you begin mapping data feed columns, identify which fields are actually being used throughout your organization. To gather this information, contact the teams or individuals who consume data feed content for Adobe Analytics.



<!--

1. View the data views throughout your organization to make sure that corresponding dimensions are available. If a corresponding dimension does not exist in the data view, create it.

   These are the dimensions that are being used for reporting in Analysis Workspace. Any Adobe Analytics data feed column needs to be mapped to a corresponding dimension that exists within a Customer Journey Analytics data view.

   

1. For each Adobe Analytics data feed field that is being used, ensure that a similar field exists in the XDM schema.

1. Verify that and that corresponding dimensions are available in the data view. If not, you need to create them. 

1. View the data views throughout your organization to see which dimensions are available. 

   These are the dimensions that are being used for reporting in Analysis Workspace. Any Adobe Analytics data feed column needs to be mapped to a corresponding dimension that exists within a Customer Journey Analytics data view. 

## Map data feed columns from Adobe Analytics to Customer Journey Analytics

### Step 1 - Map the default columns included in Customer Journey Analytics

There are roughly 20 default fields included in all WebSDK implementations. 

Before you can map these default columns, make sure that your Customer Journey Analytics environment meets the following prerequisites:

* It uses a WebSDK implementation.

* The appropriate field groups that contain the default WebSDK fields are added to your XDM schema.If the field is not added to your schema, it is included in the payload, but ultimately dropped.

* Each default field must be curated as a component in a Customer Journey Analytics data view.

* The component settings in the data view must be equivalent to how Analytics treats it (Visit persistence or hit-level persistence).

To map the default dimensions:

1. ...

1. ...

+++ View the Adobe Analytics data feed columns that are included by default

| Adobe Analytics column name | Column description | Data type |
| --- | --- | --- |
| **`accept_language`** | Lists all accepted languages, as indicated in the Accept-Language HTTP header in an image request. | char(20) |
| **`adload`** | Media ad loads | varchar(255) |
| **`aemassetid`** | A multi-value variable corresponding to Asset IDs (GUIDs) of a set of Adobe Experience Manager Assets. Increments Impression Events. | text |

+++

### Step 2: Discover which additional data feed columns your consumers use

There are over 1,100 data feed columns available to be exported in Adobe Analytics. While not all Adobe Analytics customers export all of the available columns, many customers export more than they actually use. 

Before you begin mapping data feed columns, you should first:

1. Contact the teams or individuals who consume data feed content and determine which data feed columns they use.

1. View the data views throughout your organization to see which dimensions are available. 

   These are the dimensions that are being used for reporting in Analysis Workspace. Any Adobe Analytics data feed column needs to be mapped to a corresponding dimension that exists within a Customer Journey Analytics data view. 


### Step 3 - Map each additional column

1. ...

1. ...

+++ View the Adobe Analytics data feed columns that could be mapped if they are included in your schema and data views

| Adobe Analytics column name | Column description | Data type |
| --- | --- | --- |
| **`accept_language`** | Lists all accepted languages, as indicated in the Accept-Language HTTP header in an image request. | char(20) |
| **`adload`** | Media ad loads | varchar(255) |
| **`aemassetid`** | A multi-value variable corresponding to Asset IDs (GUIDs) of a set of Adobe Experience Manager Assets. Increments Impression Events. | text |

+++

Notes below here. Ignore:

Do we group these columns by if you're using the WebSDK, or if you're using specific field groups.

Here's what is in Analytics, and here's what it maps to in CJA. Customers want us to "give them the mappings."

Some of these fields there is probably something like it that you could get in WebSDK. There will be some fields that aren't. Or some that are in AEP that aren't in here (like call center data).

We have an XDM field mappings to Analytics variables. "Adobe analytics XDM Var - first hit on Google." If you set your XDM payload to the given field on the left, it will automatically be associated to the Analytics variable on the right. But we're looking for a reverse mapping of this. 









If you're using ADC, you'll have the AA column name in there. We also have an ADC mapping doc page. (Analytics field mappings doc page maps the fields)



Make a table (or a section) that talks about fields that are new to CJA, like cross-channel fields (call center, etc.) 

The number of AA columns that they can map is not going to be that big (maybe 100). The number of columns that don't map will be huge.

## Data feed column reference

### Adobe Analytics data feed columns that are included by default in Customer Journey Analytics WebSDK implementations

### Adobe Analytics data feed columns that can be included in Customer Journey Analytics data feed

### Adobe Analytics data feed columns that don't apply to Customer Journey Analytics


### Columns, descriptions, and data types

Use this section to learn what data is contained in each column. Most implementations don't use every column, so this section can be referenced when determining which columns to include in a data feed export.

-->
