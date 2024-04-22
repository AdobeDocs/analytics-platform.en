---
title: Plan your migration from Adobe Analytics to Customer Journey Analytics
to Customer Journey Analytics
description: Plan your migration from Adobe Analytics to Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
---
# Step 3: Send data to Adobe Experience Platform

+++The information on this page is part of a larger migration process. Make sure you complete all previous migration steps before continuing with this section. </br></br>See where this section fits within the migration process.

>[!NOTE]
>
>Before you continue with this section, first make sure you have completed all previous migration tasks.
>
>The information on this page covers Step 3, as highlighted in the table below: 
>
>| Migration task | Details |
>|---------|----------|
>| **Step 1: [Get started with the migration](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Learn the benefits of migrating to Adobe Analytics and the basic migration process. |
>| **Step 2: [Choose the migration method](/help/getting-started/cja-migration/cja-migration-method.md)** | Various methods are available for migrating to Customer Journey Analytics. Choose the method that is best for your organization, depending on your organization's current Adobe Analytics environment and long-term goals. | 
>| <span class="preview">**Step 3: [Send data to Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)**</span> | <span class="preview">The process for sending data to Adobe Experience Platform differs depending on the migration method that you chose in Step 1.</span> | 
>| **Step 4: [Plan data mapping to the XDM schema](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [XDM schemas](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) are used in Adobe Experience Platform to describe the structure of data in a consistent and reusable way. By defining data consistently across systems, it becomes easier to retain meaning and therefore gain value from data.<p>Most migration methods require that you either create a new XDM schema, or map your existing Adobe Analytics schema to XDM by using datastream mapping.</p>  |
>| **Step 5: [Retain historical data](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | Most organizations need to retain their historical Adobe Analytics data for a certain amount of time. Various options are available to accomplish this.  | 
>| **Step 6: [Plan user onboarding](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | You should give your users ample time (3 - 6 months) to become familiar with the key differences of Analysis Workspace in Customer Journey Analytics. | 
>| **Step 7: [Port the reporting API usage](/help/getting-started/cja-migration/cja-migration-api.md)** | The Customer Journey Analytics reporting API is in the same format, but uses a different endpoint. Port the reporting API usage from the Adobe Analytics reporting API to the Customer Journey Analytics reporting API. | 
>| **Step 8: [Replace Data Feeds and Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)** | Decide how you will use the export options available in Customer Journey Analytics in order to replace the Data Feeds and Data Warehouse features you were using in Adobe Analytics.  |
>| **Step 9: [Migrate projects and components](/help/getting-started/cja-migration/cja-migration-projects.md)** | The Component migration area in Adobe Analytics allows you to migrate projects and their associated components from Adobe Analytics to Customer Journey Analytics.  |
>
>{style="table-layout:auto"}

+++


After you [choose the migration method](#step-2-choose-your-customer-journey-analytics-migration-method) that is best for your organization, you can begin sending data to Adobe Experience Platform in order to make it available in Customer Journey Analytics. 

The process for sending data to Experience Platform for each migration method is shown below. Follow the links for more detailed information.

|Migration method | Process for sending data to Platform | 
|---------|----------|
| New implementation of the Web SDK | [Ingest data via the Adobe Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) | 
| Migrate your Adobe Analytics implementation to use the Web SDK | If you are using the Analytics tag extension: [Migrate from the Adobe Analytics tag extension to the Web SDK tag extension](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk)<p>Or</p><p>If you are using AppMeasurement: [Migrate from AppMeasurement to the Web SDK](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk) | 
| Configure your existing Adobe Analytics Web SDK implementation to send data to Customer Journey Analytics | [Set up a datastream](/https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-datastream) in [Ingest data via the Adobe Experience Platform Web SDK](/https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk)  | 
| Analytics Source Connector | [Ingest and use data from traditional Adobe Analytics](/help/data-ingestion/analytics.md) | 

## Next, map data to the XDM schema

After you send data to Experience Platform by following the links in the table above, you need to [map data to the XDM schema](/help/getting-started/cja-migration/cja-migration-xdm.md).
