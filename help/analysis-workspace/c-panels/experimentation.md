---
description: Learn about how you can analyze the results of A/B tests in the CJA Experimentation panel.
title: Experimentation panel
feature: Panels
exl-id: e11169b4-2c73-4dd4-bca7-c26189d60631
---
# Experimentation panel

>[!NOTE]
>
>This functionality is currently in [limited testing](/help/release-notes/releases.md).

The **[!UICONTROL Experimentation]** panel lets you compare different user experience, marketing, or messaging variations to determine which is best at driving a specific outcome. You can evaluate the lift and confidence of any A/B experiment from any experimentation platform - online, offline, from Adobe solutions, Adobe Journey Optimizer, and even BYO (bring-your-own) data. 

>[!IMPORTANT]
>
>At this point, [Adobe Analytics for Target](https://experienceleague.adobe.com/docs/target/using/integrate/a4t/a4t.html) (A4T) data cannot be evaluated in the [!UICONTROL Experimentation] panel.

## Access Control

The Experimentation panel is available to use by all Customer Journey Analytics (CJA) users. No Admin rights or other permissions are required. However, the setup (steps 1 and 2 below) requires actions that only Admins can perform.

## Step 1: Create connection to experiment dataset/s

After your experiment data has been [ingested](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=en) into Adobe Experience Platform, [create a connection in CJA](/help/connections/create-connection.md) to one or more experiment dataset/s.

## Step 2: Add context labels in data views

In CJA data views settings, admins can add [context labels](/help/data-views/component-settings/overview.md) to a dimension or metric and CJA services like [!UICONTROL Experimentation] panel can use these labels for their purposes. Two pre-defined labels are used for the Experimentation panel:

* [!UICONTROL Experiment]
* [!UICONTROL Variant]

In your data view that contains experimentation data, pick two dimension, one with the experimentation data and one with the variant data. Then label those dimensions with the **[!UICONTROL Experiment]** and the **[!UICONTROL Variant]** labels.

![context label](assets/context-label.png)

Without these labels present, the Experiment panel does not work, since there will be no experiments to work with.

## Step 3: Configure the Experiment panel

1. In CJA Workspace, drag the Experimentation panel into a project.

  ![experiment panel](assets/experiment.png)

   >[!IMPORTANT]
   >If the necessary setup in CJA data views has not been completed, you will receive a message to that effect before you can proceed.

1. Configure the panel input settings.

   | Setting | Definition |
   | --- | --- |
   | **[!UICONTROL Experiment]** | A set of variations on an experience that were exposed to end users in order to determine which is best to keep in perpetuity. An experiment is made up of two or more variants, one of which is considered the control variant. This setting is pre-populated with the dimensions that have been labeled with the  **[!UICONTROL Experiment]** label in data views, and the last 3 months' worth of experiment data. |
   | **[!UICONTROL Control Variant]** | One of two or more alterations in an end user's experience that are being compared for the purpose of identifying the better alternative. One variant must be selected as the control, and only one variant can be considered to be the control variant. This setting is pre-populated with the dimensions that have been labeled with the  **[!UICONTROL Variant]** label in data views. This setting pulls up the variant data that is associated with this experiment. |
   | **[!UICONTROL Success Metrics]** | The metric or metrics that a user is comparing variants with. The variant with the most desirable outcome for the conversion metric (whether highest or lowest) is declared the "primary metric" of an experiment. You can add up to 5 metrics. |
   | **[!UICONTROL Normalizing Metric]** | The basis ([!UICONTROL People], [!UICONTROL Sessions], or [!UICONTROL Events]) on which a test will be run. For example, a test may compare the conversion rates of several variations where **[!UICONTROL Conversion rate]** is calculated as **[!UICONTROL Conversions per session]** or **[!UICONTROL Conversions per person]**. |

1. Click **[!UICONTROL Build]**.

## Step 4: Interpret the panel output

The Experimentation panel returns a rich set of data and visualizations to help you better understand how your experiments are performing. At the top of the panel, a summary line is provided to remind you of the panel settings you selected. At any time, you can edit the panel by clicking the edit pencil at the top right. You also get a text summary that indicates whether the experiment is conclusive or not, and summarizes the outcome. You can also see summary numbers for the variant with the highest lift and confidence.

![experiment output](assets/exp-output1.png)   

For each success metric you selected, one freeform table and one conversion rate trend will be shown:

![experiment output](assets/exp-output2.png)

![experiment output](assets/exp-output3.png)


## Statistical methodology behind Experimentation panel

To follow.



