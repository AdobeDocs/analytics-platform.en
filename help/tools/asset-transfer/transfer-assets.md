---
title: Transfer assets
description: Learn how to transfer components from one user to another
role: Admin
solution: Customer Journey Analytics
exl-id: c5ed81ea-1d55-4193-9bb1-a2a93ebde91f
---
# Transfer assets

The Asset Transfer tool lets you transfer ownership of assets to other users. Assets can include components such as projects, segments, date ranges, calculated metrics, annotations, alerts and scheduled projects.

Assets are often tied to an individual owner and in some cases, such as segments and calculated metrics, cannot be edited or shared even by administrators. When users leave the organization or their role changes, it may become necessary to transfer ownership of these assets to other users to ensure continuity and appropriate access. 

## Permissions

Asset Transfer requires the Product Administrator permission for Customer Journey Analytics.

## Transfer assets

1. In CJA, navigate to **[!UICONTROL Tools]** > **[!UICONTROL Asset Transfer]**.

    ![Asset transfer menu item](/help/tools/asset-transfer/assets/asset-transfer.png)

1. In the **[!UICONTROL Users]** dialog, search for and select the user you want to transfer assets from. 

    >[!IMPORTANT]
    >
    >You can only do a 1:1 transfer, from one user to another user. One-to-many or many-to-one transfers are not supported.


1. After you have selected a user, the Transfer assets option appears at the bottom of the screen.

    ![Transfer assets menu option](/help/tools/asset-transfer/assets/after-selection.png)

1. Click **[!UICONTROL Transfer assets]**.

1. On the **[!UICONTROL Transfer assets]** screen, first select the recipient to whom you want to transfer assets.

1. Now go through each component folder in the left navigation to select individual components or all assets in a folder to transfer.

    >[!NOTE]
    >
    >Transferring assets from an admin to a non-admin does not upgrade the recipient to an admin. 


    >[!NOTE]
    >
    >    When transferring assets that reference other components (for example, projects that reference other segments and calculated metrics), components not owned by the current owner of the project will only be shared with the recipient. Ownership of all other components will be transferred to the recipient.

1. To select _all_ assets in a folder, check the box next to **[!UICONTROL Name]** at the top of the table.

    ![select assets to transfer](/help/tools/asset-transfer/assets/select-assets.png)

1. Click **[!UICONTROL Transfer]** at the top right after you have made all your selections.

1. Click **[!UICONTROL Confirm]** when the confirmation message appears.

    >[!IMPORTANT]
    >
    >Do not not close the screen during transfer to avoid abortion of the process. This ensures a smooth transfer experience.

## Transfer outcomes

There are three possible outcomes for a transfer:

- **Transfer success**: "Assets transferred successfully."

- **Partial success**: "Some assets were transferred successfully."

- **Transfer failure**: "Failed to transfer assets. Please try again."

### Potential reasons for asset transfer failure

- Dependent services causing failures:  Asset transfer interacts with a different service for each component type (e.g. network issues, downstream service problems), so this could cause a partial or complete failure, or intermittent failures.

- Missing component or transferred by another Admin:  A component was deleted by another user, or transferred by another admin to someone else, while an asset transfer job was still in progress.

- API POST body not populating correctly: a component may not be sent in API POST body when multiple component types are selected.

- User does not exist:  User was deleted mid-transfer, or is invalid for another reason. If the user is invalid before transfer starts, the tool will catch this and will not process the job. If the user was deleted mid-transfer, this could cause partial failures.

- Connection/network failure: connection dies mid transfer. Any batches of transfer jobs that were already transmitted to the backend still process to completion, but the user will not see the transfer result message with a summary of what succeeded and what failed.

- Browser tab closed mid-transfer: For very large transfers, if the browser tab is closed or the page is navigated away from mid-transfer, only the network requests made before the tab close/page navigation occurs will properly transfer assets. If the user navigates back to the page, they will not receive the response status message indicating which assets did transfer, and which ones did not.

## Transfer assets during upgrade from Adobe Analytics to Customer Journey Analytics

One of the major use cases for asset transfer is during upgrade from Adobe Analytics to Customer Journey Analytics. 

The [Component Migration](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/component-migration/component-migration) feature in Adobe Analytics lets you migrate admin-owned projects to other admins. All components that make up these projects are then recreated in Customer Journey Analytics and the recipient admin owns all those components, irrespective of who created them.

This Asset Transfer tool subsequently lets admins reassign components to their rightful owners, whether they are admins or not.

>[!IMPORTANT]
>
>While you can transfer components using this tool, you as the admin still need to ensure that the recipient has access to the data views required to view/use these components. You can view and assign permissions in the [Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html).

## Export to CSV

The **[!UICONTROL Export to CSV]** option only lets admins download a list of users displayed to a .csv file. It does not let them export a list of transferred assets to a .csv file.

## Inactive users

All previously deleted users appear under one "Inactive users"" entry, along with all their orphan components. These components can be transferred to a new recipient. This feature will be available in January.

![Inactive users showing up in Transfer assets UI](assets/inactive-users.png)

