---
title: Transform datasets for B2B lookups
description: Describes how to transform data in datasets of specific B2B lookup schemas
solution: Customer Journey Analytics
feature: Connections
role: Admin
---
# Transform datasets for B2B lookups

To support person-based lookups on B2B data (including accounts, opportunities, marketing lists and campaigns), additional transformation on specific B2B lookup datasets is supported.

This transformation is only available for datasets with data for B2B lookup schemas, based on the following classes:

* XDM Business Account Person Relation
* XDM Business Opportunity Person Relation
* XDM Business Marketing List Members
* XDM Business Campaign Members

To enable transformation for such a dataset:

![Enable transform dataset](assets/transform-dataset.gif)

* Ensure you select the proper identifier for **[!UICONTROL Key]** and **[!UICONTROL Matching key]**, for example `personKey.sourceKey`.

* Select **[!UICONTROL Transform dataset for B2B lookups]**.

  This option will transform the dataset so it can be used for person-based lookups in B2B scenarios. 
  
  
  >[!IMPORTANT]
  >
  >Once turned on, and when the connection is saved, the transformation is irreversible. You can not modify the transformation setting for a dataset once a connection is saved, other than by removing and adding the dataset once more to the connection. 



## Background information

Non-transformed datasets, for schemas based on the four schema classes mentioned above, can contain multiple rows for a single person identifier. Person-based lookups will only match the most recent occurrence of that person identifier, preventing a proper person id based lookup of accounts, opportunities, marketing lists or campaigns.

The transformation will transform the dataset so that for each person identifier an (object) array is created for the relevant data (accounts, opportunities, marketing lists or campaigns), enabling correct working person id based lookups.
