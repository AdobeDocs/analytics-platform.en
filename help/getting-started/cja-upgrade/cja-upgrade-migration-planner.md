---
title: Migrate from AppMeasurement or tags to XDM
description: Learn about migrating from AppMeasurement or tags to XDM
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
---
# Migrate from Tags to XDM {#upgrade-migration-planner}

{{upgrade-note-step}}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="migration_intro"
>title="Migrations overview"
>abstract="Migrate a Tags implementation to the Adobe Experience Platform Web SDK when upgrading to Customer Journey Analytics.<br/>Continue with an existing migration or start a new one."

<!-- markdownlint-enable MD034 -->

The Migration Planner provides a migration wizard that automates the migration from tags to XDM, including schema creation. These are some of the most complex and time-consuming tasks associated with an upgrade from Adobe Analytics to Customer Journey Analytics.

## Supported Adobe Analytics implementations

The Migration Planner supports Adobe Analytics implementations that use the Analytics extension (tags).

The Migration Planner is not available for Adobe Analytics implementations that use AppMeasurement or the Experience Platform Web SDK.

## Upgrade tasks included in the Migration Planner

The Migration Planner provides a migration wizard that automates the following complex and time-consuming upgrade tasks:

* **XDM schema creation**: Automatically creates a new XDM schema that is based on your Adobe Analytics report suite variables. The Migration Planner intelligently scans your Adobe Analytics report suite variables, then uses that information to create the necessary fields in XDM. The resulting XDM schema includes only those fields that are needed in your Customer Journey Analytics schema.
   
     Alternatively, you can point to an existing XDM schema or you can create an XDM schema from scratch. 
   
     +++ If you choose to create an XDM schema from scratch, you can expand this section for information on helpful resources.

     * [Plan your XDM schema architecture](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md){target="_blank"}.

     * [Create your desired custom schema in Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md){target="_blank"}.

       Consider the following options when creating your schema:

       * If you want to integrate Customer Journey Analytics with RTCDP, you must enable the **[!UICONTROL Profile]** option on your schema, as described in [Create an XDM schema to use with Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md){target="_blank"}. With this option enabled, when data is ingested into datasets based on this schema, that data is merged into the Real-Time Customer Profile.

       * If you want to include streaming media data, you must [configure your schema to ingest and use streaming data](/help/data-ingestion/streaming.md){target="_blank"}.

       +++

     * **Migration of your Adobe Analytics implementation to the Web SDK**: Whether your Adobe Analytics implementation uses tags or JavaScript, the Migration Planner walks you through the migration to the Experience Platform Web SDK.
   
       * **Migrate tag properties from AppMeasurement to the Web SDK**:

       * **Migrate a JavaScript implementation from AppMeasurement to the Web SDK JavaScript library**

     * **Data view creation in Customer Journey Analytics**: Automatically creates Data views and populates them with components, based on the XDM schema fields that are created. 


## Before you begin

Before you create a migration, make sure that you have the following:

