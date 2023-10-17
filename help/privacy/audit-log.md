---
title: Audit logs
description: Learn how to view and manage Customer Journey Analytics audit logs.
exl-id: 360609f2-b811-49ee-ad4a-a54ceb23bfa3
feature: Privacy
---
# Audit logs

To increase the transparency and visibility of activities performed in the system, Adobe Customer Journey Analytics allows you to audit user activity for various services and capabilities in the form of "audit logs". These logs form an audit trail that can help with troubleshooting issues, and help your business effectively comply with corporate data stewardship policies and regulatory requirements, such as the Health Insurance Portability and Accountability Act (HIPAA).

In a basic sense, an audit log tells **who** performed **what** action, and **when**. Each action recorded in a log contains metadata that indicates the action type, date and time, the email ID of the user who performed the action, and additional attributes relevant to the action type.

This topic covers audit logs in Customer Journey Analytics, including how to view and manage them in the UI.

## Access to audit logs

When the feature is enabled for your organization, audit logs are automatically collected as activity occurs. You do not need to manually enable log collection.

In order to view and export audit logs, you must have been granted the **[!UICONTROL Audit Logs Access]** access control permission in Adobe Console. To learn how to manage individual permissions for Customer Journey Analytics features, please refer to the [access control documentation](../admin/cja-access-control.md).

## View the audit log in the UI

In Customer Journey Analytics, navigate to **[!UICONTROL Tools]** > **[!UICONTROL Audit Logs]**.

The audit log for today and yesterday are shown by default.

![audit log](assets/audit_ui.png)

You can select which columns are visible by going to the column selector at the top right.

## View information about individual log entries

Double click the info (i) button next to a description.

![audit log](assets/info-button-audit.png)

The following items are shown:

* **[!UICONTROL Action Name]**: The action taken. Possible values include:
  * API_REQUEST
  * APPROVE
  * CREATE
  * DELETE
  * EDIT
  * EMBARGO
  * EXPORT
  * ORG_CHANGE
  * REFRESH
  * SHARE
  * TRANSFER
  * UNAPPROVE
  * UNSHARE
* **[!UICONTROL Date Created]**: The date and time that the action was taken.
* **[!UICONTROL Description]**: A summary of the action.
* **[!UICONTROL User Name]**: The user that took the action.
* **[!UICONTROL Email]**: The email address of the user that took the action.
* **[!UICONTROL Component Name]**: The component that the user took action on.
* **[!UICONTROL Component Type]**: The type of component. Possible values include:
  * ANNOTATION
  * AUDIENCE
  * CALCULATED_METRIC
  * CONNECTION
  * DATA_GROUP
  * DATA_VIEW
  * DATASET_STITCHING
  * DATE_RANGE
  * FEATURE_ACCESS
  * FILTER
  * IMS_ORG
  * MOBILE
  * PROJECT
  * REPORT
  * SCHEDULED_PROJECT
  * USER
  * USER_GROUP
* **[!UICONTROL Component ID]**: The ID of the component that the user took action on.
* **[!UICONTROL IMS Org ID]**: The organization's IMS ID, in the format of `ABC123@AdobeOrg`.
* **[!UICONTROL Log ID]**: A unique ID identifying this log entry.
* **[!UICONTROL User ID]**: The unique ID identifying the user that took the action.
* **[!UICONTROL User Type]**: The authentication type used. Valid values include:
  * IMS
  * OKTA

### Filter audit logs

Select the funnel icon (![filter](assets/filter-icon.png)) to display a list of filter controls to help narrow results. Only the last 1,000 records are displayed, irrespective of the various filters selected.

![filters](assets/filters.png)

The following filters are available for audit events in the UI:

| Filter | Description |
| --- | --- |
| [!UICONTROL Date Range] | Filter on a different date range by selecting a different date or selecting a date range by dragging the cursor across multiple dates. By default, today's and yesterday's date are selected. |
| [!UICONTROL Action] | Filter on any action name listed above. |
| [!UICONTROL User ID] | Filter on a specific user by their user ID. The user ID can be found by selecting the info (i) button next to a user name.|
| [!UICONTROL Email] | Filter on a specific user's email address. The email can be found by selecting the info (i) button next to a user name.|
| [!UICONTROL Component ID] | Filter on a specific Component ID. The user ID can be found by selecting the info (i) button for a desired component. |
| [!UICONTROL Component Type] | Filter on any component type listed above. |

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

All actions that you can perform in the UI can also be done using API calls. See the [Customer Journey Analytics API reference document](https://developer.adobe.com/cja-apis/docs/api/#tag/Audit-Logs) for more information.
