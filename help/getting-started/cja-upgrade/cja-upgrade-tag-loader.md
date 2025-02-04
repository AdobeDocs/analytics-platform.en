---
title: Implement the loader tag for the Web SDK extension
description: Learn how to implement the loader tag for the Web SDK extension
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: yes
hidefromtoc: yes
exl-id: 471ecd60-6e1e-4889-93bd-c654b35d40dc
---
# Implement the loader tag for the Web SDK extension

>[!NOTE]
> 
>Follow the steps on this page only after you complete all previous upgrade steps. You can follow the [recommended upgrade steps](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations), or you can follow the upgrade steps that were dynamically generated for your organization with the [Adobe Analytics to Customer Journey Analytics upgrade questionnaire](https://gigazelle.github.io/cja-ttv/). 
>
>After you complete the steps on this page, continue following the recommended upgrade steps or the dynamically generated upgrade steps. 

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

1. Continue following the [recommended upgrade steps](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) or the [dynamically generated upgrade steps](https://gigazelle.github.io/cja-ttv/).
