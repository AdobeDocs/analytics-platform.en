---
title: Product usage opt-out settings
description: Manage opt-out settings for individual users within your organization.
hide: yes
hidefromtoc: yes
---
# Product usage opt-out settings {#product-usage-opt-out-settings}

The _Opt-out settings_ page allows you to exclude or re-include users within your organization from product usage tracking.

**Customer Journey Analytics** > **[!UICONTROL Tools]** > **[!UICONTROL Product Usage]** > **[!UICONTROL Opt-out settings]**

The following settings are available on this page:

* **[!UICONTROL Opt-out user]**: A drop-down list containing all Customer Journey Analytics users in your organization. Select a user from this drop-down list and select **[!UICONTROL Opt-out]** to exclude that user from product usage tracking. That user is added to the [!UICONTROL Opt-out user list] table below.
* **[!UICONTROL Opt-out user list]**: A table that shows you all users that are currently opted out of product usage tracking. To opt a user back in to product usage tracking, select the check box next to a given user, then select the **[!UICONTROL Opt-in]** button.

Adobe uses a combination of client-side and server-side tracking to collect product usage data for your organization. When a user is initially opted out, that user might still see client-side tracking data in their debugger until they log out and back in to Customer Journey Analytics. Adobe's server-side validation ensures that client-side tracking data is discarded for opted out users. 

>[!CONTEXTUALHELP]
>id="cja_product_usage_opt_out_settings"
>title="Opt out users"
>abstract="Exclude users from product usage tracking."
