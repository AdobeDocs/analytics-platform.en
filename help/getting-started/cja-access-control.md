---
title: CJA Access Control
description: Learn about access control requirements for the three levels of access in CJA.
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
---
# CJA Access Control

Customer Journey Analytics (CJA) is governed by three levels of access or three roles: Product Admin role, Product Profile Admin role, and user-level access. This topic explains these roles in more detail. 

## Product Admin role

Product Admins have permissions to complete any task necessary within CJA. You must be added as an Product Admin to the **Customer Journey Analytics Product Profile** in the [Admin Console](https://adminconsole.adobe.com/enterprise/) under Customer Journey Analytics > Admins tab > Add Admin. Product admins are granted the following permissions:

* Create/update/delete connections or data views
* Update/delete projects, filters, calculated metrics, or filters created by other users
* Share Workspace projects to all users

Becoming a product admin in Customer Journey Analytics alone is not enough to create, update, or delete a connection. To create a connection to an Experience Platform dataset, you also need Experience Platform permissions. Specifically, you must be part of an **Experience Platform Product Profile** that gives you the following permissions:

* Data Modeling: View Schemas, Manage Schemas
* Data Management: View Datasets, Manage Datasets
* Data Ingestion: Manage Sources
* View Identity Namespaces  

For more information on Experience Platform permissions, see [Access control in Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html).

## Product Profile Admin role

This role is similar to the Product Admin, but has a more limited scope. A product profile is a set of permissions. For example, a Product Profile Admin can give access to all or specific data views to members of a product profile. For reporting tools, these admins can add these permissions:

![admin console permissions](assets/permissions.png)

## User-level access

Non-product admins (users) in Customer Journey Analytics cannot create, edit, or view data views or connections. Users can create filters, projects, audiences, and calculated metrics with special permissions in the Admin Console.

## Workspace project curation

For more information on how to limit components (dimensions, metrics, segments, date ranges) at the Workspace project level, and how curation is tied to data views, see [Curate projects](/help/analysis-workspace/curate-share/curate.md).

## Grant access to individual metrics or dimensions

You cannot grant or deny permissions on individual metrics or dimensions in Customer Journey Analytics like you can in traditional Adobe Analytics. Metrics and dimensions can be modified in [data views](/help/data-views/data-views.md) and are thus subject to change in CJA, which also changes reporting retroactively.

