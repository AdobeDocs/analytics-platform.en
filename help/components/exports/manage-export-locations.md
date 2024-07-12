---
description: Manage the cloud export location where Customer Journey Analytics data can be sent
keywords: Analysis Workspace
title: Manage cloud export locations and accounts
feature: Components
exl-id: 8e82fe6f-99df-4360-8693-99692aac002b
role: User, Admin
---
# Manage cloud export locations and accounts

You can view, edit, and delete cloud export locations.

For information about how to create a new location, see [Configure cloud export locations](/help/components/exports/cloud-export-locations.md).

## Filter and search locations

To find information you need, you can either filter the list of locations or search for a location.

### Filter the list of locations

1. In Customer Journey Analytics, select [!UICONTROL **Components**] > [!UICONTROL **Exports**].

1. Select the [!UICONTROL **Locations**] tab.

1. Select the **Filter** icon.

   <!-- add screenshot -->

   You can filter by the following criteria:

   |Filter | Description |
   |---------|----------|
   | [!UICONTROL **Location type**]<!--should this be changed to Account type?--> | The account type that the location is associated with. The following account types can be available: <ul><li>[!UICONTROL **AEP Data Landing Zone**]</li><li>[!UICONTROL **Amazon S3 Role ARN**]</li><li>[!UICONTROL **Azure SAS**]</li><li>[!UICONTROL **Azure RBAC**]</li><li>[!UICONTROL **Google Cloud Platform**]</li><li>[!UICONTROL **Snowflake**]</li></ul> | 
   | [!UICONTROL **Account**] | The name of account that the location is associated with. |
   | [!UICONTROL **Created by**] | The email address of the user who created the location. |

   {style="table-layout:auto"}

### Search for locations

1. In Customer Journey Analytics, select [!UICONTROL **Components**] > [!UICONTROL **Exports**].

1. Select the [!UICONTROL **Locations**] tab.

1. (Conditional) If you are a system administrator, you can enable the [!UICONTROL **View locations for all users**] option to view locations created by all users in your organization.

1. In the search field, begin typing any information associated with the location you're searching for. You can search for data from any column available in the table.

## Edit locations

A location can be edited only by the user who created it or by a system administrator.

To edit a location:

1. In Customer Journey Analytics, select [!UICONTROL **Components**] > [!UICONTROL **Exports**].

1. Select the [!UICONTROL **Locations**] tab.

1. (Conditional) If you are a system administrator, you can enable the [!UICONTROL **View locations for all users**] option to view locations created by all users in your organization.

1. Select the location you want to edit.

   ![Exports window showing Locations tab and list of locations.](assets/locations-edit.png)

1. Select [!UICONTROL **Edit**].

1. Make any desired changes, then select [!UICONTROL **Save**].

## Delete locations

If you delete a location, any exports that use the location are also deleted. Check the confirmation dialog when deleting to ensure that no exports are associated with the location.

To delete a location:

1. In Customer Journey Analytics, select [!UICONTROL **Components**] > [!UICONTROL **Exports**].

1. Select the [!UICONTROL **Locations**] tab.

1. (Conditional) If you are a system administrator, you can enable the [!UICONTROL **View locations for all users**] option to view locations created by all users in your organization.

1. Select one or more locations that you want to delete.

   ![Exports window showing Locations tab and list of locations](assets/locations-edit.png)

1. Select [!UICONTROL **Delete**].

   The Delete Location dialog box displays.

1. In the Delete Location dialog box, ensure that the location is not associated with any exports prior to confirming the delete. 

   ![Delete Location confirmation dialog](assets/delete-location-confirmation-dialog.png)

1. Select [!UICONTROL **Delete**] again to confirm.

## Edit accounts

An account can be edited only by the user who created it or by a system administrator.

To edit an account:

1. In Customer Journey Analytics, select [!UICONTROL **Components**] > [!UICONTROL **Exports**].

1. Select the [!UICONTROL **Location accounts**] tab.

   ![Exports window showing Location accounts tab](assets/account-add.png)

1. (Conditional) If you are a system administrator, you can enable the [!UICONTROL **View accounts for all users**] option to view locations created by all users in your organization.

1. Select [!UICONTROL **View details**] on the account that you want to edit.

1. Make any desired changes, then select [!UICONTROL **Save**].

## View account keys

After you create an account, you can view any associated account keys for that account. You might need to view this information if you didn't finish configuring the account with your cloud provider [when you originally configured the account](/help/components/exports/cloud-export-accounts.md). 

To view keys associated with an export account:

1. In Customer Journey Analytics, select [!UICONTROL **Components**] > [!UICONTROL **Exports**].

1. Select the [!UICONTROL **Location accounts**] tab.

   ![Exports window showing Location accounts tab](assets/account-add.png)

1. (Conditional) If you are a system administrator, you can enable the [!UICONTROL **View accounts for all users**] option to view locations created by all users in your organization.

