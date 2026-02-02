---
title: Configure audience analysis
description: Learn how to configure audience analysis
solution: Customer Journey Analytics
feature: Audiences
role: Admin
---
# Configure audience analysis {#configure-audience-analysis}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-audience-analysis-merge-policy"
>title="Merge policy"
>abstract="Merge policies combine profile data from multiple datasets into unified customer profiles used for audience creation. Select 'Default Timebased' if you see multiple merge policies and you are unsure which to choose. Or consult your data team to learn which audiences are associated with each merge policy."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-audience-analysis-sandbox"
>title="Sandbox"
>abstract="Select the sandbox that contains the correct Experience Platform profile datasets. These datasets need to contain the audience data that you want to report on in Analysis Workspace. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-audience-person-id"
>title="Person ID"
>abstract="Select a field from the schema that represents the Person ID. The selection is limited to the list of fields in the schema that are marked as Identity and have an identity namespace."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-audience-namespace"
>title="Use primary identity namespace"
>abstract="Enable this option if you want Customer Journey Analytics to find the identity in the Identity Map that is marked with a primary=true attribute, and then use that identity as the Person ID for that row. This identity is the primary key that is used in Experience Platform for partitioning. <br/>If you leave this option disabled, select a namespace from the Identity namespace field below. Customer Journey Analytics searches each row's Identity Map for this namespace key and uses the identity under that namespace as the Person ID for that row."

<!-- markdownlint-enable MD034 -->

Audience analysis allows you to ingest audience membership data from Experience Platform Profile datasets into a Customer Journey Analytics connection. Audiences become available as new dimensions for use in Analysis Workspace. For more detailed overview information about audience analysis, see [Audience analysis overview](/help/connections/audience-analysis/audience-analysis-overview.md).

>[!IMPORTANT]
>
>Audience data is reprocessed and generated each night, making audience data accurate for analysis only for the previous day ("yesterday"). 
>
>Audiences are available in Customer Journey Analytics data views on the day after you create the audience analysis configuration. 

## Create an audience analysis configuration

When creating an audience analysis configuration, you select the sandbox and merge policy associated with the Experience Platform audiences that you want to analyze. Customer Journey Analytics creates a new lookup dataset, then automatically adds the lookup dataset and the profile dataset to the connection you choose. 

Only system administrators can create audience analysis configurations.

To create an audience analysis configuration:

1. In Customer Journey Analytics, select **[!UICONTROL Data Management]** > **[!UICONTROL Audience analysis configuration]**.

   ![Audience analysis main page](assets/audience-analysis-empty.png)

1. Select **[!UICONTROL Create configuration]**.

   ![Create audience analysis configuration](assets/audience-analysis-create.png)

