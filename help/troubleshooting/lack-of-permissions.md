---
title: Lack of permissions
description: Learn how to troubleshoot issues resulting from lack of permissions
role: Data Engineer, Data Architect, Admin
solution: Customer Journey Analytics
feature: Troubleshooting
exl-id: 341123b9-f4d6-4ef7-96f1-789850261b96
---
# Lack of permissions

Customer Journey Analytics does not function properly when certain Adobe Experience Platform permissions are not in place.

As an example, after creating a [Connection](../connections/overview.md) and [Data view](../data-views/data-views.md), you might be presented with the following error message in the [Components](/help/data-views/create-dataview.md#components) section: 


>[!BEGINSHADEBOX]

*[!UICONTROL Something went wrong retrieving DULE policies. Please verify account permissions, policies, or labels. Message: Forbidden.]*

>[!ENDSHADEBOX]


To correct this error, you must have system or product administrator privileges for an organization that has an Experience Platform product. See [Access control overview](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=en#platform-permissions) for more information.

1. Navigate to the Adobe Experience Platfom UI.

1. Select **[!UICONTROL Permissions]** from the left rail.

1. Select **[!UICONTROL Roles]**.

1. Navigate into the relevant role.

1. Select ![Edit](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Edit]** to edit the role.

1. Ensure **[!UICONTROL Manage Data Usage Policies]** and **[!UICONTROL View Data Usage Policies]** are added to the **[!UICONTROL Data Governance]** container.

1. Select **[!UICONTROL Save]** to save the changes.
