---
title: Create a tag property and add the Web SDK extension
description: Learn how to create a tag property and add the Web SDK extension
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: yes
hidefromtoc: yes
---
# Create a tag for your property

>[!NOTE]
> 
>Follow the steps on this page only after you complete all previous upgrade steps. You can follow the [recommended upgrade steps](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations), or you can follow the upgrade steps that were dynamically generated for your organization with the [Adobe Analytics to Customer Journey Analytics upgrade questionnaire](https://gigazelle.github.io/cja-ttv/). 
>
>After you complete the steps on this page, continue following the recommended upgrade steps or the dynamically generated upgrade steps. 

You can use the Tags feature within Adobe Experience Platform to implement code on your site to collect data. This tag management solution lets you deploy code alongside other tagging requirements. Tags offer seamless integration with Adobe Experience Platform using the Adobe Experience Platform Web SDK extension.

The following information describes create a tag for your property. For supplemental information, see the [Configure the Web SDK tag extension](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration) in the Experience Platform documentation. The Web SDK includes the [!UICONTROL Adobe Experience Cloud ID Service] natively, so you do not need to add the ID service extension to your tag.

A property is basically a container that you fill with extensions, rules, data elements, and libraries as you deploy tags to your site. Many people create a property for each website (or group of closely related sites) where they want to deploy the same set of tags. For more about properties, see [Properties](https://experienceleague.adobe.com/en/docs/experience-platform/tags/admin/companies-and-properties) in the Experience Platform data collection documentation.

To create a tag for your property:

1. Log in to experience.adobe.com using your Adobe ID credentials.

1. In Adobe Experience Platform, go to **[!UICONTROL Data Collection]** > **[!UICONTROL Tags]**.

1. Select **[!UICONTROL New Property]**. 

    Name the tag, select **[!UICONTROL Web]** and enter a domain name. Select **[!UICONTROL Save]** to continue.

    ![Create a property](assets/create-property.png)

1. Continue following the [recommended upgrade steps](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) or the [dynamically generated upgrade steps](https://gigazelle.github.io/cja-ttv/).

