---
title: Retain historical data when upgrading to Customer Journey Analytics
description: Learn how to retain historical data when upgrading to Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 1d17151b-3a12-468e-9a4f-9e5994599570
---
# Step 4: Retain historical data when upgrading

+++Expand this section to see where the information on this page fits into the larger upgrade process. Make sure all previous upgrade steps are complete.

Before you continue with this section, first make sure you have completed all previous upgrade tasks.

The information on this page covers Step 4 of the upgrade process, as highlighted in the table below: 

| Upgrade task | Details |
|---------|----------|
| **Step 1: [Get started with the upgrade](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)** | Learn the benefits of upgrading to Customer Journey Analytics and the basic upgrade process. |
| **Step 2: [Choose the upgrade path](/help/getting-started/cja-upgrade/cja-upgrade-path.md)** | Various methods are available for upgrading to Customer Journey Analytics. Choose the method that is best for your organization, depending on your organization's current Adobe Analytics environment and long-term goals. | 
| **Step 3: [Send data to Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)** | The process for sending data to Adobe Experience Platform differs depending on the upgrade path that you chose in Step 2. | 
| <span class="preview">**Step 4: Retain historical data**</span> | <span class="preview">Most organizations need to retain their historical Adobe Analytics data for a certain amount of time. Various options are available to accomplish this.</span> | 
| **Step 5: [Perform additional implementation tasks](/help/getting-started/cja-getting-started.md)** | At this point in the upgrade process, you need to perform various tasks before your Customer Journey Analytics environment is ready to use.<p>These additional tasks apply to upgrades from Adobe Analytics as well as new Customer Journey Analytics implementations.</p><p>These tasks include:</p><ul><li>Bringing other data into Experience Platform</li><li>Creating connections between Platform datasets and Customer Journey Analytics</li><li>Creating data views</li><li>Porting the reporting API usage</li><li>Accounting for Data Feeds and Data Warehouse</li><li>Migrating projects and components</li><li>Planning user onboarding</li></ul> <p>For more information, see [Customer Journey Analytics Getting Started](/help/getting-started/cja-getting-started.md).  |

{style="table-layout:auto"}

+++

<!--

>[!AVAILABILITY]
>
>The information on this page is being replaced with the following more comprehensive upgrade information: <ul><li>**Recommended upgrade steps**<p>For detailed information, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).</p></li><li>**Customer Journey Analytics Upgrade Guide**<p>A new upgrade guide is available that dynamically generates upgrade steps that are tailored for your organization and your unique circumstances.</p><p>To access the guide from Customer Journey Analytics, select the **[!UICONTROL Workspace]** tab, then select **[!UICONTROL Upgrade to Customer Journey Analytics]** in the left panel. Follow the on-screen instructions.</p></li></ul>

-->

Choose one of the following options to retain historical data when moving from Adobe Analytics to Customer Journey Analytics:  

>[!IMPORTANT]
>
>When choosing how to retain historical data, contact your Adobe account representative to determine pricing. 

## Use the Analytics source connector

  You can use the [Analytics source connector](/help/data-ingestion/analytics.md) to retain historical data. Regardless of the upgrade path that you choose (even if you upgrade using the Web SDK), you can use the Analytics source connector to retain historical data from your Adobe Analytics environment. 

  You can use the Analytics source connector to retain historical data by bringing historical data into its own dedicated location, separate from your current data.

  The Analytics source connector must be functioning for as long as you need access to the historical data.

  <!-- Another possibility in the future: Map historical data in a way that allows you to tie it to your new data.  Possible? Explain -->

## Maintain your existing Adobe Analytics implementation

You can maintain your existing Adobe Analytics implementation alongside your new Customer Journey Analytics implementation for a specific time frame (for example, 1 year). When choosing this option, consider the following:

* Data would not be available in Experience Platform.

* You should plan to decommission the Adobe Analytics implementation after you have sufficient data in Customer Journey Analytics. 

## Next, perform additional implementation tasks

At this point in the upgrade process, you need to perform various implementation tasks before your Customer Journey Analytics environment is ready to use.

These additional tasks apply to upgrades from Adobe Analytics as well as new Customer Journey Analytics implementations.

These tasks include:

* Bringing other data into Experience Platform

* Creating connections between Platform datasets and Customer Journey Analytics

* Creating data views

* Porting the reporting API usage

* Accounting for Data Feeds and Data Warehouse use cases

* Migrating projects and components

* Planning user onboarding

For more information, begin with Step 2 in [Customer Journey Analytics Getting Started](/help/getting-started/cja-getting-started.md).
