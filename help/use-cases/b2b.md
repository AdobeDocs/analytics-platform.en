---
title: (B2B) Add account-level data as a lookup dataset
description: Learn how to add account-based data as a lookup dataset to CJA
exl-id: d345f680-b657-4b87-9560-a50fc59bb7a7
---
# (B2B) Add account-level data as a lookup dataset

This B2B use case shows you how to specify your data at an account level rather than at a person level for analysis. Account-level analysis can answer questions such as

* What company name is matched with this account?
* How many employees are associated with this account/company?
* What roles are represented in this account?
* How is this account performing as a whole with respect to a specific marketing campaign, compared to another account?
* Are certain roles (such as IT Manager) at one account behaving differently than the same role at a different account?

You accomplish all this by bringing in the account-level information as a [lookup](/help/getting-started/cja-glossary.md) dataset. 

You first create a lookup schema in Adobe Experience Platform, then create a lookup table data set by ingesting .csv-based account-level data. Then you proceed to create a connection in Customer Journey Analytics (CJA0 that combines different datasets, including the lookup one you created. You subsequently create a data view and finally are able to utilize all this data in Workspace.

>[!NOTE]
>
>Lookup tables can be up to 1 GB in size.

## 1. Create lookup schema (Experience Platform)

Creating your own schema for the [lookup](/help/getting-started/cja-glossary.md) table ensures that the dataset used will be available in CJA with the correct setup (record type). Best practice is to [create a custom schema class](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html#create-new-class) called “Lookup”, empty of any element, that can be re-used for all lookup tables.

![](assets/create-new-class.png)

## 2. Create lookup data set (Experience Platform)

Once the schema has been created, you need to create a lookup dataset from that schema, in Experience Platform. This lookup dataset contains account-level marketing information, such as: company name, total number of employees, domain name, what industry they belong to, annual revenue, whether they are current customers of the Experience Platform or not, which sales stage they are in, which team inside the account is using CJA, etc.

>[!IMPORTANT]
>
>CJA does not support integers in lookup datasets. If you add the integer fields in your XDM schema for your lookup dataset, you will not able to use those integers as metrics or calculated metrics. For example, if annualRevenue or totalEmployees are defined as integers, they will show as “0” in reporting in CJA. However, if you assign them as strings, you can use them as lookup information.
 
For example, annualRevenue or totalEmployees are defined as Integer in following example - that’s the reason it's showing “0” in CJA.

1. In Adobe Experience Platform, go to **[!UICONTROL Data Management > Datasets]**.
1. Click **[!UICONTROL + Create dataset]**.
1. Click **[!UICONTROL Create dataset from schema]**.
1. Select the Lookup Schema class you created.
1. Click **[!UICONTROL Next]**.
1. Name the dataset (in our example, B2B Info) and provide a description.
1. Click **[!UICONTROL Finish]**.

## 3. Ingest data into Experience Platform

Instructions on how to [Map a CSV file to an XDM schema](https://experienceleague.adobe.com/docs/experience-platform/ingestion/tutorials/map-a-csv-file.html) should help if you are using a CSV file.

[Other methods](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html) are available as well.

On-boarding the data and establishing the lookup takes about 2 to 4 hours, depending on the size of the lookup table.

## 4. Combine datasets in a connection (Customer Journey Analytics)

For this example, we are combining 3 datasets into one CJA connection:

| Dataset name | Description | AEP Schema class | Dataset details |
| --- | --- | --- | --- |
| B2B Impression | Contains clickstream, event-level data at the account level. For example, it contains the email ID and corresponding account ID, as well as the marketing name, for running marketing ads. It also includes the impressions for those ads, per user. | Based on XDM ExperienceEvent schema class | The `emailID` is used as the primary identity and assigned a `Customer ID` namespace. As a result, it will show up as the default **[!UICONTROL Person ID]** in Customer Journey Analytics. ![Impressions](assets/impressions-mixins.png) |
| B2B Profile | This profile dataset tells you more about the users in an account, such as their job title, which account they belong to, their LinkedIn profile, etc. | Based on XDM Individual Profile schema class | No need to select `emailID` as the primary ID in this schema. Make sure to enable **[!UICONTROL Profile]**; if you don't, CJA will not be able to connect the `emailID` in B2B Profile with the `emailID` in B2B Impression data. ![Profile](assets/profile-mixins.png) |
| B2B Info | See "Create lookup data set" above. | B2BAccount (custom lookup schema class) | The relationship between `accountID` and the B2B Impressions dataset has automatically been created by connecting the B2B Info dataset with the B2B Impression dataset in CJA, as described in the steps below. ![Lookup](assets/lookup-mixins.png) |

Here is how you combine the datasets:

1. In Customer Journey Analytics, select the **[!UICONTROL Connections]** tab.
1. Select the datasets (in our example, the three above) you want to combine.
1. For the B2B Info dataset, select the `accountID` key that will be used in your lookup table. Then select its matching key (corresponding dimension), also `accountID` in your event dataset.
1. Click **[!UICONTROL Next]**.
1. Name and describe the connection and configure it according to [these instructions](/help/connections/create-connection.md).
1. Click **[!UICONTROL Save]**. 

## 5. Create a data view from this connection

Follow instructions on [creating data views](/help/data-views/create-dataview.md).

* Add all the components (dimensions and metrics) that you need from the datasets.

## 6. Analyze the data in Workspace

You can now create Workspace projects based on the data from all 3 datasets.

For example, you can find answers to the answers posed in the introduction:

* Break down the emailID by accountID to figure out which company an email ID belongs to.
* How many employees are mapped to a specific account ID?
* What industry does an account ID belong to?

![](assets/project-lookup.png)
