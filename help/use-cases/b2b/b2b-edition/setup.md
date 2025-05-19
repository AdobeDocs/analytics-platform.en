---
title: B2B Edition Use Cases Setup
description: Learn about how to setup Customer Journey Analytics B2B Edition for typical B2B use cases.
solution: Customer Journey Analytics
feature: Use Cases
role: User
---
# Setup for B2B Edition use cases

This article covers a typical setup of the Customer Journey Analytics B2B Edition to support the following uses cases:

* [Optimize account marketing](optimize-account-marketing.md)
* [Grow key accounts](grow-key-accounts.md)
* [Build product value](build-product-value.md)

## Solution Design Reference

For the use cases, the following solution design reference is used.

+++ Event dimensions

| Dimension  name |
|---|
| Account ID |
| Account Name |
| Buying Group ID |
| Call Center |
| Call Center Representative ID |
| Call ID |
| Campaign Tracking Code |
| Content ID |
| Content Type |
| Data Source |
| Device Type |
| Event Details |
| Event Name |
| Funnel |
| Interaction Channel |
| Lead ID |
| Marketing Channel |
| Marketing Event ID |
| Marketing Event Type |
| Opportunity ID |
| Page |
| Page Details |
| Referring Domain |
| Sales Representative ID |
| Sales Stage Name |
| Sales Stage Number |
| Site Section |
| SKU |
| Subsidiary Account ID |
| Survey ID |
| Survey Satisfaction Score |
| Survey Type |
| User ID |

+++


+++ Event metrics

| Metric name | Event type |
|---|---|
| Account Creation: Complete | Counter | 
| Account Creation: Start | Counter | 
| Call Cost | Currency | 
| Call Length | Counter | 
| Call Satisfaction Score |  Numeric | 
| Call Surveys Completed |  Counter | 
| Calls | Counter | 
| Closed-Lost | Counter | 
| Closed-Won | Counter | 
| Content Views | Counter | 
| Deal Size Currency Display Click-throughs | Counter | 
| Display Impressions | Counter | 
| Email Bounced | Counter | 
| Email Clicked | Counter | 
| Email Delivered | Counter | 
| Email Opened | Counter | 
| Email Sent | Counter | 
| Event Attendance | Counter | 
| Event Registration: Complete | Counter | 
| Event Registration: Step 1 | Counter | 
| Event Registration: Step 2 | Counter | 
| Event Registration: Step 3 | Counter | 
| Global Satisfaction Score Numeric Inbound Call | Counter | 
| Lead Form: Complete | Counter | 
| Lead Form: Step 1 | Counter | 
| Lead Form: Step 2 | Counter | 
| Lead Generated | Counter | 
| Lead Qualification | Counter | 
| Meetings | Counter | 
| MQL Disqualified | Counter | 
| MQL Qualified | Counter | 
| Needs Assessment | Counter | 
| Negotiation | Counter | 
| Objection Handling | Counter | 
| Opportunities | Counter | 
| Opportunity Creation | Counter | 
| Orders | Counter | 
| Outbound Call | Counter | 
| Post-Sales Follow-Up | Counter | 
| Proposal Submission | Counter | 
| Revenue Closed-Lost | Currency |
| Revenue Closed-Won | Currency |
| Sales Contact Calls | Counter |
| Sales Stage Started | Counter |
| SMS Click-throughs | Counter |
| SMS Sent | Counter |
| Social Click-throughs | Counter |
| Social Impressions | Counter |
| Solution Presentation | Counter |
| SQL Disqualified | Counter |
| SQL Qualified|  Counter |
| Units (do not expose) | Counter |
| VoC Survey Satisfaction Score | Numeric |
| VoC Surveys Completed | Counter |

+++


+++ Person records

