---
title: Lack of permissions
description: Learn how to troubleshoot issues resulting from lack of permissions
role: Admin
solution: Customer Journey Analytics
feature: Troubleshooting
exl-id: 341123b9-f4d6-4ef7-96f1-789850261b96
autotag-review: '2026-05-19T09:32:28.410Z'
TQID: 'https://experienceleague.adobe.com/qGrpX20MMcrjeEO75K2Ndoki4eiDmEvmaUCzED8jR1w'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: eb00932f-4d46-46bc-b1d8-10de7588db8d
    internal-label: Data governance
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
    internal-label: Administration
subfeature_v2:
  - id: a67cb189-a535-41f6-afa2-448f39c4759f
    internal-label: Access control
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
    internal-label: Governance
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
---
# Lack of permissions

Customer Journey Analytics does not function properly when certain Adobe Experience Platform permissions are not in place.

As an example, after creating a [Connection](../connections/overview.md) and [Data view](../data-views/data-views.md), you might be presented with the following error message in the [Components](/help/data-views/create-dataview.md#components) section: 


>[!BEGINSHADEBOX]

*[!UICONTROL Something went wrong retrieving DULE policies. Please verify account permissions, policies, or labels. Message: Forbidden.]*

>[!ENDSHADEBOX]


1. Ensure you have the right access control:

   * You must have system or product administrator privileges for an organization that has an Experience Platform product. See [Access control overview](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html#platform-permissions) for more information.

   * You must be a user in the AEP-Default-All-Users product profile. Ask your administrator if you don't have the permissions to add yourself to this profile. See [Access control hierarchy and workflow](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html#access-control-hierarchy-and-workflow) for more information.


1. Navigate to the Adobe Experience Platfom UI.

1. Select **[!UICONTROL Permissions]** from the left rail.

1. Select **[!UICONTROL Roles]**.

1. Navigate into the relevant role.

1. Select ![Edit](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Edit]** to edit the role.

1. Ensure **[!UICONTROL Manage Data Usage Policies]** and **[!UICONTROL View Data Usage Policies]** are added to the **[!UICONTROL Data Governance]** container.

1. Select **[!UICONTROL Save]** to save the changes.
