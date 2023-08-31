---
description: Configure the cloud export location where Customer Journey Analytics data can be sent
keywords: Analysis Workspace
title: Configure cloud export locations
feature: Components
---
# Configure cloud export locations

{{select-package}}

Before you can export Customer Journey Analytics data to a cloud destination as described in [Export Customer Journey Analytics data to the cloud](/help/analysis-workspace/export/export-cloud.md), you need to add and configure the location where you want the data to be sent. 

This process consists of adding and configuring the account (such as Amazon S3, Google Cloud Platform, and so forth) as described in [Configure cloud export accounts](/help/components/exports/cloud-export-accounts.md), and then adding and configuring the location within that account (such as a folder within the account) as described in this article.

To configure a cloud export location:

1. You need to add an account before you can add a location. If you haven't already, add an account as described in [Configure cloud export accounts](/help/components/exports/cloud-export-accounts.md).
1. In Customer Journey Analytics, select [!UICONTROL **Components**] > [!UICONTROL **Exports**].
1. On the [!UICONTROL Exports] page, select the [!UICONTROL **Locations**] tab.
1. Select [!UICONTROL **Add location**]. 
   
   ![add location button](assets/location-add.png)

   The Location dialog displays.

1. Specify the following information:
   |Field | Function | 
   |---------|----------|
   | [!UICONTROL **Name**] | The name of the location.  | 
   | [!UICONTROL **Description**] | Provide a short description of the account to help differentiate it from other accounts of the same account type. |
   | [!UICONTROL **Location account**] | Select the location account that you created in [Add an account](#add-an-account). | 

1. In the [!UICONTROL **Location properties**] section, specify information specific to the account type of your location account.  

   For configuration instructions, expand the section below that corresponds to the account type that you selected in the [!UICONTROL **Location accounts**] field. 

   +++Amazon S3 Role ARN

      Specify the following information to configure an Amazon S3 Role ARN location:

      <!-- still need to update; can't create S3 role ARN account -->

      |Field | Function | 
      |---------|----------|
      | [!UICONTROL **Role ARN**] | You must provide a Role ARN (Amazon Resource Name) that Adobe can use to gain access to the Amazon S3 account. To do this, you create an IAM permission policy for the source account, attach the policy to a user, and then create a role for the destination account. For specific information, see [this AWS documentation](https://aws.amazon.com/premiumsupport/knowledge-center/cross-account-access-iam/). | 
      | [!UICONTROL **User ARN**] | The User ARN (Amazon Resource Name) is provided by Adobe. You must attach this user to the policy you created. | 

      {style="table-layout:auto"}

   +++

   +++Google Cloud Platform

      Specify the following information to configure a Google Cloud Platform location:

      <!-- still need to update; can't create GCP account -->

      |Field | Function | 
      |---------|----------|
      | [!UICONTROL **Bucket name**] | The bucket within your GCP account where you want Adobe Analytics data to be sent. Ensure that you have granted permission to the Principal provided by Adobe to upload files to this bucket. For information about granting permissions, see [Add a principal to a bucket-level policy](https://cloud.google.com/storage/docs/access-control/using-iam-permissions#bucket-add) in the Google Cloud documentation.|  
      | [!UICONTROL **Key prefix**] | The folder within the bucket where you want to put the data. Specify a folder name, then add a backslash after the name to create the folder. For example, folder_name/ | 

      {style="table-layout:auto"}
   
   +++

   +++Azure SAS

      Specify the following information to configure an Azure SAS location:

      |Field | Function | 
      |---------|----------|
      | [!UICONTROL **Container name**] | The container within the account you specified where you want Adobe Analytics data to be sent. | 
      | [!UICONTROL **Key prefix**] | The folder within the container where you want to put the data. Specify a folder name, then add a backslash after the name to create the folder. For example, `folder_name/` | 

      {style="table-layout:auto"}

   +++   

   +++Azure RBAC

      Specify the following information to configure an Azure RBAC location:

      |Field | Function | 
      |---------|----------|
      | [!UICONTROL **Container name**] | The container within the account you specified where you want Adobe Analytics data to be sent. Ensure that you grant permissions to upload files to the Azure application that you created earlier. | 
      | [!UICONTROL **Key prefix**] | The folder within the container where you want to put the data. Specify a folder name, then add a backslash after the name to create the folder. For example, `folder_name/` |
      | [!UICONTROL **Account name**] | The Azure storage account. | 

      {style="table-layout:auto"}

   +++

   +++Snowflake

      Specify the following information to configure a Snowflake location:

      |Field | Function | 
      |---------|----------|
      | [!UICONTROL **DB**] | <!--add info --> | 
      | [!UICONTROL **Schema**] | <!--add info --> | 
      | [!UICONTROL **Stage name**] | <!--add info --> | 
      | [!UICONTROL **Stage path**] | <!--add info --> | 

      {style="table-layout:auto"}

   +++

   +++Adobe Experience Platform

      Specify the following information to configure an Adobe Experience Platform location:

      <!-- still need to update; can't create AEP account -->

      |Field | Function | 
      |---------|----------|
      | [!UICONTROL **Location Account Secret**] | Copy the secret from the Adobe Experience Platform application that you created. In Adobe Exprience Platform, this information is located in <!--add link to AEP docs -->. | 

   +++

1. Select [!UICONTROL **Save**].

1. You can now export data from Analysis Workspace to the account and location that you configured. For information about how to export data to the cloud, see [Export project data to the cloud](/help/analysis-workspace/export/export-cloud.md).