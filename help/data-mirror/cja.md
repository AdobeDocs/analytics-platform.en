---
title: Configure Customer Journey Analytics
description: Understand how to confgure Customer Journey Analytics connections, data views, and projects for Experience Platform Data Mirror for Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
role: Admin
hide: yes
hidefromtoc: yes
badgePremium: label="Beta"
---

# Configure Customer Journey Analytics

To use the Experience Platform Data Mirror feture for Customer Journey Analytics, you have to create or update a connections, data views and workspace projects to use the model-based data.

## Connections

In your connection add the model-based datasets that represent the data from the data warehouse native solutions. These datasets do have the mode dataset type.

When you add a model-basd dataset that contains mirrored data from a data warehouse native solution, that data is usually event data. Ensure you select the correct settings for the dataset. For example, select the correct field for identity and timestamp.


## Data views

In your data view, ensure you add fields from the model-based dataset as metrics and dimensions. Metrics and dimensions that you need when you create projects in Workspace. The data mirrored fields are available in the **[!UICONTROL Adhoc & Model-based fields]** subfolder of the **[!UICONTROL Event datasets]** folder. Use functionality, like derived fields, to transform fields as you see fit.


## Workspace projects

Set up Workspace projects that use metrics and dimensions which are ultimately based on data in your data warehouse native solution and are updated based on the data mirror functionality you configured.

