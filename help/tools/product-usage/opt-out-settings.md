---
title: Product usage opt-out settings
description: Manage opt-out settings for individual users within your organization.
exl-id: 0ea24582-bab8-4a76-ac00-7c265423e8bb
autotag-review: '2026-05-19T09:31:49.294Z'
TQID: 'https://experienceleague.adobe.com/O67EiLS9ltB20iQ3d4mxlDcrwR06-r9SmbXZJ37slJs'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
    internal-label: Administration
subfeature_v2:
  - id: a67cb189-a535-41f6-afa2-448f39c4759f
    internal-label: Access control
  - id: cc5596a7-18f9-4e6c-87eb-ce3d0a9efb66
    internal-label: User management
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
---
# Product usage opt-out settings {#product-usage-opt-out-settings}

The _Opt-out settings_ page allows you to exclude or re-include users within your organization from product usage tracking. It is only visible to product admins.

**[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Tools]** > **[!UICONTROL Product Usage]** > **[!UICONTROL Opt-out settings]**

The following settings are available on this page:

* **[!UICONTROL Opt-out user]**: A drop-down menu containing all Customer Journey Analytics users in your organization. Select a user from this drop-down menu and select **[!UICONTROL Opt-out]** to exclude that user from product usage tracking. That user is added to the [!UICONTROL Opt-out user list] table below.
* **[!UICONTROL Opt-out user list]**: A table that shows you all users that are currently opted out of product usage tracking. To opt a user back in to product usage tracking, select the check box next to a given user, then select the **[!UICONTROL Opt-in]** button.

Adobe uses a combination of client-side and server-side tracking to collect product usage data for your organization. When a user is initially opted out, that user might still see client-side tracking data in their debugger until they log out and back in to Customer Journey Analytics. Adobe's server-side validation ensures that client-side tracking data is discarded for opted out users. 

>[!CONTEXTUALHELP]
>id="cja_product_usage_opt_out_settings"
>title="Opt out users"
>abstract="Exclude users from product usage tracking."

>[!CONTEXTUALHELP]
>id="product_usage_opt_out_settings"
>title="Opt out users"
>abstract="Exclude users from product usage tracking."
