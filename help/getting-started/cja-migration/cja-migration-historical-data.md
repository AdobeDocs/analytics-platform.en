---
title: Retain historical data when migrating to Customer Journey Analytics
description: Learn how to retain historical data when migrating to Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: yes
hidefromtoc: yes
exl-id: 1d17151b-3a12-468e-9a4f-9e5994599570
---
# Step 5: Retain historical data when migrating to Customer Journey Analytics

+++Expand this section to see where the information on this page fits into the larger migration process. Make sure all previous migration steps are complete.

Before you continue with this section, first make sure you have completed all previous migration tasks.

The information on this page covers Step 4, as highlighted in the table below: 

| Migration task | Details |
|---------|----------|
| **Step 1: [Get started with the migration](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Learn the benefits of migrating to Adobe Analytics and the basic migration process. |
| **Step 2: [Choose the migration path](/help/getting-started/cja-migration/cja-migration-path.md)** | Various methods are available for migrating to Customer Journey Analytics. Choose the method that is best for your organization, depending on your organization's current Adobe Analytics environment and long-term goals. | 
| **Step 4: [Send data to Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | The process for sending data to Adobe Experience Platform differs depending on the migration path that you chose in Step 2. | 
| <span class="preview">**Step 4: Retain historical data**</span> | <span class="preview">Most organizations need to retain their historical Adobe Analytics data for a certain amount of time. Various options are available to accomplish this.</span> | 
| **Step 5: [Perform additional implementation tasks](/help/getting-started/cja-getting-started.md)** | At this point in the migration process, you need to perform various tasks before your Customer Journey Analytics environment is ready to use.<p>These additional tasks apply to migrations from Adobe Analytics as well as new Customer Journey Analytics implementations.</p><p>These tasks include:</p><ul><li>Bringing other data into Experience Platform</li><li>Creating connections between Platform datasets and Customer Journey Analytics</li><li>Creating data views</li><li>Porting the reporting API usage</li><li>Accounting for Data Feeds and Data Warehouse</li><li>Migrating projects and components</li><li>Planning user onboarding</li></ul> <p>For more information, see [Customer Journey Analytics Getting Started](/help/getting-started/cja-getting-started.md).  |

{style="table-layout:auto"}

+++

Choose one of the following options to retain historical data when moving from Adobe Analytics to Customer Journey Analytics: 

>[!IMPORTANT]
>
>When choosing how to retain historical data, contact your Adobe account representative to determine pricing. 

## Utilize the Analytics Source Connector

  You can Utilize the [Analytics Source Connector](/help/data-ingestion/analytics.md) to retain historical data. Regardless of the migration path that you choose (even if you migrate using the Web SDK), you can use the Analytics Source Connector to retain historical data from your Adobe Analytics environment. 

  You can use the Analytics Source Connector to retain historical data in the following ways:
  
  * Bring historical data into its own dedicated location, separate from your current data.

  * Map historical data in a way that allows you to tie it to your new data. <!-- Possible? Explain -->

## Maintain your existing Adobe Analytics implementation

You can maintain your existing Adobe Analytics implementation alongside your new Customer Journey Analytics implementation for a specific time frame (for example, 1 year). When choosing this option, consider the following:

* Data would not be available in Experience Platform.

* You must plan to decommission the Adobe Analytics implementation after you have sufficient data in Customer Journey Analytics. 

## Next, perform additional implementation tasks

At this point in the migration process, you need to perform various tasks before your Customer Journey Analytics environment is ready to use.

These additional tasks apply to migrations from Adobe Analytics as well as new Customer Journey Analytics implementations.

These tasks include:

* Bringing other data into Experience Platform

* Creating connections between Platform datasets and Customer Journey Analytics

* Creating data views

* Porting the reporting API usage

* Accounting for Data Feeds and Data Warehouse

* Migrating projects and components

* Planning user onboarding

For more information, see [Customer Journey Analytics Getting Started](/help/getting-started/cja-getting-started.md).
