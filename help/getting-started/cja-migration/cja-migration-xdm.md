---
title: Map data to the XDM schema when migrating to Customer Journey Analytics
description: Learn how to map data to the XDM schema when migrating to Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: yes
hidefromtoc: yes
exl-id: 86ce60cf-b3c7-43b5-aa18-9e16fa942e54
---
# Step 4: Map data to the XDM schema when migrating to Customer Journey Analytics

+++Expand this section to see where the information on this page fits into the larger migration process. Make sure all previous migration steps are complete.

Before you continue with this section, first make sure you have completed all previous migration tasks.

The information on this page covers Step 4, as highlighted in the table below: 

| Migration task | Details |
|---------|----------|
| **Step 1: [Get started with the migration](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Learn the benefits of migrating to Adobe Analytics and the basic migration process. |
| **Step 2: [Choose the migration method](/help/getting-started/cja-migration/cja-migration-method.md)** | Various methods are available for migrating to Customer Journey Analytics. Choose the method that is best for your organization, depending on your organization's current Adobe Analytics environment and long-term goals. | 
| **Step 3: [Send data to Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | The process for sending data to Adobe Experience Platform differs depending on the migration method that you chose in Step 1. | 
| <span class="preview">**Step 4: [Map data to the XDM schema](/help/getting-started/cja-migration/cja-migration-xdm.md)**</span> | <span class="preview">[XDM schemas](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) are used in Adobe Experience Platform to describe the structure of data in a consistent and reusable way. By defining data consistently across systems, it becomes easier to retain meaning and therefore gain value from data.<p>Most migration methods require that you either create a new XDM schema, or map your existing Adobe Analytics schema to XDM by using datastream mapping.</p></span>  |
| **Step 5: [Retain historical data](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | Most organizations need to retain their historical Adobe Analytics data for a certain amount of time. Various options are available to accomplish this.  | 
| **Step 6: [Plan user onboarding](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | You should give your users ample time (3 - 6 months) to become familiar with the key differences of Analysis Workspace in Customer Journey Analytics. | 
| **Step 7: [Port the reporting API usage](/help/getting-started/cja-migration/cja-migration-api.md)** | The Customer Journey Analytics reporting API is in the same format, but uses a different endpoint. Port the reporting API usage from the Adobe Analytics reporting API to the Customer Journey Analytics reporting API. | 
| **Step 8: [Replace Data Feeds and Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)** | Decide how you will use the export options available in Customer Journey Analytics in order to replace the Data Feeds and Data Warehouse features you were using in Adobe Analytics.  |
| **Step 9: [Migrate projects and components](/help/getting-started/cja-migration/cja-migration-projects.md)** | The Component migration area in Adobe Analytics allows you to migrate projects and their associated components from Adobe Analytics to Customer Journey Analytics.  |

{style="table-layout:auto"}

+++

Not all migration methods require that you map your Adobe Analytics data to the XDM schema. The following table shows which implementation methods require XDM schema mapping:
 

| Migration method | XDM mapping required? | More information |
|---------|----------|---------|
| **New implementation of the Web SDK**<p>The basic steps are:</p><ol><li>Create an XDM schema for your organization</li><li>Implement the Web SDK</li><li>Send data to Platform</li></ol>| No | A mapping is not required because you already [set up a new XDM schema](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema) as part of the new implementation. |
| **Migrate your Adobe Analytics implementation to use the Web SDK**<p>The basic steps are:</p><ol><li>Move your existing Adobe Analytics implementation to the Web SDK and validate that everything is working there.</li><li>Create an XDM schema for your organization as you have time.</li><li>Use Data stream mapping to map all of the fields in the data object to your XDM schema.</li><li>Send data to Platform</li></ol> | Yes | Working with your data team, identify your organization's ideal schema design for Customer Journey Analytics, then determine how you will map eVars and Props to XDM.</br>[Use Data Prep to map all of the fields in the data object to your XDM schema](https://experienceleague.adobe.com/en/docs/experience-platform/data-prep/home) |
| **Configure your existing Adobe Analytics Web SDK implementation to send data to Customer Journey Analytics**<p>The basic steps are:</p><ol><li>Begin sending data to Customer Journey Analytics.<!-- What's involved here? Just point it at CJA? --></li><li>(Optional) Create an XDM schema for your organization as you have time.</li><li>Use Data stream mapping to map all of the fields in the data object to your XDM schema.</li></ol>  | Yes | Working with your data team, identify your organization's ideal schema design for Customer Journey Analytics, then determine how you will map eVars and Props to XDM.</br>[Use Data Prep to map all of the fields in the data object to your XDM schema](https://experienceleague.adobe.com/en/docs/experience-platform/data-prep/home) |
| **Analytics Source Connector**</br>If your Adobe Analytics implementation is AppMeasurement or the Analytics extension, you can begin sending data to a data view in Customer Journey Analytics.<p>This is the easiest way to get data to Customer Journey Analytics, but is the least viable method in the long term.</p>  | No | A mapping is not required because the Analytics Source Connector uses your existing Adobe Analytics schema rather than the XDM schema. |

{style="table-layout:auto"}

<!-- Does it benefit the customer to do this all at the same time if they're using multiple AEP apps? If so, have multiple sections like this. Or can they do CJA first and AJO later?

### Plan data mapping for Customer Journey Analytics


### Plan data mapping for Customer Journey analytics and other Adobe Experience platform applications

-->

## Next, retain historical data

Next, choose the method you will use to [retain historical Adobe Analytics data](/help/getting-started/cja-migration/cja-migration-historical-data.md).
