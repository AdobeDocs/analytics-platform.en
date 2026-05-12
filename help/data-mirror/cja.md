---
title: Configure Customer Journey Analytics
description: Understand how to configure Customer Journey Analytics connections, data views, and projects for Experience Platform Data Mirror for Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
role: Admin
badgePremium: label="Beta"
exl-id: f7687bba-efbe-4a2c-8ad1-cf216554a1e9
TQID: https://experienceleague.adobe.com/1LArX1cyRWpEY8O9xMwTcgwc0aUTjMrniFiDXtpkCNY
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
    internal-label: Dimensions
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
---
# Configure Customer Journey Analytics

{{release-limited-testing}}

{{relational-model-based}}

To use the Experience Platform Data Mirror feature for Customer Journey Analytics, you have to create or update connections, data views and workspace projects to use relational data.

## Connections

In your connection, add the relational datasets that represent the data from the data warehouse native solutions. These datasets do have the Relational dataset type.

When you add a relational dataset that contains mirrored data from a data warehouse native solution, that data is usually event data. Ensure you select the correct settings for the dataset. For example, select the correct dataset type, field for identity, and field for timestamp.


## Data views

Define fields from the relational schema as components (metrics and dimensions) in your data view. The data mirrored fields are available in the **[!UICONTROL Adhoc & relational fields]** subfolder of the **[!UICONTROL Event datasets]** folder. Use functionalities, like [derived fields](/help/data-views/derived-fields/derived-fields.md) or [component settings](/help/data-views/component-settings/overview.md), to modify the components that are based on relational fields.


## Workspace projects

Set up Workspace projects that use metrics and dimensions from your relational data. Components that are ultimately based on data in your data warehouse native solution. And are updated based on the data mirror functionality you have configured.

>[!MORELIKETHIS]
>
>[Data Mirror quick start guide: Mirror and use relationald data](relational.md)
>
