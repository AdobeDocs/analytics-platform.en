---
title: Create a marketing channel derived field for Customer Journey Analytics
description: Learn how to create a marketing channel derived field for Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: yes
hidefromtoc: yes
exl-id: 2a74da97-61cb-4c98-949b-3fc428839d70
---
# Create a marketing channel derived field for Customer Journey Analytics {#create-marketing-channel-derived-field}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-marketing-channel"
>title="Create a marketin channel derived field"
>abstract="Derived fields are created within a data view.<br><br>Using a default marketing channel setup only takes a few minutes; creating a highly customized marketing channel setup might take several hours."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>Follow the steps on this page only after you complete all previous upgrade steps. You can follow the [recommended upgrade steps](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations), or you can follow the upgrade steps that were dynamically generated for your organization with the [Adobe Analytics to Customer Journey Analytics upgrade questionnaire](https://gigazelle.github.io/cja-ttv/). 
>
>After you complete the steps on this page, continue following the recommended upgrade steps or the dynamically generated upgrade steps. 

When using the Analytics source connector, marketing channels data flows into Customer Journey Analytics through that connector. Marketing Channel rules are configured in traditional Adobe Analytics and some rules are not supported. For more information, see [Use marketing channel dimensions](/help/use-cases/aa-data/marketing-channels.md).

In order to use marketing channels in Customer Journey Analytics when using the Experience Platform Web SDK, you can use derived fields in a data view to re-create the same marketing channels and processing rules for Customer Journey Analytics.  

1. In Customer Journey Analytics, select the data view where you want to add marketing channels. 

1. In the data view, select the **[!UICONTROL Components]** tab.

1. Select **[!UICONTROL Create derived field]** in the left rail.

1. In the **[!UICONTROL Create derived field]** dialog box, select **[!UICONTROL Function templates]** from the drop-down menu.

   ![Create derived field function templates](assets/derived-field-create.png)

1. Drag the **[!UICONTROL Marketing channels]** template onto the blank canvas.

1. Customize the logic for each marketing channel to ensure it matches the logic you use to identify each channel in your Adobe Analytics environment. 

   You can modify the output channel names or add logic to identify additional channels specific to your organization.

1. In the right column, specify a name and a description for the marketing channel.

1. Select **[!UICONTROL Save]**.

   Your new derived field is added to the Derived fields > container, as part of Schema fields in the left rail of your Data view.

1. Continue following the [recommended upgrade steps](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) or the [dynamically generated upgrade steps](https://gigazelle.github.io/cja-ttv/).
