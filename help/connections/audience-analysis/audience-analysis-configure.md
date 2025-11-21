---
title: Configure audience analysis
description: Learn how to configure audience analysis
solution: Customer Journey Analytics
feature: Audiences
role: Admin
hide: yes
hidefromtoc: yes
---
# Configure audience analysis {#configure-audience-analysis}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-audience-analysis-merge-policy"
>title="Merge policy"
>abstract="Merge policies combine profile data from multiple datasets into unified customer profiles used for audience creation. Select the Default Timebased merge policy if you see multiple merge policies and you are unsure which to choose. You can also consult your data team to better understand which audiences are associated with each merge policy."

<!-- markdownlint-enable MD034 -->

Audience analysis allows you to ingest audience membership data from Experience Platform Profile datasets into a Customer Journey Analytics connection. Audiences become available as new dimensions for use in Analysis Workspace. For more detailed overview information about audience analysis, see [Audience analysis overview](/help/connections/audience-analysis/audience-analysis-overview.md).

When creating an audience analysis configuration, you select the sandbox and merge policy associated with the Experience Platform audiences that you want to analyze. Customer Journey Analytics creates a new lookup dataset, then automatically adds the lookup dataset and the profile dataset to the connection you choose. 

To create an audience analysis configuration:

1. In Customer Journey Analytics, select **[!UICONTROL Data Management]** > **[!UICONTROL Audience analysis configuration]**.

   ![Audience analysis main page](assets/audience-analysis-empty.png)

1. Select **[!UICONTROL Create configuration]**.

   ![Create audience analysis configuration](assets/audience-analysis-create.png)

1. In the **[!UICONTROL Details]** section, specify the following information:

   | Field | Description | 
   |---------|----------|
   | **[!UICONTROL Name]** | Specify a name for the configuration. | 
   | **[!UICONTROL Sandbox]** | Select the sandbox that contains the profile dataset that you want to add to your connection. <p>Adobe Experience Platform provides [sandboxes](https://experienceleague.adobe.com/en/docs/experience-platform/sandbox/home) which partition a single Platform instance into separate virtual environments to help develop and evolve digital experience applications. You can think of sandboxes as "data silos" that contain datasets. Sandboxes are used to control access to datasets.</p> |

1. In the **[!UICONTROL Profile dataset]** section, specify the following information:

   | Field | Description | 
   |---------|----------|
   | **[!UICONTROL Merge policy]** | Select the merge policy that corresponds to the profile dataset that you want to use for audience analysis. <p>Merge Policies determine how Adobe Experience Platform combines profile data from multiple datasets into unified customer profiles used for audience creation. The merge policy you select affects which profile's attributes are included in your audiences. Each day, a snapshot of this data is generated in Experience Platform. This snapshot provides a static view of the data at a specific point in time and does not include any event data.</p><p>Select the **[!UICONTROL Default Timebased]** merge policy if you see multiple merge policies and you are unsure which one to choose. You can also consult your data team to better understand which audiences are associated with each merge policy.</p> | 
   | **[!UICONTROL Profile dataset]** | The profile dataset that is associated with the merge policy you selected. This profile dataset includes the Experience Platform audience data that you want to analyze. This profile dataset is added to the connection that you select.<p>After you choose a merge policy, the profile snapshot export is shown. For example: `Profile-Snapshot-Export-abbc7093-80f4-4b49-b96e-e743397d763f`.</p><p>For more inofrmation, see [Profile attribute datasets](https://experienceleague.adobe.com/en/docs/experience-platform/dashboards/query#profile-attribute-datasets) in the Experience Platform Dashboards Guide.</p> |

In the Connection section, 



1. In the Connection section, select Choose a connection (or something similar?)

1. After you choose a connection, in the **[!UICONTROL Person ID]** field, select a field from the model-based schema that represents the Person ID. The selection is limited to the list of fields in the model-based schema that are marked as Identity and do have an identity namespace. 

   If you select Identity Map for the person ID, you have to select a namespace. You have two options:

   * Enable **[!UICONTROL Use primary identity namespace]** to use the primary identity namespace.

   * Select a namespace from the **[!UICONTROL Identity namespace]** drop-down menu.

   If there are no Person IDs to choose from, that means one or more Person IDs have not been defined in the schema. See [Define identity fields in the UI](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/ui/fields/identity) for more information.

1. Choose whether to enable the option, **[!UICONTROL Use Primary Identity Namespace]**. This option instructs Customer Journey Analytics to find the identity in the Identity Map that is marked with a primary=true attribute and use that identity as the Person ID for that row. This identity is the primary key that is used in Experience Platform for partitioning. And this identity is also the prime candidate for usage as Customer Journey Analytics Person ID (depending on how the dataset is configured in a Customer Journey Analytics connection).

1. **[!UICONTROL Identity Namespace]**: (This option is disabled if you use the Primary ID Namespace.) Identity namespaces are a component of the [Experience Platform Identity Service](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/namespaces). Namespaces serve as indicators of the context to which an identity relates. If you specify a namespace, Customer Journey Analytics searches each row's Identity Map for this namespace key and use the identity under that namespace as the Person ID for that row. Since Customer Journey Analytics cannot do a full dataset scan of all rows to determine which namespaces are present, all possible namespaces are displayed in the drop-down menu. Know which namespaces are specified in the data; these namespaces are not auto-detected.

1. Data views: The audiences that come in become dimensions. There are 4 that we create (via derived fields).  


   

 

