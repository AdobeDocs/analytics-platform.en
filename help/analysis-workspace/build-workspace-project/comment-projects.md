---
description: Learn how to comment on a project in Analysis Workspace
title: Add And Manage Comments In Projects
feature: Workspace Basics
role: User
exl-id: 05f69a1c-31c2-40d8-ae8b-a084169897b1
---
# Add and manage comments in projects {#comment-on-projects}

Comments in Analysis Workspace allow you to share insights and ask questions within the context of an Analysis Workspace project. This can streamline discussions about the data, keeping conversations within the context of the data that is being discussed. 

>[!NOTE]
>
>The ability to add and manage comments on a project can be disabled either at the project level or at the organization level. If you can't add and manage comments as described in this section, the Customer Journey Analytics administrator or project owner has disabled this ability.
>
>* **Project:** The project owner can disable this functionality for the project, as described in [Create projects](/help/analysis-workspace/build-workspace-project/create-projects.md).
>* **Organization:** The Customer Journey Analytics administrator can disable this functionality for the organization, as described in [Preferences](/help/analysis-workspace/user-preferences.md). 

## View comments

You can view comments from the comments area in the right rail or from the comment badge if one exists. 

>[!NOTE]
>
>A project must be saved before the comments area is visible in the right rail. If the project has not been previously saved, you need to [save the project](/help/analysis-workspace/build-workspace-project/save-projects.md) before adding comments.


![View comments in Analysis Workspace](assets/workspace-comments-view.png)

### View comments in the comments area

All comments made in an Analysis Workspace project are visible in the comments area in the right rail. The total number of existing comments is shown on the comments icon.

1. By default, the comments area is expanded for each project in Analysis Workspace the first time you open a project. 

   Select the comments area icon in the right rail of a project to open or close the comments area. 

   ![Comments area closed](assets/comments-area-closed.png)

   Each comment shows a time stamp of the day that the comment was posted. If the comment was posted on the current day, the time of day is shown. Mouse over the day or time to show the full date and time the comment was posted.

1. (Optional) To search the comments area, select the search icon ![search icon](assets/comments-search-icon.png), then type a word or phrase. The comments area is filtered to contain only those comments that include that word or phrase.

### View comment badges in a project

