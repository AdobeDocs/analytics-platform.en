---
title: Analyze Consent Policy Data in Customer Journey Analytics
description: Learn how to use consent policy dimensions, metrics, and templates to report on visitor consent policy membership in Analysis Workspace.
solution: Customer Journey Analytics
feature: Privacy
role: Admin, User
hold: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: eb00932f-4d46-46bc-b1d8-10de7588db8d
    internal-label: Data governance
subfeature_v2:
  - id: ffe2fd81-0630-49b3-a33b-4b8899e89c51
    internal-label: Privacy
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
    internal-label: Governance
---
# Analyze consent policy data

You can ingest consent policy data from Experience Platform Profile datasets into a Customer Journey Analytics connection.

After you [create a consent reporting and filtering configuration](/help/connections/consent-reporting-filtering/consent-configure.md), consent policy data becomes available as new components in the data views under the configured connection. You can use these components anywhere in Analysis Workspace if you have access to a data view where they exist.

## Consent policy components

Consent reporting adds the following components to your data views. These components read from the `consentPoliciesIDMap` field in your Profile dataset, and policy names and descriptions come from the consent policy lookup dataset.

### Dimensions

| Dimension | Description |
|---------|----------|
| **[!UICONTROL Consent Policy ID]** | The identifier of a consent policy that a visitor matches. |
| **[!UICONTROL Policy Name]** | The friendly name of the consent policy, from the consent policy lookup dataset. |
| **[!UICONTROL Policy Description]** | The description of the consent policy, from the consent policy lookup dataset. |

### Metrics

| Metric | Description |
|---------|----------|
| **[!UICONTROL Visitors with Consent]** | The number of visitors who match a consent policy. |
| **[!UICONTROL Events with Consent]** | The number of events associated with visitors who match a consent policy. |
| **[!UICONTROL Unique Consent Policies]** | The number of distinct consent policies represented in the reporting window. |

### Derived field

A derived field references the `consentPoliciesIDMap` field to extract consent policy IDs. You can use this derived field as the basis for additional consent-based dimensions. For more information about derived fields, see [Derived fields](/help/data-views/derived-fields/derived-fields.md).

## Use consent policy components in Analysis Workspace

To report on consent policy membership:

1. In Analysis Workspace, open a project that uses a data view configured for consent reporting.

1. From the components panel, drag a consent policy dimension, such as **[!UICONTROL Policy Name]**, into a freeform table.

1. Add a consent metric, such as **[!UICONTROL Visitors with Consent]**, to the table.

1. Break down the results by any other dimension, such as Page or Channel, to understand how consenting visitors behave.

## Use the consent policy analysis template

When a data view is configured for consent reporting, Customer Journey Analytics automatically makes a consent policy analysis template available in Analysis Workspace. This template provides a starting point for reporting on visitor consent policy membership.

For information about how to access templates, see [Access and run a template](/help/analysis-workspace/templates/use-templates.md#access-and-run-a-template).
