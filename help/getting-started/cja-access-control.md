---
title: CJA Access Control
description: Learn about access control requirements for creating connections, adding datasets, creating data views, etc.
solution: Customer Journey Analytics
feature: CJA Basics
---

# CJA Access Control

To access and perform tasks in Customer Journey Analytics, you must be added as an Admin to the **Customer Journey Analytics Product Profile** in the [Admin Console](https://adminconsole.adobe.com/enterprise/). Product admins are granted the following permissions:

* Create/update/delete connections or data views
* Update/delete projects, filters, calculated metrics, or filters created by other users
* Share Workspace projects to all users

## Required Adobe Experience Platform permissions

Becoming a product admin in Customer Journey Analytics alone is not enough to create, update, or delete a connection. To create a connection to an Experience Platform dataset, you also need Experience Platform permissions. Specifically, you must be part of an **Experience Platform Product Profile** that gives you the following permissions:

* View Schemas
* Manage Schemas
* View Identity Namespaces
* View Datasets
  
For more information on Experience Platform permissions, see [Access control in Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html).

## Grant access to individual metrics or dimensions

You cannot grant or deny permissions on individual metrics or dimensions in Customer Journey Analytics like you can in traditional Adobe Analytics. Metrics and dimensions can be modified in [data views](/help/data-views/data-views.md) and are thus subject to change in CJA, which also changes reporting retroactively.

## User access

Non-product admins (users) in Customer Journey Analytics cannot view data views or connections, but can create filters, projects, and calculated metrics.