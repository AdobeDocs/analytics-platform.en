---
title: Create a data view in Customer Journey Analytics
description: Learn about the recommended path when upgrading from Adobe Analytics to Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: yes
hidefromtoc: yes
---
# Create a data view in Customer Journey Analytics

>[!NOTE]
> 
>Follow the steps on this page only after you complete all previous upgrade steps. You can follow the [recommended upgrade steps](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations), or you can follow the upgrade steps that were dynamically generated for your organization with the [Adobe Analytics to Customer Journey Analytics upgrade questionnaire](https://gigazelle.github.io/cja-ttv/). 
>
>After you complete the steps on this page, continue following the recommended upgrade steps or the dynamically generated upgrade steps. 

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-views/create-dataview.md -->

Creating a data view involves either creating metrics and dimensions from schema elements or using standard components. Most schema elements can be either a dimension or a metric, depending on your business's requirements. Once you drag a schema element into a data view, options appear on the right where you can adjust how the dimension or metric operates in Customer Journey Analytics.

To create a data view:

1. Log in to [Customer Journey Analytics](https://analytics.adobe.com) and go to the **[!UICONTROL Data views]** tab.

1. Select **[!UICONTROL Create new data view]**. Alternatively, you can select an existing data view from the list of data views to edit it.

1. On the [!UICONTROL **Configure**] tab, specify a name for the data view and configure its basic settings, components, and calendar options. 

   For detailed information about each field, see [Configure](/help/data-views/create-dataview.md#configure) in [Create or edit a data view](/help/data-views/create-dataview.md).

   ![Configure data view](assets/dataview-configure.png)

1. Select the [!UICONTROL **Components**] tab. 

   The [!UICONTROL **Components**] tab is where you set a data view's components, which means you can create metrics and dimensions from schema elements. You can also use standard components.

   ![Components tab](assets/dataview-components.png)

1. From the [!UICONTROL **Components**] tab, drag schema elements from the left rail into the [!UICONTROL **Metrics**] section or the [!UICONTROL **Dimensions**] section. The schema elements that you add become metrics or dimensions in the data view. 

   For detailed information about the options available when adding components to a data view, see [Components](/help/data-views/create-dataview.md#components) in [Create or edit a data view](/help/data-views/create-dataview.md).

1. Select the [!UICONTROL **Settings**] tab. From here, you can configure filters to apply to your entire data view and configure session timeout and metrics.

   For detailed information about the options available when configuring settings for a data view, see [Settings](/help/data-views/create-dataview.md#settings) in [Create or edit a data view](/help/data-views/create-dataview.md).

1. Select **[!UICONTROL Save]** to save the configuration for your data view.

1. After all desired settings are specified, select **[!UICONTROL Save and finish]**.

1. Continue following the [recommended upgrade steps](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) or the [dynamically generated upgrade steps](https://gigazelle.github.io/cja-ttv/). 

