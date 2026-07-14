---
title: Consent Reporting and Filtering Use Cases
description: Explore use cases for reporting on visitor consent policy membership and filtering non-consenting visitors at ingest time in Customer Journey Analytics.
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
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
---
# Consent reporting and filtering use cases

Consent reporting and filtering helps you report on visitor consent policy membership and, optionally, exclude non-consenting visitors before their data enters Customer Journey Analytics. For overview information, see [Consent reporting and filtering overview](/help/connections/consent-reporting-filtering/crf-overview.md).

This article describes example use cases. Before you review them, become familiar with the considerations below, because they affect the results you see in your reports.

## Reporting considerations

* **Filtering applies at the connection level**: When you enable filtering, all data views under the configured connection inherit the same behavior. You cannot filter one data view under a connection differently from another.

* **Filtering uses inclusion logic**: A visitor's data is ingested only if the visitor matches all consent policies that apply to the enabled marketing actions. A visitor who is missing any applicable policy is excluded.

* **Excluded data is not recoverable**: Because filtering happens at ingest time, data that is excluded is not stored in Customer Journey Analytics. Changing your configuration later does not recover excluded data for past dates.

* **Consent policy membership comes from the Profile dataset**: Reporting reflects the consent policy membership present in the `consentPoliciesIDMap` field of the Profile dataset. A visitor must have a corresponding event in the connection to appear in reporting.

## Example use cases

### Use case 1: Report on consent without filtering data

Understand how many visitors match each consent policy before you decide whether to filter, to answer questions like:

* _"How many of our visitors have consented to analytics use?"_
* _"Which consent policies have the most and least coverage across our visitors?"_

**Configuration flow:**

1. Create a configuration and select the sandbox, Profile dataset, and connection that contain your consent policy membership data.

1. Leave both the **[!UICONTROL Analytics]** and **[!UICONTROL Data science]** filtering toggles off.

1. In Analysis Workspace, build a freeform table with the **[!UICONTROL Policy Name]** dimension and the **[!UICONTROL Visitors with Consent]** metric to see coverage per policy.

Use these insights to decide whether to enable filtering and for which marketing actions.

### Use case 2: Exclude non-consenting visitors from analytics reporting

Make sure that standard reporting includes only visitors who have consented to analytics use, to answer questions like:

* _"How does our audience behave when we report only on consenting visitors?"_
* _"Can we make sure non-consenting visitor data never enters our analytics reports?"_

**Configuration flow:**

1. Create or edit a configuration for the connection that powers your analytics reporting.

1. Enable the **[!UICONTROL Analytics]** filtering toggle.

1. Confirm the configuration. From this point forward, Customer Journey Analytics ingests a visitor's data only if the visitor matches all consent policies that apply to the analytics marketing action.

Because filtering happens at ingest time, downstream reports, exports, and APIs automatically reflect only consenting visitors, with no report-time changes required.

### Use case 3: Filter analytics and data science use cases independently

Apply different consent requirements to standard reporting and to data science use cases, to answer questions like:

* _"Can we include a broader set of visitors in analytics while applying stricter consent for machine learning?"_

**Configuration flow:**

1. Create or edit a configuration for the relevant connection.

1. Enable the **[!UICONTROL Analytics]** toggle, the **[!UICONTROL Data science]** toggle, or both, depending on the consent requirements for each use case.

1. Confirm the configuration. Customer Journey Analytics evaluates the consent policies that apply to each enabled marketing action independently.

Use this approach when your organization applies different consent requirements to different categories of data use.
