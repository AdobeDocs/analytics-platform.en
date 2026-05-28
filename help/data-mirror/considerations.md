---
title: Data Mirror Considerations
description: Understand additional consideration to take into account when you want to synchronize data between data warehouse native solutions and Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
role: Admin
badgePremium: label="Beta"
autotag-review: '2026-05-19T06:55:09.938Z'
TQID: 'https://experienceleague.adobe.com/uZjXZUKUMeXLxxpTRrkCZrPsGhxseSxOtJ9X0ZjG5wU'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: b3197353-f189-4932-8378-3f3bc40e6071
    internal-label: Data management
subfeature_v2:
  - id: bfef374d-acfd-4c57-bf74-a2b36053c545
    internal-label: Data ingestion
  - id: e1471301-a189-438e-8d48-264a8db508a6
    internal-label: Data views
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
    internal-label: Governance
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
---
# Experience Platform Data Mirror considerations

This article describes factors you should consider when you set up Data Mirror datasets.

## New column to source table

When a new column is added to a source table in a CDC-enabled data mirrored dataset, that change can trigger updates for all existing rows. These updates are processed as changes through CDC, which:

* Can behave like a full table rewrite from a progressing perspective.
* Can dramatically increase ingestion volume, which could cause the update to exceed your ingestion entitlement.

The recommended strategy for columns in the source table:

* Ensure all relevant columns are defined initially.
* Map every column you might think you need initially.

If you want to add a new column, there are two options, depending on whether retroactive backfill is required:
  
* Retroactive backfill:
 
  * Remove the current dataset.
  * Configure the connector again with the updated column. 
  
  This ensures the data is backfilled more efficiently and timely.
  
* No retroactive backfill:
  
  * Add the column in the source table.
  * Add the column in the target dataset schema.
  * Update the mapping to include the new field (column) from the source table to the target dataset.

This strategy: 

* Avoids costly schema evolution later (mass updates when adding columns).
* Keeps change volume more predictable than when columns are added or modified later.
* Helps to limit potential compute costs on the external database side as the data warehouse might interpret the new column as an update to all rows..


## Privacy Service

Privacy requests need to happen the same way privacy requests are handled today for non-relational schemas as privacy requests are indifferent to how data is structured.

Data mirrored from an external relational schema becomes part of the Adobe ecosystem and can be shared throughout that ecosystem, such as through Customer Journey Analytics Audience Publishing. Submitting a privacy request ensures identities and associated data are handled properly throughout the Adobe ecosystem.

Therefore, privacy requests should not be limited to the mirrored dataset, but should also involve updates to the source data in the external database.

## Hygiene behavior

Hygiene service operates on *primary identities*, but tables in the external database that are mirrored have *primary keys*, not primary identities.

The consequences of the difference between primary identities and primary keys are that hygiene deletes cannot be executed directly against these relational tables. As a result, you must:

  * Delete data in their own source tables within the data warehouse solution and ensure that the delete operations flow through CDC (or the manual change column).
  * Submit hygiene and privacy requests into Adobe for any downstream XDM-based datasets with identity information (for example:  Customer Journey Analytics views, Real-Time Customer Data Platform datasets, Adobe Journey Optimizer specific datasets, and more).
  
The difference between primary identity and primary key introduces a shared responsibility model:

* Adobe processes hygiene where identities are present.
* You, as the customer, are responsible for aligning your own hygiene processes in the source database with the hygiene requests that are submitted to Adobe.

## Governance differences

In XDM [schemas](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition) and underlying concepts like [field groups](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition#field-group), a defined [field](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition#field) within a field group propagates its labels across all datasets where the field group is used. For example, an email field `emailID` in a field group `identities`, is labeled the same across all datasets where the fieldgroup `identities` is used.

In a relational schema, a column name is independent. A column named `email` in table `customers` is independent of and distinct from a column named `email` in a table `prospects`. This behavior implies that labels (like DULE usage labels, policies) must be applied individually to the fields in the mirrored datasets. Based on the example above, you need to apply labels to both the `email` field in the `customers` dataset and on the `email` field in the `prospects` dataset.
  
The governance difference has the following impact:

* More manual governance and configuration work for you as a customer.
* You might need explicit guidance, so you do not assume one-time labeling via field groups is sufficient for proper governance.

## Stitching

Relational schemas have the following considerations as it relates to stitching:

* Graph-based stitching is partially supported. Relational schemas can't be enabled for profile / contributing to the graph.
* Field-based stitching is fully supported.


## System keys and fields

The following considerations apply to system keys and fields:

* The primary key, version descriptor, and timestamp descriptor need to be root level fields in the relational XDM schema. Use [field mapping](https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/dataflow/databases#map-data-fields-to-an-xdm-schema) during ingestion to support this requirement.
* You can omit appropriate source fields during the [mapping phase](https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/dataflow/databases#map-data-fields-to-an-xdm-schema).

## Backfill

For any mirrored dataset that is configured as part of a connection, and for which you enable [Dataset backfill](/help/connections/create-connection.md#general-dataset-settings-and-details), the backfill cannot exceed more than 100GB of data.
