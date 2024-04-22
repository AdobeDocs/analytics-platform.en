---
title: Replace Data Feeds and Data Warehouse when migrating to Customer Journey Analytics
description: Plan your migration from Adobe Analytics to Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: yes
hidefromtoc: yes
exl-id: 3a99aed3-26b9-494f-aaf9-f8eaa2c2d88f
---
# Step 8: Replace Data Feeds and Data Warehouse when migrating to Customer Journey Analytics

+++Expand this section to see where the information on this page fits into the larger migration process. Make sure all previous migration steps are complete.

Before you continue with this section, first make sure you have completed all previous migration tasks.

The information on this page covers Step 8, as highlighted in the table below: 

| Migration task | Details |
|---------|----------|
| **Step 1: [Get started with the migration](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Learn the benefits of migrating to Adobe Analytics and the basic migration process. |
| **Step 2: [Choose the migration method](/help/getting-started/cja-migration/cja-migration-method.md)** | Various methods are available for migrating to Customer Journey Analytics. Choose the method that is best for your organization, depending on your organization's current Adobe Analytics environment and long-term goals. | 
| **Step 3: [Send data to Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | The process for sending data to Adobe Experience Platform differs depending on the migration method that you chose in Step 1. | 
| **Step 4: [Map data to the XDM schema](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [XDM schemas](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) are used in Adobe Experience Platform to describe the structure of data in a consistent and reusable way. By defining data consistently across systems, it becomes easier to retain meaning and therefore gain value from data.<p>Most migration methods require that you either create a new XDM schema, or map your existing Adobe Analytics schema to XDM by using datastream mapping.</p>  |
| **Step 5: [Retain historical data](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | Most organizations need to retain their historical Adobe Analytics data for a certain amount of time. Various options are available to accomplish this. | 
| **Step 6: [Plan user onboarding](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | You should give your users ample time (3 - 6 months) to become familiar with the key differences of Analysis Workspace in Customer Journey Analytics. | 
| **Step 7: [Port the reporting API usage](/help/getting-started/cja-migration/cja-migration-api.md)** | The Customer Journey Analytics reporting API is in the same format, but uses a different endpoint. Port the reporting API usage from the Adobe Analytics reporting API to the Customer Journey Analytics reporting API. | 
| <span class="preview">**Step 8: [Replace Data Feeds and Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)**</span> | <span class="preview">Decide how you will use the export options available in Customer Journey Analytics in order to replace the Data Feeds and Data Warehouse features you were using in Adobe Analytics.</span>  |
| **Step 9: [Migrate projects and components](/help/getting-started/cja-migration/cja-migration-projects.md)** | The Component migration area in Adobe Analytics allows you to migrate projects and their associated components from Adobe Analytics to Customer Journey Analytics.  |
| **Step 10: [Perform post-migration tasks](/help/getting-started/cja-getting-started.md)** | After you complete the migration, you need to perform various tasks, including bringing other data into Experience Platform, creating connections between Platform datasets and Customer Journey Analytics, creating data views, and learning how to report on cross-channel data in Analysis Workspace.  |

{style="table-layout:auto"}

+++

If you currently use Data Feeds or Data Warehouse in Adobe Analytics, use the following table to learn about the various export options available in Customer Journey Analytics:

| Adobe Analytics | Customer Journey Analytics | 
|---------|----------|
| Data Feeds | Assess your Data Feeds use cases, then use any combination of alternative export methods that are available in Customer Journey Analytics: <ul><li>To export raw datasets, [export datasets to cloud storage destinations](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets).​</li><li>For audience or event-level exports using Person ID or Timestamp, use [Full Table Export](/help/analysis-workspace/export/export-cloud.md).​</li><li>For direct integration with Power BI and Tableau, use the [Customer Journey Analytics BI Extension](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/bi-extension).​</li><li>For direct SQL access to data in Adobe Experience Platform, use the [Adobe Experience Platform Query Service](https://experienceleague.adobe.com/en/docs/experience-platform/query/home).</li></ul> | 
| Data Warehouse | Change Adobe Analytics Data Warehouse exports to use [Full Table Export](/help/analysis-workspace/export/export-cloud.md) in Customer Journey Analytics.<p>Customer Journey Analytics Full Table Export is the evolution of Data Warehouse reports in Adobe Analytics, with many new, often-requested features that are not available in Data Warehouse today.</p> | 

{style="table-layout:auto"}

## Next, migrate projects and components

Use the Component migration area in Adobe Analytics to [migrate projects and their associated components](/help/getting-started/cja-migration/cja-migration-projects.md) from Adobe Analytics to Customer Journey Analytics.
