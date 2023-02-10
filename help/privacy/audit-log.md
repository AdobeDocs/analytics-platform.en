---
title: Audit logs
description: Learn how to view and manage CJA audit logs.
exl-id: 360609f2-b811-49ee-ad4a-a54ceb23bfa3
---
# Audit logs

To increase the transparency and visibility of activities performed in the system, Customer Journey Analytics (CJA) allows you to audit user activity for various services and capabilities in the form of "audit logs". These logs form an audit trail that can help with troubleshooting issues, and help your business effectively comply with corporate data stewardship policies and regulatory requirements, such as the Health Insurance Portability and Accountability Act (HIPAA).

In a basic sense, an audit log tells **who** performed **what** action, and **when**. Each action recorded in a log contains metadata that indicates the action type, date and time, the email ID of the user who performed the action, and additional attributes relevant to the action type.

This topic covers audit logs in CJA, including how to view and manage them in the UI.

## Access to audit logs

When the feature is enabled for your organization, audit logs are automatically collected as activity occurs. You do not need to manually enable log collection.

In order to view and export audit logs, you must have been granted the **[!UICONTROL Audit Logs Access]** access control permission in Adobe Console. To learn how to manage individual permissions for CJA features, please refer to the [access control documentation](../admin/cja-access-control.md).

## View the audit log in the UI

In CJA, navigate to **[!UICONTROL Tools]** > **[!UICONTROL Audit Logs]**.

The audit log for today and yesterday are shown by default.

![audit log](assets/audit_ui.png)

You can select which columns are visible by going to the column selector at the top right.

## View information about individual log entries

Double click the info (i) button next to a description.

![audit log](assets/info-button-audit.png)

The following items are shown:

| Item | Description |
| --- | --- |
| Action Name | Here is the list of possible actions: <ul><li>API_Request</li><li>Approve</li><li>Create</li><li>Edit</li><li>Export</li><li>Login_failed</li><li>Login_successful</li><li>Logout</li><li>Org_change</li><li>Refresh</li><li>Share</li><li>Transfer</li><li>Unapprove</li><li>Unshare</li></ul> |
| Description | A summary of the action, component type (with ID) and other values. |
| User Name | The user taking the action. |
| Component Type | Possible component types include: <ul><li>Annotation</li><li>Audience</li><li>Calculated Metric</li><li>Connection</li><li>Data_Group</li><li>Data_View (this component type includes dimensions and metrics)</li><li>Feature_Access</li><li>Filter</li><li>IMS_Org</li><li>Mobile</li><li>Project</li><li>Report</li><li>Scheduled_Project</li><li>User</li><li>User_Group</li></ul> |
| IMS Org ID | A unique ID that is given to your instance when you first log in to Adobe Experience Cloud. It should be in the format: xxx@AdobeOrg. |
| User ID | A unique ID identifying the user who took this action. |
| Date Created | When this action was taken. |
| Email | The email of the user taking the action. |
| Component ID | A unique ID that identifies the component that is being actioned upon. |
| Log ID | A unique ID identifying this log entry. |
| User Type | Possible types include: IMS, OKTA |

### Filter audit logs

Select the funnel icon (![filter](assets/filter-icon.png)) to display a list of filter controls to help narrow results. Only the last 1,000 records are displayed, irrespective of the various filters selected.

![filters](assets/filters.png)

The following filters are available for audit events in the UI:

| Filter | Description |
| --- | --- |
| [!UICONTROL Date Range] | Filter on a different date range by selecting a different date or selecting a date range by dragging the cursor across multiple dates. By default, today's and yesterday's date are selected. |
| [!UICONTROL Action] | Filter on one or more of the following actions: <ul><li>API_Request</li><li>Approve</li><li>Create</li><li>Edit</li><li>Export</li><li>Login_failed</li><li>Login_successful</li><li>Logout</li><li>Org_change</li><li>Refresh</li><li>Share</li><li>Transfer</li><li>Unapprove</li><li>Unshare</li></ul> |
| [!UICONTROL User ID] | Filter on a specific user by their user ID. The user ID can be found by selecting the info (i) button next to a user name.|
| [!UICONTROL Email] | Filter on a specific user's email address. The email can be found by selecting the info (i) button next to a user name.|
| [!UICONTROL Component ID] | Filter on a specific Component ID. The user ID can be found by selecting the info (i) button for a desired component. |
| [!UICONTROL Component Type] | Filter on one or more component type/s: <ul><li>Annotation</li><li>Audience</li><li>Calculated Metric</li><li>Connection</li><li>Data_Group</li><li>Data_View</li><li>Feature_Access</li><li>Filter</li><li>IMS_Org</li><li>Mobile</li><li>Project</li><li>Report</li><li>Scheduled_Project</li><li>User</li><li>User_Group</li></ul> |

{style="table-layout:auto"}

## Event types captured by audit logs

The following table outlines which actions on which component types are recorded by audit logs:

| Component Type | Actions |
| --- | --- |
| [!UICONTROL Annotation] |<ul><li>Create</li><li>Delete</li><li>Edit</li></ul>|
| [!UICONTROL Audience] | <ul><li>API_Request</li><li>Create</li><li>Delete</li><li>Edit</li><li>Export</li><li>Refresh</li></ul> |
| [!UICONTROL Calculated Metric] | <ul><li>API_Request</li><li>Create</li><li>Delete</li><li>Edit</li></ul> |
| [!UICONTROL Connection] | <ul><li>API_Request</li><li>Create</li><li>Delete</li><li>Edit</li></ul> |
| [!UICONTROL Data View] | <ul><li>API_Request</li><li>Create</li><li>Delete</li><li>Edit</li></ul> |
| [!UICONTROL Date Range] | <ul><li>API_Request</li><li>Create</li><li>Delete</li><li>Edit</li></ul>  |
| [!UICONTROL Filter] | <ul><li>API_Request</li><li>Create</li><li>Delete</li><li>Edit</li></ul>  |
| [!UICONTROL IMS Org] | <ul><li>API_Request</li><li>Create</li><li>Delete</li><li>Edit</li></ul> |
| [!UICONTROL Project] | <ul><li>API_Request</li><li>Create</li><li>Delete</li><li>Edit</li></ul> |
| [!UICONTROL Report] | <ul><li>API_Request</li></ul> |
| [!UICONTROL Scheduled Project] | <ul><li>API_Request</li><li>Create</li><li>Delete</li><li>Edit</li></ul> |
| [!UICONTROL User] | <ul><li>API_Request</li><li>Create</li><li>Delete</li><li>Edit</li></ul> |
| [!UICONTROL User Group] | <ul><li>API_Request</li><li>Create</li><li>Delete</li><li>Edit</li></ul> |

{style="table-layout:auto"}

## Download audit logs

You can download audit logs in CSV or JSON formats. Any filters applied or columns selected are reflected in the downloaded files.

1. Click **[!UICONTROL Download]** at the top right of the screen.
1. Specify the format. 
1. Click **[!UICONTROL Download]** again.

## Manage audit logs in the API

All actions that you can perform in the UI can also be done using API calls. See the [CJA API reference document](https://developer.adobe.com/cja-apis/docs/api/#tag/Audit-Logs) for more information.