1. In the **[!UICONTROL Details]** section, specify the following information:

   | Field | Description |
   |---------|----------|
   | **[!UICONTROL Name]** | Specify a name for the configuration. | 
   | **[!UICONTROL Sandbox]** | Select the Experience Platform sandbox that contains the profile dataset that you want to add to your connection. A single sandbox can support up to 100 audience analysis configurations. <p>Adobe Experience Platform provides [sandboxes](https://experienceleague.adobe.com/en/docs/experience-platform/sandbox/home) which partition a single Platform instance into separate virtual environments to help develop and evolve digital experience applications. You can think of sandboxes as "data silos" that contain datasets. Sandboxes are used to control access to datasets.</p> |

1. In the **[!UICONTROL Profile dataset]** section, specify the following information:

   | Field | Description |
   |---------|----------|
   | **[!UICONTROL Merge policy]** | Select the merge policy that corresponds to the profile dataset that you want to use for audience analysis. <p>Merge Policies determine how Adobe Experience Platform combines profile data from multiple datasets into unified customer profiles used for audience creation. The merge policy you select affects which profile's attributes are included in your audiences. Each day, a snapshot of this data is generated in Experience Platform. This snapshot provides a static view of the data at a specific point in time and does not include any event data.</p><p>Select the **[!UICONTROL Default Timebased]** merge policy if you see multiple merge policies and you are unsure which one to choose. You can also consult your data team to better understand which audiences are associated with each merge policy.</p> |
   | **[!UICONTROL Profile dataset]** | The profile dataset that is associated with the merge policy you selected. This profile dataset includes the Experience Platform audience data that you want to analyze. This profile dataset is added to the connection that you select.<p>After you choose a merge policy, the profile snapshot export is shown. For example: `Profile-Snapshot-Export-abbc7093-80f4-4b49-b96e-e743397d763f`.</p><p>For more information, see [Profile attribute datasets](https://experienceleague.adobe.com/en/docs/experience-platform/dashboards/query#profile-attribute-datasets) in the Experience Platform Dashboards Guide.</p> |

1. In the **[!UICONTROL Connection]** section, click **[!UICONTROL Select a connection]**.

1. In the Connections dialog, select the checkbox next to the connection where you want to add the profile dataset, then select **[!UICONTROL Use connection]**.

   A connection can be associated with only one audience analysis configuration.

1. Specify the following information to configure the connection:

   | Field | Description |
   |---------|----------|
   | **[!UICONTROL Person ID]** | Select a field from the schema that represents the Person ID.<p>The selection is limited to the list of fields in the schema that are marked as Identity and do have an identity namespace. **[!UICONTROL IdentityMap]** is selected by default and is appropriate for most configurations. </p><p>If there are no Person IDs to choose from, it means one or more Person IDs have not been defined in the schema. See [Define identity fields in the UI](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/ui/fields/identity) for more information.</p>  |
   | **[!UICONTROL Use primary identity namespace]** | This option shows if you select **[!UICONTROL Identity Map]** for the Person ID. <p>Enable this option if you want Customer Journey Analytics to find the identity in the Identity Map that is marked with a primary=true attribute, and then use that identity as the Person ID for that row. This identity is the primary key that is used in Experience Platform for partitioning. And this identity is also the prime candidate for usage as Customer Journey Analytics Person ID (depending on how the dataset is configured in a Customer Journey Analytics connection).</p> |
   | **[!UICONTROL Identity namespace]** | This option shows if you select **[!UICONTROL Identity Map]** for the Person ID. This option is disabled if you use the Primary ID Namespace. <p>Identity namespaces are a component of the [Experience Platform Identity Service](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/namespaces). Namespaces serve as indicators of the context to which an identity relates. If you specify a namespace, Customer Journey Analytics searches each row's Identity Map for this namespace key and uses the identity under that namespace as the Person ID for that row. Because Customer Journey Analytics cannot do a full dataset scan of all rows to determine which namespaces are present, all possible namespaces are displayed in the drop-down menu. You must know which namespaces are specified in the data; these namespaces are not auto-detected.</p> |
   
   <!-- Add this when B2B releases for AuA **[!UICONTROL Account ID]** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}|  (only displayed for account-based connections) The Account ID that is used to support account-based reporting for the dataset. -->

1. In the **[!UICONTROL Data views]** section, click **[!UICONTROL Select data views]**.

1. In the Data views dialog, select the checkbox next to one or more data views that you want to use when analyzing Experience Platform audience data within Analysis Workspace. These data views are automatically configured with Experience Platform audience data for reporting.

1. Select **[!UICONTROL Use data views]**.

1. Select **[!UICONTROL Create]** to create the configuration.

   >[!IMPORTANT]
   >
   >Because the profile dataset is updated once per day, audiences are available in Customer Journey Analytics data views on the day after you create the audience analysis configuration.


1. After 24 hours, [view audience dimensions in the data view](#view-audience-dimensions-in-the-data-view) to verify that the audience dimensions are available in the data views that you selected. 
 
## View audience dimensions in the data view

After you [create an audience analysis configuration](#create-an-audience-analysis-configuration), you can verify that audience dimensions were added to the data views that you selected during the configuration.

To view audience dimensions in the data view, you must be a product profile administrator for the product profile that the data view is assigned to. For more information, see [Access control](/help/technotes/access-control.md).

To view the audience analysis dimensions in the data view:

1. In Customer Journey Analytics, select **[!UICONTROL Data Management]** > **[!UICONTROL Data views]**.

1. In the **[!UICONTROL Dimensions]** section, the following dimensions should now be available:

   * **[!UICONTROL Audience Name]**

   * **[!UICONTROL Audience Origin]**

   * **[!UICONTROL Exited Audience Origin]**

   * **[!UICONTROL Exited Audience Name]**

   Note that each of these dimensions was added to the profile dataset that is associated with the merge policy that you selected during the audience analysis configuration, and each was added to the new lookup dataset that was created.

   ![Audience dimensions available in the data view](assets/audience-analysis-dataview-dataset.png)

1. Use the audience analysis dimensions in Analysis Workspace. 

   Users who have access to use the data view in Analysis Workspace can now see the new dimensions and use them in their analyses. For information about how to use the audience analysis dimensions in Analysis Workspace, see [Analyze Experience Platform audiences in Customer Journey Analytics](/help/connections/audience-analysis/analyze-audiences.md).


