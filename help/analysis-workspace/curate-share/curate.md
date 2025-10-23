---
description: Learn how to curate projects in Analysis Workspace. Curation limits access to components before you share a project.
keywords: Analysis Workspace curation
title: Curate Projects
feature: Curate and Share
exl-id: f9636191-8414-458c-9881-8c03f3d45efb
role: User
---
# Curate projects

Curation lets you limit the components (dimensions, metrics, segments, date ranges) before sharing a project. When a recipient opens the project, they see a limited set of components that you have curated for them. Curation is an optional but recommended step before sharing a project. 

>[!NOTE]
> Product profiles are the primary mechanism governing which components a user can see. They are managed through the [Adobe Experience Cloud Admin Console](https://experienceleague.adobe.com/en/docs/core-services/interface/administration/admin-tool-experience-cloud). Curation is a secondary segment. 

## Apply project curation

1. Select **[!UICONTROL Share]** > **[!UICONTROL Curate Project Data]**. 
   The components that are used in the project are automatically added.
    If a project has multiple data view, you see a curate drop target for each data view in the project.  
1. (Optional) To add more components, drag components you want to share from the left panel to the **[!UICONTROL Curate components]** drop zone for the data view. 
1. Select **[!UICONTROL Done]**.

<!--
Curation can also be applied from the [!UICONTROL Share] menu by selecting **[!UICONTROL Curate and Share]**. This option automatically curates the project to the components in use in the project. You can add additional components following the steps above.
-->

![The Curate Components window showing the components in use in the project.](assets/curation-field.png)

When a recipient opens a curated project, they only see the curated set of components you have defined:


## Remove project curation

To remove project curation and restore the full set of components in the left panel:

1. Select **[!UICONTROL Share]** > **[!UICONTROL Curate Project Data]**. 
1. Select **[!UICONTROL Remove Curation]**. 
1. Select **[!UICONTROL Done]**.

## Component curation options

In a curated project, the recipient is presented with the option to **[!UICONTROL Show All]** components in the left panel. [!UICONTROL Show All] reveals different sets of components, depending on:

* The user's permission level (admin or non-admin)
* Project role (owner/editor or not)
* Type of curation applied (at the project level)

| Curation type | Admin can see | Non-admin project owner (or edit role) can see | Non-admin duplicate role can see |
| --- | --- | --- | --- |
| **Components *hidden* from a data view** | All data view components are available for reporting (hidden components require you to select **[!UICONTROL Show all]**) | Not available for reporting | Not available for reporting |
| **Components added or removed from a data view** | Only components added to the data view (hidden or not hidden). Admins cannot report on fields or components that are not defined in the data view. | Only components added to the data view, or components owned by or shared with the user. Hidden components are not available (like Virtual report suite curation). | Only components added to the data view are not hidden and are included in the Project curation. | 
| **Curated components in a Project** | All data view components that are available for reporting (hidden components require you to select **[!UICONTROL Show all]**) | All non-hidden data view components (requires clicking "show all") | Only curated components, plus any components owned or shared with the user |
| **Curated Project using a data view with hidden components** | All data components available for reporting (hidden and non-curated components require you to select **[!UICONTROL Show all]**)| All non-curated project components, all non-hidden data view components, and any components owned by or shared with the user | Only curated components, plus any components owned by or shared with the user |
