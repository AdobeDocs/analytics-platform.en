---
title: Monitor dataset ingestion when upgrading to Customer Journey Analytics
description: Learn how to monitor dataset ingestion when upgrading to Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: yes
hidefromtoc: yes
---
# Monitor dataset ingestion when upgrading to Customer Journey Analytics

>[!NOTE]
> 
>Follow the steps on this page only after you complete all previous upgrade steps. You can follow the [recommended upgrade steps](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations), or you can follow the upgrade steps that were dynamically generated for your organization with the [Adobe Analytics to Customer Journey Analytics upgrade questionnaire](https://gigazelle.github.io/cja-ttv/). 
>
>After you complete the steps on this page, continue following the recommended upgrade steps or the dynamically generated upgrade steps. 

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

After you configure your Web SDK implementation, you need to verify that data is being ingested into the dataset. the statuses of individual batches

is  can use the Dataset activity manager in Adobe Experience Platform to see ingested and failed batches. If you see primarily ingested batches, this step is complete. If you see primarily failed batches or no batches, check your Web SDK implementation to ensure that it is correctly sending data to Adobe.

1. In the Experience Platform UI, select **[!UICONTROL Monitoring]** in the left-navigation.

   The Monitoring dashboard displays. This dashboard lets you view the statuses of inbound data from either batch or streaming ingestion. 
   
1. Select **[!UICONTROL Batch end-to-end]** to view a list of batches. 

   The dashboards list all batch ingestion runs, including those that are successful, failed, or still in progress. Each listing provides details of the batch, including the batch ID, the name of the target dataset, and the number of records ingested. If the target dataset is enabled for Profile, the number of ingested identity and profile records is also displayed.

1. 

<!-- insert screenshot -->

You can select on an individual Batch ID to access the Batch overview dashboard and see details for the batch, including error logs should the batch fail to ingest.

<!-- insert screenshot -->

If you wish to delete the batch, select Delete batch near the top right of the dashboard. Deleting a batch also removes its records from the dataset that the batch was originally ingested to.

>[!NOTE]
>
>If the ingested data has been enabled for Profile and processed, then deleting a batch does not delete that data from the Profile store.

<!-- insert screenshot -->




