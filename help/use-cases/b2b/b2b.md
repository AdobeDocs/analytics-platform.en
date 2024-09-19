---
title: Add account data as a lookup dataset
description: Learn how to add account data as a lookup dataset to Customer Journey Analytics
exl-id: d345f680-b657-4b87-9560-a50fc59bb7a7
solution: Customer Journey Analytics
feature: Use Cases
role: User
---
# Add account data as a lookup dataset

This B2B use case shows you how to add account data to a person-level and event-level analysis. When you add account data, you can answer questions such as:

* What company name is matched with this account?
* What roles are represented in this account?
* Are certain roles (such as IT Manager) at one account behaving differently than the same role at a different account?

To add account data information, you add and use a [lookup](/help/technotes/glossary.md) dataset that contains this information.

The steps involved are:

1. [Create a lookup schema](#create-lookup-schema) in Experience Platform.
1. [Create a lookup dataset](#create-lookup-dataset) in Experience Platform that allows you to ingest CSV-based account data. 
1. [Combine datasets in a connection](#combine-datasets-in-a-connection) in Customer Journey Analytics, including the lookup one you created. 
1. [Create a data view](#create-a-data-view-from-this-connection) in Customer Journey Analytics.
1. [Analyze this data](#analyze-the-data-in-workspace) in Workspace in Customer Journey Analytics.

>[!NOTE]
>
>Lookup tables can be up to 1 GB in size.
>

## Create lookup schema

When you create your own schema for the [lookup](/help/technotes/glossary.md) table, that schema ensures that the dataset used is available in Customer Journey Analytics with the correct setup (record type). The best practice is to [create a custom schema class](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/tutorials/create-schema-ui) that can be re-used for all lookup tables.

![Create New Class dialogue.](../assets/create-new-class.png)

## Create lookup dataset

Once the schema is created you need to create a lookup dataset, based on that schema, in Experience Platform. This lookup dataset contains the account information. For example: company name, total number of employees, domain name, what industry the company belongs to, annual revenue, and more. Ensure that the data contains a person identifier that can be matched with the person identifier used in the event data.

1. In Experience Platform, go to **[!UICONTROL Data Management > Datasets]**.
1. Click **[!UICONTROL + Create dataset]**.
1. Click **[!UICONTROL Create dataset from schema]**.
1. Select the Lookup Schema class that you created.
1. Click **[!UICONTROL Next]**.
1. Name the dataset (for example, `B2B Info`) and provide a description.
1. Click **[!UICONTROL Finish]**.

## Ingest data

Instructions on how to [Map a CSV file to an XDM schema](https://experienceleague.adobe.com/en/docs/experience-platform/ingestion/tutorials/map-csv/existing-schema) should help if you are using a CSV file.

[Other methods](https://experienceleague.adobe.com/en/docs/experience-platform/ingestion/home) are available as well.

On-boarding the data and establishing the lookup takes about 2 to 4 hours, depending on the size of the lookup table.

## Combine datasets in a connection

For this example, you combine 3 datasets into one Customer Journey Analytics connection:

| Dataset name | Description | Adobe Experience Platform Schema class | Dataset details |
| --- | --- | --- | --- |
| B2B Impression | Contains clickstream, event-level data at the account level. For example, it contains the email ID and corresponding account ID, as well as the marketing name, for running marketing ads. It also includes the impressions for those ads per user. | Based on the XDM ExperienceEvent schema class | The `emailID` is used as the primary identity and assigned a `Customer ID` namespace. As a result, it shows up as the default **[!UICONTROL Person ID]** in Customer Journey Analytics. ![Impressions](../assets/impressions-mixins.png) |
| B2B Profile | This profile dataset tells you more about the users in an account, such as their job title, which account they belong to, their LinkedIn profile, etc. | Based on XDM Individual Profile schema class | Select `emailID` as the primary ID in this schema. |
| B2B Info | See "Create lookup dataset" above. | B2B Account (custom lookup schema class) | The relationship between `accountID` and the B2B Impressions dataset is automatically created when you connect the B2B Info dataset with the B2B Impression dataset in Customer Journey Analytics, as described in the steps below. ![Lookup](../assets/lookup-mixins.png) |

Here is how you combine the datasets:

1. In Customer Journey Analytics, select the **[!UICONTROL Connections]** tab.
1. Select the datasets you want to combine.
1. For the B2B Info dataset, select the key that is used in your lookup table (for example `personKey.sourceKey`). Then select its matching key (corresponding dimension), also in your event dataset (for example p`ersonKey.sourceKey`).
1. Click **[!UICONTROL Next]**.
1. Name and describe the connection and configure it according to [these instructions](/help/connections/create-connection.md).
1. Click **[!UICONTROL Save]**. 

## Create a data view from this connection

Follow the instructions on [creating data views](/help/data-views/create-dataview.md).

* Add all the components (dimensions and metrics) that you need from the datasets. Ensure that for metrics that require deduplication for overcounting, you configure these metrics accordingly (see [Metric deduplication component settings](/help/data-views/component-settings/metric-deduplication.md)). Examples of such metrics are the number of employees or revenue.

## Analyze the data in Workspace

You can now create Workspace projects based on the data from all 3 datasets.

For example, you can find answers to the answers posed in the introduction:

* Break down the emailID by accountID to figure out which company an email ID belongs to.
* How many employees are mapped to a specific account ID?
* What industry does an account ID belong to?

>[!MORELIKETHIS]
>
>See [An example B2B project](example.md) for more details.

