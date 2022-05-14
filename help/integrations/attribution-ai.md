---
description: Find out how AEP Attribution AI integrates with Workspace in CJA.
title: Integrate Attribution AI with CJA
role: Admin
solution: Customer Journey Analytics
---
# Integrate Attribution AI with CJA

[Attribution AI](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/attribution-ai/overview.html?lang=en), as part of Adobe Experience Platform Intelligent Services, is a multi-channel, algorithmic attribution service that calculates the influence and incremental impact of customer interactions against specified outcomes. With Attribution AI, marketers can measure and optimize marketing and advertising spend by understanding the impact of every individual customer interaction across each phase of the customer journeys. 

Attribution AI supports two categories of scores: algorithmic and rule-based. Algorithmic scores include incremental and influenced scores. Rule-based scores include First touch, Last touch, Linear, U-shaped, and Time-Decay.

Attribution AI integrates with Customer Journey Analytics (CJA) to the extent that Attribution AI runs models against data and then CJA imports the output of those models as a data set, which can then be integrated with the rest of your CJA data sets. Attribution AI-enabled datasets can be then be leveraged in data views and reporting in CJA.  

Attribution AI supports 3 Experience Platform schemas: Experience Event, Adobe Analytics, and Consumer Experience Event.

## Workflow

Some of the steps are performed in Adobe Experience Platform prior to working with the output in CJA.

### Download Attribution AI scores

1. In Experience Platform, download Attribution AI scores, as described [here](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/attribution-ai/getting-started.html?lang=en#downloading-attribution-ai-scores).
1. In Experience Platform, create an Attribution AI instance by selecting and mapping data, defining events, and training your data, as described [here](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/attribution-ai/user-guide.html).
1. In CJA, 

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
