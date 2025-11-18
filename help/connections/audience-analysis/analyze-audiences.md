---
title: Analyze audiences from RTCDP
description: Learn how to analyze audiences from RTCDP in Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Audiences
role: Admin
hide: yes
hidefromtoc: yes
---
# Analyze audiences from RTCDP {#analyze-audiences-RTCDP}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-audience-analysis-consent"
>title="Import profile consent policy data from Experience Platform"
>abstract="Consent policies are Experience Platform rules that define which marketing actions you can perform on data. You should enable this option if you have a consent policy defined on a dataset in your sandbox."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-audience-analysis-merge-policy"
>title="Merge policy"
>abstract="Merge policies are Experience Platform rules that determines which data is prioritized and what data is combined to create a unified view of a person. You should enable this option if you have a merge policy defined on a dataset in your sandbox."

<!-- markdownlint-enable MD034 -->

Audience analysis allows you to ingest audience membership data from Experience Platform Profile datasets into a Customer Journey Analytics connection. Audiences become available as new dimensions for use in Analysis Workspace.

You make the following selections when creating an audience analysis configuration:

* **The sandbox** that contains the profile dataset that you want to add to your connection

* **The profile dataset** that includes the Experience Platform audience data that you want to analyze

* **The connection** where you want to add the profile dataset that you select

* **Any data views** associated with your connection that you want to use when analyzing Experience Platform audience data within Analysis Workspace

  These data views are automatically configured with Experience Platform audience data for reporting. 

The following are automatically created:

* **New audience dimensions**<!--and metrics?--> that represent the Experience Platform audiences that are included in the profile dataset you selected, and are available for reporting in Analysis Workspace.

* **New lookup dataset** that provides friendly names for the new audience dimensions. The lookup dataset is also added to the connection, along with the profile dataset you select.

Something above Details that says, "We're just configuring data views for reporting, and we have to configure them at the connection level, and so we're having you choose some things ... We're going to be creating brand new lookup datasets to provide friendly names for audiences." 

"Here's what we're going to do: add this profile dataset to the connection you select, create a new lookup dataset, and add that to the connection as well, and then create new dimensions and metrics within the selected data views." 

We're creating, automatically populating, and keeping them up to date. That is the value that this is providing. And automatically creating the dimension and metrics in their data views. The audiences that come in become dimensions. There are 4 that we create (via derived fields).  

To create an audience analysis configuration:

1. In Customer Journey Analytics, select **[!UICONTROL Data Management]** > **[!UICONTROL Audience analysis configuration]**.

   ![Audience analysis main page](assets/audience-analysis-empty.png)

1. Select **[!UICONTROL Create configuration]**.

   ![Create audience analysis configuration](assets/audience-analysis-create.png)

1. In the **[!UICONTROL Details]** section, in the **[!UICONTROL Name]** field, specify a name for the configuration.

1. In the **[!UICONTROL Sandbox]** dropdown menu, select the sandbox that contains the profile dataset that you want to add to your connection. 

   Adobe Experience Platform provides [sandboxes](https://experienceleague.adobe.com/en/docs/experience-platform/sandbox/home) which partition a single Platform instance into separate virtual environments to help develop and evolve digital experience applications. You can think of sandboxes as "data silos" that contain datasets. Sandboxes are used to control access to datasets.


   

 

