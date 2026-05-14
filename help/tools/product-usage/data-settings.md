---
title: Product usage data settings
description: Enable, disable, or configure product usage settings.
exl-id: 85e2b515-78e6-41e8-9947-369b1e65e4fd
TQID: https://experienceleague.adobe.com/2iLjMb4UCiA3bwZVozXyes4f0Ux1hCLv85oUPVL-CJw
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
---
# Product usage data settings {#product-usage-data-settings}

The _Data settings_ page handles your product usage configuration. You can use this page to enable or disable product usage for your organization. You can also configure which Adobe Experience Platform sandbox that the dataset is created under, and override the data retention window if desired. It is only visible to product admins.

**[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Tools]** > **[!UICONTROL Product Usage]** > **[!UICONTROL Data settings]**

>[!IMPORTANT]
>When you enable this feature, you must accept the terms and conditions before using it. When you accept these terms and conditions, you do so on behalf of your entire organization.

The following settings are available on this page:

* **[!UICONTROL Enable product usage]**: Toggles the availability of product usage data collection. If you enable product usage then disable it in the future, the dataset, connection and data view are not deleted. Tracking is disabled globally for your organization when toggled off.
* **[!UICONTROL Sandbox]**: Determines the Adobe Experience Platform sandbox that the schema and dataset is created under. The sandbox that you choose does not impact product usage data collection. If you change this sandbox setting, all existing data is deleted. A new dataset, connection, and data view are created in the selected sandbox.
* **[!UICONTROL Override data retention window]**: Every dataset has a default data retention window. If this setting is disabled, product usage follows that default time period. You can enable this setting if you want to shorten the amount of time that data is kept. Shortening the data retention window and help reduce costs and allow you to comply with any employee-specific privacy guidelines. You cannot extend data retention beyond the dataset's default data retention window. 

>[!CONTEXTUALHELP]
>id="cja_product_usage_sandbox"
>title="Adobe Experience Platform sandbox"
>abstract="Determines the Adobe Experience Platform sandbox that the schema and dataset is created under."

>[!CONTEXTUALHELP]
>id="cja_product_usage_data_retention"
>title="Override data retention window"
>abstract="Shorten the availability of product usage data to help reduce costs or comply with privacy guidelines."

>[!CONTEXTUALHELP]
>id="product_usage_sandbox"
>title="Adobe Experience Platform sandbox"
>abstract="Determines the Adobe Experience Platform sandbox that the schema and dataset is created under."

>[!CONTEXTUALHELP]
>id="product_usage_data_retention"
>title="Override data retention window"
>abstract="Shorten the availability of product usage data to help reduce costs or comply with privacy guidelines."
