---
title: Create a schema for Customer Journey Analytics
description: Learn about the recommended path when upgrading from Adobe Analytics to Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: f76d098d-d223-40e4-be81-d28e7581396b
---
# Create a datastream to use with Customer Journey Analytics {#upgrade-create-datastream}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-datastream-create"
>title="Create a datastream in Adobe Experience Platform"
>abstract="A datastream is an intermediary location that passes your data along to all configured services. Create this location in Adobe Experience Platform.<br><br>The initial creation of a datastream in the Platform interface takes only a few minutes."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

A datastream represents the server-side configuration when implementing the Adobe Experience Platform Web and Mobile SDKs. When collecting data with the Adobe Experience Platform SDKs, data is sent to the Adobe Experience Platform Edge Network. It is the datastream that determines to which services that data is forwarded.

In your setup, you want to configure the datastream to send the collected data to your dataset in Adobe Experience Platform.

>[!NOTE]
>
>The following steps are required only for Adobe Analytics implementations using AppMeasurement or the Analytics extension (tags).
>
>If your Adobe Analytics implementation uses the Web SDK or the Web SDK Extension, the datastream already exists in your Adobe Analytics environment.

To set up your datastream:

1. In Adobe Experience Platform, select **[!UICONTROL Datastreams]** from [!UICONTROL DATA COLLECTION] in the left rail.

1. Select **[!UICONTROL New Datastream]**.

1. Name and describe your datastream. Select your schema from the [!UICONTROL Event Schema] list.

   ![New Datastream](assets/new-datastream.png)

1. Select **[!UICONTROL Save]**.

{{upgrade-final-step}}
