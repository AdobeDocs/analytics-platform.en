---
description: Configure the cloud export account where Customer Journey Analytics data can be sent
keywords: Analysis Workspace
title: Configure cloud export accounts
feature: Components
exl-id: 7c9d100f-0dbd-4dd2-b20b-d2ee117f1b7a
---
# Configure cloud export accounts

{{release-limited-testing}}

Before you can export Customer Journey Analytics reports to a cloud destination as described in [Export Customer Journey Analytics reports to the cloud](/help/analysis-workspace/export/export-cloud.md), you need to add and configure the destination where you want the data to be sent. 

This process consists of adding and configuring the account (such as Amazon S3, Google Cloud Platform, and so forth) as described in this article, and then adding and configuring the location within that account (such as a folder within the account) as described in [Configure cloud export locations](/help/components/exports/cloud-export-locations.md).

For information about how to manage existing accounts, including viewing, editing, and deleting accounts, see [Manage cloud export locations and accounts](/help/components/exports/manage-export-locations.md).

## Begin creating a cloud export account

1. In Customer Journey Analytics, select [!UICONTROL **Components**] > [!UICONTROL **Exports**].
1. On the [!UICONTROL Exports] page, select the [!UICONTROL **Location accounts**] tab.
1. Select [!UICONTROL **Add account**]. 

   ![Add account](assets/account-add.png)
   
   The Add account dialog displays.

1. In the [!UICONTROL **Location account name**] field, specify a name for the location account. This name appears when creating a location.

1. In the [!UICONTROL **Location account description**] field, provide a short description of the account to help differentiate it from other accounts of the same account type.

1. In the [!UICONTROL **Account type**] field, select the type of cloud account you are exporting to. Available account types are Amazon S3 Role ARN, Google Cloud Platform, Azure SAS, Azure RBAC, Snowflake, and AEP Data Landing Zone.

