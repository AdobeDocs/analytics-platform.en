---
description: Project sharing and project roles in Workspace
keywords: Analysis Workspace sharing
title: Share projects
feature: Curate and Share
exl-id: ac4ed73a-e890-46cc-be08-4ccedf66b47d
---
# Share projects

You can share an Analysis Workspace project with the following types of people:

* Users and groups in your organization who have access to Adobe Customer Journey Analytics 

  You can share Edit, Duplicate, or View access

* Users and groups in your organization who don't have access to Customer Journey Analytics

  Recipients have read-only access

* People outside your organization

  Recipients have read-only access

Any [curation](curate.md) you apply prior to sharing is reflected when recipients open the project. 

Here is a video overview of project sharing:

>[!VIDEO](https://video.tv.adobe.com/v/36207/?quality=12)


## Share with Customer Journey Analytics users and groups in your organization {#Add}

You can share a project with existing Customer Journey Analytics users or groups in your organization. When you share a project as described in this section, the users you share with must already have an Customer Journey Analytics account.

You can share a specific role with users or groups, or you can share a link.

* [Share a specific project role](#share-a-specific-project-role)

* [Share a link to a project](#share-a-link-to-a-project)

## Share a specific project role

When sharing a specific project role with users and groups in your organization, consider the following:

* Project roles (**[!UICONTROL Can edit]**, **[!UICONTROL Can duplicate]**, and **[!UICONTROL Can view]**) are tied to the user and specific project ID. Project roles are independent of user permissions managed in the [Adobe Experience Cloud admin console](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html).
   
* In Customer Journey Analytics, groups are defined by product profiles in the [Adobe Experience Cloud admin console](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html). Admins can share to any group, including "All." Non-admins can share to any group they are a member of, with the exception of "All."

* A user who is placed in multiple roles always get the highest experience. This might occur if a user is added both as an individual and as part of a group. For example, if a user is given the **[!UICONTROL Can edit]** role as an individual and the **[!UICONTROL Can view]** role as a member of a group, they will receive a **[!UICONTROL Can edit]** project experience.

* Admins placed in the **[!UICONTROL Can duplicate]** or **[!UICONTROL Can view]** role receive those limited experiences when they open a project. If desired, an Admin can increase their role to **[!UICONTROL Can edit]** at anytime through **[!UICONTROL Components] > [!UICONTROL Projects]**. 

To share a specific project role with users or groups in your organization:

1. Go to the project that you want to share, then click **[!UICONTROL Share]** > **[!UICONTROL Share with Workspace users]**. 
   If there are unsaved changes, you are prompted to save your project first. 

   ![](assets/share-proj-modal.png)

   For information about how to share multiple projects simultaneously, see [Share projects in the Project manager](#share-projects-in-the-project-manager).

1. Add recipients or groups of recipients in one of the provided role fields:

   **Can edit:** Recipients can **[!UICONTROL Save]** changes to a project and function as co-owners. This role is useful if you want to co-manage a project with other colleagues; this includes editing, deleting, and modifying recipient lists for a shared project. <br>Note: Analysis Workspace does not currently support live collaboration, so it is recommended that only one user edit a project at a given time. If projects are saved at the same time, the last version will be kept. 

   **Can duplicate:** Recipients can **[!UICONTROL Save as]** and have access to the left rail. Project interactions are not limited in this role. This role is useful if you want to share a project to users who understand your organization's data and how to use Analysis Workspace, but you do not want your project altered.

   **Can view:** Recipients cannot **[!UICONTROL Save]** or **[!UICONTROL Save as]** and do not have access to the left rail. Project interactions are also limited. This role is useful if you want to share a project to users that are less familiar with your organization's data structure, Analysis Workspace or Customer Journey Analytics generally. However, you still want them to consume data and insights in a safe environment. Learn more about the [Can view project experience](/help/analysis-workspace/curate-share/view-only-projects.md).

1. Choose whether to enable the following options when sharing the project:

   * **Share embedded project components:** Shares segments, calculated metrics, and date ranges with all recipients. After being shared, these components will appear in the Components drop-down of the recipient's Workspace. This setting does not persist - it is a one-time action at the time of sharing.

   * **Set as landing page for recipients:** Sets this page as the landing page for recipients. This setting does not persist - it is a one-time action at the time of sharing.
 
1. Click **[!UICONTROL Share]**. (If the project has already been shared, click [!UICONTROL **Update**].)
  
   Or
   
   Click **[!UICONTROL Curate and Share]** to apply project curation automatically. (If the project has already been shared, click **[!UICONTROL Curate & Update]**.) Learn more about [project curation](curate.md).

## Share a link to a project 

When sharing a link as described in this section, consider the following: 

* Recipients who use the link are required to log in to Customer Journey Analytics before gaining access to the project. 

* If a recipient is not assigned a role and receives a [link](/help/analysis-workspace/curate-share/shareable-links.md) to the project (**[!UICONTROL Share] > [!UICONTROL Get project link]**), they are given a role by default. Admins receive **[!UICONTROL Can edit]** and Non-admins receive **[!UICONTROL Can duplicate]**.

To share the project link with users in your organization:

1. Click **[!UICONTROL Share]** > **[!UICONTROL Share with Workspace users]**.
   If there are unsaved changes, you are prompted to save your project first. 

   ![](assets/share-proj-modal.png)

1. Click **[!UICONTROL Copy link]** next to the **[!UICONTROL Share URL field]**. 

1. Share the link with users in your organization. For example, you can paste it into an email, onto an internal web site, and so forth. 

## Share a project with anyone (no login required) {#share-public-link}

{{release-limited-testing-section}}

You can grant [read-only access](/help/analysis-workspace/curate-share/view-only-projects.md) to Analysis Workspace projects to people who don't have access to Customer Journey Analytics. This can include:

* People outside your organization 

* People within your organization who are not provisioned with Customer Journey Analytics  

>[!NOTE]
>
>Consider the following when sharing an Analysis Workspace project with people who don't have access to CJA:
>
>* The ability to share a project in this way can be disabled by the CJA administrator, as described in [Preferences](/help/analysis-workspace/user-preferences.md). If you can't share a project as described in this section, your CJA administrator has disabled this ability.
>
>* Projects with more than 14 expanded visualizations can't be shared with people who don't have access to CJA.
>
>* Users you share with can view any filters that were applied to the project during [curation](curate.md). 
> 
>* Users you share with can change the project date range. The date range you set for the project is shown by default.

To share an Analysis Workspace project with anyone:

1. Open the Analysis Workspace project that you want to share.

1. Click **[!UICONTROL Share]** > **[!UICONTROL Share with anyone]**.
   
   If there are unsaved changes, you are prompted to save your project. 

   <!-- Add screen shot of new modal -->

1. Enable the **[!UICONTROL Link is active]** option if it is not already enabled.

1. Choose whether to enable the following security option (this option can be controlled by your CJA administrator): 

   * **[!UICONTROL Require Experience Cloud authentication]:** 
   
     When this option is enabled, only users who can log in to the Adobe Experience Cloud organization where the project that you are sharing was created can access the project.

     CJA administrators can configure this preference for the company, as described in [Preferences](/help/analysis-workspace/user-preferences.md). You might encounter the following scenarios, depending on how the administrator configured this option:
     
     * If this option is not visible, your CJA administrator did not enable this feature. 

     * If this option is enabled and dimmed, your CJA administrator requires Experience Cloud authentication for anyone accessing Analysis Workspace projects. 

1. Next to the **[!UICONTROL Share with anyone (no login required)]** field, click the **Copy link** icon ![Copy link icon](assets/copy-link-icon.png) to copy the link to your system clipboard. 

1. Share the link with the people you want to have access to the project. For example, you can paste the link in an email. 
   
   Any person you share the link with can view the Analysis Workspace project.

1. (Optional) You can click the **Generate new link** icon ![Generate link icon](assets/regenerate-link.png) to remove access from users who previously received a link to the project. A new link is generated that you can share with users who you want to access the project.

1. Select **[!UICONTROL Close]** to close the share dialog box. Your changes are automatically saved. 

## Share projects in the Project manager {#Manager} 

Projects can also be shared from **[!UICONTROL Components] > [!UICONTROL Projects]**. A single project can be shared following the same steps above.  If multiple projects are selected to be shared, recipients will be added to the existing list of recipients for each project. 

For example: 

* Project A is shared to recipients  1, 2, 3 
* Project B is shared to recipients 4, 5, 6 

With Project A and B selected, recipients 4 and 7 are added to the share lists. The new share list for each project is now: 

* Project A: 1, 2, 3, 4, 7 
* Project B: 4, 5, 6, 7 

![](assets/mult-proj-sharing.png)

## Share embedded components

Here is a video on the topic:

>[!VIDEO](https://video.tv.adobe.com/v/24713/?quality=12)

## FAQs {#FAQs}

|Question|Answer|
|---|---|
|What happens if two editors save a project at the same time?|Changes are not merged and the last saved project version will be kept. Analysis Workspace does not currently support live collaboration.|
|As an admin, what project experience will I see?|Admins placed in a **[!UICONTROL Can duplicate]** or **[!UICONTROL Can view]** role will receive those limited experiences when they open a project. If desired, an Admin can increase their role to **[!UICONTROL Can edit]** at anytime through **[!UICONTROL Components] > [!UICONTROL Projects]**. |
|What happens if a recipient is placed in one role as an individual and another role as a member of a group?|If a recipient is placed in multiple roles, they will always receive the higher experience. For example, if a recipient is given the **[!UICONTROL Can edit]** role as an individual and the **[!UICONTROL Can view]** role as a member of a group, they will receive a **[!UICONTROL Can edit]** project experience.|
|What experience does a recipient get if they open a project link?|Recipients receive the role you placed them in the share modal. If a recipient is not assigned a role and receives a link to the project (**[!UICONTROL Share] > [!UICONTROL Get project link]**), they will be placed into a role by default. Admins receive **[!UICONTROL Can edit]** and Non-admins receive **[!UICONTROL Can duplicate]**.|
