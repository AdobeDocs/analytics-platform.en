---
title: Retain historical data when migrating to Customer Journey Analytics
description: Learn how to retain historical data when migrating to Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: yes
hidefromtoc: yes
---
# Step 5: Retain historical data when migrating to Customer Journey Analytics

+++The information on this page is part of a larger migration process. Expand this section to see where this information fits within the migration process. </br></br>You must complete all previous migration steps before continuing with the information on this page.

Before you continue with this section, first make sure you have completed all previous migration tasks.

The information on this page covers Step 5, as highlighted in the table below: 

| Migration task | Details |
|---------|----------|
| **Step 1: [Get started with the migration](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Learn the benefits of migrating to Adobe Analytics and the basic migration process. |
| **Step 2: [Choose the migration method](/help/getting-started/cja-migration/cja-migration-method.md)** | Various methods are available for migrating to Customer Journey Analytics. Choose the method that is best for your organization, depending on your organization's current Adobe Analytics environment and long-term goals. | 
| **Step 3: [Send data to Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | The process for sending data to Adobe Experience Platform differs depending on the migration method that you chose in Step 1. | 
| **Step 4: [Plan data mapping to the XDM schema](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [XDM schemas](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) are used in Adobe Experience Platform to describe the structure of data in a consistent and reusable way. By defining data consistently across systems, it becomes easier to retain meaning and therefore gain value from data.<p>Most migration methods require that you either create a new XDM schema, or map your existing Adobe Analytics schema to XDM by using datastream mapping.</p>  |
| <span class="preview">**Step 5: [Retain historical data](/help/getting-started/cja-migration/cja-migration-historical-data.md)**</span> | <span class="preview">Most organizations need to retain their historical Adobe Analytics data for a certain amount of time. Various options are available to accomplish this.</span>  | 
| **Step 6: [Plan user onboarding](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | You should give your users ample time (3 - 6 months) to become familiar with the key differences of Analysis Workspace in Customer Journey Analytics. | 
| **Step 7: [Port the reporting API usage](/help/getting-started/cja-migration/cja-migration-api.md)** | The Customer Journey Analytics reporting API is in the same format, but uses a different endpoint. Port the reporting API usage from the Adobe Analytics reporting API to the Customer Journey Analytics reporting API. | 
| **Step 8: [Replace Data Feeds and Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)** | Decide how you will use the export options available in Customer Journey Analytics in order to replace the Data Feeds and Data Warehouse features you were using in Adobe Analytics.  |
| **Step 9: [Migrate projects and components](/help/getting-started/cja-migration/cja-migration-projects.md)** | The Component migration area in Adobe Analytics allows you to migrate projects and their associated components from Adobe Analytics to Customer Journey Analytics.  |

{style="table-layout:auto"}

+++

Choose one of the following options to retain historical data when moving from Adobe Analytics to Customer Journey Analytics: 

## Utilize the Analytics Source Connector

  You can Utilize the [Analytics Source Connector](/help/data-ingestion/analytics.md) to retain historical data. Regardless of the migration method that you choose (even if you migrate using the Web SDK), you can use the Analytics Source Connector to retain historical data from your Adobe Analytics environment. 

  You can use the Analytics Source Connector to retain historical data in the following ways:
  
  * Bring historical data into its own dedicated location, separate from your current data.

  * Map historical data in a way that allows you to tie it to your new data. <!-- Possible? Explain -->

## Maintain your existing Adobe Analytics implementation

You can maintain your existing Adobe Analytics implementation alongside your new Customer Journey Analytics implementation for a specific time frame (for example, 1 year). When choosing this option, you must plan to decommission the Adobe Analytics implementation after you have sufficient data in Customer Journey Analytics. 

Contact your Adobe account representative to determine pricing for this option. 

## Next, plan user onboarding

[Plan user onboarding to Customer Journey Analytics](/help/getting-started/cja-migration/cja-migration-onboarding.md). You should give your users ample time (3 - 6 months) to become familiar with the key differences of Analysis Workspace in Customer Journey Analytics.