1. Continue with the section below that corresponds to the [!UICONTROL **Account type**] you selected.

   * [AEP Data Landing Zone](#adobe-experience-platform)

   * [Amazon S3 Role ARN](#amazon-s3-role-arn)

   * [Google Cloud Platform](#google-cloud-platform)

   * [Azure SAS](#azure-sas)

   * [Azure RBAC](#azure-rbac)

   * [Snowflake](#snowflake)

### AEP Data Landing Zone

>[!IMPORTANT]
>
>When exporting Customer Journey Analytics reports to Adobe Experience Platform Data Landing Zone, make sure that you download the data within 7 days, then delete it from AEP Data Landing Zone. After 7 days, the data is automatically deleted from AEP Data Landing Zone.

1. [Begin creating a cloud export account](#begin-creating-a-cloud-export-account), as described above. 

1. Select [!UICONTROL **Save**].

   The [!UICONTROL **Export account created**] dialog displays.

   ![Export account dialog AEP Data Landing Zone](assets/export-account-aep.png)

1. Copy the contents of the [!UICONTROL **SAS URI**] field to your clipboard. 

   You will use this SAS URI to access the data that is exported from Analysis Workspace from the AEP Data Landing Zone.

1. In Adobe Experience Platform, configure your Data Landing Zone container to use the SAS URI that you copied.

   >[!NOTE]
   >
   >Because the AEP Data Landing Zone account is based on Azure, the easiest way to access reports that you export to AEP Data Landing Zone is by using the Azure Storage Explorer. The following steps use this method.

   1. If you haven't already, download the [Microsoft Azure Storage Explorer](https://azure.microsoft.com/en-us/products/storage/storage-explorer/).
   
   1. In the Adobe Experience Platform documentation, follow the steps described in [Connect your Data Landing Zone container to Azure Storage Explorer](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone.html?lang=en#connect-your-data-landing-zone-container-to-azure-storage-explorer).

      You can skip the tasks described in the sections [Retrieve the credentials for your Data Landing Zone](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone.html?lang=en#retrieve-dlz-credentials) and [Update Data Landing Zone credentials](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone.html?lang=en#update-dlz-credentials), because the URI that you copied contains these credentials.

   1. When following the Adobe Experience Platform documentation and you come to the [!UICONTROL **Blob container SAS URL**] field, paste the SAS URI that you copied in Step 3.

        ![SAS URL field](assets/blob-container-sas-uri.png)

   1. Select [!UICONTROL **Next**] > [!UICONTROL **Connect**].

1. In Customer Journey Analytics, in the [!UICONTROL **Export account created**] dialog, select [!UICONTROL **OK**].

   ![Export account dialog AEP Data Landing Zone](assets/export-account-aep.png)

1. Continue with [Configure cloud export locations](/help/components/exports/cloud-export-locations.md).

### Amazon S3 Role ARN

1. [Begin creating a cloud export account](#begin-creating-a-cloud-export-account), as described above. 

1. In the [!UICONTROL **Account properties**] section of the [!UICONTROL **Add account**] dialog box, specify the following information:

   |Field | Function | 
   |---------|----------|
   | [!UICONTROL **Role ARN**] | You must provide a Role ARN (Amazon Resource Name) that Adobe can use to gain access to the Amazon S3 account. To do this, you create an IAM permission policy for the source account, attach the policy to a user, and then create a role for the destination account. For specific information, see [this AWS documentation](https://aws.amazon.com/premiumsupport/knowledge-center/cross-account-access-iam/). | 

   {style="table-layout:auto"}

1. Select [!UICONTROL **Save**].

   The [!UICONTROL **Export account created**] dialog displays.

   ![Export account created dialog Amazon S3 Role ARN](assets/export-account-amazons3.png)

1. Copy the contents of the [!UICONTROL **User ARN**] field to your clipboard. The User ARN (Amazon Resource Name) is provided by Adobe. You must attach this user to the policy you created in Amazon S3 Role ARN. 

1. Select [!UICONTROL **OK**].

1. Continue with [Configure cloud export locations](/help/components/exports/cloud-export-locations.md).

### Google Cloud Platform
  
1. [Begin creating a cloud export account](#begin-creating-a-cloud-export-account), as described above. 

1. In the [!UICONTROL **Account properties**] section of the [!UICONTROL **Add account**] dialog box, specify the following information:

      |Field | Function | 
      |---------|----------|
      | [!UICONTROL **Project ID**] | Your Google Cloud project ID that you copy from your Google Cloud account. See the [Google Cloud documentation about getting a project ID](https://cloud.google.com/resource-manager/docs/creating-managing-projects#identifying_projects). |  

      {style="table-layout:auto"}

1. Select [!UICONTROL **Save**].

   The [!UICONTROL **Export account created**] dialog displays.

   ![Export account created dialog](assets/export-account-gcp.png)

1. Copy the contents of the [!UICONTROL **Principal**] field to your clipboard, then ensure that you grant permission to the Principal to upload files to this bucket in Google Cloud Platform. <!-- add link to Google Cloud docs on how to do this --> 

1. Select [!UICONTROL **OK**].

1. Continue with [Configure cloud export locations](/help/components/exports/cloud-export-locations.md).

### Azure SAS

1. [Begin creating a cloud export account](#begin-creating-a-cloud-export-account), as described above. 

1. In the [!UICONTROL **Account properties**] section of the [!UICONTROL **Add account**] dialog box, specify the following information:

      |Field | Function | 
      |---------|----------|
      | [!UICONTROL **Application ID**] | Copy this ID from the Azure application that you created. In Microsoft Azure, this information is located on the **Overview** tab within your application. For more information, see the [Microsoft Azure documentation about how to register an application with the Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). | 
      | [!UICONTROL **Tenant ID**] | Copy this ID from the Azure application that you created. In Microsoft Azure, this information is located on the **Overview** tab within your application. For more information, see the [Microsoft Azure documentation about how to register an application with the Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
      | [!UICONTROL **Key vault URI**] | <p>The path to the SAS token in Azure Key Vault.  To configure Azure SAS, you need to store an SAS token as a secret using Azure Key Vault. For information, see the [Microsoft Azure documentation about how to set and retrieve a secret from Azure Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations).</p><p>After the key vault URI is created, add an access policy on the Key Vault in order to grant permission to the Azure application that you created. For information, see the [Microsoft Azure documentation about how to assign a Key Vault access policy](https://learn.microsoft.com/en-us/azure/key-vault/general/assign-access-policy?tabs=azure-portal).</p> | 
      | [!UICONTROL **Key vault secret name**] | The secret name you created when adding the secret to Azure Key Vault. In Microsoft Azure, this information is located in the Key Vault you created, on the **Key Vault** settings pages. For information, see the [Microsoft Azure documentation about how to set and retrieve a secret from Azure Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations). |
      | [!UICONTROL **Location account secret**] <!-- nothing for us to have them do on the second screen. Just need to permission the container if they haven't --> | Copy the secret from the Azure application that you created. In Microsoft Azure, this information is located on the **Certificates & secrets** tab within your application. For more information, see the [Microsoft Azure documentation about how to register an application with the Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). <!-- need to grant permission to the bucket. Jun will send info on where that is documented) --> |

      {style="table-layout:auto"}

1. Select [!UICONTROL **Save**].

   The [!UICONTROL **Export account created**] dialog displays.

   ![Export account created dialog](assets/export-account-azure.png)

1. If you haven't already, ensure that you grant permissions to the bucket in Azure SAS. <!-- add link to Google Cloud docs on how to do this --> 

1. Select [!UICONTROL **OK**].

1. Continue with [Configure cloud export locations](/help/components/exports/cloud-export-locations.md).

### Azure RBAC

1. [Begin creating a cloud export account](#begin-creating-a-cloud-export-account), as described above. 

1. In the [!UICONTROL **Account properties**] section of the [!UICONTROL **Add account**] dialog box, specify the following information:

      |Field | Function | 
      |---------|----------|
      | [!UICONTROL **Application ID**] | Copy this ID from the Azure application that you created. In Microsoft Azure, this information is located on the **Overview** tab within your application. For more information, see the [Microsoft Azure documentation about how to register an application with the Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). | 
      | [!UICONTROL **Tenant ID**] | Copy this ID from the Azure application that you created. In Microsoft Azure, this information is located on the **Overview** tab within your application. For more information, see the [Microsoft Azure documentation about how to register an application with the Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). | 
      | [!UICONTROL **Location account secret**] | Copy the secret from the Azure application that you created. In Microsoft Azure, this information is located on the **Certificates & secrets** tab within your application. For more information, see the [Microsoft Azure documentation about how to register an application with the Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). | 

      {style="table-layout:auto"}

1. Select [!UICONTROL **Save**].

   The [!UICONTROL **Export account created**] dialog displays.

   ![Export account created dialog](assets/export-account-azure.png)

1. If you haven't already, ensure that you grant permissions to the bucket in Azure RBAC. <!-- add link to Google Cloud docs on how to do this --> 

1. Select [!UICONTROL **OK**].

1. Continue with [Configure cloud export locations](/help/components/exports/cloud-export-locations.md).

### Snowflake

1. [Begin creating a cloud export account](#begin-creating-a-cloud-export-account), as described above. 

1. In the [!UICONTROL **Account properties**] section of the [!UICONTROL **Add account**] dialog box, specify the following information:

      |Field | Function | 
      |---------|----------|
      | [!UICONTROL **Account identifier**] | Uniquely identifies a Snowflake account within your organization, as well as throughout the global network of Snowflake-supported cloud platforms and cloud regions. <p>You need to get the account identifier from your Snowflake account, then paste the information here.</p><p>To learn where to get this information, see the [Account Identifiers page in the Snowflake documentation](https://docs.snowflake.com/en/user-guide/admin-account-identifier).</p> | 
      | [!UICONTROL **User**] | The login name of the user that will be used for the connection. We recommend creating a new user that will be used specifically for Adobe. Specify the name here, then create a user in Snowflake with the same name. You can create a user in Snowflake using the `CREATE USER` command.  <p>For more information, see the [User, Role, & Privilege Commands](https://docs.snowflake.com/en/sql-reference/commands-user-role).</p> | 
      | [!UICONTROL **Role**] | The role that will be assigned to the user. We recommend creating a new role that will be used specifically for Adobe. Specify the role here, then create a role in Snowflake with the same name and grant the role to the user. You can create a role in Snowflake using the `CREATE ROLE` command. <p>For more information, see the [User, Role, & Privilege Commands](https://docs.snowflake.com/en/sql-reference/commands-user-role).</p> |

      {style="table-layout:auto"}

1. Select [!UICONTROL **Save**].

   The [!UICONTROL **Export account created**] dialog displays.

   ![Export account created dialog](assets/export-account-snowflake.png)

1. Copy the contents of the [!UICONTROL **Public key**] field to your clipboard. The Public key is provided by Adobe. 

   Use the public key in Snowflake to connect to your Snowflake account. You must associate the user that you created with this public key. 

   For example, in Snowflake, specify the following command:

   ```
   CREATE USER <your_adobe_user> RSA_PUBLIC_KEY = '<your_public_key>';
   ```

   For more information, see the [Key Pair Authentication & Key Pair Rotation page in the Snowflake documentation](https://docs.snowflake.com/en/user-guide/key-pair-auth). 

1. Select [!UICONTROL **OK**].

1. Continue with [Configure cloud export locations](/help/components/exports/cloud-export-locations.md).