Comments that are made [on a specific area of the project](#comment-on-a-specific-area-of-the-project) have a **comment badge** ![comment badge](assets/comment-indicator.svg) that displays over the area of the project that the comment pertains to. Select a badge to view the comment. After selecting the badge, you can select the comment itself to highlight the comment in the comments area in the right rail. 

Numbers display on each badge in a project and are ordered in the order they were created. If multiple comments are placed in the same area of a project, the badge shows 3 dots ![comment badge multiple](assets/comment-indicator-multiple.svg). Select the 3-dot badge to reveal all comments in that area.

<!-- Insert screeshot-->

To hide all comment badges from a project:

1. With the project open in Analysis Workspace, select the comments area icon ![Comments area icon](/help/assets/icons/Comment.svg) in the right rail of Analysis Workspace.

1. At the bottom of the comments area, enable the option, **[!UICONTROL Hide placed badges]**.

## Add comments

You can add a comment that references a specific area of the project or you can add a general comment.

### Comment on a specific area of the project

To comment on a specific area of the project (such as a metric value in a freeform table):

1. With the project open in Analysis Workspace, right-click the area of the project where you want to insert the comment.

   All visualizations support comment badges on the visualization header, but only the following visualizations support comment badges on specific data points within the visualization:

   * Freeform table
   * Cohort table
   * Line
   
   <!--add screenshot-->

1. Select **[!UICONTROL Add comment]**.

1. In the **[!UICONTROL New comment]** field, specify your comment. 

   Comments can be up to 15,000 characters and can include basic markup, hyperlinks, bulleted and numbered lists, and emojis.

1. (Optional) Notify another person about your comment by typing the @ symbol followed by their name. For more information about using the @ symbol to notify others, see [Include others in a comment](#include-others-in-a-comment).

1. Select **[!UICONTROL Submit]**.

   A **comment badge** ![comment badge](assets/comment-indicator.png) is placed in the area of the Workspace project where you added the comment, as described in [View comment badges in a project](#view-comment-badges-in-a-project). The comment also appears at the top of the comments area in the right rail. 

### Add a general comment about the project

To add comments to a project in Analysis Workspace:

1. With the project open in Analysis Workspace, select the comments area icon ![Comments area icon](/help/assets/icons/Comment.svg) in the right rail of Analysis Workspace. <!-- add screen shot -->

1. In the **[!UICONTROL New comment]** field, specify your comment. 

   Comments can be up to 15,000 characters and can include basic markup, hyperlinks, bulleted and numbered lists, and emojis.

1. (Optional) Notify another person about your comment by typing the @ symbol followed by their name. For more information about using the @ symbol to notify others, see [Include others in a comment](#include-others-in-a-comment).

1. Select **[!UICONTROL Submit]**.

   The comment appears at the top of the comments area, as described in [View comments in the comments area](#view-comments-in-the-comments-area). 

## Include others in a comment

The comment feature in Analysis Workspace makes it easier to collaborate with others. 

Consider the following when using the @ symbol to include people in a comment: 
   
* People you include receive notifications based on their Adobe Experience Cloud notification settings.

  For more information, see [Receive notifications about comments](#receive-notifications-about-comments).

* You can include anyone in a comment who is in your organization and has access to Customer Journey Analytics, but doing so does not automatically grant them access to edit the project.

To include another person in your comment:

1. Type the @ symbol, then begin typing the first name, last name, or email address of the person you want to include.

   ![tag user](assets/comments-tag-user.png)

1. Select the person's name when it appears in the drop-down menu. 

## Reply to a comment

1. In Analysis Workspace, open the project where you want to add a comment.

1. Select the comments area icon ![Comments area icon](/help/assets/icons/Comment.svg) in the right rail of Analysis Workspace, then select **[!UICONTROL Reply]** next to the comment you want to reply to.

   To include the text of the comment you are replying to, with the original text wrapped in a quote tag, select the 3-dot icon next to the specific comment or reply that you want to reply to, then select **[!UICONTROL Quote reply]**. A quote reply is a good way to indicate which comment or reply your comment refers to.

   Or

   Select the comment icon on the panel or visualization where the comment was made, then select **[!UICONTROL Reply]**.

1. In the **[!UICONTROL New comment]** field, specify your comment. 

   Comments can be up to 15,000 characters and can include basic markup, hyperlinks, bulleted and numbered lists, and emojis.

1. (Optional) Notify another person about your comment by typing the @ symbol followed by their name. For more information about using the @ symbol to notify others, see [Include others in a comment](#include-others-in-a-comment).

1. Select **[!UICONTROL Submit]**.

## Receive notifications about comments

Project owners and [specific people you mention](#include-others-in-a-comment) receive notifications based on their Adobe Experience Cloud notification settings. By default, they receive an in-app notification, visible from the [Experience Cloud notification](https://experienceleague.adobe.com/en/docs/core-services/interface/features/account-preferences#view-notifications) icon ![Experience Cloud notification icon](assets/experience-cloud-notification.svg) in Customer Journey Analytics. 

Additionally, people can configure their Experience Cloud notification settings to receive email notifications and Slack notifications by [subscribing to email notifications](https://experienceleague.adobe.com/en/docs/core-services/interface/features/account-preferences#subscribe-to-in-app-and-email-notifications) and [subscribing to Slack notifications](https://experienceleague.adobe.com/en/docs/core-services/interface/features/account-preferences#slack).

## Place a badge for an existing comment

If a comment is available in the comments area in the right rail but it does not yet have a badge in the project, you can add the badge.

1. With the project open in Analysis Workspace, select the comments area icon ![Comments area icon](/help/assets/icons/Comment.svg) in the right rail of Analysis Workspace. 

1. Select the more icon ![More icon](/help/assets/icons/MoreSmallList.svg) next to the comment for which you want to place a badge, then select **[!UICONTROL Place badge]**. 

1. Select the area of the project where you want to place the badge for the existing comment. 

   A **comment badge** ![comment badge](assets/comment-indicator.png) is placed in the area of the Workspace project that you selected. The comment also appears at the top of the comments area in the right rail.

   See [View comment badges in a project](#view-comment-badges-in-a-project) for more information. 

To remove a badge:

1. Select the badge that you want to remove, then select **[!UICONTROL Remove badge]**.

   The badge is removed, but the comment is still available in the comments area in the right rail.

## Move a badge for an existing comment

You can move a comment badge that is already placed for an existing comment. 

1. With the project open in Analysis Workspace, locate the badge for the comment that you want to move.

1. Right-click the badge, then select **[!UICONTROL Move placement]**.

1. Select the area of the project where you want to place the badge. 

<!-- add section about adding images to comments. will be available at GA. Include that "you can have a maximum of 5 images per comment, and each image can be up to 2 MB." -->

## Copy the link to a comment

You can copy the link to a comment and share the link with others. Only people who already have access to the project can access it with the link.  

To copy the link to a comment:

1. With the project open in Analysis Workspace, select the comments area icon ![Comments area icon](/help/assets/icons/Comment.svg) in the right rail of Analysis Workspace. 

1. Select the more icon ![More icon](/help/assets/icons/MoreSmallList.svg) next to the comment whose link you want to copy, then select **[!UICONTROL Copy link]**. 

   The link is copied to your system clipboard. You can paste the link in an email or other type of message.

## Copy the text of a comment

You can copy the body text of a comment and share it with others. 

To copy the body text of a comment:

1. With the project open in Analysis Workspace, select the comments area icon ![Comments area icon](/help/assets/icons/Comment.svg) in the right rail of Analysis Workspace. 

1. Select the more icon ![More icon](/help/assets/icons/MoreSmallList.svg) next to the comment that contains the text you want to copy, then select **[!UICONTROL Copy body text]**. 

   The body text of the comment is copied to your system clipboard. 

## Like a comment

1. With the project open in Analysis Workspace, select the comments area icon ![Comments area icon](/help/assets/icons/Comment.svg) in the right rail of Analysis Workspace. 

1. Select **[!UICONTROL Like]** beneath the comment that you want to endorse.

## Delete a comment

When you delete a comment, the original comment and any replies or attachments are also deleted. 

Deleted comments cannot be recovered.

To delete a comment:

1. With the project open in Analysis Workspace, select the comments area icon ![Comments area icon](/help/assets/icons/Comment.svg) in the right rail of Analysis Workspace. 

1. Select the more icon ![More icon](/help/assets/icons/MoreSmallList.svg) next to the comment that you want to delete, then select **[!UICONTROL Delete]**. 

1. Select **[!UICONTROL Delete]** again to confirm the deletion.

## Resolve a comment

When you resolve a comment, the comment is marked as resolved and hidden from the comments area. If the comment has a badge associated with it, the badge is removed from the project.

To resolve a comment:

1. With the project open in Analysis Workspace, select the comments area icon ![Comments area icon](/help/assets/icons/Comment.svg) in the right rail of Analysis Workspace. 

1. Select the more icon ![More icon](/help/assets/icons/MoreSmallList.svg) next to the comment that you want to resolve, then select **[!UICONTROL Resolve]**. 

1. Select **[!UICONTROL Resolve]** again to confirm.

By default, resolved comments are hidden from the comments area. To show resolved comments:

1. Select the filter icon in the comments area, then deselect the option, **[!UICONTROL Hide resolved comments]**.
