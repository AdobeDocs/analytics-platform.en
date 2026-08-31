---
title: Configure Consent Reporting and Filtering
description: Learn how to use the provisioning wizard to enable consent reporting and optional ingest-time filtering for a connection in Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Privacy
role: Admin
hide: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: eb00932f-4d46-46bc-b1d8-10de7588db8d
    internal-label: Data governance
  - id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
    internal-label: Integrations
subfeature_v2:
  - id: ffe2fd81-0630-49b3-a33b-4b8899e89c51
    internal-label: Privacy
  - id: d3fb138f-79e4-4a81-aedb-76dd93560085
    internal-label: Experience Platform integration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
    internal-label: Governance
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
---
# Configure consent reporting and filtering {#configure-consent-reporting}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-consent-merge-policy"
>title="Merge policy"
>abstract="Merge policies combine profile data from multiple datasets into unified customer profiles used for audience creation. select merge policy the Profile dataset that contains the consent policy membership data (the `consentPoliciesIDMap` field) that you want to report on. Or consult your data team to learn which audiences are associated with each merge policy."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-consent-sandbox"
>title="Sandbox"
>abstract="Select the sandbox that contains the correct Experience Platform profile datasets. These datasets need to contain the consent data that you want to report on in Analysis Workspace."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-consent-person-id"
>title="Person ID"
>abstract="Select a field from the model-based schema that represents the Person ID. The selection is limited to the list of fields in the schema that are marked as 'Identity' and do have an identity namespace."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-consent-identity-namespace"
>title="Use primary identity namespace"
>abstract="Enable this option if you want Customer Journey Analytics to find the identity in the Identity Map that is marked with a primary=true attribute and uses that identity as the Person ID for that row. This identity is the primary key that is used in Experience Platform for partitioning. <br/>If you leave this option disabled, select a namespace from the Identity namespace field below. Customer Journey Analytics searches each row's Identity Map for this namespace key and uses the identity under that namespace as the Person ID for that row."

<!-- markdownlint-enable MD034 -->

System administrators can enable consent reporting and, optionally, consent filtering for one or more connections. For overview information, see [Consent reporting and filtering overview](/help/connections/consent-reporting-filtering/consent-overview.md).

>[!IMPORTANT]
>
>Consent filtering excludes non-consenting visitor data at ingest time. Data that is excluded by filtering is not stored in Customer Journey Analytics and cannot be recovered for past dates. Review your marketing action selections carefully before you enable filtering.

## Create a configuration

When you create a configuration for consent reporting and filtering, you select the sandbox and merge policy dataset that contain your consent policy membership data, choose the connection or connections to configure, and choose whether to filter data for each marketing action. Customer Journey Analytics then creates the consent policy lookup dataset and the consent policy components automatically.

To create a consent reporting and filtering configuration:

1. In Customer Journey Analytics, select **[!UICONTROL Data Management]** > **[!UICONTROL Consent reporting and filtering]**.

1. Select **[!UICONTROL Create configuration]**.

1. In the **[!UICONTROL Details]** section, specify the following information:

   | Field | Description |
   |---------|----------|
   | **[!UICONTROL Name]** | Specify a name for the configuration. |
   | **[!UICONTROL Sandbox]** | Select the Experience Platform sandbox that contains the Profile dataset with your consent policy membership data. <p>A maximum of one consent policy lookup dataset exists per sandbox. Multiple configurations in the same sandbox share the same lookup dataset.</p> |

1. In the **[!UICONTROL Profile dataset]** section, in the [!UICONTROL **Merge policy**] field, select the merge policy that corresponds to the Profile dataset that contains the consent policy membership data (the `consentPoliciesIDMap` field) that you want to report on. When you enable consent reporting, this Profile dataset is added to the connection that you select if it is not already part of it.<p>Merge Policies determine how Adobe Experience Platform combines profile data from multiple datasets into unified customer profiles used for consent policy membership data. Each day, a snapshot of this data is generated in Experience Platform. This snapshot provides a static view of the data at a specific point in time and does not include any event data.</p><p>Select the **[!UICONTROL Default Timebased]** merge policy if you see multiple merge policies and you are unsure which one to choose. You can also consult your data team to better understand which consent data is associated with each merge policy.</p>

