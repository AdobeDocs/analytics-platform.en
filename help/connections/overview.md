---
title: Customer Journey Analytics Connections overview
description: Learn about connections in Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Connections
exl-id: 012371d7-aaef-4018-95ee-5c52083e9d8f
role: Admin
---
# Connections overview

Connections allow Customer Journey Analytics product administrators to establish connections with different AEP data sources, such as event, lookup, and profile datasets. These connections enable the integration of data from a Connection to a derivative Data View. We recommended restricting access to Connections management to a core management group. Configurations at the Connection level have contractual implications regarding volume allotments for data brought into Customer Journey Analytics. 
Connections are the foundation of CJA and are created from AEP source datasets. Access to Connections also provides the ability to view the Connections manager, which lets you view the underlying datasets that make up the connection, as well as make critical editing and configuration selections.

Here is a video overview:

>[!VIDEO](https://video.tv.adobe.com/v/35111/?quality=12&learn=on)

## Required permissions

To create a Customer Journey Analytics Connection, you need the following permissions in [Adobe Admin Console](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/manage-permissions-and-roles.ug.html):

Adobe Experience Platform:
* Data Modeling: View Schemas, Manage Schemas
* Data Management: View Datasets, Manage Datasets
* Data Ingestion: Manage Sources
* View Identity Namespaces

Customer Journey Analytics
* Product Admin Access

>[!IMPORTANT]
>
>You can combine multiple [!DNL Experience Platform] datasets into a single connection.
