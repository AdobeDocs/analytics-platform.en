---
title: Create a schema for Customer Journey Analytics
description: Learn about the recommended path when upgrading from Adobe Analytics to Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: c6d49ca4-3d04-4c0f-accd-8666a587109d
autotag-review: '2026-05-19T08:12:37.701Z'
TQID: 'https://experienceleague.adobe.com/ncFpZWJRFzOg8eFg6OF7TfAw6fZRhSdKi6W-LxPUAGg'
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
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
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

{{upgrade-final-step}}
