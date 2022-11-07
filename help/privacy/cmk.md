---
title: Customer Managed Keys
description: Learn how to set up Customer Managed Keys for CJA.
---
# Customer Managed Keys

Customer Journey Analytics (CJA) provides the option for [Healthcare Shield](https://www.adobe.com/trust/compliance/hipaa-ready.html) and Privacy & Security Shield customers to utilize an Azure Customer Managed Key (CMK) to be applied to your CJA data.  Note that this process is separate from [Adobe Experience Platform CMK setup](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/customer-managed-keys.html).  

>[!NOTE]
>
>Customer Managed Keys are currently available only for organizations that have purchased the [Healthcare Shield or Privacy & Security Shield](https://experienceleague.adobe.com/docs/blueprints-learn/architecture/vertical-blueprints/healthcare-vertical.html%3Flang%3Den) add-on offering.

## Set up CMK for CJA

Follow these steps to set up CMK for CJA:

1. Ensure that you are entitled to Adobe CJA CMK by checking with your Adobe Account team.
1. Ensure that, in Azure, you are an administrator with a privileged role such as Application Administrator, Cloud Application Administrator, or Global Administrator. [Learn more from Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/roles/permissions-reference)
1. Create a new Azure Key Vault to be used only with CJA. [Learn more from Microsoft](https://learn.microsoft.com/en-us/azure/key-vault/general/)
1. Grant the Adobe Azure App access to your key in the key vault. This is the Adobe Application ID: 251e3919-1940-4296-bb8b-6b9a5e8a4805. [Learn More from Microsoft](https://learn.microsoft.com/en-us/azure/storage/common/customer-managed-keys-configure-cross-tenant-existing-account?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&tabs=powershell-preview%2Cazure-portal#the-customer-grants-the-service-providers-app-access-to-the-key-in-the-key-vault)
1. Create an Adobe Customer Care ticket requesting CMK setup. Include the Azure URI in your ticket. The URI can be found in the **Key Identifier** field of your Azure Key. 

   ![](assets/key-identifier.png)

1. Adobe Customer Care will confirm the completion of the CMK application on your CJA data.

All data utilized by Platform is encrypted in transit and at rest to keep your data secure, with or without CMK. For information on Adobe Experience Platform encryption, [learn more](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/encryption.html?lang=en).