| Data view field name | Field type |
|---|---|
| Age | Metric | 
| Age Group | Dimension | 
| Category 1 Affinity Level | Dimension | 
| Category 1 Affinity Score | Metric | 
| Category 2 Affinity Level | Dimension | 
| Category 2 Affinity Score | Metric | 
| Category 3 Affinity Level | Dimension | 
| Category 3 Affinity Score | Metric | 
| Category 4 Affinity Level | Dimension | 
| Category 4 Affinity Score | Metric | 
| Category 5 Affinity Level | Dimension | 
| Category 5 Affinity Score | Metric | 
| Consent Advertising | Dimension | 
| Consent All Communications | Dimension | 
| Consent Direct Mail | Dimension | 
| Consent Email | Dimension | 
| Consent Mobile Phone | Dimension | 
| Consent Personalization | Dimension | 
| Consent Share Data | Dimension | 
| Consent SMS | Dimension | 
| Email | Dimension | 
| First Name | Dimension | 
| Gender | Dimension | 
| Individual City | Dimension | 
| Individual CLTV Level | Dimension | 
| Individual CLTV Score | Metric |
| Individual Country |  Dimension |
| Individual Phone | Dimension |
| Individual Postal Code | Dimension |
| Individual Propensity to Buy Level | Dimension |
| Individual Propensity to Buy Score | Metric |
| Individual Propensity to Churn Level | Dimension |
| Individual Propensity to Churn Score | Metric |
| Individual Propensity to Upgrade Level | Dimension |
| Individual Propensity to Upgrade Score | Metric |
| Individual State | Dimension |
| Individual Street Address | Dimension |
| Job Title | Dimension |
| Last Name | Dimension |
| Net Promoter Score | Metric |
| Net Promoter Status | Dimension |
| Role Type | Dimension |

+++

+++ Account records

| Data view field name | Field type |
|---|---|
| Annual Revenue | Metric | 
| Company City | Dimension | 
| Company CLTV Level | Dimension | 
| Company CLTV Score | Metric | 
| Company Country | Dimension | 
| Company Name | Dimension | 
| Company Phone Dimension |
| Company Postal Code | Dimension |
| Company Propensity to Buy Level | Dimension | 
| Company Propensity to Buy Score | Metric | 
| Company Propensity to Churn Level | Dimension | 
| Company Propensity to Churn Score | Metric | 
| Company Propensity to Upgrade Level | Dimension | 
| Company Propensity to Upgrade Score | Metric | 
| Company Size | Dimension | 
| Company State | Dimension | 
| Company Street Address | Dimension | 
| Industry | Dimension | 
| Number of Employees | Metric | 
| Partner Audience - Hardware Shoppers | Dimension | 
| Partner Audience - Rapid Growth | Dimension | 
| Partner Audience - Services Needed | Dimension | 
| Partner Audience - Software Shoppers | Dimension | 
| Revenue Range | Dimension | 
| Website | Dimension |

+++


+++ SKU records

| Data view field name | Field type |
|---|---|
| Hardware Product Category | Dimension |
| Hardware Product Name | Dimension |
| Service Category | Dimension |
| Service Name | Dimension |
| Software Product Category | Dimension |
| Software Product Name | Dimension |

+++

## Schemas and datasets

The data that supports the solution design reference is structured using the following schemas and datasets.

### Event data

The event dimensions and metrics are supported through an XDM Experience Event based schema and one or more datasets containing data. In the example, data is ingested into Experience Platform from the Analytics source connector. And evars and props are mapped to the relevant event dimensions and metrics. For example: `_experience.analytics.customDimensions.eVars.eVar1` is mapped to **[!UICONTROL Account ID]**. See below for a preview of the data typically available in such a dataset.

![B2B event schema and datasets](assets/b2b-event-schema-datasets.png)


### Person data

The person records are supported through a custom CJA_B2B_Person_ID_Lookup record based schema (based on a CID_personID_Lookup class and dedicated personData field group). See below for a preview of the data typically available in such a dataset. 

![B2B person schema and datasets](assets/b2b-person-schema-datasets.png)


### Account data

The account records are supported through a custom CJA_B2B_Account_ID_Lookup record based schema (based on a CID_accountID_Lookup class and dedicated accountData field group). See below for a preview of the data typically available in such a dataset. 

![B2B account schema and datasets](assets/b2b-account-schema-datasets.png)


### SKU data

The SKU records are supported through a custom CJA_B2B_SKU_Lookup record based schema (based on a CID_sku_Lookup class and skuData field group). See below for a preview of the data typically available in such a dataset. 


![B2B SKU schema and datasets](assets/b2b-sku-schema-datasets.png)


## Connection

You setup an account-based connection in Customer Journey Analytics to ingest and join records from event, account, person and SKU datasets.

