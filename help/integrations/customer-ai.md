---
description: Find out how AEP Customer AI data integrates with Workspace in CJA.
title: Integrate Customer AI data with CJA
role: Admin
solution: Customer Journey Analytics
exl-id: 5411f843-be3b-4059-a3b9-a4e1928ee8a9
---
# Integrate Customer AI data with CJA

>[!NOTE]
>
>This functionality is currently in [limited testing](/help/release-notes/releases.md) and not generally available.

[Customer AI](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/overview.html?lang=en), as part of Adobe Experience Platform Intelligent Services, provides marketers with the power to generate customer predictions at the individual level.

With the help of influential factors, Customer AI can tell you what a customer is likely to do and why. Additionally, marketers can benefit from Customer AI predictions and insights to personalize customer experiences by serving the most appropriate offers and messaging.

Customer AI relies on individual behavioral data and profile data for propensity scoring. Customer AI is flexible in that it can take in multiple data sources, including Adobe Analytics, Adobe Audience Manager, Consumer Experience Event data and Experience Event data. If you use the Experience Platform source connector to bring in Adobe Audience Manager and Adobe Analytics data, the model automatically picks up the standard event types to train and score the model. If you bring in your own Experience Event dataset without standard event types, any relevant fields will need to be mapped as custom events or profile attributes if you'd like to use it in the model. This can be done in the Customer AI configuration step in Experience Platform. ​

Customer AI integrates with Customer Journey Analytics (CJA) to the extent that Customer AI-enabled datasets can be leveraged in data views and reporting in CJA. With this integration, you can

* **Track propensity scores for a segment of users over time**. Example use case: What is the likelihood of a hotel customer to purchase a show ticket at the hotel's concert venue? 
* **Analyze which success events or attributes are associated with propensity scores**. ​Example use case: I want to understand the attributes or success events associated with propensity scores.
* **Follow the entry flow for customer propensity over different scoring runs**. Example use case: I'd like to understand people who were initially low-propensity users and, over time, became high-propensity users.​
* **Look at the distribution of propensity**. Use case: I'd like to understand the distribution of the propensity scores to I can be more precise with my segments. ​Example: a retailer wants to run a specific promotion for $50 off a product. They may want to run only a very limited promotion due to budget, etc. They analyze the data and decide to target only the top 80%+​ of their customers.
* **Look at the propensity to accomplish an action for a particular cohort over time**. Use case: I'd like to track a specific cohort over time. This is similar to the first one, but you can track a specific cohort over time.​ Hospitality example: A marketer can track their bronze tier versus their silver tier, or silver tier versus their gold tier over time. Then they can see each cohort's propensity for booking the hotel over time. ​

Some of the steps are performed in Adobe Experience Platform prior to working with the output in CJA.

## Step 1: Configure a Customer AI instance

Once you have prepared your data and have all your credentials and schemas in place, start by following the [Configure a Customer AI Instance](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/user-guide/configure.html?lang=en) guide in Adobe Experience Platform. 

## Step 2: Set up a CJA connection to Customer AI datasets

In CJA, you can now [create one or more connections](/help/connections/create-connection.md) to Experience Platform datasets that have been instrumented for Customer AI. Each prediction, such as "Likelihood to upgrade account", equates to one dataset. These datasets appears with the "Customer AI Scores in EE Format – name_of_application" prefix.

>[!IMPORTANT]
>
>Each Customer AI instance has two output datasets if the toggle is turned on to enable scores for CJA during the configuration in Step 1. One output dataset appears in Profile XDM format and one in Experience Event XDM format.

![CAI scores](assets/cai-scores.png)

![Create connection](assets/create-conn.png)

Here is an example of an XDM schema that CJA would bring in as part of an existing or new dataset:

![CAI schema](assets/cai-schema.png)

(Note that the example is a profile dataset; the same set of schema object would be part of an Experience Event dataset that CJA would grab. The Experience Event dataset would include timestamps as the score date.) Every customer scored in this model would have a score, a scoreDate, etc. associated with them.

## Step 3: Create data views based on these connections

In CJA, you can now proceed to [create data views](/help/data-views/create-dataview.md) with the dimensions (such as score, score date, probability, and so on) and metrics that were brought in as part of the connection you established. 

![Create dataview](assets/create-dataview.png)

## Step 4: Report on CAI scores in Workspace

In CJA Workspace, create a new project and pull in visualizations. 

### Trend propensity scores

Here is an example of a Workspace project with CAI data that trends propensity scores for a segment of users over time, in ​a stacked bar chart:

![Score buckets](assets/workspace-scores.png)

### Table with reason codes

Here is a table that shows reason codes for why a segment has high or low propensity​:

![Reason codes](assets/reason-codes.png)

### Entry flow for customer propensity

This flow diagram shows the entry flow for customer propensity over different scoring runs​:

![Entry flow](assets/flow.png)

### Distribution of propensity scores

This bar chart shows the distribution of propensity scores​:

![Distribution](assets/distribution.png)

### Propensity overlaps

This Venn diagram shows the propensity overlaps over different scoring runs:

![Propensity overlaps](assets/venn.png)
