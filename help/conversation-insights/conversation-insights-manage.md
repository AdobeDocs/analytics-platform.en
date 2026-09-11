---
title: Manage Conversation Insights Configuration
description: Learn how to manage Conversation Insights configurations.
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin, User
hide: true
---
# Manage Conversation Insights Configurations

After you [create Conversation Insights configurations](/help/conversation-insights/conversation-insights-configure.md), you can view, edit, or delete these configurations. 

Only system administrators can manage Conversation Insights configurations.

For information about Conversation Insights, see [Conversation Insights overview](/help/conversation-insights/conversation-insights-overview.md).

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
1. Use the [**[!UICONTROL Create configuration]**](./conversation-insights-configure.md) dialog to configure conversation insights.

## Edit a configuration

To edit an existing Conversation Insights configuration:

1. Do any of the following:
   
   * Select the name of the configuration that you want to edit.
   * Select the checkbox next to the configuration that you want to edit, then select ![Edit](/help/assets/icons/Edit.svg) **[!UICONTROL Edit]** from the blue action bar.
   * Select ![More](/help/assets/icons/More.svg) for the configuration you want to edit. From the context menu select ![Edit](/help/assets/icons/Edit.svg) **[!UICONTROL Edit]**. 

1. Use the [**[!UICONTROL Configuration / _name of configuration_]**](./conversation-insights-configure.md) dialog to configure conversation insights.

## Delete a configuration

To delete an existing Conversation Insights configuration:

1. Do any of the following:

   * Select the checkbox next to the configuration that you want to delete, then select ![Delete](/help/assets/icons/Delete.svg) **[!UICONTROL Delete]** from the blue action bar.
   * Select ![More](/help/assets/icons/More.svg) for the configuration you want to edit. From the context menu select ![Delete](/help/assets/icons/Delete.svg) **[!UICONTROL Delete]**. 
   
1. In the **[!UICONTROL Delete Configuration]** dialog, select **[!UICONTROL Delete]** to delete the configuration. Select **[!UICONTROL Cancel]** to cancel.