1. Select the 3-dot icon on the account that you want to edit, then select [!UICONTROL **Account keys**]. 

## Delete accounts

1. In Customer Journey Analytics, select [!UICONTROL **Components**] > [!UICONTROL **Exports**].

1. Select the [!UICONTROL **Location accounts**] tab.

   ![Exports window showing Location accounts tab](assets/account-add.png)

1. (Conditional) If you are a system administrator, you can enable the [!UICONTROL **View accounts for all users**] option to view locations created by all users in your organization.

1. Select the 3-dot icon on the account that you want to edit, then select [!UICONTROL **Delete account**]. 

1. Select [!UICONTROL **Delete**] again on the confirmation dialog.

## Configure company-wide settings (administrators only)

{{release-limited-testing-section}}

System administrators can restrict users from creating accounts and locations, or they can limit the types of accounts users can create and use. 

![Admin settings tab](assets/locations-admin-settings.png)

### Configure whether users can create and edit accounts

By default, all users in the organization can create accounts and edit accounts they create in your Customer Journey Analytics environment, as described in [configure cloud export accounts](/help/components/exports/cloud-export-accounts.md).

You can restrict users from creating accounts. When you do, users can still use any accounts they have already created, but they can no longer edit them. You can delete accounts that users have created, as described in [Delete an account](#delete-an-account).

To restrict all users from creating and editing accounts:

1. In Customer Journey Analytics, select **[!UICONTROL Components]** > **[!UICONTROL Exports]**, then select the [!UICONTROL **Admin settings**] tab.

1. In the [!UICONTROL **Locations accounts**] section, deselect the option, [!UICONTROL **Allow users to create and manage location accounts**].

1. Select [!UICONTROL **Save**].

1. (Optional) Delete any accounts that users have created that you no longer want them to use, as described in [Delete an account](#delete-an-account).

### Configure whether users can create and edit locations

By default, all users in the organization can create locations and edit locations they create in your Customer Journey Analytics environment, as described in [configure cloud export locations](/help/components/exports/cloud-export-locations.md).

You can restrict users from creating locations. When you do, users can still use any locations they have already created, but they can no longer edit them. You can delete locations that users have created, as described in [Delete locations](#delete-a-location).

To restrict all users from creating and editing locations:

1. In Customer Journey Analytics, select **[!UICONTROL Components]** > **[!UICONTROL Eports]**, then select the [!UICONTROL **Admin settings**] tab.

1. In the [!UICONTROL **Locations**] section, deselect the option, [!UICONTROL **Allow users to create and manage locations**].

1. Select [!UICONTROL **Save**].

1. (Optional) Delete any locations that users have created that you no longer want them to use, as described in [Delete a location](#delete-a-location).

### Limit which accounts types users can create and use

You can limit the account types users see in the following circumstances:

* When [creating new accounts](/help/components/exports/cloud-export-accounts.md).
* When choosing which accounts to use when exporting files using [full table export](/help/analysis-workspace/export/export-cloud.md).  

When you limit account types as described in this section, any accounts of the type that you limit are no longer visible to users. This means that new accounts of that type cannot be created, and existing accounts of that type cannot be used when exporting files using full table export. 

However, existing accounts that are configured for scheduled exports must be deleted if you want to restrict them from being used.

#### Ensure that accounts are not used for scheduled exports

When you limit account types, existing accounts are hidden, not deleted. 

If schedules are already configured to send data to an account that is of the type that you limit, the schedules will continue to run even after you limit the account type, and data will continue to be sent to the account. For example, if a full table export is scheduled to send data to an account type that you limit, the schedule will continue to run.

If you need to ensure that accounts of a certain type are not used in scheduled exports, you can delete the accounts before you [limit the account types](#limit-the-account-types-that-are-available-to-users).

To delete accounts:

1. Locate the accounts of the account type you plan to limit, which are being used for scheduled exports. 

1. Delete the accounts, as described in [Delete an account](#delete-an-account).

1. Continue with the following section, [Limit the account types that are available to users](#limit-the-account-types-that-are-available-to-users).

#### Limit the account types that are available to users

To limit the account types that are available to users when creating and using accounts:

1. In Customer Journey Analytics, select **[!UICONTROL Components]** > **[!UICONTROL Exports]**, then select the [!UICONTROL **Admin settings**] tab.

1. Locate the [!UICONTROL **Permitted account types**] section.

   The following account types are available to users by default. Deselect any of these account types that you want to restrict users from using. 
  
   * [!UICONTROL **AEP Data Landing Zone**]
   
   * [!UICONTROL **Amazon S3 Role ARN**]

   * [!UICONTROL **Google Cloud Platform**]

   * [!UICONTROL **Azure SAS**]

   * [!UICONTROL **Azure RBAC**]

   * [!UICONTROL **Snowflake**]

1. Select [!UICONTROL **Save**].
