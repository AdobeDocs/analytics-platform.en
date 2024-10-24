---
title: Create a schema for Customer Journey Analytics
description: Learn about the recommended path when upgrading from Adobe Analytics to Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
---
# Add Platform as a service to your datastream

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

A datastream should already exist before you complete the steps in this section. When and how the datastream was created depends on your Adobe Analytics implementation, as follows: 

* If your Adobe Analytics implementation is using the Web SDK or the Web SDK Extension, the datastream was available for your Adobe Analytics environment, prior to the upgrade process.

* For other Adobe Analytics implementations, creating a datastream is part of the upgrade process, as described in [Create a datastream to use with Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md). 

With the datastream available, you need to add Platform as a service:

1. In the Adobe Experience Platform UI, select **[!UICONTROL Datastreams]** from [!UICONTROL DATA COLLECTION] in the left rail.

2. Select the datastream that was previously configured. <!--true?-->

5. Select **[!UICONTROL Add Service]**.

6. In the [!UICONTROL Add Service screen]:

   1. Select **[!UICONTROL Adobe Experience Platform]** from the [!UICONTROL Service] list.

   2. Ensure **[!UICONTROL Enabled]** is selected.

   3. Select your dataset from the [!UICONTROL Event Dataset] list.

      ![Datastream AEP service](./assets/datastream-aep-service.png)

   4. Leave the other settings and select **[!UICONTROL Save]** to save the datastream.

Your datastream is now configured to forward the data collected from your website to your dataset in Adobe Experience Platform.

See [Datastreams overview](https://experienceleague.adobe.com/docs/experience-platform/datastreams/overview.html) for more information on how to configure a datastream and how to handle sensitive data.