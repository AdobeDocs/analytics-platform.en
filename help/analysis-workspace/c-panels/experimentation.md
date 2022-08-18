---
description: Learn about how you can analyze the results of A/B tests in the CJA Experimentation panel.
title: Experimentation panel
feature: Panels
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

The Experimentation panel is available to all CJA users. No Admin rights or other permissions are required. However, the setup requires labels in data views that only Admins can assign.

## Terminology

* **Experiment**: An experiment is a set of variations on an experience that were exposed to end users in order to determine which is best to keep in perpetuity. An experiment is made up of two or more variations, one of which is considered the control variation.

* **Variation**: One of two or more alterations in an end user's experience that are being compared for the purpose of identifying the better alternative. One variation must be selected as the control, and only one variation can be considered to be the control variation.

* **Control**: A specific variation that represents the status quo, or default state of a users' experience. What all other variations are being compared to.

* **Normalizing Metric**: The basis (sessions or people) on which a test will be run. For example, a test may compare the conversion rates of several variations where conversion rate is calculated as conversions per session or conversions per person.

* **Conversion Metric**: The metric that a user is comparing variations with. The variation with the most desirable outcome for the conversion metric (whether highest or lowest) is declared the "winner" of an experiment.

## Step 1: Create connection

After your experiment data has been ingested into Adobe Experience Platform, [create a connection in CJA](/help/connections/create-connection.md) to this experiment dataset.

## Step 2: Add context-aware labels in data views

In CJA data views settings, admins can add context labels to a dimension or metric and other CJA services can use these labels for their purposes. Two pre-defined labels are used for the Experimentation panel:

* Experiment
* Variant

In your data view that contains experimentation data, pick two dimension, one with the experimentation data and one with the variant data. Then label those dimensions with the Experiment and the Variant labels.

[](assets/context-label.png)

Without these labels present, the Experiment panel does not work.

## Step 3: Configure the Experiment panel




