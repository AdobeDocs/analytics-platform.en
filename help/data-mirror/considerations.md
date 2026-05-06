---
title: Data Mirror Considerations
description: Understand additional consideration to take into account when you want to synchronize data between data warehouse native solutions and Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
role: Admin
badgePremium: label="Beta"
hide: true
---
# Experience Platform Data Mirror considerations

This article describes factors you should consider when you set up Data Mirror datasets.

## New column to source table

When a new column is added to a source table in a CDC-enabled data mirrored dataset, that change can trigger updates for all existing rows. These updates are processed as changes through CDC, which:

* Can behave like a full table rewrite from a cost perspective.
* Can dramatically increase ingestion volume, especially with any future *change multiplier* pricing (for example, merge operations might be charged at higher rates).

The recommended strategy for columns in the source table:

* Ensure most, if not all, relevant columns are defined initially.
* Map every column you might think you need initially.

This strategy: 

* Avoids costly schema evolution later (mass updates when adding columns).
* Keeps change volume more predictable than when columns are added or modified later.
* Could incur some additional compute costs on the external database side as the data warehouse might interpret  all columns as updates.

To handle new columns in external data warehouse tables, follow these steps:

1. Create a new schema with the added column.
1. Configure a new source connector that brings the data in.
1. Load the backfill appropriately.
1. Use CDC changes going forward. 
 
This approach minimizes the impact on both sides.

## Privacy Service

Privacy requests need to happen the same way privacy requests are handled today for non-relational schemas as privacy requests are indifferent to how data is structured.

Data mirrored in a dataset from external data that is based on a relational schema becomes part of the Adobe ecosystem and can be shared in many ways. For example, through audience publishing. 

Therefore, privacy requests should not be limited to the mirrored dataset, but should also involve updates to the source data in the external database.

## Hygiene behavior

Hygiene service operates on *primary identities*, but tables in the external database that are mirrored have *primary keys*, not primary identities.

The consequences of the difference between primary identities and primary keys are that hygiene deletes cannot be executed directly against thee relational tables. As a result, you must:

  * Delete data in their own source tables within the data warehouse solution and ensure that the delete operations flow through CDC (or the manual change column).
  * Submit hygiene and privacy requests into Adobe for any downstream XDM-based datasets with identity information (for example:  Customer Journey Analytics views, Real-Time Customer Data Platform datasets, Adobe Journey Optimizer specific datasets, and more).
  
The difference between primary identity and primary key introduces a shared responsibility model:

* Adobe processes hygiene where identities are present.
* You, as the customer, are responsible for aligning your own hygiene processes in the source database with what hygiene requests are submitted to Adobe.

## Governance differences

In XDM [schemas](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition) and underlying concepts like [field groups](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition#field-group), a defined [field](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition#field) within a field group propagates its labels across all datasets where the field group is used. For example, an email field `emailID` in a field group `identities`, is labeled the same across all datasets where the fieldgroup `identities` is used.

In a relational schema, a column name is independent. A column named `email` in table `customers` is independent of and distinct from a column named `email` in a table `prospects`. This behavior implies that labels (like DULE usage labels, policies) must be applied individually to the fields in the mirrored datasets. Based on the example above, you need to apply labels to both the `email` field in the `customers` dataset and on the `email` field in the `prospects` dataset.
  
The governance difference has the following impact:

* More manual governance and configuration work for you as a customer.
* You might need explicit guidance, so you do not assume one-time labeling via field groups is sufficient for proper governance.
