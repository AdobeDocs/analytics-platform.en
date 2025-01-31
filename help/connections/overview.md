---
title: Customer Journey Analytics Connections overview
description: Learn about connections in Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Connections
exl-id: 012371d7-aaef-4018-95ee-5c52083e9d8f
role: Admin
---
# Connections overview

Connections allow Customer Journey Analytics product administrators to establish connections with different [!DNL Adobe Experience Platform] data sources, such as event, lookup, and profile datasets. These connections enable the integration of data from a Connection to a derivative Data View. Connections are the foundation of CJA and are created from [!DNL Experience Platform] source datasets. Access to Connections also lets you view the Connections manager, where you can view the underlying datasets that make up the connection, as well as make critical editing and configuration selections.

We recommended restricting access to Connections management to a core management group. Configurations at the Connection level have contractual implications regarding volume allotments for data brought into Customer Journey Analytics. 

<!-- Outdated interface 

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Configuring connections](https://video.tv.adobe.com/v/35111/?quality=12&learn=on){target=&#34;_blank&#34;} for a demo video.

>[!ENDSHADEBOX]

-->

## Required permissions

To create a Customer Journey Analytics Connection, you need the following permissions. For additional details about permissions, refer to documentation for the [Adobe Admin Console](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/manage-permissions-and-roles.ug.html) and [Adobe Experience Platform Permissions](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/home).

### Within Adobe Admin Console:

* Customer Journey Analytics: Product Admin
* Adobe Experience Platform: Added to Product Profile named *AEP-Default-All-Users*

### Within Adobe Experience Platform Permissions:

* Data Modeling: View Schemas, Manage Schemas
* Data Management: View Datasets, Manage Datasets
* Data Ingestion: Manage Sources
* Identity Management: View Identity Namespaces
* Sandboxes: Sandboxes used in related Customer Journey Analytics Connections

>[!IMPORTANT]
>
>You can combine multiple [!DNL Experience Platform] datasets into a single connection.
