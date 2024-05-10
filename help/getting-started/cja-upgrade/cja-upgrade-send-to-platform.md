---
title: Send data to Adobe Experience Platform when migrating to Customer Journey Analytics
description: Send data to Adobe Experience Platform when migrating to Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
exl-id: d9d7f186-9077-4372-94ad-8dd5b97779ca
---
# Step 3: Send data to Adobe Experience Platform when upgrading

+++Expand this section to see where the information on this page fits into the larger upgrade process. Make sure all previous upgrade steps are complete.

Before you continue with this section, first make sure you have completed all previous upgrade tasks.

The information on this page covers Step 3 of the upgrade process, as highlighted in the table below: 

| Upgrade task | Details |
|---------|----------|
| **Step 1: [Get started with the upgrade](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)** | Learn the benefits of upgrading to Customer Journey Analytics and the basic upgrade process. |
| **Step 2: [Choose the upgrade path](/help/getting-started/cja-upgrade/cja-upgrade-path.md)** | Various methods are available for upgrading to Customer Journey Analytics. Choose the method that is best for your organization, depending on your organization's current Adobe Analytics environment and long-term goals. | 
| <span class="preview">**Step 3: Send data to Adobe Experience Platform**</span> | <span class="preview">The process for sending data to Adobe Experience Platform differs depending on the upgrade path that you chose in Step 2.</span> | 
| **Step 4: [Retain historical data](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)** | Most organizations need to retain their historical Adobe Analytics data for a certain amount of time. Various options are available to accomplish this. | 
| **Step 5: [Perform additional implementation tasks](/help/getting-started/cja-getting-started.md)** | At this point in the upgrade process, you need to perform various tasks before your Customer Journey Analytics environment is ready to use.<p>These additional tasks apply to upgrades from Adobe Analytics as well as new Customer Journey Analytics implementations.</p><p>These tasks include:</p><ul><li>Bringing other data into Experience Platform</li><li>Creating connections between Platform datasets and Customer Journey Analytics</li><li>Creating data views</li><li>Porting the reporting API usage</li><li>Accounting for Data Feeds and Data Warehouse</li><li>Migrating projects and components</li><li>Planning user onboarding</li></ul> <p>For more information, see [Customer Journey Analytics Getting Started](/help/getting-started/cja-getting-started.md).  |

{style="table-layout:auto"}

+++


After you [choose the upgrade path](/help/getting-started/cja-upgrade/cja-upgrade-path.md) that is best for your organization, you can begin sending data to Adobe Experience Platform in order to make it available in Customer Journey Analytics.  

The process for sending data to Experience Platform for each upgrade path is shown below. Follow the links in the table for detailed configuration information.

|Upgrade path | Process for sending data to Platform | Additional information |
|---------|----------|----------|
| New implementation of the Experience Platform Web SDK | <ol><li>Create an XDM schema for your organization.<p>Work with your data team to identify your organization's ideal schema design for Customer Journey Analytics.</p></li><li>Implement the Experience Platform Web SDK.</li><li>Send data to Platform.</li></ol><p>For detailed information about each of these steps, see [Ingest data via the Adobe Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md). | Because this is a new implementation of the Experience Platform Web SDK, schema mapping is not required because you must create the schema as one of the first steps during implementation. |
| Migrate your Adobe Analytics implementation to use the Web SDK |<ol><li>Move your existing Adobe Analytics implementation to the Experience Platform Web SDK, then validate that everything is working in Adobe Analytics.<p>For information about how to do this, use the following resources, depending on whether your current implementation is the Analytics tag extension or AppMeasurement:</p><ul><li>If you are using the Analytics tag extension, see [Migrate from the Adobe Analytics tag extension to the Web SDK tag extension](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk)</li><li>If you are using AppMeasurement, see [Migrate from AppMeasurement to the Web SDK](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk)</li></ul><li>[Create an XDM schema for your organization](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema-and-dataset).<p>Work with your data team to identify your organization's ideal schema design for Customer Journey Analytics.</p></li><li>[Use Data Prep to map all of the fields in the data object to your XDM schema](https://experienceleague.adobe.com/en/docs/experience-platform/data-prep/home).</li><li>Begin sending data to Platform by [setting up a datastream](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-datastream).</li></ol> |  |
| Configure your existing Adobe Analytics Web SDK implementation to send data to Customer Journey Analytics | <ol><li>Begin sending data to Platform by [setting up a datastream](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-datastream).<p>Because your Adobe Analytics implementation is already using the Experience Platform Web SDK, you can ignore the other sections in [Ingest data via the Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk).</li><li>(Optional) [Create an XDM schema for your organization](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema-and-dataset).<p>Work with your data team to identify your organization's ideal schema design for Customer Journey Analytics.</p><p>Note: For information about the advantages of creating an XDM schema, see [Choose your schema](/help/getting-started/cja-upgrade/cja-upgrade-path.md#choose-your-schema).</li><li>(Conditional) If you created an XDM schema, [use Data Prep to map all of the fields in the data object to your XDM schema](https://experienceleague.adobe.com/en/docs/experience-platform/data-prep/home).</li></ol> | 
| Use the Analytics Source Connector | [Ingest and use data from traditional Adobe Analytics](/help/data-ingestion/analytics.md) |  Adobe Analytics data is automatically mapped to the XDM schema when you use the Analytics Source Connector. Additional mapping is not required. |

## Next, retain historical data

Next, decide how you will [retain historical Adobe Analytics data](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md).
