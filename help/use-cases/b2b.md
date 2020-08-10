---
title: (B2B) Add account-level data as a lookup dataset
description: Learn how to add account-based data as a lookup dataset to CJA
---

# (B2B) Add account-level data as a lookup dataset

This B2B use case shows you how to specify your data at an account level rather than a person level for analysis. Account-level analysis can answer questions such as

* What company name is matched with this account?
* How many employees are associated with this account/company?
* What roles are represented in this account?
* How is this account performing as a whole with respect to a specific marketing campaign, compared to another account?
* Are certain roles (such as IT Manager) at one account behaving differently than the same role at a different account?

You accomplish all this by bringing in the account-level information as a [lookup](/help/getting-started/cja-glossary.md) dataset (similar to classifications in traditional Adobe Analytics). 

You first create a lookup schema in Adobe Experience Platform, then create a lookup table data set by ingesting .csv-based account-level data. Then you proceed to create a connection CJA that combines different datasets, including the lookup one you created. You then create a dataview and finally are able to utilize all this data in Workspace.

>[!NOTE]
>
>Lookup tables can be up to 1 GB in size.

## 1. Create lookup schema (Experience Platform)

Creating your own schema for the [lookup](/help/getting-started/cja-glossary.md) table ensures that the dataset used will be available in CJA with the correct setup (record type). Best practice is to [create a custom schema class](https://docs.adobe.com/content/help/en/experience-platform/xdm/tutorials/create-schema-ui.html#create-new-class) called “Lookup”, empty of any element, that can be re-used for all lookup tables.

![](assets/create-new-class.png)

## 2. Create lookup data set (Experience Platform)

Once the schema has been created, you need to create a dataset from that schema, in AEP. This lookup dataset contains account-level marketing information, such as: company name, total number of employees, domain name, what industry they belong to, annual revenue, whether they are current customers of the Experience Platform or not, which sales stage they are in, which team inside the account is using CJA, etc.

## 3. Combine datasets in a connection (Customer Journey Analytics)

Select the key that will be used in your lookup table. Then select its corresponding dimension in your dataset that you will realize the lookup with.

For this use case, we are combining 3 datasets into one CJA connection:

|Dataset name|Description|AEP Schema class |Mixins|
|---|---|---|---|
|B2B Impression| Contains clickstream, event-level data at the account level. For example, it contains the email ID and corresponding account ID, as well as the marketing name, for running marketing ads. It also includes the impressions for those ads, per user. | Based on XDM ExperienceEvent schema class |The `emailID` is used as the primary identity and assigned a `Customer ID` namespace. ![Impressions](assets/impressions-mixins.png)|
| B2B Profile | This profile dataset tells you more about the users in an account, such as their job title, which account they belong to, their LinkedIn profile, etc. | Based on XDM Individual Profile schema class |No need to select `emailID` as the primary ID in this schema. Make sure to enable **[!UICONTROL Profile]**; if you don't, CJA will not be able to connect the `emailID` in B2B Profile with the `emailID` in B2B Impression data. (This capability is called field-based stitching.) ![Profile](assets/profile-mixins.png)|
| B2B Info | See "Create lookup data set" above. | B2BAccount (custom lookup schema class)||

## Analyze the data in Workspace

On-boarding the data and establishing the lookup takes about 2 to 4 hours, depending on the size of the lookup table. 

You can then utilize the classified lookup data in Workspace as usual.

screenshot
