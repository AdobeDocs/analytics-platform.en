---
title: Create a schema for Customer Journey Analytics
description: Learn about the recommended path when upgrading from Adobe Analytics to Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
---
# Create a dataset to use with Customer Journey Analytics

>[!NOTE]
>
>This documentation should be used after completing the [Adobe Analytics to Customer Journey Analytics upgrade questionnaire](https://gigazelle.github.io/cja-ttv/).
> 
>Follow the steps on this page only after you complete all previous steps that were dynamically generated for your organization. 
>
>After you complete the steps on this page, continue following the upgrade steps that were dynamically generated for your organization from the [Adobe Analytics to Customer Journey Analytics upgrade questionnaire](https://gigazelle.github.io/cja-ttv/). 

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

After creating an XDM schema, you now have to define the construct to store and manage that data, which is done in Adobe Experience Platform through a dataset.

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

1. Continue following the upgrade steps that were dynamically generated for your organization from the [Adobe Analytics to Customer Journey Analytics upgrade questionnaire](https://gigazelle.github.io/cja-ttv/).

