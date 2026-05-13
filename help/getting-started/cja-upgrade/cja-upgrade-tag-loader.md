---
title: Implement the loader tag for the Web SDK extension
description: Learn how to implement the loader tag for the Web SDK extension
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 471ecd60-6e1e-4889-93bd-c654b35d40dc
TQID: https://experienceleague.adobe.com/XAf3EoX-Ptq0NzfNEMrRJX8Bkr-ZbMsdXPy7SBsSKR4
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
---
# Implement the loader tag for the Web SDK extension {#upgrade-tag-loader}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tag-loader"
>title="Implement the loader tag on your site"
>abstract="Work with your website development team to install the loader tag on every page of your site.<br><br>Completion time for this task heavily depends on the response time of the engineering team that you work with to deploy the code. Some organizations who have highly adaptive engineering teams can complete this step in days, while engineering teams with an extensive backlog of tasks can potentially take a month or longer."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

You must install your tag on the website you want to track, which implies placing code in the header tag of your website's template.

The following process describes how to get the code that references your tag. For supplemental information, see the [Implementation guides for tags and event forwarding](https://experienceleague.adobe.com/en/docs/experience-platform/tags/get-started/implementation-guides) in the Experience Platform documentation.

To get the code that references your tag:

1. Log in to experience.adobe.com using your Adobe ID credentials.

1. In Adobe Experience Platform, go to **[!UICONTROL Data Collection]** > **[!UICONTROL Tags]**.

1. On the **[!UICONTROL Tag Properties]** page, select your newly created tag from the list of properties to open it.

1. Select **[!UICONTROL Environments]** in the left rail.

1. From the list of environments, select the correct install (box) button.

   In the [!UICONTROL Web Install Instructions] dialog, select the copy button next to the script code that should read like:

   ```
   <script src="https://assets.adobedtm.com/2a518741ab24/.../launch-...-development.min.js" async></script>>
         
   ```   

   ![Environment](assets/environment.png)

1. Select **[!UICONTROL Close]**.

   Instead of the code for the development environment, you could have selected another environment (staging, production) based on where you are in the process of deploying the Adobe Experience Platform Web SDK. 

   See [Environments](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/environments/environments.html?) for more information.

{{upgrade-final-step}}
