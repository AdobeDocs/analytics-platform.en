---
title: Utilizing Adobe Analytics report suite data in Customer Journey Analytics
description: How to configure Adobe Analytics report suites for ingestion into Adobe Experience Platform and Customer Journey Analytics
role: User
solution: Customer Journey Analytics
feature: Basics
exl-id: db5506e0-6159-4d4b-8149-e4966dab9807
---
# Utilizing Adobe Analytics report suite data in Customer Journey Analytics

Adobe Analytics customers can easily leverage their report suites in the Adobe Experience Platform and Customer Journey Analytics using the [Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=en). The following discussion explains how to do so.

## Preparation

As you get ready to start using Adobe Analytics report suites in Adobe Experience Platform and Customer Journey Analytics, there are several things you should consider doing to prepare your data for a seamless move to Customer Journey Analytics. Please review the following page for more information:

* [Adobe Analytics to Customer Journey Analytics evolution](/help/getting-started/aa-to-cja.md)

## Set up report suites for ingestion into the Adobe Experience Platform and Customer Journey Analytics

Once you have prepared your data you are ready to start configuring report suites for use in Adobe Experience Platform and Customer Journey Analytics. 

1. **Create a dataflow for each report suite you wish to use in Adobe Experience Platform and Customer Journey Analytics.** The [Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=en) is the tool which allows you to [create a connection](/help/connections/create-connection.md) (a.k.a dataflow) between Adobe Analytics and Adobe Experience Platform. You will use the source connector to create one dataflow for each report suite you want to use in Adobe Experience Platform. The dataflow creates a copy of your report suite data where the schema has been converted to  [XDM](https://experienceleague.adobe.com/docs/platform-learn/tutorials/schemas/schemas-and-experience-data-model.html?lang=en) for consumption by Adobe Experience Platform applications including Customer Journey Analytics.<p>Each report suite configured with a dataflow via the source connector is stored as a separate dataset in the Adobe Experience Platform Data Lake. 13 months of historical report suite data will automatically be included with each dataflow, and new data will flow into Adobe Experience Platform on an ongoing basis. (Note that beginning April 26, 2023, the backfill in non-production sandboxes is limited to 3 months.) With the Analytics Source Connector you don't need to worry about creating the schema ahead of time. A standardized schema specific to Adobe Analytics is automatically created for you. However, Adobe Experience Platform [Data Prep](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=en) tool can be used to enhance this schema before the data is stored in Data Lake and made available to Customer Journey Analytics. Please note that certain types of data are filtered out by the source connector and will not be present in the dataset in Adobe Experience Platform Data Lake. Other rows may be filtered out between Data Lake and Customer Journey Analytics. See [Compare your Adobe Analytics data to Customer Journey Analytics data](/help/troubleshooting/compare.md) for more details.
1. **Use Data Prep to help you combine report suites in Customer Journey Analytics.** Data Prep can be used for many types of data transformation, and one common use for Adobe Analytics data is to resolve differences in prop and/or eVar mappings across multiple report suites so that report suites can easily be combined within Customer Journey Analytics. See [combine report suites with different schemas](/help/use-cases/aa-data/combine-report-suites.md) for more details.
1. **Enable Stitching** as necessary. When combining multiple datasets in Customer Journey Analytics, the stitching capabilities can help resolve different ID namespaces into a single stitched ID for a single view of the customer across devices and channels. See [Stitching overview](../../stitching/overview.md) for more details.
1. **Create one or more Customer Journey Analytics connections.** Once the datasets for your report suites are available in Adobe Experience Platform Data Lake, you can create one or more [Customer Journey Analytics connections](/help/connections/overview.md) to bring those datasets into Customer Journey Analytics. Within a connection, report suite data can be combined with other types of data, allowing you to create a true cross-channel view of customer experiences.
1. **Create one or more Customer Journey Analytics data views.** A [data view](/help/data-views/data-views.md) is a container specific to Customer Journey Analytics that lets you determine how to interpret data from a Customer Journey Analytics connection. Data views have many powerful [configuration options](/help/data-views/create-dataview.md) for customizing the data which is presented to your users within [Analysis Workspace](/help/analysis-workspace/home.md).

## Comparing Customer Journey Analytics and Adobe Analytics

Customer Journey Analytics and Adobe Analytics have a number of similarities. For example, both Customer Journey Analytics and Adobe Analytics offer the power of Analysis Workspace for freeform speed-of-thought analysis. However, since Customer Journey Analytics is an application within the Adobe Experience Platform and utilizes Adobe Experience Platform for data ingestion, Customer Journey Analytics and Adobe Analytics differ in  a number of important ways. The following articles are helpful for understanding these differences:

* [Compare your Adobe Analytics data to Customer Journey Analytics data](/help/troubleshooting/compare.md)
* [Customer Journey Analytics feature support](/help/getting-started/aa-vs-cja/cja-aa.md)
* [Compare terminology for Analytics data passed through the Analytics Source Connector](/help/getting-started/aa-vs-cja/terminology.md)
* [Compare data processing across Adobe Analytics and Customer Journey Analytics reporting features](/help/getting-started/aa-vs-cja/data-processing-comparisons.md)
* [Virtual Report Suites, Data Views, Adobe Experience Platform Sandboxes and the Analytics Source Connector](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)
* [Processing rules, VISTA and classifications versus Data Prep](/help/getting-started/aa-vs-cja/pr-vista-dataprep.md)
* [AAID, ECID, AACUSTOMID and the Analytics Source Connector](/help/getting-started/aa-vs-cja/aaid-ecid-adc.md)
