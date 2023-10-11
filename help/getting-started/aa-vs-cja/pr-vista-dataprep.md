---
title: Processing Rules, VISTA, and classifications vs. Data Prep for the Analytics source connector
description: Learn about data transformation using processing rules and VISTA vs. using Data Prep
exl-id: 049ad97e-0b4f-4163-a022-32661e48bf13
feature: Basics
---
# Processing rules, VISTA, and classifications versus Data Prep

Adobe Analytics [processing rules and VISTA rules](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/processing-rule-order.html?lang=en) provide a means to transform and manipulate data which is passed into Adobe Analytics [data collection](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/reporting-interface/overview-data-collection.html?lang=en). These transformations occur as a part of Adobe's data processing before the data is stored for reporting and analytics purposes in Adobe Analytics. 

[Data Prep](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=en) is a tool that lets you apply row-based mappings and transformations to data ingested into [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform.html?lang=en). Subsequently, the data is made available to Experience Platform applications including Customer Journey Analytics and others. Data prep is integrated with many of the Platform [source connectors](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=en), as well as with the [Analytics source connector](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en). This connector provides a way to ingest report suite data from Adobe Analytics into Platform. 

## Further transformation using Data Prep {#data-prep}

Data which is collected by and stored in Adobe Analytics can be transformed by either processing rules or VISTA rules or both. But report suites that are then forwarded to Platform via the Analytics source connector may be transformed yet another time using Data Prep. This can be desirable for a number of a number of purposes:

* **Resolving schema differences between report suites for use in Customer Journey Analytics and/or RTCDP**. For example, let's say report suite A defines `eVar1` as "Search Term" and report suite B defines `eVar2` as "Search Term". You can use data prep to map the two different eVars into a common field which contains data from both eVars. This makes it possible to [combine report suites with different schemas](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/combine-report-suites.html?lang=en) in a [Customer Journey Analytics connection](/help/connections/overview.md) or for use in [Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/application-services/rtcdp/understanding-the-real-time-customer-data-platform.html?lang=en).
* **Mapping `eVars` fields to semantically meaningful names**. `eVars` and `props` coming through the Analytics source connector are mapped to fields such as _\_experience.analytics.customDimensions.eVars.eVar1_. Data prep can be used to map `eVar` and `prop` fields to new fields that have more meaningful names for your users, or that match names coming from other data sources. (This can also be accomplished via other means, such as renaming the fields in a [Customer Journey Analytics data view](/help/data-views/create-dataview.md).)
* **Generally transforming data**. Data prep has hundreds of mapping functions that can be used to compute and calculate new fields based on the data coming through the Analytics source connector. You can split delimited fields into separate fields. You can combine fields. You can manipulate strings. You can extract information from a field based on regular expressions, and much more.

## Data Prep and classification {#classifications}

Data Prep has crossover with [classifications](https://experienceleague.adobe.com/docs/analytics/components/classifications/c-classifications.html?lang=en) in some situations. 

For example, in a delimited field you can use Data Prep to split that field into multiple individual fields without the use of classifications. Generally, classifications are a way to add metadata to a field by uploading a lookup file that is supplied outside the stream of incoming Analytics events. 

For example, you can upload a classification file which groups SKUs into 'size', 'brand', 'color', etc. Another difference between classifications and Data Prep is that classifications apply to data _both historically and going forward_. Data Prep mappings, on the other hand, are applied _forward_ to data from the time the mapping is created.
