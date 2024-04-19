---
title: Plan your migration from Adobe Analytics to Customer Journey Analytics
to Customer Journey Analytics
description: Plan your migration from Adobe Analytics to Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
---
# Replace Data Feeds and Data Warehouse

If you currently use Data Feeds or Data Warehouse in Adobe Analytics, use the following table to learn about the various export options available in Customer Journey Analytics:

| Adobe Analytics | Customer Journey Analytics | 
|---------|----------|
| Data Feeds | Assess your Data Feeds use cases, then use any combination of alternative export methods that are available in Customer Journey Analytics: <ul><li>To export raw datasets, [export datasets to cloud storage destinations](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets).​</li><li>For audience or event-level exports using Person ID or Timestamp, use [Full Table Export](/help/analysis-workspace/export/export-cloud.md).​</li><li>For direct integration with Power BI and Tableau, use the [Customer Journey Analytics BI Extension](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/bi-extension).​</li><li>For direct SQL access to data in Adobe Experience Platform, use the [Adobe Experience Platform Query Service](https://experienceleague.adobe.com/en/docs/experience-platform/query/home).</li></ul> | 
| Data Warehouse | Change Adobe Analytics Data Warehouse exports to use [Full Table Export](/help/analysis-workspace/export/export-cloud.md) in Customer Journey Analytics.<p>Customer Journey Analytics Full Table Export is the evolution of Data Warehouse reports in Adobe Analytics, with many new, often-requested features that are not available in Data Warehouse today.</p> | 

{style="table-layout:auto"}