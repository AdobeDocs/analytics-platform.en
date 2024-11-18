---
title: Move from the Analytics source connector to the Web SDK for Customer Journey Analytics
description: Learn how to move to the Web SDK from the Analytics source connector when upgrading to Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: yes
hidefromtoc: yes
---
# Move from the Analytics source connector to the Web SDK for Customer Journey Analytics

>[!NOTE]
> 
>Use the information on this page when answering questions in the [Customer Journey Analytics upgrade checklist](https://gigazelle.github.io/cja-ttv/).

There are inherent disadvantages with using the Analytics source connector as your sole implementation for Customer Journey Analytics. If your organization has already upgraded to Customer Journey Analytics using only the Analytics source connector implementation, you should consider moving to a Web SDK implementation. 

Adobe recommends using the Analytics source connector (for bringing over historical data), in conjunction with a new implementation of the Web SDK (for ongoing data collection). 

## Understand advantages and disadvantages of using the Analytics source connector exclusively

For information about the advantages and disadvantages of using the Analytics source connector, see [Use the Analytics source connector exclusively to upgrade to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-exclusively.md).

## Move from the Analytics source connector to the Web SDK

Following is the high-level process for moving from the Analytics source connector to an implementation comprised of both the Analytics source connector and a Web SDK implementation: 

1. Create a Web SDK implementation, as described in [Detailed recommended upgrade steps](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#detailed-recommended-upgrade-steps) in the article, [Upgrade from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).

   After the Web SDK implementation is configured, continue with the following step.

1. Decide whether you will use the Adobe Analytics schema or an XDM schema in your Web SDK implementation. 

   For more information, see [Choose your schema for Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md).

1. (Conditional) If you plan to use the Adobe Analytics schema, add the dataset that was automatically created by the Analytics source connector to your Customer Journey Analytics connection. 

   For more information, see [Add the Analytics source connector dataset to the connection](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md).

1. (Conditional) If you plan to create an XDM schema:

   1. [Create an XDM schema for the Analytics source connector](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md).

   1. Add the dataset that was automatically created with your original Analytics source connector to your Customer Journey Analytics connection.

      For more information, see [Add the dataset from your current Analytics source connector to the connection](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md).

   1. Delete your original Analytics source connector. <!-- need to add steps somewhere about how to do this -->

   1. [Create a new Analytics source connector and map fields](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md).








