---
title: Manage Consent Reporting and Filtering Configurations
description: Learn how to view, edit, and delete consent reporting and filtering configurations and how the consent policy lookup dataset stays in sync in Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Privacy
role: Admin
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
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
    internal-label: Governance
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
---
# Manage consent reporting and filtering configurations

After you [create a consent reporting and filtering configuration](/help/connections/consent-reporting-filtering/crf-configure.md), you can view, edit, or delete it.

Only system administrators can manage consent reporting and filtering configurations.

For overview information, see [Consent reporting and filtering overview](/help/connections/consent-reporting-filtering/crf-overview.md).

## View existing configurations

To view your existing configurations:

1. In Customer Journey Analytics, select **[!UICONTROL Data Management]** > **[!UICONTROL Consent reporting and filtering]**.

   The following columns of information are available about each configuration:

   * **[!UICONTROL Created by]**: The user who created the configuration.

   * **[!UICONTROL Sandbox]**: The Experience Platform sandbox that contains the Profile dataset.

   * **[!UICONTROL Connection]**: The connection that the configuration is applied to.

   * **[!UICONTROL Filtering]**: The marketing actions that filtering is enabled for, if any.

   * **[!UICONTROL Date created]**: The date the configuration was created.

   * **[!UICONTROL Last modified]**: The date the configuration was last modified.

   * **[!UICONTROL Status]**: The status of the configuration.

## Edit a configuration

>[!IMPORTANT]
>
>Changes to filtering affect only data that is ingested after you save your changes to the configuration. Enabling filtering does not remove non-consenting visitor data that was ingested before the change, and disabling filtering does not recover data that was excluded while filtering was enabled.

To edit an existing configuration:

1. In Customer Journey Analytics, select **[!UICONTROL Data Management]** > **[!UICONTROL Consent reporting and filtering]**.

1. Select the name of the configuration that you want to edit.

1. Make your changes, then select **[!UICONTROL Save]**.

## Delete a configuration

To delete an existing configuration:

1. In Customer Journey Analytics, select **[!UICONTROL Data Management]** > **[!UICONTROL Consent reporting and filtering]**.

1. Select the checkbox next to the configuration that you want to delete, then select **[!UICONTROL Delete]**.

## How the consent policy lookup dataset stays in sync

Customer Journey Analytics keeps the consent policy lookup dataset in sync with Experience Platform automatically. When a consent policy is created, updated, renamed, or deleted in Experience Platform, the corresponding policy name and description in the lookup dataset are updated.

Keep the following in mind:

* A maximum of one consent policy lookup dataset exists per sandbox. Multiple configurations in the same sandbox share that lookup dataset.
* Because policy names and descriptions come from Experience Platform, update policy metadata in Experience Platform rather than editing the lookup dataset directly.
