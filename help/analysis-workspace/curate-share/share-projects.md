---
description: Learn how to share projects in Analysis Workspace.
keywords: Analysis Workspace sharing
title: Share Projects
feature: Curate and Share
exl-id: ac4ed73a-e890-46cc-be08-4ccedf66b47d
role: User
---
# Share projects {#share-projects}

>[!CONTEXTUALHELP]
>id="workspace_shareprojects"
>title="Share projects"
>abstract="You can share any of these project roles with other users in your organization."



You can share an Analysis Workspace project with the following types of people:

* Users and groups in your organization who have access to Customer Journey Analytics 

  You can share Edit, Duplicate, or View access

* Users and groups in your organization who don't have access to Customer Journey Analytics

  Recipients have read-only access

* People outside your organization

  Recipients have read-only access

Any [curation](curate.md) you apply prior to sharing is reflected when recipients open the project. 


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Project sharing in Analysis Workspace](https://video.tv.adobe.com/v/36207/?quality=12&learn=on){target="_blank"} for a demo video.

{{videoaa}}

>[!ENDSHADEBOX]


## Share with users and groups in your organization {#Add}

You can share a project with existing Analysis Workspace users or groups in your organization. When you share a project as described in this section, the users you share with must already have a Customer Journey Analytics account.

You can share a specific role with users or groups, or you can share a link.

* [Share a specific project role](#share-a-specific-project-role)

* [Share a link to a project](#share-a-link-to-a-project)

## Share a specific project role

When sharing a specific project role with users and groups in your organization, consider the following:

* Project roles (**[!UICONTROL Edit original]**, **[!UICONTROL Edit copy]**, and **[!UICONTROL Read only]**) are tied to the user and specific project ID. Project roles are independent of user permissions managed in the [Adobe Experience Cloud Admin Console](https://experienceleague.adobe.com/en/docs/core-services/interface/administration/admin-getting-started).
   
* In Customer Journey Analytics, groups are defined by product profiles in the [Adobe Experience Cloud Admin Console](https://experienceleague.adobe.com/en/docs/core-services/interface/administration/admin-getting-started). Admins can share to any group, including *All*. Non-admins can share to any group they are a member of, except for *All*.

* A user who is placed in multiple roles always get the highest experience. This scenario might occur if a user is added both as an individual and as part of a group. For example, if a user is given the **[!UICONTROL Edit original]** role as an individual and the **[!UICONTROL Read only]** role as a member of a group, the user receives a **[!UICONTROL Edit original]** project experience.

* Admins placed in the **[!UICONTROL Edit copy]** or **[!UICONTROL Read only]** role receive those limited experiences when they open a project. An Admin can change their role to **[!UICONTROL Edit original]** by sharing the project with themselves and granting the Edit role, as described in the following procedure. 

* If you select multiple projects to share, recipients are added to the existing list of recipients for each project. 

  For example, Project A is already shared with recipients 1, 2, and 3, while Project B is already shared with recipients 4, 5, and 6. 

  Projects A and B are then shared with recipients 4 and 7. The new share list for Project A is now 1, 2, 3, 4, and 7, while the new share list for Project B is 4, 5, 6, and 7. 

To share a specific project role with users or groups in your organization:

1. In Customer Journey Analytics, select the [!UICONTROL **Workspace**] tab, then select [!UICONTROL **Projects**] in the left panel.

1. Select the checkbox next to one or more projects that you want to share, then select [!UICONTROL **Share**].

   Or

   To share an individual project only, you can open the project that you want to share, then select **[!UICONTROL Share]** > **[!UICONTROL Share with Workspace users]**. 
   If there are unsaved changes, you are prompted to save your project first. 

   The Share project dialog box displays. The [!UICONTROL **Share by link**] and [!UICONTROL **Settings**] sections of the dialog box are visible only when sharing a single project.

   ![The Share project window.](assets/share-proj-modal.png)

1. Add recipients or groups of recipients in one of the provided role fields:

   **Edit original:** Recipients can **[!UICONTROL Save]** changes to a project and function as co-owners. This role is useful if you want to co-manage a project with other colleagues. This role includes editing, deleting, and modifying recipient lists for a shared project. <br>Note: Analysis Workspace does not currently support live collaboration, so it is recommended that only one user edit a project at a given time. If projects are saved at the same time, the last version is kept. 

   **Edit copy:** Recipients can **[!UICONTROL Save as]** and have access to the left panel. Project interactions are not limited to this role. This role is useful if you want to share a project to users who understand your organization's data and how to use Analysis Workspace. But you do not want these users to modify your project.

   **Read only:** Recipients cannot **[!UICONTROL Save]** or **[!UICONTROL Save as]** and do not have access to the left panel. Project interactions are also limited. This role is useful if you want to share a project to users that are less familiar with your organization's data structure, Analysis Workspace or Customer Journey Analytics generally. However, you still want them to consume data and insights in a safe environment. Learn more about the [Read only project experience](/help/analysis-workspace/curate-share/view-only-projects.md).

1. (Conditional) If you are sharing a single project, choose whether to enable the following options when sharing the project:

   * **Share embedded project components:** Shares segments, calculated metrics, and date ranges with all recipients. After being shared, these components will appear in the Components drop-down menu of the recipient's Workspace. This setting does not persist - it is a one-time action at the time of sharing.

   * **Set as landing page for recipients:** Sets this page as the landing page for recipients. This setting does not persist - it is a one-time action at the time of sharing.
 
1. Select **[!UICONTROL Share]**. (If the project has already been shared, select [!UICONTROL **Update**].)
  
   Or
   
   Select **[!UICONTROL Curate and Share]** to apply project curation automatically. (If the project has already been shared, select **[!UICONTROL Curate & Update]**.) Learn more about [project curation](curate.md).


## Share a link to a project 

When sharing a link as described in this section, consider the following: 

* Recipients who use the link are required to log in to Customer Journey Analytics before gaining access to the project. 

* If a recipient is not assigned a role and receives a [shareable link](/help/analysis-workspace/curate-share/shareable-links.md) to the project (**[!UICONTROL Share] > [!UICONTROL Get project link]**), they are given a role by default. Admins receive **[!UICONTROL Edit original]** and non-admins receive **[!UICONTROL Edit copy]**.

To share the project link with users in your organization:

1. Save the project. If there are unsaved changes, you are prompted to save your project before sharing a link.

1. Select **[!UICONTROL Share]** > **[!UICONTROL Share with Workspace users]**, then select **[!UICONTROL Copy]** next to the **[!UICONTROL Share by link]** field.  

   ![The Share project highlighting the Share by link field.](assets/share-proj-modal.png)

1. Share the link with users in your organization. For example, you can paste it into an email, onto an internal web site, and so forth. 

## Share a project with anyone (no login required) {#share-public-link}

>[!CONTEXTUALHELP]
>id="workspace_share_with_anyone_require_aec_authentication"
>title="Require Experience Cloud authentication"
>abstract="Your organization requires that users log in to the Experience Cloud in order to use this link."


You can grant [read-only access](/help/analysis-workspace/curate-share/view-only-projects.md) to Analysis Workspace projects to people who don't have access to Customer Journey Analytics. This granted access can include:

* People outside your organization 

* People within your organization who do not have access to Customer Journey Analytics  

>[!NOTE]
>
>Consider the following when sharing an Analysis Workspace project with people who don't have access to Customer Journey Analytics:
>
>* The ability to share a project in this way can be disabled by the Customer Journey Analytics administrator, as described in [Preferences](/help/analysis-workspace/user-preferences.md). If you can't share a project as described in this section, your Customer Journey Analytics administrator has disabled this ability.
>
>* Projects with more than 50 expanded visualizations can only be shared with people who have access to Customer Journey Analytics.
>
>* Users you share with can view any segments that were applied to the project during [curation](curate.md). 
> 
>* Users you share with can change the project date range. The date range that you set for the project is shown by default.
>
>* A project might become inaccessible if many users attempt to access a given link at the same time. By default, more than 190 people can access a single link every 5 minutes. If your organization reaches this limit, wait 5 minutes and then try accessing the link again.
>
>* For both [!DNL Healthcare Shield] and [!DNL Privacy & Security Shield] licenses, the [!UICONTROL Share with anyone] feature requires Experience Cloud authentication. For [!DNL Healthcare Shield] customers, a "HIPAA compliance" warning appears, but you can still use this feature after authenticating to Experience Cloud. 

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Share with anyone](https://video.tv.adobe.com/v/3420093/?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]


To share an Analysis Workspace project with anyone:

1. Open the Analysis Workspace project that you want to share.

1. Select **[!UICONTROL Share]** > **[!UICONTROL Share with anyone]**.
   
   If there are unsaved changes, you are prompted to save your project. 

   <!-- Add screen shot of new modal -->

1. Enable the **[!UICONTROL Link is active]** option if it is not already enabled.

   Selecting this option creates a link to the project that can be shared with anyone. You can disable access to the project at any time by disabling this option.

   The owner of the project is also the owner of this link. Link ownership can be transferred to another user only when project ownership is transferred, as described in [Transfer user assets](/help/tools/asset-transfer/transfer-assets.md) in the Analytics Admin guide.

1. Choose whether to enable the following security option (this option can be controlled by your Customer Journey Analytics administrator): 

   * **[!UICONTROL Require Experience Cloud authentication]:** 
   
     When this option is enabled, the only users who can access the project are those who can log in to the Adobe Experience Cloud organization where the project that you are sharing was created. However, users you share with do not need to have access to Customer Journey Analytics.

     Customer Journey Analytics administrators can configure this preference for the company, as described in [Preferences](/help/analysis-workspace/user-preferences.md). You might encounter the following scenarios, depending on how the administrator configured this option:
     
     * If this option is not visible, your Customer Journey Analytics administrator did not enable this feature. 

     * If this option is enabled and you can't disable it, the locked option means that your Customer Journey Analytics administrator requires Experience Cloud authentication for anyone accessing Analysis Workspace projects. This is always the case for organizations who license Healthcare Shield. 

1. Next to the **[!UICONTROL Share with anyone (no login required)]** field, select ![Link](/help/assets/icons/Link.svg) to copy the link to your system clipboard. 

1. Share the link with the people you want to have access to the project. For example, you can paste the link in an email. 
   
   Any person you share the link with can view the Analysis Workspace project.

1. (Optional) You can select ![Generate new link icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) to remove access from users who previously received a link to the project. A new link is generated that you can share with users who you want to access the project.

1. Select **[!UICONTROL Close]** to close the share dialog box. Your changes are automatically saved. 

## View projects shared with you

When someone shares a project with you by [sharing a specific project role](#share-a-specific-project-role), you can access the shared projects from the [Projects tab of on the Analytics landing page](/help/getting-started/landing.md#navigate-the-projects-tab). 

When someone shares a project with you by sharing a link (either from the [Share project tab](#share-a-link-to-a-project) or using a [share with anyone link](#share-a-project-with-anyone-no-login-required)), you must use the link that was shared with you to access the project. For example, the link might have been shared in an email, on an internal website, and so forth.

## Share embedded components

You can share the embedded components that are part of your project.

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Share embedded components in Analysis Workspace](https://video.tv.adobe.com/v/24713/?quality=12&learn=on){target="_blank"} for a demo video.

{{videoaa}}

>[!ENDSHADEBOX]


## FAQs {#FAQs}

|Question|Answer|
|---|---|
|What happens if two editors save a project at the same time?|Changes are not merged and the last saved project version is kept. Analysis Workspace does not currently support live collaboration.|
|As an admin, what project experience do I see?|Admins placed in a **[!UICONTROL Edit copy]** or **[!UICONTROL Read only]** role receives those limited experiences when they open a project. If desired, an Admin can increase their role to **[!UICONTROL Edit original]** at anytime through **[!UICONTROL Components] > [!UICONTROL Projects]**. |
|What happens if a recipient is placed in one role as an individual and another role as a member of a group?|If a recipient is placed in multiple roles, they always receive the higher experience. For example, if a recipient is given the **[!UICONTROL Edit original]** role as an individual and the **[!UICONTROL Can view]** role as a member of a group, the user receives a **[!UICONTROL Edit original]** project experience.|
|What experience does a recipient get if they open a project link?|Recipients receive the role that you placed them in the share modal. If a recipient is not assigned a role and receives a link to the project (**[!UICONTROL Share]** > **[!UICONTROL Share with Workspace users]** and then selects **[!UICONTROL Copy]** next to the **[!UICONTROL Share by link]** field), the is placed into a default role. Admins receive **[!UICONTROL Edit original]** and Non-admins receive **[!UICONTROL Edit copy]** roles.|
