---
title: Product usage data settings
description: Enable, disable, or configure product usage settings.
hide: yes
hidefromtoc: yes
---
# Product usage data settings {#product-usage-data-settings}

{{release-limited-testing}}

The _Data settings_ page handles your product usage configuration. You can use this page to enable or disable product usage for your organization. You can also configure which Adobe Experience Platform sandbox that the dataset is created under, and override the data retention window if desired. It is only visible to product admins.

**Customer Journey Analytics** > **Tools** > **Product Usage** > **Data settings**

>[!IMPORTANT]
>
>When you enable this feature, you must accept the terms and conditions before using it. When you accept these terms and conditions, you do so on behalf of your entire organization.

The following settings are available on this page:

* **Enable product usage**: Toggles the availability of product usage data collection. If you enable product usage, then disable it in the future, the dataset, connection and data view are not deleted. Tracking is disabled globally for your organization when toggled off.
* **Sandbox**: Determines the Adobe Experience Platform sandbox that the schema and dataset is created under. The sandbox that you choose does not impact product usage data collection. If you change this sandbox setting, all existing data is deleted. A new dataset, connection, and data view are created in the selected sandbox.
* **Override data retention window**: Every dataset has a default data retention window. If this setting is disabled, product usage follows that default time period. You can enable this setting if you want to shorten the amount of time that data is kept. Shortening the data retention window and help reduce costs and allow you to comply with any employee-specific privacy guidelines. You cannot extend data retention beyond the dataset's default data retention window. 

>[!CONTEXTUALHELP]
>id="cja_product_usage_sandbox"
>title="Adobe Experience Platform sandbox"
>abstract="Determines the Adobe Experience Platform sandbox that the schema and dataset is created under."

>[!CONTEXTUALHELP]
>id="cja_product_usage_data_retention"
>title="Override data retention window"
>abstract="Shorten the availability of product usage data to help reduce costs."
