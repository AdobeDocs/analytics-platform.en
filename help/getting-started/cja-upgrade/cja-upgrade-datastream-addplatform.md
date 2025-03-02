---
title: Create a schema for Customer Journey Analytics
description: Learn about the recommended path when upgrading from Adobe Analytics to Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: yes
hidefromtoc: yes
exl-id: c6d49ca4-3d04-4c0f-accd-8666a587109d
---
# Add Platform as a service to your datastream {#upgrade-addplatform-datastream}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-addplatform-datastream"
>title="Add Adobe Experience Platform as a service to the datastream"
>abstract="A datastream needs one or more services to send data to. Set up Adobe Experience Platform as a service in your datastream.<br><br>Adding services to a datastream is a simple process, taking only a few minutes to complete."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

A datastream should already exist before you complete the steps in this section. When and how the datastream was created depends on your Adobe Analytics implementation, as follows: 

* If your Adobe Analytics implementation uses the Web SDK or the Web SDK Extension, the datastream was available for your Adobe Analytics environment, prior to the upgrade process.

* For other Adobe Analytics implementations, creating a datastream is part of the upgrade process, as described in [Create a datastream to use with Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md). 

With the datastream available, you need to add Platform as a service:

1. In the Adobe Experience Platform UI, select **[!UICONTROL Datastreams]** from [!UICONTROL DATA COLLECTION] in the left rail.

1. Select the datastream that was previously configured. <!--true?-->

1. Select **[!UICONTROL Add Service]**.

1. In the [!UICONTROL Add Service screen]:

   1. Select **[!UICONTROL Adobe Experience Platform]** from the [!UICONTROL Service] list.

   1. Ensure **[!UICONTROL Enabled]** is selected.

   1. Select your dataset from the [!UICONTROL Event Dataset] list.

      ![Datastream AEP service](./assets/datastream-aep-service.png)

   1. Leave the other settings and select **[!UICONTROL Save]** to save the datastream.

   Your datastream is now configured to forward the data collected from your website to your dataset in Adobe Experience Platform.

   See [Datastreams overview](https://experienceleague.adobe.com/docs/experience-platform/datastreams/overview.html) for more information on how to configure a datastream and how to handle sensitive data.

1. Continue following the [recommended upgrade steps](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) or the [dynamically generated upgrade steps](https://gigazelle.github.io/cja-ttv/).
