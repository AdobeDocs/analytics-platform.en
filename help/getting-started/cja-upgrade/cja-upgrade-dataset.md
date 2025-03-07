---
title: Create a schema for Customer Journey Analytics
description: Learn about the recommended path when upgrading from Adobe Analytics to Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: yes
hidefromtoc: yes
exl-id: d686dcdd-08d5-4e8f-8f0d-76c8c7b0427f
---
# Create a dataset to use with Customer Journey Analytics {#upgrade-create-dataset}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-dataset-create"
>title="Create a dataset in Adobe Experience Platform"
>abstract="A dataset is a location where collected data resides. Create this location in Adobe Experience Platform.<br><br>Creating a dataset with a schema in mind takes only a few minutes."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

A dataset is the construct that stores and manages the data that you collect into Adobe Experience Platform.

To create a dataset:

1. In Adobe Experience Platform, in the left rail, select **[!UICONTROL Datasets]** within [!UICONTROL DATA MANAGEMENT].

1. Select **[!UICONTROL Create dataset]**.

   ![Create dataset](assets/create-dataset.png)

1. Select **[!UICONTROL Create dataset from schema]**.

   ![Create dataset from schema](assets/create-dataset-from-schema.png)

1. Select the schema that you created earlier and select **[!UICONTROL Next]**.

1. Name your dataset and (optional) provide a description.

   ![Name dataset](assets/name-your-datatest.png)

1. Select **[!UICONTROL Finish]**.

1. Select the **[!UICONTROL Profile]** switch.

   You are prompted to enable the dataset for profile. Once enabled, the dataset enriches real-time customer profiles with its ingested data.

   >[!IMPORTANT]
   >
   >    You can only enable a dataset for profile when the schema, to which the dataset adheres, is also enabled for profile.

   ![Enable schema for profile](assets/aepwebsdk-dataset-profile.png)

   See [Datasets UI guide](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html) for much more information on how to view, preview, create, and delete a dataset. You can also learn how to enable a dataset for Real-Time Customer Profile.

{{upgrade-final-step}}
