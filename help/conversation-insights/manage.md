---
title: Manage Conversation Insights Configuration
description: Learn how to manage Conversation Insights configurations.
solution: Customer Journey Analytics
feature: AI Tools
role: Admin, User
autotag-review: '2026-10-02T07:03:36.851Z'
TQID: 'https://experienceleague.adobe.com/D2nrhtN2SaHoAw0PU7yJtabvx-q0L5FHtBFu1sORfaI'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ae3aff40-b2f6-4df1-8c01-0b0720d1510f
    internal-label: AI Tools
  - id: d7a261eb-f9ac-4dd6-bd60-1637efcd3d36
    internal-label: Conversation Insights
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
    internal-label: Data management
---
# Manage configurations

After you [create Conversation Insights configurations](/help/conversation-insights/configure.md), you can view, edit, or delete these configurations. 

Only system administrators can manage Conversation Insights configurations.

For information about Conversation Insights, see [Conversation Insights overview](/help/conversation-insights/overview.md).


## View and filter existing configurations

To view your existing Conversation Insights configurations:

1. In Customer Journey Analytics, select **[!UICONTROL Data Management]** > **[!UICONTROL Conversation Insights configuration]**.

   ![Conversation Insights configurations overview](assets/conversation-insights-configurations.png)

   The following columns of information are available about each configuration:

   * **[!UICONTROL Name]**: The name of the Conversation Insights configuration. 
   * **[!UICONTROL Created by]**: The user who created the configuration.

   * **[!UICONTROL Sandbox]**: The Experience Platform sandbox that contains the profile dataset that you added to your connection. 

   * **[!UICONTROL Connection]**: The connection that you added to your configuration. 

   * **[!UICONTROL Date created]**: The date and time that the configuration was created.

   * **[!UICONTROL Last modified]**: The date the configuration was last modified.

   * **[!UICONTROL Status]**: The status of the configuration. Possible values are: 
     ![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL Complete]**, ![StatusBlue](/help/assets/icons/StatusBlue.svg) **[!UICONTROL Pending]**, or ![StatusRed](/help/assets/icons/StatusRed.svg) **[!UICONTROL Failed]**.

   To configure which columns to display in the table, select ![ColumnSetting](/help/assets/icons/ColumnSetting.svg). In the **[!UICONTROL Customize table]** dialog, select the columns to show. Then select **[!UICONTROL Apply]**.

1. (Optional) To filter the list of configurations, select ![Filter](/help/assets/icons/Filter.svg), then filter by any of the following criteria:

   * **[!UICONTROL Connection]**

   * **[!UICONTROL Created by]**

   * **[!UICONTROL Sandbox]**

   * **[!UICONTROL Status]**

## Create a configuration

To create a new Conversation Insights configuration:

1. Select **[!UICONTROL Create configuration]**.
1. Use the [**[!UICONTROL Create configuration]**](./configure.md) dialog to configure conversation insights.

## Edit a configuration

To edit an existing Conversation Insights configuration:

1. Do any of the following:
   
   * Select the name of the configuration that you want to edit.
   * Select the checkbox next to the configuration that you want to edit, then select ![Edit](/help/assets/icons/Edit.svg) **[!UICONTROL Edit]** from the blue action bar.
   * Select ![More](/help/assets/icons/More.svg) for the configuration you want to edit. From the context menu select ![Edit](/help/assets/icons/Edit.svg) **[!UICONTROL Edit]**. 

1. Use the [**[!UICONTROL Configuration / _name of configuration_]**](./configure.md) dialog to manage conversation insights.

## Delete a configuration

To delete an existing Conversation Insights configuration:

1. Do any of the following:

   * Select the checkbox next to the configuration that you want to delete, then select ![Delete](/help/assets/icons/Delete.svg) **[!UICONTROL Delete]** from the blue action bar.
   * Select ![More](/help/assets/icons/More.svg) for the configuration you want to edit. From the context menu select ![Delete](/help/assets/icons/Delete.svg) **[!UICONTROL Delete]**. 
   
1. In the **[!UICONTROL Delete Configuration]** dialog, select **[!UICONTROL Delete]** to delete the configuration. Select **[!UICONTROL Cancel]** to cancel.
