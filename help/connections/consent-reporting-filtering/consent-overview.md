---
title: Consent Reporting and Filtering Overview
description: Learn how to report on visitor consent policy membership and filter non-consenting visitors at ingest time in Customer Journey Analytics.
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
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
    internal-label: Governance
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
---
# Consent reporting and filtering overview

Consent reporting and filtering uses the consent policy membership data stored in your Adobe Experience Platform Profile datasets to help you report on visitor consent and, optionally, exclude non-consenting visitors before their data is ingested into Customer Journey Analytics.

The following diagram and associated table show a high-level representation of how consent reporting and filtering makes consent policy data available in Analysis Workspace and filters visitor data at ingest time:

![Consent reporting and filtering overview](assets/consent-overview.png)

<!-- TODO: Add the customer-facing service-flow diagram. Do not expose internal service names (for example, Omnivore, CPES, Audience Service, DULE) in the published image or table. -->

| Number | Feature | Function |
|---------|----------|---------|
| 1 | Provisioning wizard | The configuration interface in Customer Journey Analytics used to enable consent reporting and, optionally, consent filtering. |
| 2 | Sandbox | Must contain the Profile dataset that includes the consent policy membership data you want to report on. |
| 3 | Profile dataset | Includes the consent policy membership data for each visitor. Consent policy membership is stored in the `consentPoliciesIDMap` field of a Profile dataset. This Profile dataset is added to the connection that you select. <p>Each visitor's profile lists the consent policies that the visitor matches. Customer Journey Analytics reads this field to make consent policies available for reporting and to evaluate which visitors to include during ingestion.</p> |
| 4 | Consent policy lookup dataset | Provides friendly policy names and descriptions for reporting. The lookup dataset is created automatically and kept in sync with Experience Platform. A maximum of one consent policy lookup dataset exists per sandbox. |
| 5 | Connection | The connection where consent reporting and filtering is applied. All data views under the connection inherit the configuration. |
| 6 | Consent policy components | New dimensions, metrics, and a derived field that represent consent policy membership. These components are created automatically and are available for reporting in Analysis Workspace. |
| 7 | Ingest-time filtering | When filtering is enabled, non-consenting visitors are excluded during ingestion, based on the marketing actions that you configure. |

## Consent reporting vs. filtering

Consent reporting and filtering are two separate capabilities. You can enable consent reporting on its own, or enable both reporting and filtering together.

### Consent reporting

When you enable consent reporting, Customer Journey Analytics adds a set of consent policy components to the data views under the configured connection. These components let you use Analysis Workspace to report on which visitors match the various consent policies, using the consent policy membership data in your Experience Platform Profile datasets. 

To keep reporting readable, Customer Journey Analytics syncs policy names and descriptions from Experience Platform into a consent policy lookup dataset. When a policy is created, updated, renamed, or deleted in Experience Platform, the lookup dataset is updated automatically.

For information about the components that consent reporting creates, see [Analyze consent policy data](/help/connections/consent-reporting-filtering/consent-analyze.md).

### Consent filtering

>[!IMPORTANT]
>
>Consent data that is filtered out (excluded) is not stored in Customer Journey Analytics and cannot be recovered for past dates by updating your configuration.

When you enable consent filtering, Customer Journey Analytics excludes non-consenting visitors at ingest time. Because filtering happens at ingest time, the data for excluded visitors never enters Customer Journey Analytics and is not available for reporting.

Consider the following when using consent filtering:

* Customer Journey Analytics determines the consent policies that apply to the marketing actions you configured.

  A marketing action represents a category of data use. Customer Journey Analytics determines which consent policies apply to each marketing action, and you enable filtering for each marketing action independently when [creating your configuration](/help/connections/consent-reporting-filtering/consent-configure.md#create-a-configuration).

  | Marketing action | Description |
  |---------|----------|
  | **Analytics** | Standard Customer Journey Analytics reporting in Analysis Workspace. |
  | **Data science** | Advanced analytics, machine learning, and data science use cases. |

* A visitor's data is ingested only if the visitor matches **all** applicable consent policies. If a visitor is missing any applicable policy, that visitor's data is excluded.

## Consent reporting and filtering role and permission requirements

The following Customer Journey Analytics roles and Experience Platform permissions are required for consent reporting and filtering:

| Capability | Customer Journey Analytics role or permission requirements | Experience Platform permission requirements |
|---------|----------|----------|
| [Create consent reporting and filtering configurations](/help/connections/consent-reporting-filtering/consent-configure.md) | System administrator | <ul><li>Datasets: Read, Write</li><li>Schemas: Read, Write</li></ul> <p>Read access is required for the Profile dataset that contains the consent policy membership data. Write access is required because a consent policy lookup dataset is created and kept in sync.</p> |
| View consent policy components in the data view | Product profile administrator for the product profile that the data view is assigned to <p>For more information, see [Access control](/help/technotes/access-control.md).</p> | N/A |
| Use consent policy components in Analysis Workspace | Access to a data view where the consent policy components were added | N/A |

## Next steps

* [Configure consent reporting and filtering](/help/connections/consent-reporting-filtering/consent-configure.md)
* [Manage consent reporting and filtering configurations](/help/connections/consent-reporting-filtering/consent-manage.md)
* [Analyze consent policy data](/help/connections/consent-reporting-filtering/consent-analyze.md)
* [Consent reporting and filtering use cases](/help/connections/consent-reporting-filtering/consent-use-cases.md)
