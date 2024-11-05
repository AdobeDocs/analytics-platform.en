---
title: Create a schema for Customer Journey Analytics
description: Learn about the recommended path when upgrading from Adobe Analytics to Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: yes
hidefromtoc: yes
---
# Create a datastream to use with Customer Journey Analytics

>[!NOTE]
> 
>Follow the steps on this page only after you complete all previous upgrade steps. You can follow the [recommended upgrade steps](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations), or you can follow the upgrade steps that were dynamically generated for your organization with the [Adobe Analytics to Customer Journey Analytics upgrade questionnaire](https://gigazelle.github.io/cja-ttv/). 
>
>After you complete the steps on this page, continue following the recommended or dynamically generated upgrade steps.

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

A datastream represents the server-side configuration when implementing the Adobe Experience Platform Web and Mobile SDKs. When collecting data with the Adobe Experience Platform SDKs, data is sent to the Adobe Experience Platform Edge Network. It is the datastream that determines to which services that data is forwarded.

In your setup, you want to configure the datastream to send the collected data to your dataset in Adobe Experience Platform.

To set up your datastream:

1. In Adobe Experience Platform, select **[!UICONTROL Datastreams]** from [!UICONTROL DATA COLLECTION] in the left rail.

1. Select **[!UICONTROL New Datastream]**.

1. Name and describe your datastream. Select your schema from the [!UICONTROL Event Schema] list.

   ![New Datastream](assets/new-datastream.png)

1. Select **[!UICONTROL Save]**.

1. Continue following the upgrade steps that were dynamically generated for your organization from the [Adobe Analytics to Customer Journey Analytics upgrade questionnaire](https://gigazelle.github.io/cja-ttv/).

