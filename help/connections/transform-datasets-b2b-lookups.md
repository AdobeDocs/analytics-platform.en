---
title: Transform datasets for B2B lookups
description: Describes how to transform data in datasets of specific B2B lookup schemas
solution: Customer Journey Analytics
feature: Connections
role: Admin
exl-id: 7729c1b9-b3ed-4662-a446-2088389bbd97
---
# Transform datasets for B2B lookups

To support person-based lookups on B2B data (including accounts, opportunities, marketing lists and campaigns), transformation of B2B lookup datasets is required.

This transformation is only available for datasets with data for B2B lookup schemas, based on the following classes:

* [XDM Business Account Person Relation](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/b2b/business-account-person-relation)
* [XDM Business Opportunity Person Relation](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/b2b/business-opportunity-person-relation)
* [XDM Business Marketing List Members](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/b2b/business-marketing-list-members)
* [XDM Business Campaign Members](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/b2b/business-campaign-members)

>[!NOTE]
>
>There is a limit of no more than 10,000 items for each id. This limitation implies that for any given person id you can only have 10,000 accounts, or 10,000 opportunities, or 10,000 marketing lists, or 10,000 campaigns.


To enable transformation for such a dataset:

![Enable transform dataset](assets/transform-dataset.gif)

* Ensure you select the proper identifier for **[!UICONTROL Key]** and **[!UICONTROL Matching key]**, for example `personKey.sourceKey`.

* Select the options for importing new data and dataset backfill. 

* Select **[!UICONTROL Transform dataset for B2B lookups]**.

  This option transforms the dataset so it can be used for person-based lookups in B2B scenarios. 
  
  
  >[!IMPORTANT]
  >
  >Once turned on, and when the connection is saved, the transformation is irreversible. You cannot modify the transformation setting for a dataset once a connection is saved, other than by removing and adding the dataset once more to the connection. 

To enable transformation for one or more datasets that are already part of an existing connection:

1. Remove the datasets from the connection.
1. Save the connection.
1. Add the datasets to the connection while turning on transformation for the datasets.

## Background information

Non-transformed datasets, for schemas based on the four schema classes mentioned above, can contain multiple rows for a single person identifier. Person-based lookups only match the most recent occurrence of that person identifier, preventing a proper person id based lookup of accounts, opportunities, marketing lists or campaigns.

The transformation modifies the dataset of each of the four schema classes (orange in the illustration below) so that for each person identifier an (object) array is created for the relevant data (accounts, opportunities, marketing lists or campaigns) in the lookup datasets (pink in the illustration below). This transformation allows for a correct working of person id based lookups.

![B2B schemas](./assets/b2b-schemas.svg)
