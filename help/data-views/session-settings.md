---
title: Session Settings
description: Learn about the settings in a data view you can use to define length of a session and the trigger to initiate a new session
solution: Customer Journey Analytics
feature: Data Views
exl-id: 25710bf1-ec85-4a7d-a404-54549013cc2c
role: Admin
---
# Session settings {#session-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_settings_datapreview"
>title="Data preview"
>abstract="Compares the data of this data view with data of the connection. The preview percentage is based on the total number in the connection from the **last 90 days**.<br><br/>If the preview is not loading, your connection could still be backfilling."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-enable MD034 -->


In Customer Journey Analytics, you can define a session in any way to match how persons interact with your digital experiences. You configure session settings within a data view.

Session settings definitions are non-destructive and do not alter the underlying data. You can set up multiple data views (each with their own specific session settings definition) as a foundation for your Workspace projects.

To define the context of a session within a data view:

1. Select **[!UICONTROL Data views]**, optionally from **[!UICONTROL Data management]**, in the main navigation of the Customer Journey Analytics UI.

2. Create a new or edit an existing data view. See [Create or edit a data view](create-dataview.md) for more information.

3. Select the **[!UICONTROL Settings]** tab. Underneath [!UICONTROL Session settings]:

   1. Enter a value for **[!UICONTROL Session timeout]** in [!UICONTROL minute(s)], [!UICONTROL hour(s)], [!UICONTROL day(s)], or [!UICONTROL week(s)]. The session timeout determines how long a session can be idle (no events occur) before starting a new session.

      Use a short session timeout (for example 30 minutes) if you are interested in analyzing mostly online interactions. For example, analyzing whether profiles visiting your online store product pages did add products to their cart or even purchased online.

      Use a long session timeout (for example 3 months) if you are combining online and offline data and want to analyze whether customers that have purchased one or more of your products, have called your contact center within the first three months after their purchase.


   2. Select a metric from the **[!UICONTROL Drop a metric here]** list underneath **[!UICONTROL Start new session with a metric]**. Alternatively, you can drag and drop a metric from the left pane on the **[!UICONTROL Drop a metric field]**. The selected metric defines the start of a new session. You can define more than one metric.
   
      You can use any kind of metric to define a new session. As an example, imagine you want to define a new session every time a profile launches your mobile app. In **[!UICONTROL Data view]** > **[!UICONTROL Components]**, you define a component of type metric, named **[!UICONTROL Launch]**, based on an **[!UICONTROL appInteraction]** **[!UICONTROL Name]** schema field. You further specify the **[!UICONTROL Launch]** metric component to only count the value when the value matches `launch`. 
      
      ![App Interaction Metric Component Launches](assets/component-launches.png)
      
      Then you drag and drop, or select the **[!UICONTROL Launch]** metric as the metric to define a new session.

      ![Session Settings Launches](assets/session-settings-launches-metric.png)



4. Select **[!UICONTROL Save]** or **[!UICONTROL Save and finish]** to save the session settings definition.
