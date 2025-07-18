---
description: Configure the cloud export location where Customer Journey Analytics data can be sent
keywords: Analysis Workspace
title: Configure cloud export locations
feature: Components
exl-id: 93f1cca0-95da-41a0-a4f9-5ab620a5b9da
role: User, Admin
---
# Configure cloud export locations

Before you can export Customer Journey Analytics reports to a cloud destination (either from Analysis Workspace, as described in [Export Customer Journey Analytics reports to the cloud](/help/analysis-workspace/export/export-cloud.md) or from Report Builder, as described in [Export reports from Report Builder](/help/report-builder/report-builder-export.md)) as described in [Export Customer Journey Analytics reports to the cloud](/help/analysis-workspace/export/export-cloud.md), you need to add and configure the location where you want the data to be sent. 

This process consists of adding and configuring the account (such as Amazon S3, Google Cloud Platform, and so forth) as described in [Configure cloud export accounts](/help/components/exports/cloud-export-accounts.md), and then adding and configuring the location within that account (such as a folder within the account) as described in this article.

For information about how to manage existing locations, including viewing, editing, and deleting locations, see [Manage cloud export locations and accounts](/help/components/exports/manage-export-locations.md).

## Begin creating a cloud export location

1. You need to add an account before you can add a location. If you haven't already, add an account as described in [Configure cloud export accounts](/help/components/exports/cloud-export-accounts.md).

1. In Customer Journey Analytics, select [!UICONTROL **Components**] > [!UICONTROL **Exports**].

1. Select the [!UICONTROL **Locations**] tab, then select [!UICONTROL **Add location**]. 
   
   ![Exports window with Location tab selected highlighting the Add location button](assets/location-add.png)

   Or

   Select the [!UICONTROL **Location accounts**] tab, select the 3-dot icon on an existing account where you want to add a location, then select [!UICONTROL **Add location**].

   ![GCP account and elipsis drop-down menu showing Add location selected](assets/add-location-existing-account.png)

   The Location dialog displays.

1. Specify the following information:

   |Field | Function | 
   |---------|----------|
   | [!UICONTROL **Name**] | The name of the location.  | 
   | [!UICONTROL **Description**] | Provide a short description of the location to help differentiate it from other locations on the account. |
   | [!UICONTROL **Make location available to all users in your organization**] | Enable this option to allow other users in your organization to use the location. <p>Consider the following when sharing locations:</p><ul><li>Locations that you share cannot be unshared.</li><li>Shared locations can be edited only by the owner of the location.</li><li>Locations can be shared only if the account that the location is associated with is also shared.</li></ul> |
   | [!UICONTROL **Location account**] | Select the account where you want to create the location. For information about how to create an account, see [Configure cloud export accounts](/help/components/exports/cloud-export-accounts.md). | 

