---
title: Configure Consent Reporting and Filtering
description: Learn how to use the provisioning wizard to enable consent reporting and optional ingest-time filtering for a connection in Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Privacy
role: Admin
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
# Configure consent reporting and filtering

System administrators can enable consent reporting and, optionally, consent filtering for one or more connections. For overview information, see [Consent reporting and filtering overview](/help/connections/consent-reporting-filtering/crf-overview.md).

>[!IMPORTANT]
>
>Consent filtering excludes non-consenting visitor data at ingest time. Data that is excluded by filtering is not stored in Customer Journey Analytics and cannot be recovered for past dates. Review your marketing action selections carefully before you enable filtering.

## Prerequisites

Before you configure consent reporting and filtering, make sure that:

* You have system administrator permissions in Customer Journey Analytics.
* The sandbox that you want to use contains a Profile dataset with consent policy membership data in the `consentPoliciesIDMap` field.
* The connection that you want to configure already exists. For more information, see [Create or edit a connection](/help/connections/create-connection.md).

## Create a configuration

When you create a configuration for consent reporting and filtering, you select the sandbox and Profile dataset that contain your consent policy membership data, choose the connection or connections to configure, and choose whether to filter data for each marketing action. Customer Journey Analytics then creates the consent policy lookup dataset and the consent policy components automatically.

To create a consent reporting and filtering configuration:

1. In Customer Journey Analytics, select **[!UICONTROL Data Management]** > **[!UICONTROL Consent reporting and filtering]**.

1. Select **[!UICONTROL Create configuration]**.

1. In the **[!UICONTROL Details]** section, specify the following information:

   | Field | Description |
   |---------|----------|
   | **[!UICONTROL Name]** | Specify a name for the configuration. |
   | **[!UICONTROL Sandbox]** | Select the Experience Platform sandbox that contains the Profile dataset with your consent policy membership data. <p>A maximum of one consent policy lookup dataset exists per sandbox. Multiple configurations in the same sandbox share the same lookup dataset.</p> |

1. In the **[!UICONTROL Profile dataset]** section, select the Profile dataset that contains the consent policy membership data (the `consentPoliciesIDMap` field) that you want to report on. This Profile dataset is added to the connection that you select.

1. In the **[!UICONTROL Connection]** section, select **[!UICONTROL Select a connection]**, select the checkbox next to one or more connections to configure, then select **[!UICONTROL Use connection]**.

   Consent reporting and filtering is applied at the connection level. All data views under a configured connection inherit the same behavior.

1. (Optional) In the **[!UICONTROL Filtering]** section, you can enable filtering for the following marketing actions:

   >[!NOTE]
   >
   >Leave both toggles unselected to enable consent reporting without filtering.
   >
   >When filtering for a marketing action is enabled, Customer Journey Analytics ingests a visitor's data only if the visitor matches **all** consent policies that apply to that marketing action. For more information, see [Consent reporting and filtering overview](/help/connections/consent-reporting-filtering/crf-overview.md#consent-filtering).

   | Marketing action | Description |
   |---------|----------|
   | **[!UICONTROL Analytics]** | Filter data used for standard Customer Journey Analytics reporting in Analysis Workspace. |
   | **[!UICONTROL Data science]** | Filter data used for advanced analytics, machine learning, and data science use cases. |

1. Select **[!UICONTROL Create]** to create the configuration.

## What the configuration creates

When you create a configuration, Customer Journey Analytics automatically:

* Adds the selected Profile dataset to the connection.
* Creates a consent policy lookup dataset for the sandbox (if one does not already exist) and syncs policy names and descriptions from Experience Platform.
* Adds the consent policy components (dimensions, metrics, and a derived field) to the data views within the configured connection.
* Applies the **consent** internal label to the new components so that you can filter for them in the data view. For more information about internal labels, see [Labels and policies](/help/data-views/data-governance.md).

After the configuration completes, verify that the consent policy components are available in your data views. For more information, see [Analyze consent policy data](/help/connections/consent-reporting-filtering/crf-analyze.md).
