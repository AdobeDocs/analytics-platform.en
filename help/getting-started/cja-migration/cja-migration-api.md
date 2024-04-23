---
title: Port the reporting API usage when migrating to Customer Journey Analytics
description: Learn how to port API usage from Adobe Analytics to Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: yes
hidefromtoc: yes
exl-id: d26a6956-870f-44f2-9c32-f732bff17737
---
# Step 7: Port the reporting API usage when migrating to Customer Journey Analytics

+++Expand this section to see where the information on this page fits into the larger migration process. Make sure all previous migration steps are complete.

Before you continue with this section, first make sure you have completed all previous migration tasks.

The information on this page covers Step 7, as highlighted in the table below: 

| Migration task | Details |
|---------|----------|
| **Step 1: [Get started with the migration](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Learn the benefits of migrating to Adobe Analytics and the basic migration process. |
| **Step 2: [Choose the migration path](/help/getting-started/cja-migration/cja-migration-path.md)** | Various methods are available for migrating to Customer Journey Analytics. Choose the method that is best for your organization, depending on your organization's current Adobe Analytics environment and long-term goals. | 
| **Step 3: [Send data to Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | The process for sending data to Adobe Experience Platform differs depending on the migration path that you chose in Step 2. | 
| **Step 4: [Retain historical data](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | Most organizations need to retain their historical Adobe Analytics data for a certain amount of time. Various options are available to accomplish this. | 
| **Step 5: [Perform additional implementation tasks](/help/getting-started/cja-getting-started.md)** | At this point in the migration process, you need to perform various tasks before your Customer Journey Analytics environment is ready to use.<p>These additional tasks apply to migrations from Adobe Analytics as well as new Customer Journey Analytics implementations.</p><p>These tasks include:</p><ul><li>Bringing other data into Experience Platform</li><li>Creating connections between Platform datasets and Customer Journey Analytics</li><li>Creating data views</li><li>Porting the reporting API usage</li><li>Accounting for Data Feeds and Data Warehouse</li><li>Migrating projects and components</li><li>Planning user onboarding</li></ul> <p>For more information, see [Customer Journey Analytics Getting Started](/help/getting-started/cja-getting-started.md).  |

{style="table-layout:auto"}

+++

Port the reporting API usage from the Adobe Analytics reporting API to the Customer Journey Analytics reporting API. 

The Customer Journey Analytics reporting API is in the same format, but uses a different subdomain.

See the endpoint guide for Adobe Analytics and Customer Journey Analytics. 

Most API calls can be easily translated from Adobe Analytics to Customer Journey Analytics.

Add the Customer Journey Analytics API to their API project. 

Add the IMS org id to the header of their API calls. 

cja.adobe.io vs. analytics.adobe.io

Additional headers

## Next, replace Data Feeds and Data Warehouse

Decide how you will use the export options available in Customer Journey Analytics in order to [replace the Data Feeds and Data Warehouse features](/help/getting-started/cja-migration/cja-migration-export-options.md) you were using in Adobe Analytics.