1. In the **[!UICONTROL Connection]** section, select **[!UICONTROL Select a connection]**, select the checkbox next to the connection to configure, then select **[!UICONTROL Use connection]**.

   Consent reporting and filtering is applied at the connection level. All data views under a configured connection inherit the same behavior.

1. (Optional) Choose whether to enable reporting for the consent data. <!--explanation of why you would or wouldn't want to -->

   To enable and configure reporting:

   1. In the [!UICONTROL **Reporting**] section, select [!UICONTROL **Enable reporting**].

   1. Select any data views associated with your connection that you want to use when analyzing Platform consent data within Analysis Workspace. In the **[!UICONTROL Data views]** section, click **[!UICONTROL Select data views]**.

   1. In the Data views dialog, select the checkbox next to one or more data views that you want to use for consent reporting. These data views are automatically configured with Experience Platform consent data for reporting.

   1. Select **[!UICONTROL Use data views]**.

1. (Optional) In the **[!UICONTROL Filtering]** section, select [!UICONTROL **Enable filtering**] to filter consent data.

   When filtering is enabled, Customer Journey Analytics ingests a visitor's data only if the visitor matches any consent policies that are enabled. For more information, see [Consent filtering](/help/connections/consent-reporting-filtering/consent-overview.md#consent-filtering) in [Consent reporting and filtering overview](/help/connections/consent-reporting-filtering/consent-overview.md).

1. (Optional) Enable filtering for the following marketing actions:

   >[!NOTE]
   >
   >When filtering for a marketing action is enabled, Customer Journey Analytics ingests a visitor's data only if the visitor matches **all** consent policies that apply to that marketing action. For more information, see [Consent filtering](/help/connections/consent-reporting-filtering/consent-overview.md#consent-filtering) in [Consent reporting and filtering overview](/help/connections/consent-reporting-filtering/consent-overview.md).

   | Marketing action | Description |
   |---------|----------|
   | **[!UICONTROL Analytics data]** | Filter data used for standard Customer Journey Analytics reporting in Analysis Workspace. |
   | **[!UICONTROL Data science data]** | Filter data used for advanced analytics, machine learning, and data science use cases. |

1. Select **[!UICONTROL Create]** to create the configuration.

   If you enabled reporting, Customer Journey Analytics automatically:

   * Adds the selected Profile dataset to the connection.
   * Creates a consent policy lookup dataset for the sandbox (if one does not already exist) and syncs policy names and descriptions from Experience Platform.
   * Adds the consent policy components (dimensions, metrics, and a derived field) to the data views within the configured connection.

1. After the configuration completes, [view the consent policy components in the data view](#view-consent-policy-components-in-the-data-view) to verify that they are available.

## View consent policy components in the data view

After you [create a configuration](#create-a-configuration), you can verify that the consent policy components were added to the data views under the configured connection.

To view the consent policy components in the data view, you must be a product profile administrator for the product profile that the data view is assigned to. For more information, see [Access control](/help/technotes/access-control.md).

To view the consent policy components in the data view:

1. In Customer Journey Analytics, select **[!UICONTROL Data Management]** > **[!UICONTROL Data views]**.

1. Open a data view that is associated with the configured connection.

1. In the **[!UICONTROL Dimensions]** section, the following dimensions should now be available:

   * **[!UICONTROL Consent Policy ID]**

   * **[!UICONTROL Policy Name]**

   * **[!UICONTROL Policy Description]**

1. In the **[!UICONTROL Metrics]** section, the following metrics should now be available:

   * **[!UICONTROL Visitors with Consent]**

   * **[!UICONTROL Events with Consent]**

   * **[!UICONTROL Unique Consent Policies]**

   <!-- TODO: Add a screenshot of the consent policy components in the data view (assets/consent-components-dataview.png). -->

1. Use the consent policy components in Analysis Workspace.

   Users who have access to the data view in Analysis Workspace can now see the new components and use them in their analyses. For information about how to use the consent policy components in Analysis Workspace, see [Analyze consent policy data](/help/connections/consent-reporting-filtering/consent-analyze.md).