* A supported Adobe Analytics implementation (the Analytics extension for tags). See [Supported Adobe Analytics implementations](#supported-adobe-analytics-implementations).

* Access to the Adobe Tags property that you want to migrate, in the Experience Cloud organization that you're signed in to.

* Access to the Adobe Analytics report suite whose variables you want to map to XDM.

* Permission to create schemas in Adobe Experience Platform.

<!-- Confirm the exact roles and permissions required to use the Migration Planner and to create schemas and Data Views. -->

## Migrate an Analytics implementation to the Web SDK

A migration moves through three stages: [!UICONTROL **Audit**], [!UICONTROL **Mapping**], and [!UICONTROL **Implementation**]. Use the following steps to create a migration, then continue with [Validate and deploy a migration](#validate-and-deploy-a-migration) to complete each stage.

1. In Customer Journey Analytics, open the [!UICONTROL **Migration Planner**].

   <!-- Confirm the exact navigation path to open the Migration Planner in Customer Journey Analytics. -->

1. In the Migration Planner, on the [!UICONTROL **Migrations**] tab, select [!UICONTROL **New**].

   ![The New migration dialog, where you choose a migration type and enter a migration name.](assets/migration-planner-new-migration.png)

1. Specify the following information:
   
   | Field name | Function |
   | --------- | ---------- |
   | [!UICONTROL **Name**] | Specify a name for this migration. |
   | [!UICONTROL **Description**] | Specify an optional description for this migration. |
   | [!UICONTROL **Tags property**] | Select the Adobe Tags property that you want to migrate. For more information, see [Properties](https://experienceleague.adobe.com/en/docs/experience-platform/tags/admin/companies-and-properties){target="_blank"} in the Experience Platform documentation. |
   | [!UICONTROL **Tags library**] | Select the tag library snapshot that the migration is based on. The snapshot determines which version of your tag library is used. For more information, see [Publishing overview](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"} in the Experience Platform documentation. |

1. In the [!UICONTROL **Migration name**] field, specify a name for this migration, then select [!UICONTROL **Next**].

1. Select the tag property that you want to migrate, then select [!UICONTROL **Next**].

   Only the tag properties available to your signed-in Experience Cloud organization appear.

1. Select the tag library snapshot that you want to migrate, then select [!UICONTROL **Next**].

   The snapshot determines which version of your tag library the migration is based on. Each snapshot shows its environment (such as [!UICONTROL **Development**], [!UICONTROL **Staging**], or [!UICONTROL **Production**]).

1. Select the mapping set to determine how Analytics variables will map to XDM schema fields.

   Do either of the following:

   * Select [!UICONTROL **Create a new mapping set**].

   * Select an existing mapping set. 

     Mapping sets that were created during a previous migration or as a stand-alone mapping set are available to select. 
     
     Reusing a mapping set across multiple migrations applies the same mappings to each migration.

1. Select [!UICONTROL **Create migration**].

1. Continue with the following section, [Validate and deploy a migration](#validate-and-deploy-a-migration).

## Validate and deploy a migration

After you create a migration, open it to complete its three stages: [!UICONTROL **Audit**], [!UICONTROL **Mapping**], and [!UICONTROL **Implementation**].

1. In the Migration Planner, select the [!UICONTROL **Migrations**] tab.

1. Next to the migration that you want to validate, select [!UICONTROL **Open**].

   The migration overview page shows the three stages to complete, along with a summary of your migration and its artifacts.

   ![The migration overview page with the Audit, Mapping, and Implementation stage cards.](assets/migration-planner-overview.png)

1. Complete the [!UICONTROL **Audit**] stage:

   1. In the audit card ([!UICONTROL **Tag extension audit**] or [!UICONTROL **JavaScript audit**], depending on your migration type), select [!UICONTROL **Start audit**] to review the rules and data elements included in the migration.

      ![The audit page, where you select rules and data elements and resolve any findings.](assets/migration-planner-audit.png)

   1. On the [!UICONTROL **Rules**] and [!UICONTROL **Data elements**] tabs, select the items to include in the migration.

      Rules marked [!UICONTROL **In library**] are published. Rules marked [!UICONTROL **Property only**] exist in the property but aren't part of the selected library.

   1. Review any findings on the selected rules. For each finding, select [!UICONTROL **Review**] to resolve it, or [!UICONTROL **Ignore**] to leave it unaddressed.

      For example, when two rules have identical events and conditions, the [!UICONTROL **Duplicate rule events**] finding lets you keep one rule and remove the other, or select [!UICONTROL **Do nothing**] to acknowledge the finding without making a change.

      Resolving findings is optional before you continue. For the full list of finding types and how to resolve each one, see [Review and resolve audit findings](#review-and-resolve-audit-findings).

   1. Select [!UICONTROL **Save and continue**].

1. Complete the [!UICONTROL **Mapping**] stage:

   1. In the [!UICONTROL **Analytics → XDM mapping**] card, select [!UICONTROL **Create new mapping**].

   1. Choose whether to create a new schema based on your Analytics variables or map against an existing Experience Platform schema, then follow the prompts to select your report suite, map fields, and review the schema.

      For detailed steps, see [Map Analytics variables to XDM fields](#map-analytics-variables-to-xdm-fields). To reuse a set of mappings across migrations, see [Create and manage mapping sets](#create-and-manage-mapping-sets).

1. Complete the [!UICONTROL **Implementation**] stage:

   1. In the [!UICONTROL **Generate Web SDK implementation**] card, use the audit and mapping results to generate the Web SDK implementation package, then deploy it to your site.

      For detailed steps, see [Generate and deploy the Web SDK implementation](#generate-and-deploy-the-web-sdk-implementation).


## Review and resolve audit findings

During the [!UICONTROL **Audit**] stage, the Migration Planner flags findings on the rules you selected. Resolving findings is optional before you continue, but resolving them helps ensure a clean migration.

For each finding, select [!UICONTROL **Review**] to open the finding and choose how to resolve it, or select [!UICONTROL **Ignore**] to leave it unaddressed.

The Migration Planner can flag the following types of findings:

* [!UICONTROL **Duplicate rule events**]: Two or more rules have identical events and conditions. When you review the finding, compare the primary and duplicate rules, then keep one rule and remove the other, or select [!UICONTROL **Do nothing**] to acknowledge the finding without making a change.

* [!UICONTROL **Duplicate rule logic**]: Rules share the same logic. <!-- Confirm the exact remediation options for this finding type. -->

* [!UICONTROL **Misordered rule actions**]: A rule's actions run in an order that could cause problems during migration. <!-- Confirm the exact remediation options for this finding type. -->

If a finding has no guided remediation, the Migration Planner displays [!UICONTROL **No remediation details available**]. Review the finding manually and dismiss it when it's resolved.

The [!UICONTROL **Findings**] panel shows how many findings you've addressed and how many are still open. When you're finished, select [!UICONTROL **Save and continue**].

## Map Analytics variables to XDM fields

During the [!UICONTROL **Mapping**] stage, you map your Analytics variables to XDM fields and generate or select the target schema. In the [!UICONTROL **Analytics → XDM mapping**] card, select [!UICONTROL **Create new mapping**], then complete the following steps:

1. **Schema choice**: Choose whether to create a new schema based on your Analytics variables, or map against an existing Experience Platform schema.

1. **Report suite**: Select the Analytics report suite whose variables you want to map.

1. **Experience Platform schema**: Create the target XDM schema, or select the existing schema to map against.

1. **Manual mapping**: Review the automatic mappings and adjust how individual Analytics variables map to XDM fields.

1. **Review schema**: Review the resulting mappings and schema, then confirm.

<!-- The XDM mapping editor was not captured in the walkthrough. Confirm the exact steps, controls, and options on each step (Schema choice, Report suite, Experience Platform schema, Manual mapping, Review schema). -->

To reuse a set of mappings across migrations, see [Create and manage mapping sets](#create-and-manage-mapping-sets).

## Compare migration outputs

Use [!UICONTROL **Compare outputs**] on the migration overview page to validate your migration before you deploy it.

<!-- The Compare outputs screen was not captured in the walkthrough. Confirm what the comparison shows (for example, AppMeasurement output compared with the Web SDK / XDM output) and how to interpret the results. -->

## Generate and deploy the Web SDK implementation

During the [!UICONTROL **Implementation**] stage, the Migration Planner uses your audit and mapping results to build the Web SDK implementation package.

1. On the migration overview page, in the [!UICONTROL **Generate Web SDK implementation**] card, generate the implementation package.

1. Build the tag library for the migration by selecting [!UICONTROL **Build tag library**].

1. Configure the dual deployment, then deploy the Web SDK implementation to your site.

<!-- This stage was not captured in the walkthrough. Confirm the exact steps for generating the package, configuring the dual deployment, building the tag library, and deploying to the site. -->

For the artifacts produced by this stage, see [Export migration artifacts](#export-migration-artifacts).

## Export migration artifacts

The migration overview page provides the artifacts that the Migration Planner generates. You can download individual artifacts from the [!UICONTROL **Project artifacts**] panel, or select [!UICONTROL **Export all**] to export everything at once.

The following artifacts are available:

* [!UICONTROL **Mapping JSON**]: The mapping between your Analytics variables and XDM fields.

* [!UICONTROL **XDM schema (JSON)**]: The target XDM schema created for the migration.

* [!UICONTROL **Tag development library**]: The tag library built for the Web SDK implementation.

Each artifact shows its status, such as [!UICONTROL **Ready**] or [!UICONTROL **Not built**]. An artifact is available to download after it's generated in the corresponding stage.

## Create and manage mapping sets {#mapping-sets}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="migration_mapping_sets"
>title="Mapping sets"
>abstract="Mapping sets determine how Analytics variables map to XDM fields.<br/>Create a new mapping set or choose an existing one to apply the same mappings across multiple migrations. You can also reference mapping sets in other migration tasks."

<!-- markdownlint-enable MD034 -->

Mapping sets determine how Analytics variables map to XDM schema fields.

You can create a new mapping set [during the migration process](#migrate-an-analytics-implementation-to-the-web-sdk). Or, you can create a stand-alone mapping set to use with a future migration or with other migration tasks.

### Create a stand-alone mapping set {#xdm-mapping}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="migration_mapping_schema"
>title="Choose a schema"
>abstract="Mapping sets determine how Analytics variables map to XDM fields.<br/>Create a new mapping set or choose an existing one to apply the same mappings across multiple migrations. You can also reference mapping sets in other migration tasks."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="migration_mapping_field_group"
>title="Field group preference"
>abstract="Choose standard field groups to use published Adobe field groups when possible. This promotes maximum consistency, and falls back to custom tenant fields when no standard fields are available.<br/>Choose custom field groups to use tenant-namespace custom fields when possible. This promotes maximum flexibility."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="migration_mapping_lookback"
>title="Lookback period"
>abstract="Controls how far back to look to when determining which variables are actively receiving data. Variables that include data within the lookback period are included in the schema."

<!-- markdownlint-enable MD034 -->

1. In the Migration Planner, select the [!UICONTROL **Mapping sets**] tab.

1. Select [!UICONTROL **New mapping set**].

1. In the [!UICONTROL **Name**] field, enter a descriptive name so you can identify this mapping set later, then select [!UICONTROL **Next**].

1. From the [!UICONTROL **Report suite**] menu, select the report suite whose variables you want to map to XDM fields, then select [!UICONTROL **Next**].

1. In the [!UICONTROL **Choose a schema for your XDM mapping section**], choose whether to create a new schema based on your Analytics variables or map against an existing Experience Platform schema.

   Choosing to create a new schema guides you through the process of mapping your Analytics variables to XDM fields. Choosing to use an existing schema allows you to manually map your variables to a pre-registered schema in the Experience Platform schema registry.

   <!-- Screenshot pending: the XDM mapping editor (Create new mapping) was not available for capture in the walkthrough. -->

   * [!UICONTROL **Create a new schema**]: Run the Basic and Advanced scans to automatically suggest XDM field mappings for your Analytics variables, then review the resulting schema.

   * [!UICONTROL **Use an existing schema**]: Search for and select a schema that is already registered in the Experience Platform schema registry, then manually drag Analytics variables onto XDM fields.

1. In the [!UICONTROL **Field group preference**] drop-down menu, choose how you want to organize custom variables into field groups:

   * [!UICONTROL **Standard first**]: Use published Adobe field groups when possible. This promotes maximum consistency, and falls back to custom tenant fields when no standard fields are available.

   * [!UICONTROL **Custom first**]: Use tenant-namespace custom fields when possible. This promotes maximum flexibility.

   <!-- * [!UICONTROL **Ask each time**]: Prompt for each signal so you can decide individually. -->

1. In the [!UICONTROL **Lookback period**] field, select how far back to look when determining which variables are actively receiving data. Variables that include data within the lookback period are included in the schema.

1. Select [!UICONTROL **Create mapping set**].
  
  The new mapping set appears on the [!UICONTROL **Mapping sets**] tab, where you can open it to review its details.

### Export a mapping set

You can export a mapping set to use it with other migration tasks or in other tools.

<!-- Confirm where the export control lives (the Mapping sets list exposes only an Open action) and the export format (for example, JSON). -->

### Publish and version mapping sets

Each mapping set has a status and a version. On the [!UICONTROL **Mapping sets**] tab, a mapping set can appear as:

* [!UICONTROL **draft**]: The mapping set is still being edited.

* [!UICONTROL **published**]: The mapping set has been finalized.

* [!UICONTROL **in migration**]: The mapping set is bound to one or more migrations.

<!-- Confirm how to publish a mapping set, how versions are created (v1, v2, v3), and what "bindings" represent. -->

### Edit a mapping set <!-- can you? -->

<!-- Steps pending: confirm whether a mapping set can be edited after creation and where the edit control lives (the Mapping sets list exposes only an Open action). -->

### Delete a mapping set <!-- can you? -->

<!-- Steps pending: confirm whether a mapping set can be deleted, and whether deletion is blocked while the set is in use by a migration. -->

## Manage existing migrations

### Find and track your migrations

The [!UICONTROL **Migrations**] tab lists your migrations and their progress. Use it to find a migration to continue, or to check the status of migrations that are underway.

* **Search**: Use the search field to find a migration by name or property.

* **Filter**: Filter the list by migration type or by status.

* **Track progress**: Each migration shows its progress through the three stages (for example, 1/3) and an overall status:

   * [!UICONTROL **Not started**]: The migration has been created, but no stage is complete.

   * [!UICONTROL **In progress**]: At least one stage is complete.

   * [!UICONTROL **Completed**]: All three stages are complete.

To continue a migration, select [!UICONTROL **Open**] next to it.

<!-- The row actions ("...") menu was not captured in the walkthrough. Confirm which actions it contains (for example, rename, duplicate, or delete a migration). -->

