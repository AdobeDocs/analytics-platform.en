---
title: Use tags to create a tag property and add the Web SDK extension
description: Learn how to create a tag property and add the Web SDK extension
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: yes
hidefromtoc: yes
---
# Use tags: Create a tag property and add the Web SDK extension

>[!NOTE]
> 
>Follow the steps on this page only after you complete all previous upgrade steps. You can follow the [recommended upgrade steps](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations), or you can follow the upgrade steps that were dynamically generated for your organization with the [Adobe Analytics to Customer Journey Analytics upgrade questionnaire](https://gigazelle.github.io/cja-ttv/). 
>
>After you complete the steps on this page, continue following the recommended upgrade steps or the dynamically generated upgrade steps. 

You can use the Tags feature within Adobe Experience Platform to implement code on your site to collect data. This tag management solution lets you deploy code alongside other tagging requirements. Tags offer seamless integration with Adobe Experience Platform using the Adobe Experience Platform Web SDK extension.

The following information describes create a tag for your property and add the Web SDK extension to your tag. For supplemental information, see the [Configure the Web SDK tag extension](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration) in the Experience Platform documentation. The Web SDK includes the [!UICONTROL Adobe Experience Cloud ID Service] natively, so you do not need to add the ID service extension to your tag.

## Create a tag for your property

A property is basically a container that you fill with extensions, rules, data elements, and libraries as you deploy tags to your site. Many people create a property for each website (or group of closely related sites) where they want to deploy the same set of tags. For more about properties, see [Properties](https://experienceleague.adobe.com/en/docs/experience-platform/tags/admin/companies-and-properties) in the Experience Platform data collection documentation.

To create a tag for your property:

1. Log in to experience.adobe.com using your Adobe ID credentials.

1. In Adobe Experience Platform, go to **[!UICONTROL Data Collection]** > **[!UICONTROL Tags]**.

1. Select **[!UICONTROL New Property]**. 

    Name the tag, select **[!UICONTROL Web]** and enter a domain name. Select **[!UICONTROL Save]** to continue.

    ![Create a property](assets/create-property.png)

1. Continue with the following section, [Add the Web SDK extension to your tag](#add-the-web-sdk-extension-to-your-tag)

## Add the Web SDK extension to your tag

After creating the tag, you must configure it with the Adobe Experience Platform Web SDK extension. This ensures that you can send data to Adobe Experience Platform (through your datastream).

1. Select your newly created tag from the list of [!UICONTROL Tag Properties] to open it.

1. Select **[!UICONTROL Extensions]** in the left rail.

1. Select **[!UICONTROL Catalog]** in the top bar.

1. Search for or scroll to the **[!UICONTROL Adobe Experience Platform Web SDK extension]**, then select **[!UICONTROL Install]** to install it.

   <img src="assets/aepwebsdk-extension.png" width="35%"/>

1. Select your sandbox and your earlier created datastream for your [!UICONTROL Production Environment] and (optional) [!UICONTROL Staging Environment] and [!UICONTROL Development Environment].

   ![AEP Web SDK extension configuration](assets/aepwebsk-extension-datastreams.png)

1. Select **[!UICONTROL Save]**.

1. Continue following the [recommended upgrade steps](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) or the [dynamically generated upgrade steps](https://gigazelle.github.io/cja-ttv/).

