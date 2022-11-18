---
title: Utilizing Adobe Analytics report suite data in Customer Journey Analytics
description: How to configure Adobe Analytics report suites for ingestion into AEP and CJA
role: User
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: tbd
---

# Utilizing Adobe Analytics report suite data in Customer Journey Analytics

Adobe Analytics customers can easily leverage their report suites in the Adobe Experience Platform and Customer Journey Analytics using the [Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=en). The following discussion explains how to do so.

## Preparation

As you get ready to start using Adobe Analytics report suites in AEP and CJA, there are several ideas you should consider to prepare your data for a seamless move to Customer Journey Analytics. Please review the following page for more information:

* [Adobe Analytics to Customer Journey Analytics evolution](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/aa-to-cja.html?lang=en)

## Set up report suites for ingestion into the Adobe Experience Platform and CJA

Once you have prepared your data you are ready to start configuring report suites for use in AEP and CJA. 

1. **Create a dataflow for each report suite you wish to use in AEP and CJA.** The [Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=en) is the tool which allows you to create "dataflows" which forward Adobe Analytics report suite data into AEP. You will use the source connector to create one dataflow for each report suite you want to use in AEP. The dataflow creates a copy of your report suite that will be formatted in [XDM](https://experienceleague.adobe.com/docs/platform-learn/tutorials/schemas/schemas-and-experience-data-model.html?lang=en) for consumption by AEP applications including CJA. Each report suite configured with a dataflow via the source connector is stored as a separate dataset in the AEP data lake. 

Schema...
Filters applied during ADC...

2. Use dataprep to help you combine report suites in CJA.
3. Create one or more CJA connections
4. Create one or more CJA data views


## Comparing Customer Journey Analytics and Adobe Analytics

Customer Journey Analytics and Adobe Analytics have a number of similarities. For example, both CJA and Adobe Analytics offer the power of Analysis Workspace for freeform speed-of-thought analysis. However, since CJA is an application within the Adobe Experience Platform and utilizes AEP for data ingestion, CJA and Adobe Analytics differ in  a number of important ways. The following articles are helpful for understanding these differences:

* [Customer Journey Analytics feature support](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/compare-aa-cja/cja-aa.html?lang=en)
* [Compare terminology for Analytics data passed through the Analytics Source Connector](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/compare-aa-cja/terminology.html?lang=en)
* [Compare data processing across Adobe Analytics and CJA reporting features](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/compare-aa-cja/data-processing-comparisons.html?lang=en)
* [Virtual Report Suites, Data Views, AEP Sandboxes and the Analytics Source Connector](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/compare-aa-cja/vrs-dataview-sandbox-adc.html?lang=en)
* [Processing rules, VISTA and classifications versus Data Prep](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/compare-aa-cja/pr-vista-dataprep.html?lang=en)
* [AAID, ECID, AACUSTOMID and the Analytics Source Connector](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/compare-aa-cja/aaid-ecid-adc.html?lang=en)
