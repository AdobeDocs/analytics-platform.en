---
title: Customer Managed Keys
description: Learn how to set up Customer Managed Keys for CJA.
---
# Customer Managed Keys

>[!NOTE]
>
>This functionality will be available in November 2022.

Customer Journey Analytics (CJA) provides the option for Healthcare Shield and Privacy & Security Shield customers to utilize an Azure Customer Managed Key (CMK) to be applied to your CJA data.  Note that this process is separate from Adobe Experience Platform CMK setup (link to follow).  

>[!NOTE]
>
>Customer Managed Keys are currently available only for organizations that have purchased the [Healthcare Shield or Privacy & Security Shield](https://experienceleague.adobe.com/docs/blueprints-learn/architecture/vertical-blueprints/healthcare-vertical.html%3Flang%3Den) add-on offering.

Follow these steps to set up CMK for CJA:

1. Ensure that you are entitled to CMK by checking with your Adobe Account team.
1. Create a new Azure Key Vault to be used only with CJA.
1. Tie your Azure Key Value to the Azure CJA CMK App (link to follow).
1. Create an Adobe Customer Care ticket requesting CMK setup. Include the Azure URI in your ticket.
1. Adobe Customer Care will confirm completion of CMK application on your CJA data.
