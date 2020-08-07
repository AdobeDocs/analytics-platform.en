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

You accomplish all this by first creating a lookup schema in Adobe Experience Platform, then creating a lookup table data set by ingesting .csv-based account-level data. Then you proceed to create a connection CJA that combines different datasets, including the lookup one you created. You then 


## 1. Create lookup schema (Experience Platform)


## 2. Create lookup data set (Experience Platform)

## 3. Combine datasets in a connection (Customer Journey Analytics)

For this use case, we are combining 3 datasets into one CJA connection:

* B2B Impression: contains clickstream, event-level data at the account level. For example, it contains the email ID and corresponding account ID, as well as the marketing name, for running marketing ads. It also includes the impressions for those ads, per user.
* B2B Profile: this profile dataset tells you more about the users in an account, such as their job title, which account hey belong to, their LinkedIn profile, 
* B2B Info: this lookup dataset contains account-level information, such as: company name, total number of employees, domain name, what industry they belong to, annual revenue, whether they are current customers of the 