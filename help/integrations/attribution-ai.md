---
description: Find out how AEP Attribution AI integrates with Workspace in CJA.
title: Integrate Attribution AI with CJA
role: Admin
solution: Customer Journey Analytics
exl-id: 5ab563b9-d4f6-4210-8789-e16e5c93d968
---
# Integrate Attribution AI with CJA

>[!NOTE]
>
>This page is under construction.

[Attribution AI](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/attribution-ai/overview.html?lang=en), as part of Adobe Experience Platform Intelligent Services, is a multi-channel, algorithmic attribution service that calculates the influence and incremental impact of customer interactions against specified outcomes. With Attribution AI, marketers can measure and optimize marketing and advertising spend by understanding the impact of every individual customer interaction across each phase of the customer journeys. 

Attribution AI supports two categories of scores: algorithmic and rule-based. Algorithmic scores include incremental and influenced scores. Rule-based scores include First touch, Last touch, Linear, U-shaped, and Time-Decay. Attribution AI supports 3 Experience Platform schemas: Experience Event, Adobe Analytics, and Consumer Experience Event.

Attribution AI integrates with Customer Journey Analytics (CJA) to the extent that Attribution AI runs models against data and then CJA imports the output of those models as a data set, which can then be integrated with the rest of your CJA data sets. Attribution AI-enabled datasets can be then be leveraged in data views and reporting in CJA.  

## Workflow

Some of the steps are performed in Adobe Experience Platform prior to working with the output in CJA.

### Step 1: Download Attribution AI scores

In Adobe Experience Platform, download Attribution AI scores, as described [here](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/attribution-ai/getting-started.html?lang=en#downloading-attribution-ai-scores).

### Step 2: Create an Attribution AI instance

In Experience Platform, create an Attribution AI instance by selecting and mapping data, defining events, and training your data, as described [here](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/attribution-ai/user-guide.html).

### Step 3: Set up a CJA connection to Attribution AI datasets

In CJA, you can now [create one or more connections](/help/connections/create-connection.md) to Experience Platform datasets that have been instrumented for Attribution AI. These datasets appears with the "Attribution AI Scores" prefix, as shown here:

![AAI scores](assets/aai-scores.png)

### Step 4: Create data views based on these connections

In CJA, [create one or more data views](/help/data-views/create-dataview.md) that contain the AAi XDM fields. (Would be great to have a screenshot here.)

### Step 5: Report on AAI data in CJA Workspace 

Here is an example of a Workspace project with AAI data that shows...

## Differences between Attribution AI and Attribution IQ

So when should you use Attribution AI data versus [Attribution IQ](/help/analysis-workspace/attribution/overview.md), a native CJA capability? This table shows some of the differences in functionality:

| Functionality | Attribution AI | Attribution IQ |
| --- | --- | --- |
| Does fractional attribution | Yes | No |
| Allows users to adjust model | No | Yes |
| Does attribution across channels (Note: AAI does not use the same stitched data that CJA does.) | Yes | Yes |
| Includes incremental and influenced scores | Yes | No |
| Does ML modeling | Yes | Yes |
| Does ML modeling with predictions | Yes | No |

{style="table-layout:auto"}
