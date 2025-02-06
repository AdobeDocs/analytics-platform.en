---
title: Monitor dataset ingestion when upgrading to Customer Journey Analytics
description: Learn how to monitor dataset ingestion when upgrading to Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: yes
hidefromtoc: yes
exl-id: 35fcd213-d831-4da0-b946-f6f0d8561f60
---
# Monitor dataset ingestion when upgrading to Customer Journey Analytics {#monitor-ingestion}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-dataset-validate"
>title="Validate data in the dataset"
>abstract="Now that you have configured your Web SDK implementation, you can use the Dataset activity manager to see ingested and failed batches. If you see primarily ingested batches, this step is complete. If you see primarily failed batches or no batches, check your Web SDK implementation to ensure that it is correctly sending data to Adobe.<br><br>If everything was done correctly and flawlessly, this step can be done in less than a day. If there are multiple data collection issues, troubleshooting them can take notably longer."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>Follow the steps on this page only after you complete all previous upgrade steps. You can follow the [recommended upgrade steps](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations), or you can follow the upgrade steps that were dynamically generated for your organization with the [Adobe Analytics to Customer Journey Analytics upgrade questionnaire](https://gigazelle.github.io/cja-ttv/). 
>
>After you complete the steps on this page, continue following the recommended upgrade steps or the dynamically generated upgrade steps. 

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

After you configure your Web SDK implementation, you need to check the statuses of individual batches to verify that data is being ingested into the dataset.

1. In the Experience Platform UI, select **[!UICONTROL Monitoring]** in the left-navigation.

   The Monitoring dashboard displays. This dashboard lets you view the statuses of inbound data from either batch or streaming ingestion. 

   <!-- insert screenshot -->
   
1. Select **[!UICONTROL Batch end-to-end]** to view a list of batches. 

   If no batches are displayed, check your Web SDK implementation to ensure that it is correctly sending data to Adobe.

   <!-- insert screenshot -->

1. Select the batch ID for a given dataset, then validate that **[!UICONTROL Success]** is shown in the **[!UICONTROL Status]** field.

   If **[!UICONTROL Failed]** is shown in the **[!UICONTROL Status]** field, check your Web SDK implementation to ensure that it is correctly sending data to Adobe.

   Repeat this step to verify the status of each batch.

1. Continue following the [recommended upgrade steps](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) or the [dynamically generated upgrade steps](https://gigazelle.github.io/cja-ttv/).