1. In the [!UICONTROL **Location properties**] section, specify information specific to the account type of your location account.  

   Continue with the section below that corresponds to the account type that you selected in the [!UICONTROL **Location account**] field.

   * [AEP Data Landing Zone](#aep-data-landing-zone)
   * [Amazon S3 Role ARN](#amazon-s3-role-arn)
   * [Google Cloud Platform](#google-cloud-platform)
   * [Azure SAS](#azure-sas)
   * [Azure RBAC](#azure-rbac)
   * [Snowflake](#snowflake)

### AEP Data Landing Zone

>[!IMPORTANT]
>
>When exporting Customer Journey Analytics reports to Adobe Experience Platform Data Landing Zone, make sure that you download the data within 7 days, then delete it from AEP Data Landing Zone. After 7 days, the data is automatically deleted from AEP Data Landing Zone.

1. Begin creating a cloud export location in either of the following ways:

   * From the Exports page as described above, in [Begin creating a cloud export location](#begin-creating-a-cloud-export-location)
   
   * When [exporting full tables from Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. In the [!UICONTROL **Location properties**] section of the [!UICONTROL **Add location**] dialog box, specify the following information to configure an Adobe Experience Platform Data Landing Zone location:

   <!-- still need to update; can't create AEP account -->

   |Field | Function | 
   |---------|----------|
   | [!UICONTROL **Prefix**] | The folder within the container where you want to put the data. Specify a folder name, then add a slash after the name to create the folder. For example, `folder_name/` |

   {style="table-layout:auto"}

1. Select [!UICONTROL **Save**].

1. You can now export data from Analysis Workspace to the account and location that you configured. For information about how to export data to the cloud, see [Export project data to the cloud](/help/analysis-workspace/export/export-cloud.md).

1. The easiest way to access your data in AEP Data Landing Zone is to use the Microsoft Azure Storage Explorer. This is the same tool that is used in the instructions to configure the [AEP Data Landing Zone account](/help/components/exports/cloud-export-accounts.md#aep-data-landing-zone).

   1. Open the [Microsoft Azure Storage Explorer](https://azure.microsoft.com/en-us/products/storage/storage-explorer/).

   1. Go to [!UICONTROL **Storage Accounts**] > [!UICONTROL **(Attached Containers)**] > [!UICONTROL **Blob Containers**] > **[!UICONTROL cjaexport-_number_]** > ***your_container_name***.

      >[!NOTE]
      >
      >The folder name **[!UICONTROL cjaexport-_number_]** is the default name provided by Azure Storage Explorer. If you have only a single connection associated with your SAS URI (which is normal), then the name of this folder will be **[!UICONTROL cjaexport-1]**.


      ![Access files in Azure storage explorer](assets/azure-storage-explorer-access.png)

   1. Select the export that you want to download, then select [!UICONTROL **Download**] to download.

### Amazon S3 Role ARN

1. Begin creating a cloud export location in either of the following ways:

   * From the Exports page as described above, in [Begin creating a cloud export location](#begin-creating-a-cloud-export-location)
   
   * When [exporting full tables from Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. In the [!UICONTROL **Location properties**] section of the [!UICONTROL **Add location**] dialog box, specify the following information to configure an Amazon S3 Role ARN location:

    <!-- still need to update; can't create S3 role ARN account -->

   |Field | Function | 
   |---------|----------|
   | [!UICONTROL **Bucket**] | The bucket within your Amazon S3 account where you want Customer Journey Analytics data to be sent. <p>Ensure that the User ARN that was provided by Adobe has the `S3:PutObject` permission in order to upload files to this bucket. </p><p>Bucket names must meet specific naming rules. For example, they must be between 3 to 63 characters long, can consist only of lowercase letters, numbers, dots (.), and hyphens (-), and must begin and end with a letter or number. [A complete list of naming rules are available in the AWS documentation](https://docs.aws.amazon.com/AmazonS3/latest/userguide/bucketnamingrules.html). </p>   | 
   | [!UICONTROL **Prefix**] | The folder within the bucket where you want to put the data. Specify a folder name, then add a slash after the name to create the folder. For example, folder_name/ | 

   {style="table-layout:auto"}

1. Select [!UICONTROL **Save**].

1. You can now export data from Analysis Workspace to the account and location that you configured. For information about how to export data to the cloud, see [Export project data to the cloud](/help/analysis-workspace/export/export-cloud.md).

### Google Cloud Platform

1. Begin creating a cloud export location in either of the following ways:

   * From the Exports page as described above, in [Begin creating a cloud export location](#begin-creating-a-cloud-export-location)
   
   * When [exporting full tables from Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. In the [!UICONTROL **Location properties**] section of the [!UICONTROL **Add location**] dialog box, specify the following information to configure a Google Cloud Platform location:

   |Field | Function | 
   |---------|----------|
   | [!UICONTROL **Bucket**] | The bucket within your GCP account where you want Customer Journey Analytics data to be sent. <p>Ensure that you have granted the `roles/storage.objectCreator` permission to the Principal provided by Adobe. (The Principal is provided when [configuring the Google Cloud Platform account](/help/components/exports/cloud-export-accounts.md).) <p>For information about granting permissions, see [Add a principal to a bucket-level policy](https://cloud.google.com/storage/docs/access-control/using-iam-permissions#bucket-add) in the Google Cloud documentation.</p><p>If your organization is using [Organization policy constraints](https://cloud.google.com/storage/docs/org-policy-constraints) to allow only the Google Cloud Platform account in your allow list, you need the following Adobe-owned Google Cloud Platform organization ID: <ul><li>`DISPLAY_NAME`: `adobe.com`</li><li>`ID`: `178012854243`</li><li>`DIRECTORY_CUSTOMER_ID`: `C02jo8puj`</li></ul> </p> |  
   | [!UICONTROL **Prefix**] | The folder within the bucket where you want to put the data. Specify a folder name, then add a slash after the name to create the folder. For example, folder_name/ | 

   {style="table-layout:auto"}

1. Select [!UICONTROL **Save**].

1. You can now export data from Analysis Workspace to the account and location that you configured. For information about how to export data to the cloud, see [Export project data to the cloud](/help/analysis-workspace/export/export-cloud.md).

### Azure SAS

1. Begin creating a cloud export location in either of the following ways:

   * From the Exports page as described above, in [Begin creating a cloud export location](#begin-creating-a-cloud-export-location)
   
   * When [exporting full tables from Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. In the [!UICONTROL **Location properties**] section of the [!UICONTROL **Add location**] dialog box, specify the following information to configure an Azure SAS location:

   |Field | Function | 
   |---------|----------|
   | [!UICONTROL **Container name**] | The container within the account you specified where you want Customer Journey Analytics data to be sent. | 
   | [!UICONTROL **Prefix**] | The folder within the container where you want to put the data. Specify a folder name, then add a slash after the name to create the folder. For example, `folder_name/`<p>Make sure that the SAS token store that you specified in the Key Vault secret name field when configuring the Azure SAS account has the `Write` permission. This allows the SAS token to create files in your Azure container. <p>If you want the SAS token to also overwrite files, make sure that the SAS token store has the `Delete` permission.</p><p>For more information, see [Blob storage resources](https://learn.microsoft.com/en-us/azure/storage/blobs/storage-blobs-introduction#blob-storage-resources) in the Azure Blob Storage documentation.</p> | 

   {style="table-layout:auto"}

1. Select [!UICONTROL **Save**].

1. You can now export data from Analysis Workspace to the account and location that you configured. For information about how to export data to the cloud, see [Export project data to the cloud](/help/analysis-workspace/export/export-cloud.md).

### Azure RBAC

1. Begin creating a cloud export location in either of the following ways:

   * From the Exports page as described above, in [Begin creating a cloud export location](#begin-creating-a-cloud-export-location)
   
   * When [exporting full tables from Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. In the [!UICONTROL **Location properties**] section of the [!UICONTROL **Add location**] dialog box, specify the following information to configure an Azure RBAC location:

   |Field | Function | 
   |---------|----------|
   | [!UICONTROL **Container**] | The container within the account you specified where you want Customer Journey Analytics data to be sent. Ensure that you grant permissions to upload files to the Azure application that you created earlier. | 
   | [!UICONTROL **Prefix**] | The folder within the container where you want to put the data. Specify a folder name, then add a slash after the name to create the folder. For example, `folder_name/`<p>Make sure the Application ID that you specified when configuring the Azure RBAC account has been granted the `Storage Blob Data Contributor` role in order to access the container (folder).</p> <p>For more information, see [Azure built-in roles](https://learn.microsoft.com/en-us/azure/role-based-access-control/built-in-roles).</p> |
   | [!UICONTROL **Account**] | The Azure storage account. | 

   {style="table-layout:auto"}

1. Select [!UICONTROL **Save**].

1. You can now export data from Analysis Workspace to the account and location that you configured. For information about how to export data to the cloud, see [Export project data to the cloud](/help/analysis-workspace/export/export-cloud.md).

### Snowflake

1. Begin creating a cloud export location in either of the following ways:

   * From the Exports page as described above, in [Begin creating a cloud export location](#begin-creating-a-cloud-export-location)
   
   * When [exporting full tables from Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. In the [!UICONTROL **Location properties**] section of the [!UICONTROL **Add location**] dialog box, specify the following information to configure a Snowflake location:

   |Field | Function | 
   |---------|----------|
   | [!UICONTROL **DB**] | The specified database should be an existing database. The role you created needs to have privileges to access this database.<p>This is the database associated with the stage name.</p><p>You can grant this role privileges to the database in Snowflake using the following command: `GRANT USAGE ON DATABASE <your_database> TO ROLE <your_role>;`</p> <p>For more information, see the [Database, Schema, and Share Commands page in the Snowflake documentation](https://docs.snowflake.com/en/sql-reference/commands-database).</p> | 
   | [!UICONTROL **Schema**] | The specified schema should be an existing schema. The role you created needs to have privileges to access this schema.<p>This is the schema associated with the stage name.<p>You can grant the role that you created privileges to the schema in Snowflake using the following command: `GRANT USAGE ON SCHEMA <your_database>.<your_schema> TO ROLE <your_role>;`</p><p>For more information, see the [Database, Schema, and Share Commands page in the Snowflake documentation](https://docs.snowflake.com/en/sql-reference/commands-database).</p> | 
   | [!UICONTROL **Stage name**] | The name of the internal stage where data files are stored in Snowflake.<p>Make sure that the role you specified on the account has Read and Write access to this stage name. (Because you are granting Read and Write access, we recommend using a stage that is used only by Adobe.)<p>You can grant Read and Write access to the stage name in Snowflake using the following command: `GRANT READ, WRITE ON STAGE <your_database>.<your_schema>.<your_stage_name> TO ROLE <your_role>;`</p> <p>For information about granting privileges to a role, see [Grant privileges in the Snowflake documentation](https://docs.snowflake.com/en/sql-reference/sql/grant-privilege). <p>For more information about the stage name, see the [Choosing an Internal Stage for Local Files page in the Snowflake documentation](https://docs.snowflake.com/en/user-guide/data-load-local-file-system-create-stage).</p> | 
   | [!UICONTROL **Stage path**] | The path to the location where data files are stored in Snowflake. <p>For more information, see the [Choosing an Internal Stage for Local Files page in the Snowflake documentation](https://docs.snowflake.com/en/user-guide/data-load-local-file-system-create-stage).</p> | 

   {style="table-layout:auto"}

1. Select [!UICONTROL **Save**].

1. You can now export data from Analysis Workspace to the account and location that you configured. For information about how to export data to the cloud, see [Export project data to the cloud](/help/analysis-workspace/export/export-cloud.md).
