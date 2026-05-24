---
title: Monitor dataset ingestion when upgrading to Customer Journey Analytics
description: Learn how to monitor dataset ingestion when upgrading to Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 35fcd213-d831-4da0-b946-f6f0d8561f60
autotag-review: '2026-05-19T08:10:42.746Z'
TQID: 'https://experienceleague.adobe.com/tAPQiUUPilyH50PlqwefoZjw14QDN9ER1D6EKsMAR9w'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
    internal-label: Administration
subfeature_v2:
  - id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
    internal-label: Upgrade
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
---
# Monitor dataset ingestion when upgrading to Customer Journey Analytics {#monitor-ingestion}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-dataset-validate"
>title="Validate data in the dataset"
>abstract="Now that you have configured your implementation, you can use the Dataset activity manager to see ingested and failed batches. If you see primarily ingested batches, this step is complete. If you see primarily failed batches or no batches, check your implementation to ensure that it is correctly sending data to Adobe."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

After you configure your Web SDK or API implementation, you need to check the statuses of individual batches to verify that data is being ingested into the dataset.

1. In the Experience Platform UI, select **[!UICONTROL Monitoring]** in the left-navigation.

   The Monitoring dashboard displays. This dashboard lets you view the statuses of inbound data from either batch or streaming ingestion. 

   <!-- insert screenshot -->
   
1. Select **[!UICONTROL Batch end-to-end]** to view a list of batches. 

   If no batches are displayed, check your implementation to ensure that it is correctly sending data to Adobe.

   <!-- insert screenshot -->

1. Select the batch ID for a given dataset, then validate that **[!UICONTROL Success]** is shown in the **[!UICONTROL Status]** field.

   If **[!UICONTROL Failed]** is shown in the **[!UICONTROL Status]** field, check your implementation to ensure that it is correctly sending data to Adobe.

   Repeat this step to verify the status of each batch.

{{upgrade-final-step}}

